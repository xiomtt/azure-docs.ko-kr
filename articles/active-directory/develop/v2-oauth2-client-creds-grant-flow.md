---
title: Microsoft id 플랫폼의 OAuth 2.0 클라이언트 자격 증명 흐름 | Microsoft
description: OAuth 2.0 인증 프로토콜의 Microsoft id 플랫폼 구현을 사용 하 여 웹 응용 프로그램을 빌드합니다.
services: active-directory
author: hpsin
manager: CelesteDG
ms.service: active-directory
ms.subservice: develop
ms.workload: identity
ms.topic: conceptual
ms.date: 10/2/2020
ms.author: hirsin
ms.reviewer: hirsin
ms.custom: aaddev, identityplatformtop40
ms.openlocfilehash: 89a4c62044e3be849650de703d2daa9ca3e2a975
ms.sourcegitcommit: 50802bffd56155f3b01bfb4ed009b70045131750
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91932586"
---
# <a name="microsoft-identity-platform-and-the-oauth-20-client-credentials-flow"></a>Microsoft id 플랫폼 및 OAuth 2.0 클라이언트 자격 증명 흐름

애플리케이션의 ID를 사용하여 웹 호스팅 리소스에 액세스하기 위해 RFC 6749에 명시된 [OAuth 2.0 클라이언트 자격 증명 권한 부여](https://tools.ietf.org/html/rfc6749#section-4.4)(때로는 *2단계 OAuth*라고도 함)를 사용할 수 있습니다. 이 유형의 부여는 일반적으로 사용자와의 즉각적인 상호 작용 없이 백그라운드에서 실행되어야 하는 서버 간 상호 작용에 사용됩니다. 이러한 유형의 응용 프로그램은 종종 *디먼* 또는 *서비스 계정*이라고 합니다.

이 문서에서는 애플리케이션에서 프로토콜에 대해 직접 프로그래밍을 수행하는 방법을 설명합니다. 가능하다면 [토큰을 획득하고 보안 웹 API를 호출](authentication-flows-app-scenarios.md#scenarios-and-supported-authentication-flows)하는 대신, 지원되는 MSAL(Microsoft 인증 라이브러리)을 사용하는 것이 좋습니다.  [MSAL을 사용하는 샘플 앱](sample-v2-code.md)도 살펴봅니다.

OAuth 2.0 클라이언트 자격 증명 부여 흐름을 사용하면 웹 서비스(비밀 클라이언트)에서 다른 웹 서비스를 호출할 때 사용자를 가장하는 대신 고유한 자격 증명을 사용하여 인증할 수 있습니다. 이 시나리오에서 클라이언트는 일반적으로 중간 계층 웹 서비스, 디먼 서비스 또는 웹 사이트입니다. 더 높은 수준의 보증을 위해 Microsoft ID 플랫폼은 호출 서비스가 자격 증명으로 인증서(공유 비밀 대신)를 사용할 수 있도록 합니다.

클라이언트 자격 증명 흐름에서 관리자는 응용 프로그램 자체에 사용 권한을 직접 부여 합니다. 앱이 리소스에 대 한 토큰을 제공 하는 경우 리소스는 인증에 관련 된 사용자가 없기 때문에 앱 자체에 작업을 수행할 수 있는 권한을 부여 합니다.  이 문서에서는 [api를 호출 하는 응용 프로그램에 권한을 부여](#application-permissions)하는 데 필요한 단계와 [api를 호출 하는 데 필요한 토큰을 가져오는 방법](#get-a-token)에 대해 설명 합니다.

## <a name="protocol-diagram"></a>프로토콜 다이어그램

전체 클라이언트 자격 증명 흐름은 다음 다이어그램과 유사합니다. 이 문서의 뒷부분에서 각 단계에 대해 설명합니다.

![클라이언트 자격 증명 흐름을 보여 주는 다이어그램](./media/v2-oauth2-client-creds-grant-flow/convergence-scenarios-client-creds.svg)

## <a name="get-direct-authorization"></a>직접 권한 부여 가져오기

앱은 일반적으로 두 가지 방법 중 하나로 리소스에 액세스할 수 있는 직접 권한을 부여받습니다.

* [리소스에서 ACL(액세스 제어 목록)을 통해](#access-control-lists)
* [Azure AD에서 애플리케이션 사용 권한 할당을 통해](#application-permissions)

이러한 두 메서드는 Azure AD에서 가장 일반적이며 클라이언트 자격 증명 흐름을 수행하는 클라이언트 및 리소스에 사용하는 것이 좋습니다. 또한 리소스가 다른 방식으로 해당 클라이언트를 인증하도록 선택할 수 있습니다. 각 리소스 서버가 해당 애플리케이션에 가장 적합한 방법을 선택할 수 있습니다.

### <a name="access-control-lists"></a>액세스 제어 목록

리소스 공급자는 특정 수준의 액세스를 알고 권한을 부여하는 애플리케이션(클라이언트) ID 목록에 따라 권한 부여 확인을 적용할 수 있습니다. 리소스가 Microsoft id 플랫폼 끝점에서 토큰을 받으면 토큰을 디코딩하고 및 클레임에서 클라이언트의 응용 프로그램 ID를 추출할 수 있습니다 `appid` `iss` . 그런 다음, 유지 관리하는 ACL(액세스 제어 목록)에 대해 애플리케이션을 비교합니다. ACL의 세분성 및 메서드는 리소스 간에 크게 달라질 수 있습니다.

일반적인 사용 사례는 ACL을 사용하여 웹 애플리케이션 또는 웹 API에 대한 테스트를 실행하는 것입니다. 웹 API는 특정 클라이언트에 대한 모든 권한의 하위 집합만 부여할 수 있습니다. API에서 종단 간 테스트를 실행 하려면 Microsoft id 플랫폼 끝점에서 토큰을 가져온 다음 API로 보내는 테스트 클라이언트를 만듭니다. 그러면 API는 API의 전체 기능에 대한 모든 권한에 대해 ACL에서 테스트 클라이언트의 애플리케이션 ID를 확인합니다. 이 종류의 ACL을 사용하는 경우 호출자의 `appid` 값 뿐만 아니라 `iss` 토큰의 값을 신뢰할 수 있는지도 유효성을 검사해야 합니다.

이 종류의 권한 부여는 개인 Microsoft 계정을 가진 소비자 사용자가 소유한 데이터에 액세스해야 하는 디먼 및 서비스 계정에 일반적입니다. 조직에서 소유한 데이터의 경우 애플리케이션 사용 권한을 통해 필요한 권한 부여를 획득하는 것이 좋습니다.

#### <a name="controlling-tokens-without-the-roles-claim"></a>클레임 없이 토큰 제어 `roles`

이 ACL 기반 권한 부여 패턴을 사용 하도록 설정 하기 위해 Azure AD에서는 응용 프로그램에 다른 응용 프로그램에 대 한 토큰을 가져올 수 있는 권한이 필요 하지 않습니다. 따라서 클레임 없이 앱 전용 토큰을 발급할 수 있습니다 `roles` . Api를 노출 하는 응용 프로그램은 토큰을 허용 하기 위해 권한 확인을 구현 해야 합니다.

응용 프로그램에서 응용 프로그램에 대 한 역할 없는 앱 전용 액세스 토큰을 가져오지 못하게 하려면 [앱에 대 한 사용자 할당 요구 사항을 사용 하도록 설정](../manage-apps/assign-user-or-group-access-portal.md#configure-an-application-to-require-user-assignment)해야 합니다. 이렇게 하면 할당 된 역할이 없는 사용자와 응용 프로그램이이 응용 프로그램에 대 한 토큰을 가져올 수 없게 됩니다. 

### <a name="application-permissions"></a>애플리케이션 사용 권한

Acl을 사용 하는 대신 Api를 사용 하 여 **응용 프로그램 사용 권한**집합을 노출할 수 있습니다. 애플리케이션 사용 권한은 조직의 관리자가 애플리케이션에 부여하며 해당 조직 및 그 직원이 소유한 데이터 액세스에만 사용할 수 있습니다. 예를 들어 Microsoft Graph는 다음을 수행할 수 있는 몇 가지 애플리케이션 사용 권한을 노출합니다.

* 모든 사서함에서 메일 읽기
* 모든 사서함에서 메일 읽기 및 쓰기
* 모든 사용자로 메일 보내기
* 디렉터리 데이터 읽기

사용자 고유의 API를 사용 하 여 응용 프로그램 사용 권한을 사용 하려면 (Microsoft Graph와 반대) 먼저 Azure Portal의 API 앱 등록에서 범위를 정의 하 여 [api를 노출](quickstart-configure-app-expose-web-apis.md) 해야 합니다. 그런 다음 클라이언트 응용 프로그램의 앱 등록에서 해당 권한을 선택 하 여 [API에](quickstart-configure-app-access-web-apis.md) 대 한 액세스를 구성 합니다. API의 앱 등록에서 범위를 노출 하지 않은 경우 Azure Portal의 클라이언트 응용 프로그램의 앱 등록에서 해당 API에 대 한 응용 프로그램 권한을 지정할 수 없습니다.

사용자가 아닌 응용 프로그램으로 인증 하는 경우 *위임 된 권한* -사용자가 부여 하는 범위를 사용할 수 없습니다. 응용 프로그램에 대 한 관리자가 부여 하거나 웹 API의 사전 인증을 통해 부여 되는 응용 프로그램 사용 권한 (역할이 라고도 함)을 사용 해야 합니다.

응용 프로그램 사용 권한에 대 한 자세한 내용은 [사용 권한 및 동의](v2-permissions-and-consent.md#permission-types)를 참조 하세요.

#### <a name="recommended-sign-the-user-into-your-app"></a>권장: 사용자를 앱에 로그인 합니다.

일반적으로 애플리케이션 사용 권한을 사용하는 애플리케이션을 빌드할 때 앱에는 관리자가 앱의 사용 권한을 승인할 수 있는 페이지 또는 보기가 필요합니다. 이 페이지는 앱 로그인 흐름의 일부, 앱 설정의 일부 또는 전용 "연결" 흐름일 수 있습니다. 대부분의 경우에 사용자가 회사 또는 학교 Microsoft 계정으로 로그인한 후에 앱은 이 "연결" 보기만을 표시하게 됩니다.

사용자를 앱에 로그인 하는 경우 사용자에 게 응용 프로그램 사용 권한을 승인 하도록 요청 하기 전에 사용자가 속해 있는 조직을 식별할 수 있습니다. 반드시 필요하지는 않지만 사용자를 위한 보다 직관적인 환경을 만드는 것이 유용할 수 있습니다. 에서 사용자를 서명 하려면 [Microsoft id 플랫폼 프로토콜 자습서](active-directory-v2-protocols.md)를 따르세요.

#### <a name="request-the-permissions-from-a-directory-admin"></a>디렉터리 관리에서 사용 권한 요청

조직의 관리자에 게 권한을 요청할 준비가 되 면 Microsoft identity platform *admin 동의 끝점*으로 사용자를 리디렉션할 수 있습니다.

> [!TIP]
> Postman에서 이 요청을 실행해 보세요. 최상의 결과를 위해 고유한 앱 ID를 사용 합니다. 자습서 응용 프로그램은 유용한 권한을 요청 하지 않습니다. [ ![ Postman에서이 요청을 실행 해 보세요](./media/v2-oauth2-auth-code-flow/runInPostman.png)](https://app.getpostman.com/run-collection/f77994d794bab767596d) .

```HTTP
// Line breaks are for legibility only.

GET https://login.microsoftonline.com/{tenant}/adminconsent?
client_id=6731de76-14a6-49ae-97bc-6eba6914391e
&state=12345
&redirect_uri=http://localhost/myapp/permissions
```

Pro 팁: 브라우저에서 다음 요청 붙여넣기를 시도 합니다.

```
https://login.microsoftonline.com/common/adminconsent?client_id=6731de76-14a6-49ae-97bc-6eba6914391e&state=12345&redirect_uri=http://localhost/myapp/permissions
```

| 매개 변수 | 조건 | 설명 |
| --- | --- | --- |
| `tenant` | 필수 | 사용 권한을 요청하려는 디렉터리 테넌트입니다. 이는 GUID 또는 친숙한 이름 형식일 수 있습니다. 사용자가 속한 테넌트가 무엇인지 모르고 테넌트를 사용하여 로그인하지 않으려는 경우 `common`을 사용합니다. |
| `client_id` | 필수 | [Azure Portal - 앱 등록](https://go.microsoft.com/fwlink/?linkid=2083908) 환경이 앱에 할당한 **애플리케이션(클라이언트) ID**입니다. |
| `redirect_uri` | 필수 | 리디렉션 URI는 처리할 앱에 응답을 전송하려는 위치입니다. URL로 인코딩되어야 한다는 점을 제외하고 포털에서 등록한 리디렉션 URI 중 하나와 정확히 일치해야 하며 추가 경로 세그먼트가 있을 수 있습니다. |
| `state` | 권장 | 토큰 응답에도 반환되는 요청에 포함된 값입니다. 원하는 모든 콘텐츠의 문자열일 수 있습니다. 상태는 인증 요청이 발생하기 전에 앱에서 사용자 상태에 대한 정보(예: 사용한 페이지 또는 보기)를 인코딩하는 데 사용됩니다. |

이 시점에서 Azure AD는 테 넌 트 관리자만이 요청을 완료 하 여 로그인 할 수 있도록 합니다. 관리자에게는 앱 등록 포털에서 앱에 요청한 애플리케이션 직접 사용 권한을 모두 승인하라는 메시지가 표시됩니다.

##### <a name="successful-response"></a>성공적인 응답

관리자가 애플리케이션에 대한 사용 권한을 승인하는 경우 성공적인 응답은 다음과 같습니다.

```HTTP
GET http://localhost/myapp/permissions?tenant=a8990e1f-ff32-408a-9f8e-78d3b9139b95&state=state=12345&admin_consent=True
```

| 매개 변수 | 설명 |
| --- | --- |
| `tenant` | 디렉터리 테넌트는 GUID 형식으로 요청한 권한을 애플리케이션에 부여합니다. |
| `state` | 토큰 응답에도 반환되는 요청에 포함된 값입니다. 원하는 모든 콘텐츠의 문자열일 수 있습니다. 상태는 인증 요청이 발생하기 전에 앱에서 사용자 상태에 대한 정보(예: 사용한 페이지 또는 보기)를 인코딩하는 데 사용됩니다. |
| `admin_consent` | 을 **True**로 설정 합니다. |

##### <a name="error-response"></a>오류 응답

관리자가 애플리케이션에 대한 사용 권한을 승인하지 않는 경우 실패한 응답은 다음과 같습니다.

```HTTP
GET http://localhost/myapp/permissions?error=permission_denied&error_description=The+admin+canceled+the+request
```

| 매개 변수 | 설명 |
| --- | --- |
| `error` | 오류 유형을 분류하는 데 사용할 수 있고 오류에 대응하는 데 사용할 수 있는 오류 코드 문자열입니다. |
| `error_description` | 오류의 근본 원인을 식별하도록 도울 수 있는 특정 오류 메시지입니다. |

앱 프로비전 엔드포인트에서 성공적인 응답을 받았다면 앱은 요청한 애플리케이션 직접 사용 권한을 얻게 됩니다. 이제 원하는 리소스에 대한 토큰을 요청할 수 있습니다.

## <a name="get-a-token"></a>토큰 가져오기

애플리케이션에 필요한 권한을 부여받은 후에는 API에 대한 액세스 토큰을 획득하는 과정을 진행합니다. 클라이언트 자격 증명 부여를 사용 하 여 토큰을 가져오려면 POST 요청을 `/token` Microsoft id 플랫폼 끝점으로 보냅니다.

> [!TIP]
> Postman에서 이 요청을 실행해 보세요. 최상의 결과를 위해 고유한 앱 ID를 사용 합니다. 자습서 응용 프로그램은 유용한 권한을 요청 하지 않습니다. [ ![ Postman에서이 요청을 실행 해 보세요](./media/v2-oauth2-auth-code-flow/runInPostman.png)](https://app.getpostman.com/run-collection/f77994d794bab767596d) .

### <a name="first-case-access-token-request-with-a-shared-secret"></a>첫 번째 사례: 공유 비밀을 사용하여 액세스 토큰 요청

```HTTP
POST /{tenant}/oauth2/v2.0/token HTTP/1.1           //Line breaks for clarity
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

client_id=535fb089-9ff3-47b6-9bfb-4f1264799865
&scope=https%3A%2F%2Fgraph.microsoft.com%2F.default
&client_secret=qWgdYAmab0YSkuL1qKv5bPX
&grant_type=client_credentials
```

```Bash
# Replace {tenant} with your tenant!
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'client_id=535fb089-9ff3-47b6-9bfb-4f1264799865&scope=https%3A%2F%2Fgraph.microsoft.com%2F.default&client_secret=qWgdYAmab0YSkuL1qKv5bPX&grant_type=client_credentials' 'https://login.microsoftonline.com/{tenant}/oauth2/v2.0/token'
```

| 매개 변수 | 조건 | 설명 |
| --- | --- | --- |
| `tenant` | 필수 | 애플리케이션에서 GUID 또는 도메인 이름 형식으로 작동하도록 계획하는 디렉터리 테넌트입니다. |
| `client_id` | 필수 | 앱에 할당되는 애플리케이션 ID입니다. 앱을 등록한 포털에서 이 정보를 찾을 수 있습니다. |
| `scope` | 필수 | 이 요청에서 `scope` 매개 변수에 전달된 값은 원하는 리소스의 리소스 식별자(애플리케이션 ID URI)여야 하고, `.default` 접미사가 붙어 있어야 합니다. Microsoft Graph 예제의 경우 값은 `https://graph.microsoft.com/.default`입니다. <br/>이 값은 앱에 대해 구성한 모든 직접 응용 프로그램 사용 권한의 Microsoft id 플랫폼 끝점을 알려 주며, 끝점은 사용 하려는 리소스와 연결 된 사용 권한의 토큰을 발급 해야 합니다. `/.default` 범위에 대해 자세히 알아보려면 [동의 설명서](v2-permissions-and-consent.md#the-default-scope)를 참조하세요. |
| `client_secret` | 필수 | 앱 등록 포털에서 앱에 대해 생성한 클라이언트 암호입니다. 클라이언트 암호는 보내기 전에 URL로 인코딩해야 합니다. |
| `grant_type` | 필수 | `client_credentials`로 설정해야 합니다. |

### <a name="second-case-access-token-request-with-a-certificate"></a>두 번째 사례: 인증서를 사용하여 액세스 토큰 요청

```HTTP
POST /{tenant}/oauth2/v2.0/token HTTP/1.1               // Line breaks for clarity
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

scope=https%3A%2F%2Fgraph.microsoft.com%2F.default
&client_id=97e0a5b7-d745-40b6-94fe-5f77d35c6e05
&client_assertion_type=urn%3Aietf%3Aparams%3Aoauth%3Aclient-assertion-type%3Ajwt-bearer
&client_assertion=eyJhbGciOiJSUzI1NiIsIng1dCI6Imd4OHRHeXN5amNScUtqRlBuZDdSRnd2d1pJMCJ9.eyJ{a lot of characters here}M8U3bSUKKJDEg
&grant_type=client_credentials
```

| 매개 변수 | 조건 | 설명 |
| --- | --- | --- |
| `tenant` | 필수 | 애플리케이션에서 GUID 또는 도메인 이름 형식으로 작동하도록 계획하는 디렉터리 테넌트입니다. |
| `client_id` | 필수 |앱에 할당되는 애플리케이션(클라이언트) ID입니다. |
| `scope` | 필수 | 이 요청에서 `scope` 매개 변수에 전달된 값은 원하는 리소스의 리소스 식별자(애플리케이션 ID URI)여야 하고, `.default` 접미사가 붙어 있어야 합니다. Microsoft Graph 예제의 경우 값은 `https://graph.microsoft.com/.default`입니다. <br/>이 값은 Microsoft id 플랫폼 끝점에 앱에 대해 구성한 모든 직접 응용 프로그램 권한의 토큰을 알려 주며, 사용 하려는 리소스와 연결 된 사용 권한의 토큰을 발급 해야 합니다. `/.default` 범위에 대해 자세히 알아보려면 [동의 설명서](v2-permissions-and-consent.md#the-default-scope)를 참조하세요. |
| `client_assertion_type` | 필수 | 값은 `urn:ietf:params:oauth:client-assertion-type:jwt-bearer`로 설정해야 합니다. |
| `client_assertion` | 필수 | 애플리케이션의 자격 증명으로 등록한 인증서를 사용하여 만들고 서명해야 하는 어설션(JSON Web Token)입니다. 인증서 등록 방법 및 어설션 형식에 대한 자세한 내용은 [인증서 자격 증명](active-directory-certificate-credentials.md)을 참조하세요.|
| `grant_type` | 필수 | `client_credentials`로 설정해야 합니다. |

client_secret 매개 변수가 두 개의 매개 변수 client_assertion_type 및 client_assertion으로 바뀐다는 것을 제외하고 공유 비밀에 따른 요청 사례와 매개 변수는 거의 동일합니다.

### <a name="successful-response"></a>성공적인 응답

성공적인 응답은 다음과 같습니다.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ik1uQ19WWmNBVGZNNXBP..."
}
```

| 매개 변수 | Description |
| --- | --- |
| `access_token` | 요청된 액세스 토큰입니다. 앱은이 토큰을 사용 하 여 web API와 같은 보안 리소스를 인증할 수 있습니다. |
| `token_type` | 토큰 유형 값을 나타냅니다. Microsoft ID 플랫폼에서 지원하는 유일한 형식은 `bearer`입니다. |
| `expires_in` | 액세스 토큰이 유효한 시간(초)입니다. |

### <a name="error-response"></a>오류 응답

오류 응답은 다음과 같습니다.

```json
{
  "error": "invalid_scope",
  "error_description": "AADSTS70011: The provided value for the input parameter 'scope' is not valid. The scope https://foo.microsoft.com/.default is not valid.\r\nTrace ID: 255d1aef-8c98-452f-ac51-23d051240864\r\nCorrelation ID: fb3d2015-bc17-4bb9-bb85-30c5cf1aaaa7\r\nTimestamp: 2016-01-09 02:02:12Z",
  "error_codes": [
    70011
  ],
  "timestamp": "2016-01-09 02:02:12Z",
  "trace_id": "255d1aef-8c98-452f-ac51-23d051240864",
  "correlation_id": "fb3d2015-bc17-4bb9-bb85-30c5cf1aaaa7"
}
```

| 매개 변수 | Description |
| --- | --- |
| `error` | 발생한 오류 유형을 분류하고 오류에 대응하는 데 사용할 수 있는 오류 코드 문자열입니다. |
| `error_description` | 인증 오류의 근본 원인을 식별하도록 도울 수 있는 특정 오류 메시지입니다. |
| `error_codes` | 진단에 도움이 될 수 있는 STS 특정 오류 코드의 목록입니다. |
| `timestamp` | 오류가 발생한 시간입니다. |
| `trace_id` | 진단에 도움이 되는 요청에 대한 고유 식별자입니다. |
| `correlation_id` | 전체 구성 요소에서 진단에 도움이 되는 요청에 대한 고유 식별자입니다. |

## <a name="use-a-token"></a>토큰 사용

이제 토큰을 획득했으므로 토큰을 사용하여 리소스에 대한 요청을 수행합니다. 토큰이 만료되면 `/token` 엔드포인트에 대한 요청을 반복하여 새 액세스 토큰을 획득합니다.

```HTTP
GET /v1.0/me/messages
Host: https://graph.microsoft.com
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ik5HVEZ2ZEstZnl0aEV1Q...
```

```bash
# Pro tip: Try the following command! (Replace the token with your own.)

curl -X GET -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG...." 'https://graph.microsoft.com/v1.0/me/messages'
```

## <a name="code-samples-and-other-documentation"></a>코드 샘플 및 기타 설명서

Microsoft 인증 라이브러리에서 [클라이언트 자격 증명 개요 설명서](https://aka.ms/msal-net-client-credentials)를 읽어보세요.

| 예제 | 플랫폼 |설명 |
|--------|----------|------------|
|[active-directory-dotnetcore-daemon-v2](https://github.com/Azure-Samples/active-directory-dotnetcore-daemon-v2) | .NET Core 2.1 콘솔 | 사용자를 대신하지 않고 애플리케이션의 ID를 사용하여 Microsoft Graph를 쿼리하는 테넌트의 사용자를 표시하는 간단한 .NET Core 애플리케이션입니다. 샘플에는 인증에 인증서를 사용하는 다양한 사례도 설명되어 있습니다. |
|[active-directory-dotnet-daemon-v2](https://github.com/Azure-Samples/active-directory-dotnet-daemon-v2)|ASP.NET MVC | 사용자를 대신하지 않고 애플리케이션의 ID를 사용하여 Microsoft Graph에서 데이터를 동기화하는 웹 애플리케이션입니다. |
