---
title: Azure Active Directory의 새로운 기능 보관 | Microsoft Docs
description: 이 콘텐츠 세트의 개요 섹션에 있는 새로운 기능 릴리스 정보에는 6개월간의 작업이 포함됩니다. 6개월 후에는 항목이 기본 문서에서 제거되고 이 보관 문서에 포함됩니다.
services: active-directory
author: ajburnle
manager: daveba
ms.service: active-directory
ms.subservice: fundamentals
ms.workload: identity
ms.topic: conceptual
ms.date: 11/30/2020
ms.author: ajburnle
ms.reviewer: dhanyahk
ms.custom: it-pro, seo-update-azuread-jan, has-adal-ref
ms.collection: M365-identity-device-management
ms.openlocfilehash: e949501172dc0a156f5ecf450052f43f33a84daf
ms.sourcegitcommit: dea56e0dd919ad4250dde03c11d5406530c21c28
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96938157"
---
# <a name="archive-for-whats-new-in-azure-active-directory"></a>Azure Active Directory의 새로운 기능 보관

주요 [Azure Active Directory의 새로운 기능 릴리스 정보](whats-new.md) 문서에는 지난 6개월의 업데이트가 포함되어 있으며, 이 문서에는 모든 이전 정보가 포함되어 있습니다.

Azure Active Directory의 새로운 기능 릴리스 정보에서는 다음과 같은 정보를 제공합니다.

- 최신 릴리스
- 알려진 문제
- 버그 수정
- 사용되지 않는 기능
- 변경 계획

---
## <a name="may-2020"></a>2020년 5월

### <a name="retirement-of-properties-in-signins-riskyusers-and-riskdetections-apis"></a>SignIns, riskyUsers 및 riskDetections Api에서 속성 사용 중지

**유형:** 변경 계획  
**서비스 범주:** Id 보호  
**제품 기능:** Id 보안 & 보호

현재 열거 형식은 riskDetections API와 riskyUserHistoryItem (미리 보기)에서 riskType 속성을 나타내는 데 사용 됩니다. 또한 signIns API의 riskEventTypes 속성에도 열거 형식이 사용 됩니다. 앞으로 이러한 속성을 문자열로 나타냅니다. 

고객은 beta riskDetections 및 riskyUserHistoryItem API에서 riskEventType 속성으로 전환 하 고, 베타 signIns API에서 2020 9 월 9 일까지 속성을 riskEventTypes_v2 해야 합니다. 이 날짜에 현재 riskType 및 riskEventTypes 속성을 사용 하지 않을 것입니다. 자세한 내용은 [Microsoft Graph에서 위험 이벤트 속성 및 Id 보호 api](https://developer.microsoft.com/graph/blogs/changes-to-risk-event-properties-and-identity-protection-apis-on-microsoft-graph/)에 대 한 변경 내용을 참조 하세요.

--- 

### <a name="deprecation-of-riskeventtypes-property-in-signins-v10-api-on-microsoft-graph"></a>Microsoft Graph의 signIns v1.0 API에서 riskEventTypes 속성의 사용 중단

**유형:** 변경 계획  
**서비스 범주:** 보고  
**제품 기능:** Id 보안 & 보호

2020 9 월 Microsoft Graph에서 위험 이벤트 속성을 나타내는 경우 열거 된 형식이 문자열 형식으로 전환 됩니다. 미리 보기 Api에 영향을 주는 것 외에도이 변경 내용은 프로덕션 내 서명 API에도 영향을 줍니다.

새 riskEventsTypes_v2 (문자열) 속성이 signIns v1.0 API에 도입 되었습니다. Microsoft Graph 사용 중단 정책에 따라 2022 년 6 월 11 일에 현재 riskEventTypes (enum) 속성을 사용 중지 합니다. 고객은 2022 년 6 월 11 일에 해당 하는 v 1.0 signIns API의 riskEventTypes_v2 속성으로 전환 해야 합니다. 자세한 내용은 [Microsoft Graph에서 signIns의 riskEventTypes 속성의](https://developer.microsoft.com/graph/blogs/deprecation-of-riskeventtypes-property-in-signins-v1-0-api-on-microsoft-graph//)사용 중단을 참조 하세요.

--- 

### <a name="upcoming-changes-to-mfa-email-notifications"></a>MFA 전자 메일 알림의 예정 된 변경 내용

**유형:** 변경 계획  
**서비스 범주:** MFA  
**제품 기능:** Id 보안 & 보호
 

Cloud MFA에 대 한 전자 메일 알림을 다음과 같이 변경 합니다.

전자 메일 알림은 및 주소에서 전송 됩니다. azure-noreply@microsoft.com msonlineservicesteam@microsoftonline.com 사기 행위 경고 전자 메일의 콘텐츠를 업데이트 하 여 사용 차단을 해제 하는 데 필요한 단계를 더 잘 나타낼 수 있습니다.

---

### <a name="new-self-service-sign-up-for-users-in-federated-domains-who-cant-access-microsoft-teams-because-they-arent-synced-to-azure-active-directory"></a>Microsoft 팀에 액세스할 수 없는 페더레이션 도메인의 사용자에 대 한 새 셀프 서비스 등록은 Azure Active Directory에 동기화 되지 않기 때문입니다.

**유형:** 변경 계획  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증
 

현재 Azure AD에 페더레이션된 도메인에 있지만 테 넌 트에 동기화 되지 않은 사용자는 팀에 액세스할 수 없습니다. 6 월 말부터이 새로운 기능을 사용 하면 기존 전자 메일 확인 등록 기능을 확장 하 여이 작업을 수행할 수 있습니다. 그러면 페더레이션 IdP에 로그인 할 수 있지만 Azure ID에 사용자 개체가 아직 없는 사용자 개체를 자동으로 만들고 팀에 대해 인증할 수 있는 사용자를 사용할 수 있습니다. 해당 사용자 개체는 "셀프 서비스 등록"으로 표시 됩니다. 이는 관리 되는 도메인의 사용자가 수행할 수 있고 동일한 플래그를 사용 하 여 제어할 수 있는 전자 메일을 확인 하는 기존 기능을 확장 한 것입니다. 이 변경 내용은 다음 두 달 동안 롤아웃 완료 됩니다. [여기](../enterprise-users/directory-self-service-signup.md)에서 설명서 업데이트를 시청 하세요.
 
---

### <a name="upcoming-fix-the-oidc-discovery-document-for-the-azure-government-cloud-is-being-updated-to-reference-the-correct-graph-endpoints"></a>예정 된 해결 방법: Azure Government 클라우드에 대 한 OIDC 검색 문서가 올바른 그래프 끝점을 참조 하도록 업데이트 되 고 있습니다.

**유형:** 변경 계획  
**서비스 범주:** 소버린 클라우드  
**제품 기능:** 사용자 인증
 
6 월부터 OIDC 검색 문서 [Microsoft identity platform And Openid connect Connect protocol](../develop/v2-protocols-oidc.md) for the login.microsoftonline.us ( [클라우드](../develop/authentication-national-cloud.md) 끝점) Azure Government에서 제공 된 테 넌 트에 따라 올바른 [국가 클라우드 그래프](/graph/deployments) 끝점 (또는)을 반환 하기 시작 합니다 https://graph.microsoft.us https://dod-graph.microsoft.us) .  현재는 잘못 된 그래프 끝점 (graph.microsoft.com) "msgraph_host" 필드를 제공 합니다.  

이 버그 수정은 약 2 개월 동안 점진적으로 출시 될 예정입니다.  

---

### <a name="azure-government-users-will-no-longer-be-able-to-sign-in-on-loginmicrosoftonlinecom"></a>Azure Government 사용자가 login.microsoftonline.com에서 더 이상 로그인 할 수 없습니다.

**유형:** 변경 계획  
**서비스 범주:** 소버린 클라우드  
**제품 기능:** 사용자 인증
 
2018 년 6 월 1 일에 Azure Government에 대 한 공식 Azure Active Directory (Azure AD) 기관이에서로 변경 되었습니다 https://login-us.microsoftonline.com https://login.microsoftonline.us . Azure Government 테 넌 트 내에서 응용 프로그램을 소유 하 고 있는 경우 us 끝점에서 사용자에 게 로그인 하도록 응용 프로그램을 업데이트 해야 합니다.

5 월 5 일부터 Azure AD는 사용자가 공용 끝점 (microsoftonline.com)을 사용 하 여 Azure Government 테 넌 트에서 호스트 되는 앱에 로그인 하지 못하도록 Azure Government 차단 하는 끝점 변경을 적용 하기 시작 합니다. 영향을 받는 앱이 AADSTS900439 오류를 표시 하기 시작 합니다. 

모든 앱에서 6 월 2020에 완료 될 것으로 예상 되는 적용으로 이러한 변경의 점진적 출시가 발생 합니다. 자세한 내용은 [Azure Government 블로그 게시물](https://devblogs.microsoft.com/azuregov/azure-government-aad-authority-endpoint-update/)을 참조 하세요.

---

### <a name="saml-single-logout-request-now-sends-nameid-in-the-correct-format"></a>이제 SAML 단일 로그 아웃 요청이 올바른 형식으로 NameID를 전송 합니다.

**유형:** 고정  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증
 
사용자가 로그 아웃 (예: MyApps 포털)을 클릭 하면 Azure AD는 사용자 세션에서 활성 상태이 고 로그 아웃 URL이 구성 된 각 앱에 SAML 단일 로그 아웃 메시지를 보냅니다. 이러한 메시지는 영구 형식의 NameID를 포함 합니다.

원본 SAML 로그인 토큰이 NameID에 대해 다른 형식 (예: 메일/m s)을 사용 하는 경우 SAML 앱은 로그 아웃 메시지의 NameID와 기존 세션의 상관 관계를 지정할 수 없습니다 .이로 인해 SAML 앱 및 사용자가 로그인 상태를 유지 하기 위해 로그 아웃 메시지를 삭제 하 게 됩니다. 이 수정은 응용 프로그램에 대해 구성 된 NameID와의 로그 아웃 메시지 일치를 수행 합니다.

---

### <a name="hybrid-identity-administrator-role-is-now-available-with-cloud-provisioning"></a>이제 클라우드 프로 비전에서 하이브리드 Id 관리자 역할을 사용할 수 있습니다.

**유형:** 새로운 기능  
**서비스 범주:** Azure AD 클라우드 프로 비전  
**제품 기능:** Id 수명 주기 관리
 
IT 관리자는 Azure ADConnect 클라우드 프로 비전을 설정 하는 데 필요한 최소 권한 역할로 새로운 "하이브리드 관리자" 역할을 사용 하 여 시작할 수 있습니다. 이 새로운 역할을 사용 하는 경우 더 이상 전역 관리자 역할을 사용 하 여 클라우드 프로 비전을 설정 하 고 구성할 필요가 없습니다. [자세히 알아봅니다](../roles/delegate-by-task.md#connect).
 
---

### <a name="new-federated-apps-available-in-azure-ad-application-gallery---may-2020"></a>Azure AD 응용 프로그램 갤러리에서 사용할 수 있는 새로운 페더레이션된 앱-2020 년 5 월

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
2020 년 5 월에 앱 갤러리에 페더레이션 지원이 포함 된 다음 36 새 응용 프로그램이 추가 되었습니다.

[Moula](https://moula.com.au/pay/merchants), [Surveypal](https://www.surveypal.com/app), [Kbot365](https://www.konverso.ai/virtual-assistant-digital-workplace/), [TackleBox](http://www.tacklebox.app/), [Powell 팀](https://powell-software.com/en/powell-teams-en/), [Talentsoft Assistant](https://msteams.talent-soft.com/), [ASC 기록 정보](https://teams.asc-recording.app/product), [GO1](https://www.go1.com/), [B 개입](https://b-engaged.se/), [Competella Contact Center WORKGROUP](http://www.competella.com/), [asite](http://www.asite.com/), ImageSoft [Identity](https://identity.imagesoftinc.com/), [My IBISWorld](https://identity.imagesoftinc.com/), [insuite](../saas-apps/insuite-tutorial.md), [Change Process Management](../saas-apps/change-process-management-tutorial.md), [Cyara CX 보증 Platform](../saas-apps/cyara-cx-assurance-platform-tutorial.md), [스마트 글로벌 거 버 넌 스](../saas-apps/smart-global-governance-tutorial.md), [prezi](../saas-apps/prezi-tutorial.md), [mapbox](../saas-apps/mapbox-tutorial.md), [Datava Enterprise Service Platform](../saas-apps/datava-enterprise-service-platform-tutorial.md), Whimsical, Trelica, [](../saas-apps/whimsical-tutorial.md), [Confluence](../saas-apps/easysso-for-confluence-tutorial.md), [](../saas-apps/easysso-for-bitbucket-tutorial.md) [](../saas-apps/trelica-tutorial.md), [Bamboo](../saas-apps/easysso-for-bamboo-tutorial.md), [Torii, Axiad,](../saas-apps/torii-tutorial.md) [Humanage Cloud](../saas-apps/axiad-cloud-tutorial.md), [Vyond](../saas-apps/humanage-tutorial.md), [colortokens ztna](../saas-apps/colortokens-ztna-tutorial.md), [cch tagetik](../saas-apps/cch-tagetik-tutorial.md), [sharevault](../saas-apps/sharevault-tutorial.md), [](../saas-apps/vyond-tutorial.md), [textexpander](../saas-apps/textexpander-tutorial.md), [누구나 Home CRM](../saas-apps/anyone-home-crm-tutorial.md), [askspoke](../saas-apps/askspoke-tutorial.md), [ice 센터](../saas-apps/ice-contact-center-tutorial.md)

여기에서 모든 응용 프로그램의 설명서를 찾을 수도 있습니다 https://aka.ms/AppsTutorial .

Azure AD 앱 갤러리에 응용 프로그램을 나열 하려면 여기에서 세부 정보를 참조 하세요 https://aka.ms/AzureADAppRequest .

---

### <a name="report-only-mode-for-conditional-access-is-now-generally-available"></a>조건부 액세스에 대 한 보고서 전용 모드가 이제 일반 공급 됩니다.

**유형:** 새로운 기능  
**서비스 범주:** 조건부 액세스  
**제품 기능:** Id 보안 & 보호

[AZURE AD 조건부 액세스에 대 한 보고서 전용 모드](../conditional-access/concept-conditional-access-report-only.md) 를 통해 액세스 제어를 적용 하지 않고 정책의 결과를 평가할 수 있습니다. 조직 전체에서 보고서 전용 정책을 테스트 하 고 사용 하도록 설정 하기 전에 영향을 파악 하 여 배포를 더 안전 하 고 쉽게 만들 수 있습니다. 지난 몇 달 동안 보고서 전용 모드를 강력 하 게 채택 했습니다. 26M 사용자는 이미 보고서 전용 정책의 범위에 있습니다. 오늘 공지를 사용 하면 기본적으로 새 Azure AD 조건부 액세스 정책이 보고서 전용 모드에서 생성 됩니다. 즉, 정책을 만든 순간부터 정책의 영향을 모니터링할 수 있습니다. MS Graph Api를 사용 하는 사용자의 경우에도 [프로그래밍 방식으로 보고서 전용 정책을 관리할](/graph/api/resources/conditionalaccesspolicy?view=graph-rest-beta) 수 있습니다. 

---

### <a name="self-service-sign-up-for-guest-users"></a>게스트 사용자에 대 한 셀프 서비스 등록

**유형:** 새로운 기능  
**서비스 범주:** B2B  
**제품 기능:** B2B/B2C
 
Azure AD의 외부 Id를 사용 하 여 조직 외부 사용자가 앱과 리소스에 액세스 하도록 허용 하는 동시에 원하는 모든 id를 사용 하 여 로그인 할 수 있습니다. 외부 사용자와 애플리케이션을 공유하는 경우 애플리케이션에 액세스해야 하는 사용자를 항상 미리 알 수 있는 것은 아닙니다. [셀프 서비스 등록](../external-identities/self-service-sign-up-overview.md)을 사용 하면 게스트 사용자가 LOB (기간 업무) 앱에 등록 하 고 게스트 계정을 확보할 수 있습니다. 등록 흐름을 만들고 사용자 지정 하 여 Azure AD 및 소셜 id를 지원할 수 있습니다. 등록 하는 동안 사용자에 대 한 추가 정보를 수집할 수도 있습니다.

---

 ### <a name="conditional-access-insights-and-reporting-workbook-is-generally-available"></a>조건부 액세스 정보 및 보고 통합 문서를 일반적으로 사용할 수 있음

**유형:** 새로운 기능  
**서비스 범주:** 조건부 액세스  
**제품 기능:** Id 보안 & 보호

[Insights 및 보고 통합 문서](../conditional-access/howto-conditional-access-insights-reporting.md) 는 관리자에 게 테 넌 트의 Azure AD 조건부 액세스에 대 한 요약 보기를 제공 합니다. 관리자는 개별 정책을 선택 하는 기능을 사용 하 여 각 정책에서 수행 하는 작업을 더 잘 이해 하 고 실시간으로 변화를 모니터링할 수 있습니다. 통합 문서는 Azure Monitor에 저장 된 데이터를 스트리밍하 며 몇 분 내에 [이러한 지침에 따라](../reports-monitoring/howto-integrate-activity-logs-with-log-analytics.md)설정할 수 있습니다. 대시보드를 더 쉽게 검색할 수 있도록 Azure AD 조건부 액세스 메뉴 내의 새 정보 및 보고 탭으로 이동 했습니다.

---

### <a name="policy-details-blade-for-conditional-access-is-in-public-preview"></a>조건부 액세스에 대 한 정책 세부 정보 블레이드가 공개 미리 보기 상태입니다.

**유형:** 새로운 기능  
**서비스 범주:** 조건부 액세스  
**제품 기능:** Id 보안 & 보호

새 [정책 세부 정보 블레이드에](../conditional-access/troubleshoot-conditional-access.md) 는 조건부 액세스 정책을 평가 하는 동안 충족 된 할당, 조건 및 컨트롤이 표시 됩니다. 로그인 정보의 조건부 액세스 또는 보고서 전용 탭에서 행을 선택 하 여 블레이드에 액세스할 수 있습니다.

---

### <a name="new-query-capabilities-for-directory-objects-in-microsoft-graph-are-in-public-preview"></a>Microsoft Graph의 디렉터리 개체에 대 한 새로운 쿼리 기능은 공개 미리 보기로 제공 됩니다.

**유형:** 새로운 기능  
**서비스 범주:** MS Graph **제품 기능:** 개발자 환경

Microsoft Graph Directory 개체 Api에 대 한 새로운 기능이 도입 되어 개수, 검색, 필터 및 정렬 작업을 가능 하 게 합니다. 이를 통해 개발자는 메모리 내 필터링 및 정렬과 같은 해결 방법 없이 디렉터리 개체를 신속 하 게 쿼리할 수 있습니다. 이 [블로그 게시물](https://aka.ms/CountFilterMSGraphAAD)에서 자세히 알아보세요.

현재 공개 미리 보기 상태 이며 피드백을 찾고 있습니다. 이 [간단한 설문 조사](https://aka.ms/MsGraphAADSurveyDocs)를 통해 의견을 보내 주시기 바랍니다.

---

### <a name="configure-saml-based-single-sign-on-using-microsoft-graph-api-beta"></a>Microsoft Graph API (베타)를 사용 하 여 SAML 기반 Single Sign-On 구성

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO
 
이제 베타에서 MS Graph Api를 사용 하 여 Azure AD 갤러리에서 응용 프로그램을 만들고 구성 하는 기능을 사용할 수 있습니다. 응용 프로그램의 여러 인스턴스에 대해 SAML 기반 Single Sign-On를 설정 해야 하는 경우 Microsoft Graph Api를 사용 하 여 [saml 기반 Single Sign-On의 구성을 자동화](/graph/application-saml-sso-configure-api)하는 시간을 절약 합니다.
 
---

### <a name="new-provisioning-connectors-in-the-azure-ad-application-gallery---may-2020"></a>Azure AD 응용 프로그램 갤러리의 새로운 프로 비전 커넥터-2020 년 5 월

**유형:** 새로운 기능  
**서비스 범주:** 앱 프로비전  
**제품 기능:** 타사 통합
 
다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

* [8x8](../saas-apps/8x8-provisioning-tutorial.md)
* [Juno Journey](../saas-apps/juno-journey-provisioning-tutorial.md)
* [MediusFlow](../saas-apps/mediusflow-provisioning-tutorial.md)
* [조직별 새 Relic](../saas-apps/new-relic-by-organization-provisioning-tutorial.md)
* [Oracle Cloud Infrastructure Console](../saas-apps/oracle-cloud-infratstructure-console-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="saml-token-encryption-is-generally-available"></a>SAML 토큰 암호화를 일반적으로 사용할 수 있습니다.

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO
 
[Saml 토큰 암호화](../manage-apps/howto-saml-token-encryption.md) 를 사용 하면 암호화 된 saml 어설션을 받도록 응용 프로그램을 구성할 수 있습니다. 이 기능은 이제 모든 클라우드에서 일반적으로 사용할 수 있습니다.
 
---

### <a name="group-name-claims-in-application-tokens-is-generally-available"></a>응용 프로그램 토큰의 그룹 이름 클레임이 일반적으로 사용 가능 합니다.

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO
 
이제 토큰에서 발급 된 그룹 클레임을 응용 프로그램에 할당 된 그룹 으로만 제한할 수 있습니다.  이는 사용자가 많은 그룹의 구성원이 고 토큰 크기 제한을 초과할 위험이 있는 경우에 특히 중요 합니다. 이 새로운 기능을 사용 하는 경우 [토큰에 그룹 이름을 추가](../hybrid/how-to-connect-fed-group-claims.md) 하는 기능이 일반적으로 제공 됩니다.
 
---

### <a name="workday-writeback-now-supports-setting-work-phone-number-attributes"></a>이제 Workday 쓰기 저장에서 회사 전화 번호 특성 설정을 지원 합니다.

**유형:** 새로운 기능  
**서비스 범주:** 앱 프로비전  
**제품 기능:** Id 수명 주기 관리
 
이제 Workday 쓰기 저장 프로 비전 앱이 회사 전화 번호 및 모바일 번호 특성의 쓰기 저장을 지원 하도록 향상 되었습니다. 전자 메일 및 사용자 이름 외에도 이제 Workday 쓰기 저장 프로 비전 앱을 Azure AD에서 Workday로 이동 하는 전화 번호 값을 구성할 수 있습니다. 전화 번호 쓰기 저장을 구성 하는 방법에 대 한 자세한 내용은 [Workday 쓰기 저장](../saas-apps/workday-writeback-tutorial.md) 앱 자습서를 참조 하세요. 

---

### <a name="publisher-verification-preview"></a>게시자 확인 (미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 기타  
**제품 기능:** 개발자 환경
 
Microsoft ID 플랫폼과 통합하는 애플리케이션 개발자의 신뢰성을 관리자와 최종 사용자가 알 수 있도록 도와주는 것이 게시자 확인(미리 보기)입니다. 자세한 내용은 [게시자 확인 (미리 보기)](../develop/publisher-verification-overview.md)을 참조 하세요.
 
---

### <a name="authorization-code-flow-for-single-page-apps"></a>단일 페이지 앱에 대 한 인증 코드 흐름

**유형:** 변경 된 기능 **서비스 범주:** 인증 **제품 기능:** 개발자 환경

최신 브라우저에서 [Safari ITP와 같은 타사 쿠키 제한](../develop/reference-third-party-cookies-spas.md)때문에, SPAS는 SSO를 유지 하기 위해 암시적 흐름이 아닌 권한 부여 코드 흐름을 사용 해야 합니다. MSAL.js v 2. x는 이제 인증 코드 흐름을 지원 합니다. Azure Portal에 대 한 해당 업데이트가 있으므로 SPA를 "spa" 형식으로 업데이트 하 고 인증 코드 흐름을 사용할 수 있습니다. 지침은 [빠른 시작: 인증 사용자 로그인 및 인증 코드 흐름을 사용 하 여 JAVASCRIPT SPA에서 액세스 토큰 가져오기](../develop/quickstart-v2-javascript-auth-code.md)를 참조 하세요.

---

### <a name="improved-filtering-for-devices-is-in-public-preview"></a>공개 미리 보기로 제공 되는 장치에 대 한 필터링 향상

**유형:** 변경 된 기능   
**서비스 범주:** 장치 관리 **제품 기능:** 장치 수명 주기 관리
 
이전에는 사용할 수 있는 유일한 필터는 "사용" 및 "작업 날짜"입니다. 이제 OS 유형, 조인 유형, 규정 준수 등을 비롯 한 [더 많은 속성을 통해 장치 목록을 필터링](../devices/device-management-azure-portal.md#device-list-filtering-preview)할 수 있습니다. 이러한 추가 기능을 통해 특정 장치를 쉽게 찾을 것입니다.

---

### <a name="the-new-app-registrations-experience-for-azure-ad-b2c-is-now-generally-available"></a>이제 Azure AD B2C의 새로운 앱 등록 환경이 출시 되었습니다.

**유형:** 변경 된 기능   
**서비스 범주:** B2C - 소비자 ID 관리  
**제품 기능:** Id 수명 주기 관리
 
이제 Azure AD B2C에 대 한 새로운 앱 등록 환경이 출시 되었습니다. 

이전에는 레거시 ' 응용 프로그램 ' 환경을 사용 하 여 응용 프로그램의 나머지 부분과 별도로 B2C 소비자 지향 응용 프로그램을 관리 해야 했습니다. Azure의 여러 위치에서 다양 한 앱 만들기 환경을 의미 합니다.

새 환경에서는 모든 B2C 앱 등록 및 Azure AD 앱 등록을 한 곳에 표시 하 고 일관 된 방식으로 관리 하는 방법을 제공 합니다. Azure AD B2C 리소스를 프로그래밍 방식으로 관리 하기 위해 Microsoft Graph에 대 한 액세스 권한이 있는 앱 또는 고객 관련 앱을 관리 해야 하는지 여부에 관계 없이 작업을 수행 하는 한 가지 방법만 배워야 합니다.

Azure AD B2C 서비스를 탐색 하 고 앱 등록 블레이드를 선택 하 여 새 환경에 연결할 수 있습니다. 환경에도 Azure Active Directory 서비스에서 액세스할 수 있습니다.

Azure AD B2C 앱 등록 환경은 Azure AD 테 넌 트에 대 한 일반 [앱 등록 환경을](https://developer.microsoft.com/identity/blogs/new-app-registrations-experience-is-now-generally-available/) 기반으로 하지만 Azure AD B2C에 맞게 조정 됩니다. 레거시 "응용 프로그램" 환경은 향후 더 이상 사용 되지 않습니다.

자세한 내용은 [Azure AD B2C에 대 한 새로운 앱 등록 환경](../../active-directory-b2c/app-registrations-training-guide.md)을 참조 하세요.

---
## <a name="april-2020"></a>2020년 4월

### <a name="combined-security-info-registration-experience-is-now-generally-available"></a>결합 된 보안 정보 등록 환경이 이제 일반 공급 됩니다.

**유형:** 새로운 기능

**서비스 범주:** 인증 (로그인)

**제품 기능:** Id 보안 & 보호

Multi-Factor Authentication (MFA) 및 Self-Service 암호 재설정 (SSPR)에 대 한 결합 된 등록 환경이 이제 일반 공급 됩니다. 이 새로운 등록 환경을 통해 사용자는 단일 단계별 프로세스에서 MFA 및 SSPR에 등록할 수 있습니다. 조직의 새 환경을 배포 하는 경우 사용자는 더 짧은 시간에 더 많은 작업을 등록할 수 있습니다. 블로그 [게시물을 확인 하세요.](https://bit.ly/3etiRyQ)

---

### <a name="continuous-access-evaluation"></a>연속 액세스 평가

**유형:** 새로운 기능

**서비스 범주:** 인증 (로그인)

**제품 기능:** Id 보안 & 보호

연속 액세스 평가는 Azure AD에서 이벤트가 발생 하는 경우 (예: 사용자 계정 삭제) Azure AD 액세스 토큰을 사용 하는 신뢰 당사자에 대해 거의 실시간으로 정책을 적용할 수 있는 새로운 보안 기능입니다. 팀과 Outlook 클라이언트를 위해이 기능을 먼저 롤링 합니다. 자세한 내용은 [블로그](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/moving-towards-real-time-policy-and-security-enforcement/ba-p/1276933) 및  [설명서](../conditional-access/concept-continuous-access-evaluation.md)를 참조 하세요.

---

### <a name="sms-sign-in-firstline-workers-can-sign-in-to-azure-ad-backed-applications-with-their-phone-number-and-no-password"></a>SMS 로그인: Firstline Worker는 전화 번호를 사용 하 고 암호 없이 Azure AD 지원 응용 프로그램에 로그인 할 수 있습니다.

**유형:** 새로운 기능

**서비스 범주:** 인증 (로그인)

**제품 기능:** 사용자 인증

Office는 기존 이외의 조직에서 사용할 수 있는 일련의 모바일 중심 비즈니스 앱과 주 통신 방법으로 전자 메일을 사용 하지 않는 대기업의 직원을 시작 합니다. 이러한 앱은 frontline 직원, deskless 작업자, 현장 에이전트 또는 소매점에서 전자 메일 주소를 얻지 못할 수도 있고, 컴퓨터에 대 한 액세스 권한이 있거나, 소매 직원을 대상으로 합니다. 이 프로젝트는 전화 번호를 입력 하 고 코드를 왕복 하 여 이러한 직원이 비즈니스 응용 프로그램에 로그인 할 수 있도록 합니다. 자세한 내용은 [관리자 설명서](../authentication/howto-authentication-sms-signin.md) 및 [최종 사용자 설명서](../user-help/sms-sign-in-explainer.md)를 참조 하세요.

---

### <a name="invite-internal-users-to-use-b2b-collaboration"></a>내부 사용자에 게 B2B 공동 작업을 사용 하도록 초대

**유형:** 새로운 기능

**서비스 범주:** B2B

**제품 기능:**

Microsoft는 향후 b2b 공동 작업 자격 증명을 사용 하도록 기존 내부 계정을 초대할 수 있도록 B2B 초대 기능을 확장 하 고 있습니다. 초대 된 전자 메일 주소와 같은 일반적인 매개 변수와 함께 사용자 개체를 초대 API에 전달 하 여이 작업을 수행 합니다. 사용자의 개체 ID, UPN, 그룹 멤버 자격, 앱 할당 등은 그대로 유지 되지만 앞으로는 B2B를 사용 하 여 초대 전에 사용한 내부 자격 증명이 아닌 해당 홈 테 넌 트 자격 증명을 사용 하 여 인증 합니다. 자세한 내용은 [설명서](../external-identities/invite-internal-users.md)를 참조 하세요.

---

### <a name="report-only-mode-for-conditional-access-is-now-generally-available"></a>조건부 액세스에 대 한 보고서 전용 모드가 이제 일반 공급 됩니다.

**유형:** 새로운 기능

**서비스 범주:** 조건부 액세스

**제품 기능:** Id 보안 & 보호

[AZURE AD 조건부 액세스에 대 한 보고서 전용 모드](../conditional-access/concept-conditional-access-report-only.md) 를 통해 액세스 제어를 적용 하지 않고 정책의 결과를 평가할 수 있습니다. 조직 전체에서 보고서 전용 정책을 테스트 하 고 사용 하도록 설정 하기 전에 영향을 파악 하 여 배포를 더 안전 하 고 쉽게 만들 수 있습니다. 지난 몇 달 동안 보고서 전용 정책의 범위에 이미 있는 26M 사용자를 포함 하 여 보고서 전용 모드를 강력 하 게 채택 했습니다. 이 공지를 사용 하면 기본적으로 새 Azure AD 조건부 액세스 정책이 보고서 전용 모드에서 생성 됩니다. 즉, 정책을 만든 순간부터 정책의 영향을 모니터링할 수 있습니다. MS Graph Api를 사용 하는 사용자의 경우에는 [프로그래밍 방식으로 보고서 전용 정책을 관리할](/graph/api/resources/conditionalaccesspolicy?view=graph-rest-beta)수도 있습니다. 

---

### <a name="conditional-access-insights-and-reporting-workbook-is-generally-available"></a>조건부 액세스 정보 및 보고 통합 문서를 일반적으로 사용할 수 있음

**유형:** 새로운 기능

**서비스 범주:** 조건부 액세스

**제품 기능:** Id 보안 & 보호

조건부 액세스 [정보 및 보고 통합 문서](../conditional-access/howto-conditional-access-insights-reporting.md) 는 관리자에 게 테 넌 트의 Azure AD 조건부 액세스에 대 한 요약 보기를 제공 합니다. 관리자는 개별 정책을 선택 하는 기능을 사용 하 여 각 정책에서 수행 하는 작업을 더 잘 이해 하 고 실시간으로 변화를 모니터링할 수 있습니다. 통합 문서는 Azure Monitor에 저장 된 데이터를 스트리밍하 며 몇 분 내에 [이러한 지침에 따라](../reports-monitoring/howto-integrate-activity-logs-with-log-analytics.md)설정할 수 있습니다. 대시보드를 더 쉽게 검색할 수 있도록 Azure AD 조건부 액세스 메뉴 내의 새 정보 및 보고 탭으로 이동 했습니다.

---

### <a name="policy-details-blade-for-conditional-access-is-in-public-preview"></a>조건부 액세스에 대 한 정책 세부 정보 블레이드가 공개 미리 보기 상태입니다.

**유형:** 새로운 기능

**서비스 범주:** 조건부 액세스

**제품 기능:** Id 보안 & 보호

새 [정책 세부 정보 블레이드](../conditional-access/troubleshoot-conditional-access.md) 는 조건부 액세스 정책 평가 중에 충족 된 할당, 조건 및 컨트롤을 표시 합니다. 로그인 정보의 **조건부 액세스** 또는 **보고서 전용** 탭에서 행을 선택 하 여 블레이드에 액세스할 수 있습니다.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---april-2020"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱-4 월 2020

**유형:** 새로운 기능

**서비스 범주:** 엔터프라이즈 앱

**제품 기능:** 타사 통합

4 월 2020에 앱 갤러리에 대 한 페더레이션 지원과 함께 이러한 31 개의 새 앱을 추가 했습니다. 

[SincroPool Apps](https://www.sincropool.com/), [smartdb](https://hibiki.dreamarts.co.jp/smartdb/trial/), [Float](../saas-apps/float-tutorial.md), [LMS365](https://lms.365.systems/), [iwt-9j-u8d 조달 Suite](../saas-apps/iwt-procurement-suite-tutorial.md), [Lunni](https://lunni.fi/),, [Jira에 대 한](../saas-apps/easysso-for-jira-tutorial.md) [가상 교육 아카데미](https://vta.c3p.ca/app/en/openid?authenticate_with=microsoft), [Meraki 대시보드](../saas-apps/meraki-dashboard-tutorial.md), [Microsoft 365](https://app.mover.io/login)이동 기 [, 발표자 참여](https://speakerengage.com/login.php), [솔직히](../saas-apps/honestly-tutorial.md), [동맹](../saas-apps/ally-tutorial.md), [DutyFlow](https://app.dutyflow.nl/), [alertmedia](../saas-apps/alertmedia-tutorial.md), [gr8 사람](../saas-apps/gr8-people-tutorial.md), [Pendo](../saas-apps/pendo-tutorial.md), [highground](../saas-apps/highground-tutorial.md), [조화](../saas-apps/harmony-tutorial.md), [Timetabling 솔루션](../saas-apps/timetabling-solutions-tutorial.md), [SynchroNet 클릭](../saas-apps/synchronet-click-tutorial.md), [역량](https://www.made-in-office.com/en/), [fortes 자료 변경 클라우드](../saas-apps/fortes-change-cloud-tutorial.md), [Litmus](../saas-apps/litmus-tutorial.md), [groupcoa](https://recorder.grouptalk.com/), Frontify, [MongoDB cloud](../saas-apps/mongodb-cloud-tutorial.md), [TickitLMS 배우기](../saas-apps/tickitlms-learn-tutorial.md), [coco](https://hexaware.com/partnerships-and-alliances/digital-transformation-using-microsoft-azure/), [nitro 생산성 도구](../saas-apps/nitro-productivity-suite-tutorial.md), [(Trend 마이크로 웹 보안)](https://review.docs.microsoft.com/azure/active-directory/saas-apps/trend-micro-tutorial) [](../saas-apps/frontify-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="microsoft-graph-delta-query-support-for-oauth2permissiongrant-available-for-public-preview"></a>공개 미리 보기에 사용할 수 있는 oAuth2PermissionGrant에 대 한 델타 쿼리 지원 Microsoft Graph

**유형:** 새로운 기능

**서비스 범주:** MS 그래프

**제품 기능:** 개발자 환경

OAuth2PermissionGrant에 대 한 델타 쿼리는 공개 미리 보기에서 사용할 수 있습니다. 이제 Microsoft Graph를 지속적으로 폴링할 필요 없이 변경 내용을 추적할 수 있습니다. [자세한 정보](/graph/api/oAuth2PermissionGrant-delta?tabs=http&view=graph-rest-beta)

---

### <a name="microsoft-graph-delta-query-support-for-organizational-contact-generally-available"></a>조직 연락처에 대 한 Microsoft Graph 델타 쿼리 지원 일반 공급

**유형:** 새로운 기능

**서비스 범주:** MS 그래프

**제품 기능:** 개발자 환경

조직 연락처에 대 한 델타 쿼리를 일반적으로 사용할 수 있습니다. 이제 Microsoft Graph를 지속적으로 폴링 하지 않고도 프로덕션 앱에서 변경 내용을 추적할 수 있습니다. OrgContact 데이터를 지속적으로 폴링하는 기존 코드를 델타 쿼리로 대체 하 여 성능을 크게 향상 시킵니다. [자세한 정보](/graph/api/orgcontact-delta?tabs=http)

---

### <a name="microsoft-graph-delta-query-support-for-application-generally-available"></a>응용 프로그램에 대 한 델타 쿼리 지원이 일반 공급 되는 Microsoft Graph

**유형:** 새로운 기능

**서비스 범주:** MS 그래프

**제품 기능:** 개발자 환경

응용 프로그램에 대 한 델타 쿼리를 일반적으로 사용할 수 있습니다. 이제 Microsoft Graph를 지속적으로 폴링 하지 않고도 프로덕션 앱에서 변경 내용을 추적할 수 있습니다. 응용 프로그램 데이터를 지속적으로 폴링하는 기존 코드를 델타 쿼리로 대체 하 여 성능을 크게 향상 시킵니다. [자세한 정보](/graph/api/application-delta)

---

### <a name="microsoft-graph-delta-query-support-for-administrative-units-available-for-public-preview"></a>공개 미리 보기에 사용할 수 있는 관리 단위에 대 한 델타 쿼리 지원 Microsoft Graph

**유형:** 새로운 기능

**서비스 범주:** MS 그래프

**제품 기능:** 관리 단위에 대 한 개발자 환경 델타 쿼리는 공개 미리 보기에서 사용할 수 있습니다. 이제 Microsoft Graph를 지속적으로 폴링할 필요 없이 변경 내용을 추적할 수 있습니다. [자세한 정보](/graph/api/administrativeunit-delta?tabs=http&view=graph-rest-beta)

---

### <a name="manage-authentication-phone-numbers-and-more-in-new-microsoft-graph-beta-apis"></a>새 Microsoft Graph 베타 Api에서 인증 전화 번호 등을 관리 합니다.

**유형:** 새로운 기능

**서비스 범주:** MS 그래프

**제품 기능:** 개발자 환경

이러한 Api는 사용자의 인증 방법을 관리 하기 위한 핵심 도구입니다. 이제 MFA 및 SSPR (셀프 서비스 암호 재설정)에 사용 되는 인증자를 프로그래밍 방식으로 미리 등록 하 고 관리할 수 있습니다. 이는 Azure AD MFA, SSPR 및 Microsoft Graph 공간에서 가장 많이 요청 되는 기능 중 하나입니다. 이 wave에서 릴리스된 새 Api는 다음을 수행할 수 있는 기능을 제공 합니다.

- 사용자의 인증 전화를 읽고, 추가 하 고, 업데이트 하 고, 제거 합니다.
- 사용자의 암호 다시 설정
- SMS 로그인 설정 및 해제

자세한 내용은 [AZURE AD 인증 방법 API 개요](/graph/api/resources/authenticationmethods-overview?view=graph-rest-beta)를 참조 하세요.

---

### <a name="administrative-units-public-preview"></a>관리 단위 공개 미리 보기

**유형:** 새로운 기능

**서비스 범주:** Azure AD 역할

**제품 기능:** 액세스 제어

관리 단위를 사용하면 정의하는 조직의 부서, 지역 또는 기타 세그먼트로 제한된 관리자 권한을 부여할 수 있습니다. 관리 단위를 사용하여 지역 관리자에게 권한을 위임하거나 세부적인 수준에서 정책을 설정할 수 있습니다. 예를 들어 사용자 계정 관리자는 프로필 정보를 업데이트하고, 암호를 다시 설정하고, 자신의 관리 단위에 포함된 사용자에게만 라이선스를 할당할 수 있습니다.

중앙 관리자는 관리 단위를 사용 하 여 다음과 같은 작업을 할 수 있습니다.

- 리소스의 분산 관리를 위한 관리 단위 만들기
- 관리 단위의 Azure AD 사용자만 관리 권한을 사용 하 여 역할 할당
- 필요에 따라 사용자 및 그룹으로 관리 단위 채우기

자세한 내용은 [Azure Active Directory의 관리 단위 관리 (미리 보기)](../roles/administrative-units.md)를 참조 하세요.

---

### <a name="printer-administrator-and-printer-technician-built-in-roles"></a>프린터 관리자 및 프린터 기술자 기본 제공 역할

**유형:** 새로운 기능

**서비스 범주:** Azure AD 역할

**제품 기능:** 액세스 제어

**프린터 관리자**:이 역할의 사용자는 프린터를 등록 하 고 유니버설 인쇄 커넥터 설정을 포함 하 여 Microsoft 유니버설 인쇄 솔루션의 모든 프린터 구성의 모든 측면을 관리할 수 있습니다. 모든 위임된 인쇄 권한 요청에 동의할 수 있습니다. 또한 프린터 관리자는 보고서를 인쇄할 수 있습니다. 

**Printer 기술자**:이 역할의 사용자는 Microsoft 유니버설 인쇄 솔루션에서 프린터를 등록 하 고 프린터 상태를 관리할 수 있습니다. 또한 모든 커넥터 정보를 읽을 수 있습니다. 프린터 기술 자가 할 수 없는 주요 작업은 프린터 및 공유 프린터에 대 한 사용자 권한을 설정 하는 것입니다. [자세한 정보](../roles/permissions-reference.md#printer-administrator)

---

### <a name="hybrid-identity-admin-built-in-role"></a>하이브리드 Id 관리 기본 제공 역할

**유형:** 새로운 기능

**서비스 범주:** Azure AD 역할

**제품 기능:** 액세스 제어

이 역할의 사용자는 Azure AD에서 하이브리드 ID 사용 설정과 관련된 서비스 및 설정을 사용하도록 설정하고, 구성하고, 관리할 수 있습니다. 이 역할은 Azure AD를 PHS (암호 해시 동기화), PTA (통과 인증) 또는 페더레이션 (AD FS 또는 타사 페더레이션 공급자) &#8212;에서 지원 되는 세 가지 인증&#8212;방법 중 하나로 구성 하 고,이를 사용 하도록 설정 하는 데 관련 온-프레미스 인프라를 배포 하는 기능을 제공 합니다. 온-프레미스 인프라에는 프로 비전 및 PTA 에이전트가 포함 됩니다. 이 역할은 S-SSO(Seamless Single Sign-On)를 사용하도록 설정하여 Windows 10 이외의 디바이스 또는 Windows Server 2016 이외의 컴퓨터에서 원활한 인증이 가능하게 하는 기능을 부여합니다. 또한이 역할은 로그인 로그를 확인 하 고 모니터링 및 문제 해결을 위한 상태 및 분석에 액세스할 수 있는 기능을 부여 합니다. [자세한 정보](../roles/permissions-reference.md#hybrid-identity-administrator)

---

### <a name="network-administrator-built-in-role"></a>네트워크 관리자 기본 제공 역할

**유형:** 새로운 기능

**서비스 범주:** Azure AD 역할

**제품 기능:** 액세스 제어

이 역할을 가진 사용자는 Microsoft의 네트워크 경계 아키텍처 권장 사항을 검토 하 여 사용자 위치에서 네트워크 원격 분석을 기반으로 할 수 있습니다. Microsoft 365의 네트워크 성능은 일반적으로 사용자 위치와 관련 된 신중한 엔터프라이즈 고객 네트워크 경계 아키텍처를 사용 합니다. 이 역할이 있으면 검색된 사용자 위치와 해당 위치의 네트워크 매개 변수 구성을 편집하여 원격 분석 측정 및 디자인 권장 사항을 쉽게 개선할 수 있습니다. [자세한 정보](../roles/permissions-reference.md#network-administrator)

---

### <a name="bulk-activity-and-downloads-in-the-azure-ad-admin-portal-experience"></a>Azure AD 관리 포털 환경에서 대량 작업 및 다운로드

**유형:** 새로운 기능

**서비스 범주:** 사용자 관리

**제품 기능:** 디렉터리나

이제 Azure AD 관리 포털 환경에서 CSV 파일을 업로드 하 여 Azure AD의 사용자 및 그룹에 대 한 대량 작업을 수행할 수 있습니다. 사용자를 만들고, 사용자를 삭제 하 고, 게스트 사용자를 초대할 수 있습니다. 그리고 그룹에서 구성원을 추가 하 고 제거할 수 있습니다.

Azure AD 관리 포털 환경에서 Azure AD 리소스 목록을 다운로드할 수도 있습니다. 디렉터리, 디렉터리의 그룹 목록 및 특정 그룹의 구성원에 대 한 사용자 목록을 다운로드할 수 있습니다.

자세한 내용은 다음을 확인 하세요.

- [사용자 만들기](../enterprise-users/users-bulk-add.md) 또는 [게스트 사용자 초대](../external-identities/tutorial-bulk-invite.md)
- [사용자 삭제](../enterprise-users/users-bulk-delete.md) 또는 [삭제 된 사용자 복원](../enterprise-users/users-bulk-restore.md)
- [사용자 목록 다운로드](../enterprise-users/users-bulk-download.md) 또는 [그룹 목록 다운로드](../enterprise-users/groups-bulk-download.md)
- 그룹에 대 한 멤버 [추가 (가져오기)](../enterprise-users/groups-bulk-import-members.md) 또는 구성원 [제거](../enterprise-users/groups-bulk-remove-members.md) 또는 [구성원 목록 다운로드](../enterprise-users/groups-bulk-download-members.md)

---

### <a name="my-staff-delegated-user-management"></a>내 직원 위임 된 사용자 관리

**유형:** 새로운 기능

**서비스 범주:** 사용자 관리

**제품 기능:**

직원 들이 자신의 직원 구성원이 자신의 Azure AD 계정에 액세스할 수 있도록 내 직원은 저장소 관리자와 같은 Firstline 관리자를 사용 하도록 설정 합니다. 조직에서는 중앙 기술 지원팀에 의존 하는 대신 암호 재설정 또는 전화 번호 변경과 같은 일반적인 작업을 Firstline Manager로 위임할 수 있습니다. 직원 들이 자신의 계정에 액세스할 수 없는 사용자는 기술 지원팀 또는 IT 담당자가 필요 하지 않은 두 번의 클릭 만으로 액세스 권한을 다시 얻을 수 있습니다. 자세한 내용은 내 [직원 (미리 보기)을 사용](../roles/my-staff-configure.md) 하 여 사용자 관리 및 [내 직원 (미리 보기)을 사용 하 여 사용자 관리 위임 (미리 보기)](../user-help/my-staff-team-manager.md)을 참조 하세요.

---

### <a name="an-upgraded-end-user-experience-in-access-reviews"></a>액세스 검토에서 업그레이드 된 최종 사용자 환경

**유형:** 변경된 기능

**서비스 범주:** 액세스 검토

**제품 기능:** Id 거 버 넌 스

내 앱 포털에서 Azure AD 액세스 검토에 대 한 검토자 환경을 업데이트 했습니다. 4 월 말에 Azure AD 액세스를 검토 하는 검토자에 게는 사용자의 액세스에 업데이트 된 환경을 사용해 볼 수 있는 배너가 표시 됩니다. 업데이트 된 액세스 검토 환경은 현재 환경과 동일한 기능을 제공 하지만 사용자가 생산성을 높일 수 있도록 새로운 기능을 기반으로 하는 향상 된 사용자 인터페이스를 제공 합니다. [업데이트 된 환경에 대 한 자세한 내용은 여기에서 확인할 수](../governance/perform-access-review.md)있습니다. 이 공개 미리 보기는 7 월 2020이 끝날 때까지 마지막으로 발생 합니다. 7 월 말에 미리 보기 환경을 옵트인 하지 않은 검토자는 액세스 검토를 수행 하기 위해 자동으로 내 액세스로 전달 됩니다. 검토자가 내 액세스의 미리 보기 환경으로 영구적으로 전환 되도록 하려면 [여기에서 요청 하세요](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR5dv-S62099HtxdeKIcgO-NUOFJaRDFDWUpHRk8zQ1BWVU1MMTcyQ1FFUi4u).

---

### <a name="workday-inbound-user-provisioning-and-writeback-apps-now-support-the-latest-versions-of-workday-web-services-api"></a>Workday 인바운드 사용자 프로 비전 및 쓰기 저장 앱은 이제 최신 버전의 Workday 웹 서비스 API를 지원 합니다.

**유형:** 변경된 기능

**서비스 범주:** 앱 프로비전

**제품 기능:** 

이제 고객의 의견에 따라 엔터프라이즈 앱 갤러리에서 Workday 인바운드 사용자 프로 비전 및 쓰기 저장 앱을 업데이트 하 여 최신 버전의 WWS (Workday 웹 서비스) API를 지원 합니다. 이러한 변경을 통해 고객은 연결 문자열에서 사용할 WWS API 버전을 지정할 수 있습니다. 이를 통해 고객은 Workday 릴리스에서 제공 되는 더 많은 HR 특성을 검색할 수 있습니다. Workday 쓰기 저장 앱은 이제 권장 Change_Work_Contact_Info Workday 웹 서비스를 사용 하 여 Maintain_Contact_Info의 제한을 극복 합니다.

연결 문자열에 버전이 지정 되지 않은 경우 기본적으로 Workday 인바운드 프로 비전 앱은 WWS v 21.1를 사용 하 여 인바운드 사용자 프로 비전을 위한 최신 Workday Api로 전환 하 고, 고객은 [자습서에 설명 된](../saas-apps/workday-inbound-tutorial.md#which-workday-apis-does-the-solution-use-to-query-and-update-workday-worker-profiles) 대로 연결 문자열을 업데이트 하 고 [workday 특성 참조 가이드](../app-provisioning/workday-attribute-reference.md#xpath-values-for-workday-web-services-wws-api-v30)에 설명 된 대로 workday 특성에 사용 되는 xpath도 업데이트 해야 합니다. 

쓰기 저장 (writeback)을 위해 새 API를 사용 하려면 Workday 쓰기 저장 프로 비전 앱에 필요한 변경 내용이 없습니다. Workday 쪽에서 Workday (Workday 통합 시스템 사용자) 계정에 자습서 섹션인 [비즈니스 프로세스 보안 정책 권한 구성](../saas-apps/workday-inbound-tutorial.md#configuring-business-process-security-policy-permissions)에 설명 된 대로 Change_Work_Contact 비즈니스 프로세스를 호출할 수 있는 권한이 있는지 확인 합니다. 

새 API 버전 지원이 반영 되도록 [자습서 가이드](../saas-apps/workday-inbound-tutorial.md) 를 업데이트 했습니다.

---

### <a name="users-with-default-access-role-are-now-in-scope-for-provisioning"></a>기본 액세스 역할이 있는 사용자는 현재 프로 비전 범위에 있습니다.

**유형:** 변경된 기능

**서비스 범주:** 앱 프로비전

**제품 기능:** Id 수명 주기 관리

지금까지 기본 액세스 역할이 있는 사용자는 프로 비전 범위를 벗어났습니다. 이 역할을 가진 사용자가 프로 비전 범위에 있는 것을 고객에 게 제공할 수 있는 피드백을 받았습니다. 2020 년 4 월 16 일부 터 모든 새 프로 비전 구성을 사용 하면 기본 액세스 역할이 있는 사용자를 프로 비전 할 수 있습니다. 점진적으로 기존 프로 비전 구성의 동작을 변경 하 여이 역할을 사용 하는 사용자 프로 비전을 지원 합니다. [자세한 정보](../app-provisioning/application-provisioning-config-problem-no-users-provisioned.md)

---

### <a name="updated-provisioning-ui"></a>업데이트 된 프로 비전 UI

**유형:** 변경된 기능

**서비스 범주:** 앱 프로비전

**제품 기능:** Id 수명 주기 관리

프로 비전 환경을 새로 고쳐 더 집중 된 관리 보기를 만들었습니다. 이미 구성 된 엔터프라이즈 응용 프로그램의 프로 비전 블레이드로 이동 하면 프로 비전 시작, 중지 및 다시 시작 등의 작업을 프로 비전 하 고 관리 하는 과정을 쉽게 모니터링할 수 있습니다. [자세한 정보](../app-provisioning/configure-automatic-user-provisioning-portal.md)

---

### <a name="dynamic-group-rule-validation-is-now-available-for-public-preview"></a>동적 그룹 규칙 유효성 검사는 이제 공개 미리 보기로 제공 됩니다.

**유형:** 변경된 기능

**서비스 범주:** 그룹 관리

**제품 기능:** 협업

이제 Azure Active Directory (Azure AD)에서 동적 그룹 규칙의 유효성을 검사 하는 방법을 제공 합니다. **규칙 유효성 검사** 탭에서 샘플 그룹 멤버에 대해 동적 규칙의 유효성을 검사 하 여 규칙이 예상 대로 작동 하는지 확인할 수 있습니다. 관리자는 동적 그룹 규칙을 만들거나 업데이트할 때 사용자 또는 장치가 그룹의 구성원 인지 여부를 확인 하려고 합니다. 이를 통해 사용자 또는 장치가 규칙 기준을 충족 하는지 여부를 평가 하 고, 멤버 자격이 필요 하지 않을 때 문제 해결을 지원 합니다.

자세한 내용은 [동적 그룹 멤버 자격 규칙 유효성 검사 (미리 보기)](../enterprise-users/groups-dynamic-rule-validation.md)를 참조 하세요.

---

### <a name="identity-secure-score---security-defaults-and-mfa-improvement-action-updates"></a>Id 보안 점수-보안 기본값 및 MFA 개선 작업 업데이트

**유형:** 변경된 기능

**서비스 범주:** 해당 없음

**제품 기능:** Id 보안 & 보호

**AZURE AD 개선 작업의 보안 기본값 지원:** Microsoft Secure 점수는 [AZURE AD의 보안 기본값](./concept-fundamentals-security-defaults.md)을 지원 하도록 개선 작업을 업데이트 하 여 일반적인 공격에 대해 미리 구성 된 보안 설정으로 조직을 보호 하는 작업을 더 쉽게 수행할 수 있게 해줍니다. 이는 다음과 같은 개선 작업에 영향을 줍니다.

- 모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인
- 관리 역할에 대 한 MFA 필요
- 정책을 사용 하 여 레거시 인증 차단
 
**MFA 개선 작업 업데이트:** 비즈니스에 사용 되는 정책을 적용 하는 동시에 비즈니스의 보안을 보장 하기 위한 비즈니스 요구 사항을 반영 하기 위해 Microsoft 보안 점수는 다단계 인증 중심의 세 가지 개선 작업을 제거 하 고 2를 추가 했습니다.

제거 되는 향상 작업:

- Multi-factor authentication에 대 한 모든 사용자 등록
- 모든 사용자용 MFA 필요
- Azure AD 권한 있는 역할에 대 한 MFA 필요

추가 된 개선 작업:

- 모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인
- 관리 역할에 대 한 MFA 필요

이러한 새로운 향상 된 작업을 수행 하려면 디렉터리에서 MFA (multi-factor authentication)에 대해 사용자 또는 관리자를 등록 하 고 조직의 요구에 맞는 올바른 정책 집합을 설정 해야 합니다. 주요 목표는 모든 사용자와 관리자가 여러 요소나 위험 기반 id 확인 프롬프트를 사용 하 여 인증할 수 있도록 하는 동시에 유연성을 유지 하는 것입니다. 이는 범위가 지정 된 결정을 적용 하는 여러 정책이 있거나, Microsoft에서 MFA에 대 한 사용자의 시도 시기를 결정 하는 보안 기본값 (3 월 16 일 기준)을 설정 하는 형태를 사용할 수 있습니다. [Microsoft 보안 점수의 새로운 기능에 대해 자세히](/microsoft-365/security/mtp/microsoft-secure-score#whats-new)알아보세요.

---

## <a name="march-2020"></a>2020년 3월

### <a name="unmanaged-azure-active-directory-accounts-in-b2b-update-for-march--2021"></a>3 월 2021 B2B 업데이트의 관리 되지 않는 Azure Active Directory 계정

**유형:** 변경 계획  
**서비스 범주:** B2B  
**제품 기능:** B2B/B2C
 
**2021 년 3 월 31 일부 터** MICROSOFT는 B2B 공동 작업 시나리오에 대해 관리 되지 않는 Azure Active Directory (Azure AD) 계정 및 테 넌 트를 만들어 더 이상 초대 상환을 지원 하지 않습니다. 이를 위해 준비 하는 [동안 일회용 암호 인증을 전자 메일로](../external-identities/one-time-passcode.md)보내도록 옵트인 하는 것이 좋습니다.

---

### <a name="users-with-the-default-access-role-will-be-in-scope-for-provisioning"></a>기본 액세스 역할이 있는 사용자는 프로 비전 범위에 포함 됩니다.

**유형:** 변경 계획  
**서비스 범주:** 앱 프로비전  
**제품 기능:** Id 수명 주기 관리
 
지금까지 기본 액세스 역할이 있는 사용자는 프로 비전 범위를 벗어났습니다. 이 역할을 가진 사용자가 프로 비전 범위에 있는 것을 고객에 게 제공할 수 있는 피드백을 받았습니다. 모든 새 프로 비전 구성에서 기본 액세스 역할이 있는 사용자를 프로 비전 할 수 있도록 변경 내용을 배포 하기 위해 노력 하 고 있습니다. 점진적으로 기존 프로 비전 구성의 동작을 변경 하 여이 역할의 사용자 프로 비전을 지원 합니다. 고객 동작은 필요 하지 않습니다. 이 변경 내용이 적용 되 면 [설명서](../app-provisioning/application-provisioning-config-problem-no-users-provisioned.md) 에 대 한 업데이트를 게시 합니다.

---

### <a name="azure-ad-b2b-collaboration-will-be-available-in-microsoft-azure-operated-by-21vianet-azure-china-21vianet-tenants"></a>Azure AD B2B 공동 작업은 21Vianet (Azure 중국 21Vianet) 테 넌 트에서 운영 하는 Microsoft Azure에서 사용할 수 있습니다.

**유형:** 변경 계획  
**서비스 범주:** B2B  
**제품 기능:** B2B/B2C
 
Azure AD B2B 공동 작업 기능은 21Vianet (Azure 중국 21Vianet) 테 넌 트가 운영 하는 Microsoft Azure에서 사용할 수 있으며, Azure 중국 21Vianet 테 넌 트의 사용자가 다른 Azure 중국 21Vianet 테 넌 트의 사용자와 원활 하 게 공동 작업을 수행할 수 있도록 합니다. [AZURE AD B2B 공동 작업에 대해 자세히 알아보세요](/azure/active-directory/b2b/).

---
 
### <a name="azure-ad-b2b-collaboration-invitation-email-redesign"></a>Azure AD B2B 공동 작업 초대 전자 메일 다시 디자인

**유형:** 변경 계획  
**서비스 범주:** B2B  
**제품 기능:** B2B/B2C
 
사용자를 디렉터리에 초대 하기 위해 Azure AD B2B 공동 작업 초대 서비스에서 보낸 [전자 메일](../external-identities/invitation-email-elements.md) 은 초대 정보 및 사용자의 다음 단계를 명확 하 게 하기 위해 다시 디자인 됩니다.

---

### <a name="homerealmdiscovery-policy-changes-will-appear-in-the-audit-logs"></a>Homerealmdiscovery.aspx 정책 변경이 감사 로그에 표시 됩니다.

**유형:** 고정  
**서비스 범주:** 감사  
**제품 기능:** 모니터링 및 보고
 
[Homerealmdiscovery.aspx 정책](../manage-apps/configure-authentication-for-federated-users-portal.md) 에 대 한 변경 내용이 감사 로그에 포함 되지 않은 버그를 수정 했습니다. 이제 정책을 변경 하는 시기와 방법 및 해당 사용자를 확인할 수 있습니다. 

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---march-2020"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱-3 월 2020

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
3 월 2020에 앱 갤러리에 대 한 페더레이션 지원을 통해 이러한 51 새 앱을 추가 했습니다. 

[Cisco AnyConnect](../saas-apps/cisco-anyconnect.md), [Zoho One 중국](../saas-apps/zoho-one-china-tutorial.md), [PlusPlus](https://test.plusplus.app/auth/login/azuread-outlook/), [Profit.co SAML 앱](../saas-apps/profitco-saml-app-tutorial.md), [IPoint Service Provider](../saas-apps/ipoint-service-provider-tutorial.md), [contexxt.ai 구에](https://contexxt-sphere.com/login), [지혜가 By Invictus](../saas-apps/wisdom-by-invictus-tutorial.md), [플레어 DIGITAL Signage](https://spark-dev.pixelnebula.com/login), Logz.io [-Cloud 관찰성 for 엔지니어](../saas-apps/logzio-cloud-observability-for-engineers-tutorial.md), [SpectrumU](../saas-apps/spectrumu-tutorial.md), [BizzContact](https://bizzcontact.app/), [Elqano SSO](../saas-apps/elqano-sso-tutorial.md), [MarketSignShare](http://www.signshare.com/), [COMPAS Learning Suite](../saas-apps/crossknowledge-learning-suite-tutorial.md), [netvision compas](../saas-apps/netvision-compas-tutorial.md), [FCM HUB](../saas-apps/fcm-hub-tutorial.md), [리브 A/S byggeweb Mobile](https://apps.apple.com/us/app/docia/id529058757), [GoLinks](../saas-apps/golinks-tutorial.md), [Datadog, Zscaler](../saas-apps/datadog-tutorial.md) [B2B 사용자 포털](../saas-apps/zscaler-b2b-user-portal-tutorial.md), [리프트](../saas-apps/lift-tutorial.md), [Planview Enterprise One](../saas-apps/planview-enterprise-one-tutorial.md), [WatchTeams, 별표](https://www.devfinition.com/), [기술 워크플로](../saas-apps/skills-workflow-tutorial.md), [노드](https://admin.nodeinsight.com/AADLogin.aspx)정보, [IP 플랫폼](../saas-apps/ip-platform-tutorial.md), [INVISION](../saas-apps/invision-tutorial.md), [Pipedrive](../saas-apps/pipedrive-tutorial.md), [전시 워크숍](https://app.showcaseworkshop.com/), [Greenlight Integration Platform](../saas-apps/greenlight-integration-platform-tutorial.md), [Greenlight 규격 액세스 관리](../saas-apps/greenlight-compliant-access-management-tutorial.md), [Grok Learning](../saas-apps/grok-learning-tutorial.md), [Miradore Online](https://login.online.miradore.com/), [Khoros 주의](../saas-apps/khoros-care-tutorial.md), [askTruNarrative](../saas-apps/askyourteam-tutorial.md) [, Smartwaiver,](../saas-apps/trunarrative-tutorial.md) [Bizagi](https://www.smartwaiver.com/m/user/sw_login.php?wms_login), [insuiteX Studio for Digital Process Automation](../saas-apps/bizagi-studio-for-digital-process-automation-tutorial.md), [sybo](https://www.insuite.jp/), [Britive](https://www.systexsoftware.com.tw/), [WhosOffice](../saas-apps/britive-tutorial.md) [, Kollective](../saas-apps/whosoffice-tutorial.md), [E-일](../saas-apps/e-days-tutorial.md), [Witivio SDN](https://portal.kollective.app/login), [Playvox](https://app.witivio.com/), [한쪽](https://my.playvox.com/login), [Korn 카페 360](../saas-apps/korn-ferry-360-tutorial.md), [캠퍼스 catch 지점](../saas-apps/campus-cafe-tutorial.md) [, Code42](../saas-apps/catchpoint-tutorial.md), [](../saas-apps/code42-tutorial.md) [](https://demo.asterapp.io/login)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="azure-ad-b2b-collaboration-available-in-azure-government-tenants"></a>Azure Government 테 넌 트에서 사용할 수 있는 Azure AD B2B 공동 작업

**유형:** 새로운 기능  
**서비스 범주:** B2B  
**제품 기능:** B2B/B2C
 
이제 Azure AD B2B 공동 작업 기능을 일부 Azure Government 테 넌 트 간에 사용할 수 있습니다.  테 넌 트가 이러한 기능을 사용할 수 있는지 확인 하려면 [AZURE 미국 정부 테 넌 트에서 B2B 공동 작업을 사용할 수 있는지 어떻게 알 수 있나요?](../external-identities/current-limitations.md#how-can-i-tell-if-b2b-collaboration-is-available-in-my-azure-us-government-tenant)를 참조 하세요.

---

### <a name="azure-monitor-integration-for-azure-logs-is-now-available-in-azure-government"></a>이제 Azure Government에서 Azure 로그에 대 한 Azure Monitor 통합을 사용할 수 있습니다.

**유형:** 새로운 기능  
**서비스 범주:** 보고  
**제품 기능:** 모니터링 및 보고
 
이제 Azure Government에서 Azure AD 로그와 Azure Monitor 통합을 사용할 수 있습니다. Azure AD 로그 (감사 및 로그인 로그)를 저장소 계정, 이벤트 허브 및 Log Analytics로 라우팅할 수 있습니다. Azure AD 시나리오에 대 한 [보고 및 모니터링에 대 한](../reports-monitoring/plan-monitoring-and-reporting.md) [자세한 설명서](../reports-monitoring/concept-activity-logs-azure-monitor.md) 및 배포 계획을 확인 하세요.

---

### <a name="identity-protection-refresh-in-azure-government"></a>Azure Government에서 id 보호 새로 고침

**유형:** 새로운 기능  
**서비스 범주:** Id 보호  
**제품 기능:** Id 보안 & 보호

이제 [](../identity-protection/overview-identity-protection.md)   [Microsoft Azure Government 포털](https://portal.azure.us/)에서 새로 고친 Azure AD ID 보호 환경을 출시 했습니다. 자세한 내용은 [발표 블로그 게시물](https://techcommunity.microsoft.com/t5/public-sector-blog/identity-protection-refresh-in-microsoft-azure-government/ba-p/1223667)을 참조 하세요.

---

### <a name="disaster-recovery-download-and-store-your-provisioning-configuration"></a>재해 복구: 프로 비전 구성을 다운로드 하 고 저장 합니다.

**유형:** 새로운 기능  
**서비스 범주:** 앱 프로비전  
**제품 기능:** Id 수명 주기 관리
 
Azure AD 프로 비전 서비스는 다양 한 구성 기능 집합을 제공 합니다. 고객은 나중에 참조 하거나 알려진 올바른 버전으로 롤백할 수 있도록 구성을 저장할 수 있어야 합니다. 프로 비전 구성을 JSON 파일로 다운로드 하 고 필요할 때 업로드 하는 기능을 추가 했습니다. [자세히 알아봅니다](../app-provisioning/export-import-provisioning-configuration.md).

---
 
### <a name="sspr-self-service-password-reset-now-requires-two-gates-for-admins-in-microsoft-azure-operated-by-21vianet-azure-china-21vianet"></a>SSPR (셀프 서비스 암호 재설정)은 이제 21Vianet에서 운영 하는 Microsoft Azure의 관리자를 위한 두 개의 게이트 (Azure 중국 21Vianet)가 필요 합니다. 

**유형:** 변경된 기능  
**서비스 범주:** 암호 재설정 Self-Service  
**제품 기능:** Id 보안 & 보호
 
이전에는 21Vianet (Azure 중국 21Vianet)에서 운영 하는 Microsoft Azure에서 SSPR (셀프 서비스 암호 재설정)를 사용 하 여 자신의 암호를 재설정 하는 관리자는 본인의 id를 증명 하기 위해 하나의 "게이트" (챌린지)만 필요 했습니다. 공용 및 기타 국가에서 관리자는 일반적으로 SSPR를 사용 하는 경우 두 개의 게이트를 사용 하 여 id를 증명 해야 합니다. 그러나 Azure 중국 21Vianet에서 SMS 또는 전화 통화를 지원 하지 않았기 때문에 관리자가 한 게이트 암호 재설정을 수행할 수 있습니다.

Azure 중국 21Vianet과 공용 클라우드 간에 SSPR 기능 패리티를 만들고 있습니다. 앞으로 관리자는 SSPR를 사용할 때 두 개의 게이트를 사용 해야 합니다. SMS, 전화 통화 및 인증자 앱 알림 및 코드가 지원 됩니다. [자세히 알아봅니다](../authentication/concept-sspr-policy.md#administrator-reset-policy-differences).

---

### <a name="password-length-is-limited-to-256-characters"></a>암호 길이는 256 자로 제한 됩니다.

**유형:** 변경된 기능  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증
 
Azure AD 서비스의 안정성을 보장 하기 위해 이제 사용자 암호의 길이는 256 자로 제한 됩니다. 이 보다 긴 암호를 사용 하는 사용자는 관리자에 게 문의 하거나 셀프 서비스 암호 재설정 기능을 사용 하 여 후속 로그인 시 암호를 변경 하 라는 메시지가 표시 됩니다.

이 변경 내용은 오전 10 월 13 2020 일 오전 10 시 (18:00 UTC)에 사용 하도록 설정 되었으며 오류는 AADSTS 50052, InvalidPasswordExceedsMaxLength입니다. 자세한 내용은 [주요 변경 공지](../develop/reference-breaking-changes.md#user-passwords-will-be-restricted-to-256-characters) 를 참조 하세요.

---

### <a name="azure-ad-sign-in-logs-are-now-available-for-all-free-tenants-through-the-azure-portal"></a>이제 Azure Portal를 통해 Azure AD 로그인 로그를 모든 사용 가능한 테 넌 트에 사용할 수 있습니다.

**유형:** 변경된 기능  
**서비스 범주:** 보고  
**제품 기능:** 모니터링 및 보고
 
지금부터 무료 테 넌 트가 있는 고객은 최대 7 일 동안 [Azure Portal에서 AZURE AD 로그인 로그](../reports-monitoring/concept-sign-ins.md) 에 액세스할 수 있습니다. 이전에는 Azure Active Directory Premium 라이선스를 사용 하는 고객 에게만 로그인 로그를 사용할 수 있었습니다. 이러한 변경을 통해 모든 테 넌 트는 포털을 통해 이러한 로그에 액세스할 수 있습니다.

> [!NOTE]
> 고객은 Microsoft Graph API 및 Azure Monitor를 통해 로그인 로그에 액세스 하기 위한 프리미엄 라이선스 (Azure Active Directory Premium P1 또는 P2)도 필요 합니다.

---

### <a name="deprecation-of-directory-wide-groups-option-from-groups-general-settings-on-azure-portal"></a>그룹의 디렉터리 전체 그룹 옵션 사용 중단 Azure Portal의 일반 설정

**유형:** 사용되지 않음  
**서비스 범주:** 그룹 관리  
**제품 기능:** 협업

고객이 자신의 요구에 가장 적합 한 디렉터리 전체 그룹을 만들 수 있는 보다 유연한 방법을 제공 하기 위해 Azure Portal의 **그룹** 일반 설정에서 동적 그룹 설명서에 대 한 링크를 사용 하 여 **디렉터리 전체 그룹** 옵션을 대체 했습니다  >   [](../enterprise-users/groups-dynamic-membership.md). 관리자가 게스트 사용자를 포함 하거나 제외 하는 모든 사용자 그룹을 만들 수 있도록 더 많은 지침을 포함 하도록 설명서를 개선 했습니다.

---

## <a name="february-2020"></a>2020년 2월

### <a name="upcoming-changes-to-custom-controls"></a>사용자 지정 컨트롤의 예정 된 변경 내용

**유형:** 변경 계획  
**서비스 범주:** MFA  
**제품 기능:** Id 보안 & 보호
 
현재 사용자 지정 컨트롤 미리 보기를 파트너 제공 인증 기능이 Azure Active Directory 관리자 및 최종 사용자 환경에서 원활 하 게 작동 하도록 허용 하는 방법으로 바꿀 계획입니다. 현재 파트너 MFA 솔루션에는 다음과 같은 제한 사항이 있습니다. 암호를 입력 한 후에만 작동 합니다. 다른 주요 시나리오에서의 단계별 인증에 대 한 MFA 역할을 하지 않습니다. 최종 사용자 또는 관리 자격 증명 관리 기능과 통합 되지 않습니다. 새 구현에서는 파트너 제공 인증 요인이 등록, 사용, MFA 클레임, 인증 단계 인증, 보고, 로깅 등의 주요 시나리오에 대 한 기본 제공 요소와 함께 작동할 수 있습니다. 

사용자 지정 컨트롤은 일반 공급에 도달할 때까지 새 디자인과 함께 미리 보기에서 계속 지원 됩니다. 이 시점에서 고객에 게 새 설계로 마이그레이션할 수 있는 시간을 제공 합니다. 현재 방법의 제한 사항 때문에 새로운 디자인을 사용할 수 있을 때까지 새 공급자를 등록 하지 않습니다. Microsoft는 고객과 공급자와 긴밀 하 게 협력 하 고 있으며,이에 따라 일정에 따라 일정을 전달 합니다. [자세히 알아봅니다](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/upcoming-changes-to-custom-controls/ba-p/1144696#).

---

### <a name="identity-secure-score---mfa-improvement-action-updates"></a>Id 보안 점수-MFA 개선 작업 업데이트

**유형:** 변경 계획  
**서비스 범주:** MFA  
**제품 기능:** Id 보안 & 보호
 
비즈니스에 사용 되는 정책을 적용 하는 동시에 비즈니스의 보안을 보장 하기 위한 비즈니스 요구 사항을 반영 하기 위해 Microsoft 보안 점수는 MFA (multi-factor authentication) 중심의 세 가지 개선 작업을 제거 하 고 두 가지를 추가 하는 것입니다.

다음 개선 작업이 제거 됩니다.

- MFA에 대 한 모든 사용자 등록
- 모든 사용자용 MFA 필요
- Azure AD 권한 있는 역할에 대 한 MFA 필요

다음 개선 작업이 추가 됩니다.

- 모든 사용자가 보안 액세스를 위해 MFA를 완료할 수 있는지 확인
- 관리 역할에 대 한 MFA 필요

이러한 새로운 향상 된 작업을 수행 하려면 디렉터리에서 MFA 용 사용자 또는 관리자를 등록 하 고 조직의 요구에 맞는 올바른 정책 집합을 설정 해야 합니다. 주요 목표는 모든 사용자와 관리자가 여러 요소나 위험 기반 id 확인 프롬프트를 사용 하 여 인증할 수 있도록 하는 동시에 유연성을 유지 하는 것입니다. Microsoft에서 사용자에 게 MFA를 시도 하는 시기를 결정 하거나 범위가 지정 된 결정을 적용 하는 여러 정책을 보유 하는 경우를 결정 하는 보안 기본값 설정의 형식을 사용할 수 있습니다. 이러한 향상 작업 업데이트의 일환으로 기준선 보호 정책은 더 이상 점수 계산에 포함 되지 않습니다. [Microsoft 보안 점수에서 제공 되는 사항에 대해 자세히](/microsoft-365/security/mtp/microsoft-secure-score-whats-coming)알아보세요.

---

### <a name="azure-ad-domain-services-sku-selection"></a>SKU 선택 Azure AD Domain Services

**유형:** 새로운 기능  
**서비스 범주:** Azure AD Domain Services  
**제품 기능:** Azure AD Domain Services
 
고객이 해당 인스턴스에 대 한 성능 수준을 더 유연 하 게 선택 하는 것을 Azure AD Domain Services 하는 데 필요한 피드백을 받았습니다. 2020 년 2 월 1 일부 터 동적 모델 (Azure AD가 개체 수를 기반으로 성능 및 가격 책정 계층을 결정)을 자체 선택 모델에 대해 전환 했습니다. 이제 고객은 환경에 맞는 성능 계층을 선택할 수 있습니다. 이러한 변경으로 인해 리소스 포리스트와 같은 새로운 시나리오와 매일 백업 같은 프리미엄 기능을 사용할 수도 있습니다. 이제 모든 Sku에 대 한 개체 수에 제한이 없지만 각 계층에 대 한 개체 수 제안을 계속 제공 합니다.

**즉각적인 고객 조치가 필요 하지 않습니다.** 기존 고객의 경우 2020 년 2 월 1 일에 사용 되 던 동적 계층은 새 기본 계층을 결정 합니다. 이러한 변경의 결과로 가격이 나 성능에 영향을 주지 않습니다. 앞으로 Azure AD DS 고객은 디렉터리 크기 및 워크 로드 특성이 변경 됨에 따라 성능 요구 사항을 평가 해야 합니다. 서비스 계층 간을 전환 하면 가동 중지 시간이 발생 하지 않으며, 해당 디렉터리의 증가에 따라 더 이상 고객이 새 계층으로 이동 하지 않습니다. 또한 가격은 늘어나지만 새로운 가격은 현재 청구 모델에 맞게 조정 됩니다. 자세한 내용은 [Azure AD DS sku 설명서](../../active-directory-domain-services/administration-concepts.md#azure-ad-ds-skus) 및 [Azure AD Domain Services 가격 책정 페이지](https://azure.microsoft.com/pricing/details/active-directory-ds/)를 참조 하세요.

---
 
### <a name="new-federated-apps-available-in-azure-ad-app-gallery---february-2020"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱-2 월 2020

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
2 월 2020에 앱 갤러리에 대 한 페더레이션 지원과 함께 이러한 31 개의 새 앱을 추가 했습니다. 

[](../saas-apps/iamip-patent-platform-tutorial.md)ABa [-온라인 포털](../saas-apps/in-case-of-crisis-online-portal-tutorial.md), [bic 클라우드 디자인](../saas-apps/bic-cloud-design-tutorial.md), [Beekeeper azure AD Data Connector](../saas-apps/beekeeper-azure-ad-data-connector-tutorial.md)의 경우, [Barracuda 메일 보안 서비스](https://ess.barracudanetworks.com/sso/azure), [보고](https://myaba.co.uk/client-access/signin/auth/msad), [azure에 대 한](../saas-apps/ns1-sso-azure-tutorial.md) [환경 클라우드](../saas-apps/experience-cloud-tutorial.md) [Korn 한쪽 평가](https://www.kornferry.com/solutions/kf-digital/kf-assess), [Verkada Command](../saas-apps/verkada-command-tutorial.md), [Splashtop](../saas-apps/splashtop-tutorial.md), [syxsense](../saas-apps/syxsense-tutorial.md), [eab 탐색](../saas-apps/eab-navigate-tutorial.md), [새 유물 (제한 된 릴리스)](../saas-apps/new-relic-limited-release-tutorial.md), [Thulium](https://admin.thulium.com/login/instance), [티켓 관리자](../saas-apps/ticketmanager-tutorial.md), [팀을 위한 템플릿 선택기](https://links.officeatwork.com/templatechooser-download-teams), [Beesy](https://www.beesy.me/index.php/site/login), [의료 지원 시스템](../saas-apps/health-support-system-tutorial.md), [MURAL](https://app.mural.co/signup), [Hive](../saas-apps/hive-tutorial.md), [LavaDo](https://appsource.microsoft.com/product/web-apps/lavaloon.lavado_standard?tab=Overview), [Wakelet](https://wakelet.com/login), Firmex [vdr](../saas-apps/firmex-vdr-tutorial.md), [교사와 학교](https://www.thinglink.com/), [coda](../saas-apps/coda-tutorial.md), [ThingLink](https://nearpod.com/signup/?oc=Microsoft&utm_campaign=Microsoft&utm_medium=site&utm_source=product), [wedo](../saas-apps/wedo-tutorial.md) [, NearpodApp, InvitePeople](https://invitepeople.com/login) [Desk-문서 Galaxy](../saas-apps/reprints-desk-article-galaxy-tutorial.md), [TeamViewer](../saas-apps/teamviewer-tutorial.md)

 
앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---
 
### <a name="new-provisioning-connectors-in-the-azure-ad-application-gallery---february-2020"></a>Azure AD 응용 프로그램 갤러리의 새로운 프로 비전 커넥터-2 월 2020

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

- [Mixpanel](../saas-apps/mixpanel-provisioning-tutorial.md)
- [TeamViewer](../saas-apps/teamviewer-provisioning-tutorial.md)
- [Azure Databricks](/azure/databricks/administration-guide/users-groups/scim/aad)
- [PureCloud by Genesys](../saas-apps/purecloud-by-genesys-provisioning-tutorial.md)
- [Zapier](../saas-apps/zapier-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---
 
### <a name="azure-ad-support-for-fido2-security-keys-in-hybrid-environments"></a>하이브리드 환경에서 FIDO2 보안 키에 대 한 Azure AD 지원

**유형:** 새로운 기능  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증
 
하이브리드 환경에서 FIDO2 보안 키에 대 한 Azure AD 지원의 공개 미리 보기를 발표 하 고 있습니다. 사용자는 이제 FIDO2 보안 키를 사용 하 여 하이브리드 Azure AD에 가입 된 Windows 10 장치에 로그인 하 고 온-프레미스 및 클라우드 리소스에 원활 하 게 로그온 할 수 있습니다. 하이브리드 환경에 대 한 지원은 Azure AD 조인 장치에서 FIDO2 지원을 위한 공개 미리 보기를 처음 시작 했기 때문에 암호 없는 고객 으로부터 가장 많이 요청 되는 기능입니다. 생체 인식 및 공개/개인 키 암호화와 같은 고급 기술을 사용 하 여 암호 없는 인증을 사용 하면 안전 하 게 편리 하 고 편리 하 게 사용할 수가 제공 됩니다. 이 공개 미리 보기에서는 이제 FIDO2 보안 키와 같은 최신 인증을 사용 하 여 기존 Active Directory 리소스에 액세스할 수 있습니다. 자세한 내용은 [온-프레미스 리소스](../authentication/howto-authentication-passwordless-security-key-on-premises.md)에 대 한 SSO로 이동 합니다. 

시작 하려면 단계별 지침은 [테 넌 트에 대해 FIDO2 보안 키 사용](../authentication/howto-authentication-passwordless-security-key.md) 을 참조 하세요. 

---
 
### <a name="the-new-my-account-experience-is-now-generally-available"></a>새 내 계정 환경이 이제 일반 공급 됩니다.

**유형:** 변경된 기능  
**서비스 범주:** 내 프로필/계정  
**제품 기능:** 최종 사용자 환경
 
모든 최종 사용자 계정 관리 요구 사항에 대 한 한 가지 중지 쇼핑 계정이 이제 일반 공급 됩니다. 최종 사용자는 URL 또는 새 내 앱 환경의 헤더를 통해이 새 사이트에 액세스할 수 있습니다. [내 계정 포털 개요](../user-help/my-account-portal-overview.md)에서 새로운 환경을 제공 하는 모든 셀프 서비스 기능에 대해 자세히 알아보세요.

---
 
### <a name="my-account-site-url-updating-to-myaccountmicrosoftcom"></a>Myaccount.microsoft.com로 업데이트 하는 내 계정 사이트 URL

**유형:** 변경된 기능  
**서비스 범주:** 내 프로필/계정  
**제품 기능:** 최종 사용자 환경
 
새 내 계정 최종 사용자 환경에서는 다음 달에 해당 URL을로 업데이트 합니다 `https://myaccount.microsoft.com` . [내 계정 포털 도움말](../user-help/my-account-portal-overview.md)에서 최종 사용자에 게 제공 하는 모든 계정 셀프 서비스 기능 및 환경에 대 한 자세한 정보를 알아보세요.

---

## <a name="january-2020"></a>2020년 1월
 
### <a name="the-new-my-apps-portal-is-now-generally-available"></a>새 내 앱 포털이 이제 일반 공급 됩니다.

**유형:** 변경 계획  
**서비스 범주:** 내 앱  
**제품 기능:** 최종 사용자 환경
 
이제 일반 공급 되는 새 내 앱 포털로 조직을 업그레이드 하세요. [내 앱 포털에서 컬렉션 만들기](../manage-apps/access-panel-collections.md)의 새 포털 및 컬렉션에 대 한 자세한 내용을 확인 하세요.

---
 
### <a name="workspaces-in-azure-ad-have-been-renamed-to-collections"></a>Azure AD의 작업 영역 이름이 컬렉션으로 바뀌었습니다.

**유형:** 변경된 기능  
**서비스 범주:** 내 앱   
**제품 기능:** 최종 사용자 환경
 
관리자가 사용자의 앱을 구성 하도록 구성할 수 있는 작업 영역은 이제 컬렉션 이라고 합니다. [내 앱 포털에서 컬렉션 만들기](../manage-apps/access-panel-collections.md)에서 구성 하는 방법에 대 한 자세한 정보를 찾습니다.

---
 
### <a name="azure-ad-b2c-phone-sign-up-and-sign-in-using-custom-policy-public-preview"></a>사용자 지정 정책을 사용 하 여 전화 등록 및 로그인 Azure AD B2C (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** B2C - 소비자 ID 관리  
**제품 기능:** B2B/B2C
 
전화 번호 등록 및 로그인을 통해 개발자와 기업은 고객이 SMS를 통해 사용자의 전화 번호로 전송 된 일회용 암호를 사용 하 여 등록 하 고 로그인 할 수 있습니다. 또한이 기능을 통해 고객은 휴대폰에 대 한 액세스 권한을 상실 한 경우 전화 번호를 변경할 수 있습니다. 사용자 지정 정책 및 전화 등록 및 로그인 기능을 통해 개발자와 기업은 페이지 사용자 지정을 통해 브랜드를 통신할 수 있습니다. [Azure AD B2C에서 사용자 지정 정책을 사용 하 여 전화 등록 및 로그인을 설정](../../active-directory-b2c/phone-authentication.md)하는 방법을 알아봅니다.
 
---
 
### <a name="new-provisioning-connectors-in-the-azure-ad-application-gallery---january-2020"></a>Azure AD 응용 프로그램 갤러리의 새로운 프로 비전 커넥터-1 월 2020

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

- [Promapp]( ../saas-apps/promapp-provisioning-tutorial.md)
- [Zscaler Private Access](../saas-apps/zscaler-private-access-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---
 
### <a name="new-federated-apps-available-in-azure-ad-app-gallery---january-2020"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱-2020 년 1 월

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합
 
2020 년 1 월에 앱 갤러리에 대 한 페더레이션 지원을 통해 이러한 33 새 앱을 추가 했습니다. 

[JOSA](../saas-apps/josa-tutorial.md), [Fastly Edge Cloud](../saas-apps/fastly-edge-cloud-tutorial.md), [terraform Enterprise](../saas-apps/terraform-enterprise-tutorial.md), [Spintr SSO](../saas-apps/spintr-sso-tutorial.md), [abibot Netlogistik](https://azuremarketplace.microsoft.com/marketplace/apps/aad.abibotnetlogistik), [SkyKick](https://login.skykick.com/login?state=g6Fo2SBTd3M5Q0xBT0JMd3luS2JUTGlYN3pYTE1remJQZnR1c6N0aWTZIDhCSkwzYVQxX2ZMZjNUaWxNUHhCSXg2OHJzbllTcmYto2NpZNkgM0h6czk3ZlF6aFNJV1VNVWQzMmpHeFFDbDRIMkx5VEc&client=3Hzs97fQzhSIWUMUd32jGxQCl4H2LyTG&protocol=oauth2&audience=https://papi.skykick.com&response_type=code&redirect_uri=https://portal.skykick.com/callback&scope=openid%20profile%20offline_access), [Upshotly](../saas-apps/upshotly-tutorial.md), [LeaveBot](https://leavebot.io/#home), [Datacamp](../saas-apps/datacamp-tutorial.md), [TripActions](../saas-apps/tripactions-tutorial.md), [SMARTWORK](https://www.intumit.com/english/SmartWork.html), [Dotcom-Monitor](../saas-apps/dotcom-monitor-tutorial.md), [SSOGEN-Oracle E-비즈니스 제품군-EBS에 대 한 Azure AD SSO 게이트웨이 PeopleSoft 및 JDE](../saas-apps/ssogen-tutorial.md), [호스 티 드 MYCIRQA SSO](../saas-apps/hosted-mycirqa-sso-tutorial.md), [Yuhu Property Management Platform](../saas-apps/yuhu-property-management-platform-tutorial.md), [LumApps](https://sites.lumapps.com/login), [Upwork Enterprise](../saas-apps/upwork-enterprise-tutorial.md), [Talentsoft](../saas-apps/talentsoft-tutorial.md), [Microsoft 팀을 위한 smartwork](http://teams.smartdb.jp/login/), [PressPage](../saas-apps/presspage-tutorial.md), [](../saas-apps/taskize-connect-tutorial.md) [ContractSafe Saml2 SSO](../saas-apps/contractsafe-saml2-sso-tutorial.md), Maxient [upwork Software](../saas-apps/maxient-conduct-manager-software-tutorial.md), [helpshift](../saas-apps/helpshift-tutorial.md), [PortalTalk 365](https://www.portaltalk.com/), [CoreView](https://portal.coreview.com/), [Squelch Cloud Office365 Connector](https://laxmi.squelch.io/login) [,](https://app-staging.pingview.io/)Sandwai [](../saas-apps/printerlogic-saas-tutorial.md) [, EZRentOut, AssetSonar](https://app.sandwai.com/), Akari, [,,](../saas-apps/assetsonar-tutorial.md), [,](../saas-apps/ezrentout-tutorial.md), [Virtual Assistant](https://akari.io/akari-virtual-assistant/)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="two-new-identity-protection-detections"></a>두 개의 새로운 Id 보호 검색

**유형:** 새로운 기능  
**서비스 범주:** Id 보호  
**제품 기능:** Id 보안 & 보호
 
Id 보호에 두 가지 로그인 연결 된 검색 유형을 추가 했습니다. 의심 스러운 수신함 조작 규칙 및 불가능 한 이동입니다. 이러한 오프 라인 검색은 MCAS (Microsoft Cloud App Security)에 의해 검색 되며 Id 보호의 사용자 및 로그인 위험에 영향을 줍니다. 이러한 검색에 대 한 자세한 내용은 [로그인 위험 유형](../identity-protection/concept-identity-protection-risks.md#sign-in-risk)을 참조 하세요.
 
---
 
### <a name="breaking-change-uri-fragments-will-not-be-carried-through-the-login-redirect"></a>주요 변경: URI 조각은 로그인 리디렉션을 통해 전달 되지 않습니다.

**유형:** 변경된 기능  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증
 
2020,에서 시작 하 여 사용자를 로그인 하기 위해 login.microsoftonline.com에 요청을 보내면 서비스는 빈 조각을 요청에 추가 합니다.  이렇게 하면 브라우저에서 요청의 기존 조각을 모두 초기화 하 여 공격에 대 한 클래스를 방지할 수 있습니다. 이 동작에 대 한 종속성이 있는 응용 프로그램이 없습니다. 자세한 내용은 Microsoft id 플랫폼 설명서의 [주요 변경 내용](../develop/reference-breaking-changes.md#february-2020) 을 참조 하세요.

---

## <a name="december-2019"></a>2019년 12월

### <a name="integrate-sap-successfactors-provisioning-into-azure-ad-and-on-premises-ad-public-preview"></a>SAP SuccessFactors 프로 비전을 Azure AD 및 온-프레미스 AD에 통합 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 앱 프로비전  
**제품 기능:** Id 수명 주기 관리

이제 Azure AD에서 SAP SuccessFactors를 신뢰할 수 있는 id 원본으로 통합할 수 있습니다. 이러한 통합을 통해 새 채용 또는 종료와 같은 HR 기반 이벤트를 사용 하 여 Azure AD 계정 프로 비전을 제어 하는 등 종단 간 id 수명 주기를 자동화할 수 있습니다.

Azure AD에 대 한 SAP SuccessFactors 인바운드 프로 비전을 설정 하는 방법에 대 한 자세한 내용은 [Sap SuccessFactors 자동 프로 비전 구성](../saas-apps/sap-successfactors-inbound-provisioning-tutorial.md) 자습서를 참조 하세요.

---

### <a name="support-for-customized-emails-in-azure-ad-b2c-public-preview"></a>Azure AD B2C에서 사용자 지정 된 전자 메일 지원 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** B2C - 소비자 ID 관리  
**제품 기능:** B2B/B2C

이제 사용자가 앱을 사용 하기 위해 등록할 때 Azure AD B2C를 사용 하 여 사용자 지정 된 전자 메일을 만들 수 있습니다. DisplayControls (현재 미리 보기 상태)와 타사 전자 메일 공급자 (예: [SendGrid](https://sendgrid.com/), [SparkPost](https://sparkpost.com/)또는 사용자 지정 REST API)를 사용 하 여 사용자 고유의 전자 메일 템플릿, 주소 및 제목 텍스트 **를 사용할** 수 있을 뿐만 아니라 지역화 및 사용자 지정 OTP (일회용 암호) 설정을 지원할 수 있습니다.

자세한 내용은 [Azure Active Directory B2C에서 사용자 지정 전자 메일 확인](../../active-directory-b2c/custom-email-sendgrid.md)을 참조 하세요.

---

### <a name="replacement-of-baseline-policies-with-security-defaults"></a>보안 기본값으로 기본 정책 바꾸기

**유형:** 변경된 기능  
**서비스 범주:** 기타  
**제품 기능:** ID 보안 및 보호

인증을 위한 기본 보안 모델의 일부로 모든 테 넌 트에서 기존 기준 보호 정책을 제거 하 고 있습니다. 이 제거는 2 월 말에 완료 될 대상입니다. 이러한 기준 보호 정책에 대 한 대체는 보안 기본값입니다. 기준 보호 정책을 사용한 경우 새 보안 기본값 정책 또는 조건부 액세스로 이동 하도록 계획 해야 합니다. 이러한 정책을 사용 하지 않은 경우 수행할 작업은 없습니다.

새 보안 기본값에 대 한 자세한 내용은 [보안 기본값 이란?](./concept-fundamentals-security-defaults.md) 을 참조 하세요. 조건부 액세스 정책에 대 한 자세한 내용은 [일반적인 조건부 액세스 정책](../conditional-access/concept-conditional-access-policy-common.md)을 참조 하세요.

---

## <a name="november-2019"></a>2019년 11월

### <a name="support-for-the-samesite-attribute-and-chrome-80"></a>SameSite 특성 및 크롬 80에 대 한 지원

**유형:** 변경 계획  
**서비스 범주:** 인증 (로그인)  
**제품 기능:** 사용자 인증

쿠키에 대 한 기본 보안 모델의 일부로 Chrome 80 브라우저는 특성 없이 쿠키를 처리 하는 방식을 변경 `SameSite` 합니다. 특성을 지정 하지 않는 모든 쿠키는 `SameSite` 로 설정 된 것 처럼 처리 되며이로 `SameSite=Lax` 인해 Chrome에서 앱이 종속 될 수 있는 특정 도메인 간 쿠키 공유 시나리오를 차단 합니다. 이전 Chrome 동작을 유지 하려면 특성을 사용 하 `SameSite=None` 고 추가 특성을 추가 하 여 `Secure` HTTPS 연결을 통해서만 사이트 간 쿠키에 액세스할 수 있습니다. Chrome은 2020 년 2 월 4 일에이 변경을 완료 하도록 예약 되어 있습니다.

모든 개발자가이 지침을 사용 하 여 앱을 테스트 하는 것이 좋습니다.

- **보안 쿠키 사용** 설정의 기본값을 **예** 로 설정 합니다.

- **SameSite** 특성의 기본값을 **None** 으로 설정 합니다.

- `SameSite` **보안** 의 추가 특성을 추가 합니다.

자세한 내용은 [향후 SameSite 쿠키 변경 ASP.NET 및 ASP.NET Core](https://devblogs.microsoft.com/aspnet/upcoming-samesite-cookie-changes-in-asp-net-and-asp-net-core/) 및 [Chrome 버전 79 이상에서 고객 websites 및 Microsoft 제품 및 서비스에 대 한 잠재적인 중단](https://support.microsoft.com/help/4522904/potential-disruption-to-microsoft-services-in-chrome-beta-version-79)을 참조 하세요.

---

### <a name="new-hotfix-for-microsoft-identity-manager-mim-2016-service-pack-2-sp2"></a>Microsoft Identity Manager (MIM) 2016 서비스 팩 2 (SP2) 용 새 핫픽스

**유형:** 고정  
**서비스 범주:** Microsoft Identity Manager  
**제품 기능:** Id 수명 주기 관리

핫픽스 롤업 패키지 (build 4.6.34.0)는 Microsoft Identity Manager (MIM) 2016 서비스 팩 2 (SP2)에서 사용할 수 있습니다. 이 롤업 패키지는 문제를 해결 하 고 "이 업데이트에 추가 된 문제 해결 및 개선 사항" 섹션에 설명 된 향상 된 기능을 추가 합니다.

핫픽스 패키지를 다운로드 하 고 다운로드 하는 방법에 대 한 자세한 내용은 [Microsoft Identity Manager 2016 서비스 팩 2 (build 4.6.34.0) 업데이트 롤업을 사용 가능](https://support.microsoft.com/help/4512924/microsoft-identity-manager-2016-service-pack-2-build-4-6-34-0-update-r)을 참조 하세요.

---

### <a name="new-ad-fs-app-activity-report-to-help-migrate-apps-to-azure-ad-public-preview"></a>앱을 Azure AD로 마이그레이션하는 데 도움이 되는 새로운 AD FS 앱 활동 보고서 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO

Azure Portal에서 새 Active Directory Federation Services (AD FS) 앱 활동 보고서를 사용 하 여 Azure AD로 마이그레이션할 수 있는 앱을 식별 합니다. 이 보고서는 Azure AD와의 호환성을 위해 모든 AD FS 앱을 평가 하 고, 문제를 확인 하 고, 개별 앱을 마이그레이션하기 위한 준비에 대 한 지침을 제공 합니다.

자세한 내용은 [AD FS 응용 프로그램 작업 보고서를 사용 하 여 응용 프로그램을 AZURE AD로 마이그레이션](../manage-apps/migrate-adfs-application-activity.md)을 참조 하세요.

---

### <a name="new-workflow-for-users-to-request-administrator-consent-public-preview"></a>사용자가 관리자 동의를 요청 하는 새 워크플로 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 액세스 제어

새 관리자 동의 워크플로를 통해 관리자는 관리자 승인이 필요한 앱에 대 한 액세스 권한을 부여할 수 있습니다. 사용자가 앱에 액세스 하려고 하지만 동의를 제공할 수 없는 경우 이제 관리자 승인에 대 한 요청을 보낼 수 있습니다. 요청은 전자 메일을 통해 전송 되 고, Azure Portal에서 액세스할 수 있는 큐에 저장 되며 검토자로 지정 된 모든 관리자에 게 적용 됩니다. 검토자가 보류 중인 요청에 대해 작업을 수행 하면 요청 하는 사용자에 게 작업에 대 한 알림이 표시 됩니다.

자세한 내용은 [관리자 동의 워크플로 구성 (미리 보기)](../manage-apps/configure-admin-consent-workflow.md)을 참조 하세요.

---

### <a name="new-azure-ad-app-registrations-token-configuration-experience-for-managing-optional-claims-public-preview"></a>선택적인 클레임을 관리 하기 위한 새로운 Azure AD 앱 등록 토큰 구성 환경 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 기타  
**제품 기능:** 개발자 환경

이제 Azure Portal의 새 **Azure AD 앱 등록 토큰 구성** 블레이드에서 앱 개발자에 게 앱에 대 한 선택적 클레임의 동적 목록을 표시 합니다. 이 새로운 환경을 통해 Azure AD 앱 마이그레이션을 간소화 하 고 선택적 클레임 잘못 된 구성을 최소화할 수 있습니다.

자세한 내용은 [AZURE AD 앱에 선택적 클레임 제공](../develop/active-directory-optional-claims.md)을 참조 하세요.

---

### <a name="new-two-stage-approval-workflow-in-azure-ad-entitlement-management-public-preview"></a>Azure AD 자격 관리의 새로운 2 단계 승인 워크플로 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 기타  
**제품 기능:** 자격 관리

액세스 패키지에 대 한 사용자의 요청을 승인 하는 두 명의 승인자를 요구할 수 있는 새로운 2 단계 승인 워크플로가 도입 되었습니다. 예를 들어 요청 하는 사용자의 관리자가 먼저 승인 하도록 설정한 다음 리소스 소유자가 승인 하도록 요구할 수도 있습니다. 승인자 중 하나가 승인 되지 않으면 액세스가 허용 되지 않습니다.

자세한 내용은 [AZURE AD 자격 관리에서 액세스 패키지에 대 한 요청 및 승인 설정 변경](../governance/entitlement-management-access-package-request-policy.md)을 참조 하세요.

---

### <a name="updates-to-the-my-apps-page-along-with-new-workspaces-public-preview"></a>새 작업 영역과 함께 내 앱 페이지에 대 한 업데이트 (공개 미리 보기)

**유형:** 새로운 기능  
**서비스 범주:** 내 앱  
**제품 기능:** 타사 통합

이제 조직의 사용자가 새로 고쳐진 내 앱 환경을 보고 액세스 하는 방법을 사용자 지정할 수 있습니다. 이 새로운 환경에는 사용자가 앱을 보다 쉽게 찾고 구성할 수 있도록 하는 새로운 작업 영역 기능도 포함 되어 있습니다.

새 내 앱 환경 및 작업 영역 만들기에 대 한 자세한 내용은 [My apps 포털에서 작업 영역 만들기](../manage-apps/access-panel-collections.md)를 참조 하세요.

---

### <a name="google-social-id-support-for-azure-ad-b2b-collaboration-general-availability"></a>Azure AD B2B 공동 작업을 위한 Google 소셜 ID 지원 (일반 공급)

**유형:** 새로운 기능  
**서비스 범주:** B2B  
**제품 기능:** 사용자 인증

Azure AD에서 Google 소셜 Id (Gmail 계정)를 사용 하는 새로운 지원 기능을 통해 사용자와 파트너에 게 더 간단 하 게 공동 작업을 수행할 수 있습니다. 파트너가 새 Microsoft 특정 계정을 만들고 관리 하는 데 더 이상 필요 하지 않습니다. Microsoft 팀은 이제 모든 클라이언트와 공통 및 테 넌 트 관련 인증 끝점에서 Google 사용자를 완전히 지원 합니다.

자세한 내용은 [B2B 게스트 사용자에 대 한 id 공급자로 Google 추가](../external-identities/google-federation.md)를 참조 하세요.

---

### <a name="microsoft-edge-mobile-support-for-conditional-access-and-single-sign-on-general-availability"></a>조건부 액세스 및 Single Sign-on을 위한 Microsoft Edge 모바일 지원 (일반 공급)

**유형:** 새로운 기능  
**서비스 범주:** 조건부 액세스  
**제품 기능:** Id 보안 & 보호

IOS 및 Android의 Microsoft Edge 용 azure AD는 이제 Azure AD Single Sign-On 및 조건부 액세스를 지원 합니다.

- **SSO (Microsoft Edge Single Sign-On):** 이제 모든 Azure AD 연결 앱에 대 한 기본 클라이언트 (예: Microsoft Outlook 및 Microsoft Edge)에서 Single sign-on을 사용할 수 있습니다.

- **Microsoft Edge 조건부 액세스:** 응용 프로그램 기반 조건부 액세스 정책을 통해 사용자는 Microsoft Edge와 같은 Microsoft Intune 보호 된 브라우저를 사용 해야 합니다.

Microsoft Edge를 사용 하는 조건부 액세스 및 SSO에 대 한 자세한 내용은 [Microsoft Edge Mobile Support For 조건부 액세스 및 Single sign-on을 사용 하 여 일반적으로 사용 가능](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Edge-Mobile-Support-for-Conditional-Access-and-Single/ba-p/988179) 블로그 게시물을 참조 하세요. [앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md) 또는 [장치 기반 조건부 액세스](../conditional-access/require-managed-devices.md)를 사용 하 여 클라이언트 앱을 설정 하는 방법에 대 한 자세한 내용은 [Microsoft Intune 정책으로 보호 된 브라우저를 사용 하 여 웹 액세스 관리](/intune/apps/app-configuration-managed-browser)를 참조 하세요.

---

### <a name="azure-ad-entitlement-management-general-availability"></a>Azure AD 자격 관리 (일반 공급)

**유형:** 새로운 기능  
**서비스 범주:** 기타  
**제품 기능:** 자격 관리

Azure AD 자격 관리는 조직에서 id 및 액세스 수명 주기를 대규모로 관리할 수 있도록 하는 새로운 id 거 버 넌 스 기능입니다. 이 새로운 기능을 통해 그룹, 앱 및 SharePoint Online 사이트에서 액세스 요청 워크플로, 액세스 할당, 검토 및 만료를 자동화할 수 있습니다.

Azure AD 자격 관리를 통해 직원 및 해당 리소스에 액세스 해야 하는 조직 외부 사용자에 대 한 액세스를 보다 효율적으로 관리할 수 있습니다.

자세한 내용은 [AZURE AD 자격 관리 란?](../governance/entitlement-management-overview.md#license-requirements) 을 참조 하세요.

---

### <a name="automate-user-account-provisioning-for-these-newly-supported-saas-apps"></a>새로 지원되는 SaaS 앱에 대한 사용자 계정 프로비저닝 자동화

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합  

다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

[SAP Cloud Platform Identity Authentication Service](../saas-apps/sap-hana-cloud-platform-identity-authentication-tutorial.md), [RingCentral](../saas-apps/ringcentral-provisioning-tutorial.md), [SpaceIQ](../saas-apps/spaceiq-provisioning-tutorial.md), [Miro](../saas-apps/miro-provisioning-tutorial.md), [Cloudgate](../saas-apps/soloinsight-cloudgate-sso-provisioning-tutorial.md), [infor cloudgate](../saas-apps/infor-cloudsuite-provisioning-tutorial.md), [officespace software Software](../saas-apps/officespace-software-provisioning-tutorial.md), [Priority Matrix](../saas-apps/priority-matrix-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---november-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱-11 월 2019

**유형:** 새로운 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** 타사 통합

11 월 2019에 앱 갤러리에 대 한 페더레이션 지원을 포함 하는 새로운 21 개 앱을 추가 했습니다.

어 [표](../saas-apps/airtable-tutorial.md), [Hootsuite](../saas-apps/hootsuite-tutorial.md), [멤버에 대 한 파랑 액세스 (BAM)](../saas-apps/blue-access-for-members-tutorial.md), [bitdea](../saas-apps/bitly-tutorial.md), [Riva](../saas-apps/riva-tutorial.md), [reslife 포털](https://app.reslifecloud.com/hub5_signin/microsoft_azuread/?g=44BBB1F90915236A97502FF4BE2952CB&c=5&uid=0&ht=2&ref=), [NegometrixPortal sso (Single Sign On)](../saas-apps/negometrixportal-tutorial.md), [TeamsChamp](https://login.microsoftonline.com/551f45da-b68e-4498-a7f5-a6e1efaeb41c/adminconsent?client_id=ca9bbfa4-1316-4c0f-a9ee-1248ac27f8ab&redirect_uri=https://admin.teamschamp.com/api/adminconsent&state=6883c143-cb59-42ee-a53a-bdb5faabf279), [Motus](../saas-apps/motus-tutorial.md), [MyAryaka](../saas-apps/myaryaka-tutorial.md), [BlueMail](https://loginself1.bluemail.me/), [beedle](https://teams-web.beedle.co/#/), [visma](../saas-apps/visma-tutorial.md), [onedesk](../saas-apps/onedesk-tutorial.md), [foko Retail](../saas-apps/foko-retail-tutorial.md), [](../saas-apps/claromentis-tutorial.md) [qmarkets 아이디어 & 혁신 관리](../saas-apps/qmarkets-idea-innovation-management-tutorial.md), [net](../saas-apps/netskope-user-authentication-tutorial.md) [](../saas-apps/uniflow-online-tutorial.md) [](../saas-apps/jisc-student-voter-registration-tutorial.md) [](https://portal.e4enable.com/)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-and-improved-azure-ad-application-gallery"></a>새롭고 향상 된 Azure AD 응용 프로그램 갤러리

**유형:** 변경된 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO

Azure Active Directory 테 넌 트에서 프로 비전, Openid connect 연결 및 SAML을 지 원하는 사전 통합 된 앱을 보다 쉽게 찾을 수 있도록 Azure AD 응용 프로그램 갤러리를 업데이트 했습니다.

자세한 내용은 [Azure Active Directory 테 넌 트에 응용 프로그램 추가](../manage-apps/add-application-portal.md)를 참조 하세요.

---

### <a name="increased-app-role-definition-length-limit-from-120-to-240-characters"></a>앱 역할 정의 길이 제한을 120에서 240 자로 늘렸습니다.

**유형:** 변경된 기능  
**서비스 범주:** 엔터프라이즈 앱  
**제품 기능:** SSO

고객 으로부터 일부 앱 및 서비스의 앱 역할 정의 값에 대 한 길이 제한이 120 자에서 너무 짧습니다. 이에 대 한 응답으로 역할 값 정의의 최대 길이를 240 자로 늘립니다.

응용 프로그램 관련 역할 정의를 사용 하는 방법에 대 한 자세한 내용은 [응용 프로그램에 앱 역할 추가 및 토큰에서 수신](../develop/howto-add-app-roles-in-azure-ad-apps.md)을 참조 하세요.

---

## <a name="october-2019"></a>2019년 10월

### <a name="deprecation-of-the-identityriskevent-api-for-azure-ad-identity-protection-risk-detections"></a>Azure Active Directory Identity Protection 위험 검색을 위한 identityRiskEvent API의 사용 중단

**유형:** 변경 계획 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

개발자 피드백에 대한 응답으로, Azure AD Premium P2 구독자는 이제 새 Microsoft Graph용 riskDetection API를 사용하여 Azure Active Directory Identity Protection의 위험 검색 데이터에 대한 복합 쿼리를 수행할 수 있습니다. 기존 [identityRiskEvent](/graph/api/resources/identityriskevent?view=graph-rest-beta) API 베타 버전은 **2020년 1월 10일** 경부터 데이터 반환을 중지할 예정입니다. identityRiskEvent API를 사용하는 조직에서는 새 riskDetection API로 전환해야 합니다.

새 riskDetection API에 대한 자세한 내용은 [위험 검색 API 참조 설명서](/graph/api/resources/riskdetection)에서 확인할 수 있습니다.

---

### <a name="application-proxy-support-for-the-samesite-attribute-and-chrome-80"></a>SameSite 특성 및 Chrome 80에 대한 애플리케이션 프록시 지원

**유형:** 변경 계획 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

Chrome 80 브라우저가 릴리스되기 몇 주 전에, 저희는 애플리케이션 프록시 쿠키가 **SameSite** 특성을 처리하는 방법을 업데이트할 계획입니다. Chrome 80이 릴리스되면 **SameSite** 특성을 지정하지 않는 쿠키는 `SameSite=Lax`로 설정된 것처럼 처리됩니다.

이번 변경으로 인한 부정적 영향을 방지하기 위해, 다음과 같은 방법으로 애플리케이션 프록시 액세스 및 세션 쿠키를 업데이트할 것입니다.

- **보안 쿠키 사용** 의 기본값을 **예** 로 설정합니다.

- **SameSite** 특성의 기본값을 **없음** 으로 설정합니다.

    >[!NOTE]
    > 애플리케이션 프록시 액세스 쿠키는 항상 보안 채널을 통해 단독으로 전송됩니다. 이러한 변경 내용은 세션 쿠키에만 적용됩니다.

애플리케이션 프록시 쿠키 설정에 대한 자세한 내용은 [Azure Active Directory에서 온-프레미스 애플리케이션에 액세스하기 위한 쿠키 설정](../manage-apps/application-proxy-configure-cookie-settings.md)을 참조하세요.

---

### <a name="app-registrations-legacy-and-app-management-in-the-application-registration-portal-appsdevmicrosoftcom-is-no-longer-available"></a>애플리케이션 등록 포털(apps.dev.microsoft.com)에서 앱 등록(레거시) 및 앱 관리를 더 이상 사용할 수 없음

**유형:** 변경 계획 **서비스 범주:** 해당 없음 **제품 기능:** 개발자 환경

Azure AD 계정을 사용하는 사용자는 더 이상 애플리케이션 등록 포털(apps.dev.microsoft.com)을 사용하여 애플리케이션을 등록하고 관리하거나, Azure Portal의 앱 등록(레거시) 환경에서 애플리케이션을 등록하고 관리할 수 없습니다.

새로운 앱 등록 환경에 대한 자세한 내용은 [Azure Portal에서 앱 등록 학습 가이드](../develop/quickstart-register-app.md)를 참조하세요.

---

### <a name="users-are-no-longer-required-to-re-register-during-migration-from-per-user-mfa-to-conditional-access-based-mfa"></a>이제 사용자는 사용자 단위 MFA에서 조건부 액세스 기반 MFA로 마이그레이션할 때 다시 등록할 필요가 없습니다.

**유형:** 수정된 **서비스 범주:** MFA **제품 기능:** ID 보안 및 보호

사용자별 MFA(Multi-Factor Authentication)가 해제되었다가 조건부 액세스 정책을 통해 MFA가 다시 설정되면 사용자가 다시 등록해야 하는 알려진 문제를 수정했습니다.

사용자가 다시 등록하게 하려면 Azure AD 포털의 사용자 인증 방법에서 **MFA 재등록 필요** 옵션을 선택하면 됩니다. 사용자별 MFA에서 조건부 액세스 기반 MFA로 사용자를 마이그레이션하는 방법에 대한 자세한 내용은 [사용자별 MFA의 사용자를 조건부 액세스 기반 MFA로 변환](../authentication/howto-mfa-getstarted.md#convert-users-from-per-user-mfa-to-conditional-access-based-mfa)을 참조하세요.

---

### <a name="new-capabilities-to-transform-and-send-claims-in-your-saml-token"></a>SAML 토큰에서 클레임을 변환하고 전송하는 새 기능

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

SAML 토큰에서 클레임을 사용자 지정하고 전송하는 데 도움이 되는 기능이 추가되었습니다. 이러한 새 기능은 다음과 같습니다.

- 클레임에서 전송하는 값을 수정할 수 있는 추가 클레임 변환 함수

- 단일 클레임에 여러 변환을 적용하는 기능

- 사용자 유형 및 사용자가 속한 그룹을 기준으로 클레임 소스를 지정하는 기능

이러한 새 기능에 대한 자세한 내용과 사용 방법은 [엔터프라이즈 애플리케이션에 대한 SAML 토큰에 발급된 클레임 사용자 지정](../develop/active-directory-saml-claims-customization.md)을 참조하세요.

---

### <a name="new-my-sign-ins-page-for-end-users-in-azure-ad"></a>Azure AD의 최종 사용자에 대한 새로운 내 로그인 페이지

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 모니터링 및 보고

조직의 사용자가 자신의 최근 로그인 기록을 살펴보면서 비정상적인 활동을 확인할 수 있는 **내 로그인** 페이지(https://mysignins.microsoft.com) )가 새로 추가되었습니다. 이 새 페이지를 통해 사용자는 다음 정보를 볼 수 있습니다.

- 누군가가 내 암호를 추측하려고 시도하는지 여부

- 공격자가 내 계정에 성공적으로 로그인했는지 여부 및 위치

- 공격자가 액세스하려고 시도한 앱

자세한 내용은 [Users can now check their sign-in history for unusual activity(이제 사용자가 자신의 로그인 기록을 검토하여 비정상적인 활동을 확인할 수 있음)](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Users-can-now-check-their-sign-in-history-for-unusual-activity/ba-p/916066) 블로그를 참조하세요.

---

### <a name="migration-of-azure-ad-domain-services-azure-ad-ds-from-classic-to-azure-resource-manager-virtual-networks"></a>클래식에서 Azure Resource Manager 가상 네트워크로 Azure AD DS(Azure AD Domain Services) 마이그레이션

**유형:** 새 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

클래식 가상 네트워크에 묶여 있는 고객에게 좋은 소식이 있습니다. 이제 클래식 가상 네트워크에서 기존 Resource Manager 가상 네트워크로 마이그레이션을 1회 수행할 수 있습니다. Resource Manager 가상 네트워크로 이동한 후에는 세분화된 암호 정책, 이메일 알림, 감사 로그와 같은 추가 기능 및 업그레이드된 기능을 활용할 수 있습니다.

자세한 내용은 [미리 보기 - 클래식 가상 네트워크 모델에서 Resource Manager로 Azure AD Domain Services 마이그레이션](../../active-directory-domain-services/migrate-from-classic-vnet.md)을 참조하세요.

---

### <a name="updates-to-the-azure-ad-b2c-page-contract-layout"></a>Azure AD B2C 페이지 계약 레이아웃 업데이트

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

Azure AD B2C의 페이지 계약 버전 1.2.0에 새로운 변경 사항이 도입되었습니다. 이제 이 업데이트된 버전에서는 요소의 로드 순서를 제어할 수 있으며, 이는 스타일 시트(CSS)가 로드될 때 발생하는 깜박임을 멈추는 데 도움이 될 수도 있습니다.

페이지 계약의 변경 내용 전체 목록은 [버전 변경 로그](../../active-directory-b2c/page-layout.md#other-pages-providerselection-claimsconsent-unifiedssd)를 참조하세요.

---

### <a name="update-to-the-my-apps-page-along-with-new-workspaces-public-preview"></a>새 작업 영역과 함께 내 앱 페이지 업데이트(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** Access Control

이제 새 작업 영역 기능을 사용하여 앱을 보다 쉽게 찾을 수 있도록 만들어 주는 것을 포함하여 조직의 사용자가 완전히 새로운 [내 앱] 환경을 살펴보고 액세스하는 방법을 사용자 지정할 수 있습니다. 새 작업 영역 기능은 조직의 사용자가 이미 액세스 권한을 갖고 있는 앱의 필터 역할을 합니다.

새로운 내 앱 환경을 롤아웃하고 작업 영역을 만드는 것과 관련된 자세한 내용은 [내 앱(미리 보기) 포털에서 작업 영역 만들기](../manage-apps/access-panel-collections.md)를 참조하세요.

---

### <a name="support-for-the-monthly-active-user-based-billing-model-general-availability"></a>월간 활성 사용자 기반 대금 청구 모델에 대한 지원(일반 공급)

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 Azure AD B2C는 MAU(월간 활성 사용자) 대금 청구를 지원합니다. MAU 대금 청구는 한 달 동안 인증 활동이 있는 고유 사용자 수를 기준으로 합니다. 기존 고객은 언제든지 이 새로운 대금 청구 방법으로 전환할 수 있습니다.

2019년 11월 1일부터 모든 신규 고객에게 자동으로 이 방법을 사용하여 대금이 청구됩니다. 이 대금 청구 방법은 비용 혜택과 사전 계획이라는 장점이 있습니다.

자세한 내용은 [월간 활성 사용자 모델로 업그레이드](../../active-directory-b2c/billing.md#switch-to-mau-billing-pre-november-2019-azure-ad-b2c-tenants)를 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---october-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 10월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 10월에 페더레이션이 지원되는 다음과 같은 신규 앱 35개가 앱 갤러리에 추가되었습니다.

[In Case of Crisis – Mobile](../saas-apps/in-case-of-crisis-mobile-tutorial.md), [Juno Journey](../saas-apps/juno-journey-tutorial.md), [ExponentHR](../saas-apps/exponenthr-tutorial.md), [Tact](https://tact.ai/assistant/), [OpusCapita Cash Management](https://appsource.microsoft.com/product/web-apps/opuscapitagroupoy-1036255.opuscapita-cm), [Salestim](https://www.salestim.com/), [Learnster](../saas-apps/learnster-tutorial.md), [Dynatrace](../saas-apps/dynatrace-tutorial.md), [HunchBuzz](https://login.hunchbuzz.com/integrations/azure/process), [Freshworks](../saas-apps/freshworks-tutorial.md), [eCornell](../saas-apps/ecornell-tutorial.md), [ShipHazmat](../saas-apps/shiphazmat-tutorial.md), [Netskope Cloud Security](../saas-apps/netskope-cloud-security-tutorial.md), [Contentful](../saas-apps/contentful-tutorial.md), [Bindtuning](https://bindtuning.com/login), [HireVue Coordinate – Europe](https://www.hirevue.com/), [HireVue Coordinate - USOnly](https://www.hirevue.com/), [HireVue Coordinate - US](https://www.hirevue.com/), [WittyParrot Knowledge Box](https://wittyapi.wittyparrot.com/wittyparrot/api/provision/trail/signup), [Cloudmore](../saas-apps/cloudmore-tutorial.md), [Visit.org](../saas-apps/visitorg-tutorial.md), [Cambium Xirrus EasyPass Portal](https://login.xirrus.com/azure-signup), [Paylocity](../saas-apps/paylocity-tutorial.md), [Mail Luck!](../saas-apps/mail-luck-tutorial.md), [Teamie](https://theteamie.com/), [Velocity for Teams](https://velocity.peakup.org/teams/login), [SIGNL4](https://account.signl4.com/manage), [EAB Navigate IMPL](../saas-apps/eab-navigate-impl-tutorial.md), [ScreenMeet](https://console.screenmeet.com/), [Omega Point](https://pi.ompnt.com/), [Speaking Email for Intune(iPhone)](https://speaking.email/FAQ/98/email-access-via-microsoft-intune), [Speaking Email for Office 365 Direct(iPhone/Android)](https://speaking.email/FAQ/126/email-access-via-microsoft-office-365-direct), [ExactCare SSO](../saas-apps/exactcare-sso-tutorial.md), [iHealthHome Care Navigation System](https://ihealthnav.com/account/signin), [Qubie](https://qubie.azurewebsites.net/static/adminTab/authorize.html)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="consolidated-security-menu-item-in-the-azure-ad-portal"></a>Azure AD 포털의 통합 보안 메뉴 항목

**유형:** 변경된 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

이제 새 **보안** 메뉴 항목 및 Azure Portal의 **검색** 모음에서 사용 가능한 모든 Azure AD 보안 기능에 액세스할 수 있습니다. 또한 **보안 - 시작** 이라는 새로운 **보안** 방문 페이지는 공개 문서, 보안 지침 및 배포 가이드에 대한 링크를 제공합니다.

새 **보안** 메뉴에는 다음과 같은 항목이 있습니다.

- 조건부 액세스
- ID 보호
- Security Center
- ID 보안 점수
- 인증 방법
- MFA
- 위험 보고서 - 위험한 사용자, 위험한 로그인, 위험 검색
- 등...

자세한 내용은 [보안 - 시작](https://portal.azure.com/#blade/Microsoft_AAD_IAM/SecurityMenuBlade/GettingStarted)을 참조하세요.

---

### <a name="office-365-groups-expiration-policy-enhanced-with-autorenewal"></a>자동 갱신으로 강화된 Office 365 그룹 만료 정책

**유형:** 변경된 기능 **서비스 범주:** 그룹 관리 **제품 기능:** ID 수명 주기 관리

구성원들이 적극적으로 사용 중인 그룹을 자동으로 갱신하도록 Office 365 그룹 만료 정책이 향상되었습니다. Outlook, SharePoint, Teams를 비롯한 모든 Office 365 앱의 사용자 활동을 기반으로 그룹이 자동 갱신됩니다.

이처럼 향상된 기능은 그룹 만료 알림을 줄이고 활성 그룹을 계속 사용할 수 있도록 유지하는 데 도움이 됩니다. Office 365 그룹에 대한 활성 만료 정책이 이미 있는 경우 이 새 기능을 켜기 위해 아무 것도 할 필요가 없습니다.

자세한 내용은 [Office 365 그룹에 대한 만료 정책 구성](../enterprise-users/groups-lifecycle.md)을 참조하세요.

---

### <a name="updated-azure-ad-domain-services-azure-ad-ds-creation-experience"></a>업데이트된 Azure AD DS(Azure AD Domain Services) 만들기 환경

**유형:** 변경된 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

새롭게 향상된 만들기 환경을 포함하도록 Azure AD DS(Azure AD Domain Services)를 업데이트했으므로 이제 클릭 세 번만으로 관리되는 도메인을 만들 수 있습니다. 또한 이제 템플릿에서 Azure AD DS를 업로드하고 배포할 수 있습니다.

자세한 내용은 [자습서: Azure Active Directory Domain Services 인스턴스 만들기 및 구성](../../active-directory-domain-services/tutorial-create-instance.md)을 참조하세요.

---

## <a name="september-2019"></a>2019년 9월

### <a name="plan-for-change-deprecation-of-the-power-bi-content-packs"></a>변경 계획: Power BI 콘텐츠 팩 사용 중단

**유형:** 변경 계획 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

2019년 10월 1일부터 Power BI는 Azure AD Power BI 콘텐츠 팩을 비롯한 모든 콘텐츠 팩을 사용 중단합니다. 이 콘텐츠 팩의 대안으로, Azure AD 통합 문서를 사용하여 Azure AD 관련 서비스에 대한 인사이트를 얻을 수 있습니다. 보고서 전용 모드의 조건부 액세스 정책에 대한 통합 문서, 앱 동의 기반 인사이트 등을 비롯한 추가 통합 문서가 곧 출시됩니다.

통합 문서에 대한 자세한 내용은 [Azure Monitor 통합 문서를 Azure Active Directory 보고서에 사용하는 방법](../reports-monitoring/howto-use-azure-monitor-workbooks.md)을 참조하세요. 콘텐츠 팩 사용 중단에 대한 자세한 내용은 [Power BI 템플릿 앱 일반 공급](https://powerbi.microsoft.com/blog/announcing-power-bi-template-apps-general-availability/) 블로그 게시물을 참조하세요.

---

### <a name="my-profile-is-renaming-and-integrating-with-the-microsoft-office-account-page"></a>내 프로필의 이름이 바뀌고 Microsoft Office 계정 페이지에 통합됩니다.

**유형:** 변경 계획 **서비스 범주:** 내 프로필/계정 **제품 기능:** 협업

10월부터 내 프로필 환경이 내 계정으로 바뀝니다. 이번에 바뀌는 점으로, 현재의 **내 프로필** 이 **내 계정** 으로 변경됩니다. 이름을 변경하고 일부 디자인을 개선하여 업데이트된 환경은 Microsoft Office 계정 페이지와의 추가 통합을 제공합니다. 특히 **개인 정보** 페이지의 Office 관련 연락처 기본 설정과 함께 **개요 계정** 페이지에서 Office 설치 및 구독에 액세스할 수 있습니다.

내 프로필(미리 보기) 환경에 대한 자세한 내용은 [내 프로필(미리 보기) 포털 개요](../user-help/my-account-portal-overview.md)를 참조하세요.

---

### <a name="bulk-manage-groups-and-members-using-csv-files-in-the-azure-ad-portal-public-preview"></a>Azure AD Portal에서 CSV 파일을 사용하여 그룹 및 멤버 일괄 관리(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

Azure AD 포털의 대량 그룹 관리 환경을 공개 미리 보기로 사용할 수 있다는 기쁜 소식을 전해드립니다. 이제 CSV 파일 및 Azure AD 포털을 사용하여 다음을 비롯한 그룹 및 구성원 목록을 관리할 수 있습니다.

- 그룹 구성원을 추가 또는 제거합니다.

- 디렉터리에서 그룹 목록을 다운로드합니다.

- 특정 그룹에 대한 그룹 멤버 목록을 다운로드합니다.

자세한 내용은 [구성원 대량 추가](../enterprise-users/groups-bulk-import-members.md), [구성원 대량 제거](../enterprise-users/groups-bulk-remove-members.md), [구성원 목록 대량 다운로드](../enterprise-users/groups-bulk-download-members.md) 및 [그룹 목록 대량 다운로드](../enterprise-users/groups-bulk-download.md)를 참조하세요.

---

### <a name="dynamic-consent-is-now-supported-through-a-new-admin-consent-endpoint"></a>이제 새 관리자 동의 엔드포인트를 통한 동적 동의가 지원됩니다.

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

동적 동의를 지원하기 위해 새로운 관리자 동의 엔드포인트를 만들었으며, 이 엔드포인트는 Microsoft ID 플랫폼에서 동적 동의 모델을 사용하려는 앱에 유용합니다.

이 새 엔드포인트를 사용하는 방법에 대한 자세한 내용은 [관리자 동의 엔드포인트 사용](../develop/v2-admin-consent.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---september-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 9월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 9월에 페더레이션이 지원되는 다음과 같은 신규 앱 29개가 앱 갤러리에 추가되었습니다.

[ScheduleLook](https://schedulelook.bbsonlineservices.net/), [MS Azure SSO Access for Ethidex Compliance Office&trade; - Single  sign-on](../saas-apps/ms-azure-sso-access-for-ethidex-compliance-office-tutorial.md), [iServer Portal](../saas-apps/iserver-portal-tutorial.md), [SKYSITE](../saas-apps/skysite-tutorial.md), [Concur Travel and Expense](../saas-apps/concur-travel-and-expense-tutorial.md), [WorkBoard](../saas-apps/workboard-tutorial.md), `https://apps.yeeflow.com/`, [ARC Facilities](../saas-apps/arc-facilities-tutorial.md), [Luware Stratus Team](https://stratus.emea.luware.cloud/login), [Wide Ideas](https://wideideas.online/wideideas/), [Prisma Cloud](../saas-apps/prisma-cloud-tutorial.md), [JDLT Client Hub](https://clients.jdlt.co.uk/login), [RENRAKU](../saas-apps/renraku-tutorial.md), [SealPath Secure Browser](https://protection.sealpath.com/SealPathInterceptorWopiSaas/Open/InstallSealPathEditorOneDrive), [Prisma Cloud](../saas-apps/prisma-cloud-tutorial.md), `https://app.penneo.com/`, `https://app.testhtm.com/settings/email-integration`, [Cintoo Cloud](https://aec.cintoo.com/login), [Whitesource](../saas-apps/whitesource-tutorial.md), [Hosted Heritage Online SSO](../saas-apps/hosted-heritage-online-sso-tutorial.md), [IDC](../saas-apps/idc-tutorial.md), [CakeHR](../saas-apps/cakehr-tutorial.md), [BIS](../saas-apps/bis-tutorial.md), [Coo Kai Team Build](https://ms-contacts.coo-kai.jp/), [Sonarqube](../saas-apps/sonarqube-tutorial.md), [Adobe Identity Management](../saas-apps/tutorial-list.md), [Discovery Benefits SSO](../saas-apps/discovery-benefits-sso-tutorial.md), [Amelio](https://app.amelio.co/), `https://itask.yipinapp.com/`

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-azure-ad-global-reader-role"></a>새 Azure AD 글로벌 읽기 권한자 역할

**유형:** 새 기능 **서비스 범주:** Azure AD 역할 **제품 기능:** Access Control

2019년 9월 24일에 글로벌 읽기 권한자라고 하는 새 Azure AD(Active Directory) 역할이 출시됩니다. 이 출시는 프로덕션 및 GCC(글로벌 클라우드 고객)부터 시작하여 10월에 전 세계에 출시될 예정입니다.

글로벌 읽기 권한자 역할은 전역 관리자에 대응하는 읽기 전용 역할입니다. 이 역할의 사용자는 모든 Microsoft 365 서비스의 설정 및 관리 정보를 읽을 수 있지만 관리 작업을 수행할 수는 없습니다. 조직의 전역 관리자 수를 줄일 수 있도록 글로벌 읽기 권한자 역할을 만들었습니다. 전역 관리자 계정은 강력하지만 공격에 취약하기 때문에 전역 관리자를 5개 미만으로 유지하는 것이 좋습니다. 계획, 감사 또는 조사에 글로벌 읽기 권한자 역할을 사용하는 것이 좋습니다. 또한 글로벌 읽기 권한자 역할을 Exchange 관리자처럼 제한된 다른 관리자 역할과 함께 사용하면 전역 관리자 역할 없이 작업을 수행할 수 있습니다.

글로벌 읽기 권한자 역할은 새로운 Microsoft 365 관리 센터, Exchange 관리 센터, Teams 관리 센터, 보안 센터, 규정 준수 센터, Azure AD 관리 센터 및 디바이스 관리 센터에서 작동합니다.

>[!NOTE]
> 공개 미리 보기가 시작되면 글로벌 읽기 권한자 역할은 SharePoint, Privileged Access Management, 고객 Lockbox, 민감도 레이블, Teams 수명 주기, Teams 보고 및 호출 분석, Teams IP 전화 디바이스 관리 및 Teams 앱 카탈로그에서 작동하지 않습니다.

자세한 내용은 [Azure Active Directory의 관리자 역할 권한](../roles/permissions-reference.md)을 참조하세요.

---

### <a name="access-an-on-premises-report-server-from-your-power-bi-mobile-app-using-azure-active-directory-application-proxy"></a>Azure Active Directory 애플리케이션 프록시를 사용하여 Power BI 모바일 앱에서 온-프레미스 보고서 서버에 액세스

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

Power BI 모바일 앱과 Azure AD 애플리케이션 프록시가 통합되었기 때문에 Power BI 모바일 앱에 안전하게 로그인하여 온-프레미스 Power BI Report Server에 호스트된 조직의 보고서를 볼 수 있습니다.

앱을 다운로드할 수 있는 위치를 포함하여 Power BI 모바일 앱에 대한 자세한 내용은 [Power BI 사이트](https://powerbi.microsoft.com/mobile/)를 참조하세요. Azure AD 애플리케이션 프록시를 사용하여 Power BI 모바일 앱을 설정하는 방법에 대한 자세한 내용은 [Azure AD 애플리케이션 프록시를 사용하여 Power BI 모바일 앱에 대한 원격 액세스 설정](../manage-apps/application-proxy-integrate-with-power-bi.md)을 참조하세요.

---

### <a name="new-version-of-the-azureadpreview-powershell-module-is-available"></a>새 버전의 AzureADPreview PowerShell 모듈 사용 가능

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** 디렉터리

다음을 포함하여 Azure AD에서 사용자 지정 역할을 정의하고 할당하는 데 도움이 되는 새 cmdlet이 AzureADPreview 모듈에 추가되었습니다.

- `Add-AzureADMSFeatureRolloutPolicyDirectoryObject`
- `Get-AzureADMSFeatureRolloutPolicy`
- `New-AzureADMSFeatureRolloutPolicy`
- `Remove-AzureADMSFeatureRolloutPolicy`
- `Remove-AzureADMSFeatureRolloutPolicyDirectoryObject`
- `Set-AzureADMSFeatureRolloutPolicy`

---

### <a name="new-version-of-azure-ad-connect"></a>새 버전의 Azure AD Connect

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** 디렉터리

자동 업그레이드 고객을 위해 업데이트된 버전의 Azure AD Connect가 출시되었습니다. 새 버전에는 여러 가지 새 기능, 향상된 기능 및 버그 픽스가 포함되어 있습니다. 새 버전에 대한 자세한 내용은 [Azure AD Connect: 버전 릴리스 내역](../hybrid/reference-connect-version-history.md#14250)을 참조하세요.

---

### <a name="azure-multi-factor-authentication-mfa-server-version-802-is-now-available"></a>Azure MFA(Multi-Factor Authentication) 서버 버전 8.0.2 사용 가능

**유형:** 수정된 **서비스 범주:** MFA **제품 기능:** ID 보안 및 보호

2019년 7월 1일 전에 MFA 서버를 활성화한 기존 고객은 이제 최신 버전의 MFA 서버(버전 8.0.2)를 다운로드할 수 있습니다. 새 버전에서 바뀐 점은 다음과 같습니다.

- Azure AD 동기화가 사용자를 [사용 안 함]에서 [사용]으로 변경하면 사용자에게 이메일이 전송되는 문제가 해결되었습니다.

- 고객이 태그 기능을 계속 사용하면서 업그레이드할 수 있도록 문제가 해결되었습니다.

- 코소보(+383) 국가 코드가 추가되었습니다.

- MultiFactorAuthSvc.log에 일회성 바이패스 감사 로깅이 추가되었습니다.

- 웹 서비스 SDK 성능이 향상되었습니다.

- 기타 사소한 버그가 수정되었습니다.

2019년 7월 1일부터 Microsoft는 새 배포에 MFA 서버를 제공하지 않습니다. Multi-factor authentication을 요구 하는 신규 고객은 클라우드 기반 Azure AD Multi-Factor Authentication를 사용 해야 합니다. 자세한 내용은 [클라우드 기반 AZURE AD Multi-Factor Authentication 배포 계획](../authentication/howto-mfa-getstarted.md)을 참조 하세요.

---

## <a name="august-2019"></a>2019년 8월

### <a name="enhanced-search-filtering-and-sorting-for-groups-is-available-in-the-azure-ad-portal-public-preview"></a>Azure AD Portal(공개 미리 보기)에서 향상된 그룹 검색/필터링/정렬 기능 사용 가능

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

Azure AD 포털에서 향상된 그룹 관련 환경을 공개 미리 보기로 사용할 수 있다는 기쁜 소식을 전해드립니다. 향상된 환경은 그룹 및 구성원 목록을 보다 효율적으로 관리할 수 있도록 다음과 같은 기능을 제공합니다.

- 그룹 목록의 substring 검색 같은 고급 검색 기능
- 구성원 및 소유자 목록의 고급 필터링 및 정렬 옵션
- 구성원 및 소유자 목록을 검색하는 새 검색 기능
- 대규모 그룹의 그룹 수를 보다 정확하게 계산

자세한 내용은 [Azure Portal에서 그룹 관리](./active-directory-groups-members-azure-portal.md?context=azure%2factive-directory%2fusers-groups-roles%2fcontext%2fugr-context)를 참조하세요.

---

### <a name="new-custom-roles-are-available-for-app-registration-management-public-preview"></a>앱 등록 관리에 새 사용자 지정 역할을 사용할 수 있음(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** Azure AD 역할 **제품 기능:** Access Control

이제 사용자 지정 역할(Azure AD P1 또는 P2 구독에서 사용 가능)을 사용하여 특정 권한으로 역할 정의를 만든 다음, 특정 리소스에 해당 역할을 할당하여 세분화된 액세스를 제공할 수 있습니다. 현재는 앱 등록 관리에 필요한 권한을 사용하여 사용자 지정 역할을 만든 다음, 특정 앱에 역할을 할당합니다. 사용자 지정 역할에 대한 자세한 내용은 [Azure Active Directory의 사용자 지정 관리자 역할(미리 보기)](../roles/custom-overview.md)을 참조하세요.

원하는 권한 또는 리소스가 있는데 현재는 지원되지 않는 경우 [Azure 피드백 사이트](https://feedback.azure.com/forums/169401-azure-active-directory?category_id=166032)로 피드백을 보내주시면 해당 요청이 업데이트 로드맵에 추가됩니다.

---

### <a name="new-provisioning-logs-can-help-you-monitor-and-troubleshoot-your-app-provisioning-deployment-public-preview"></a>새 프로비저닝 로그를 사용하여 앱 프로비저닝 배포를 모니터링하고 문제를 해결할 수 있음(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** ID 수명 주기 관리

새 프로비저닝 로그를 통해 사용자 및 그룹 프로비저닝 배포를 모니터링하고 문제를 해결할 수 있습니다. 이러한 새 로그 파일에는 다음 정보가 포함됩니다.

- [ServiceNow](../saas-apps/servicenow-provisioning-tutorial.md)에서 성공적으로 생성된 그룹
- [AWS(Amazon Web Services)](../saas-apps/amazon-web-service-tutorial.md#configure-and-test-azure-ad-sso-for-amazon-web-services-aws)에서 가져온 역할
- [Workday](../saas-apps/workday-inbound-tutorial.md)에서 가져오지 않은 직원

자세한 내용은 [Azure Active Directory 포털의 프로비저닝 보고서(미리 보기)](../reports-monitoring/concept-provisioning-logs.md)를 참조하세요.

---

### <a name="new-security-reports-for-all-azure-ad-administrators-general-availability"></a>모든 Azure AD 관리자에 대한 새 보안 보고서(일반 공급)

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

기본적으로 모든 Azure AD 관리자는 조만간 Azure AD 내에서 최신 보안 보고서에 액세스할 수 있습니다. 9월 말까지는 최신 보안 보고서 맨 위에 있는 배너를 사용하여 이전 보고서로 돌아갈 수 있습니다.

최신 보안 보고서는 다음을 포함하여 이전 버전의 추가 기능을 제공합니다.

- 고급 데이터 필터링 및 분류
- 사용자 위험 해제와 같은 대량 작업
- 손상된 엔터티 또는 안전한 엔터티 확인
- 다음과 같은 위험 상태: 위험, 해제됨, 수정됨, 손상 확인됨
- 새 위험 관련 검색(Azure AD Premium 구독자만 사용 가능)

자세한 내용은 [위험한 사용자](../identity-protection/howto-identity-protection-investigate-risk.md#risky-users), [위험한 로그인](../identity-protection/howto-identity-protection-investigate-risk.md#risky-sign-ins) 및 [위험 검색](../identity-protection/howto-identity-protection-investigate-risk.md#risk-detections)을 참조하세요.

---

### <a name="user-assigned-managed-identity-is-available-for-virtual-machines-and-virtual-machine-scale-sets-general-availability"></a>사용자가 할당한 관리 ID를 Virtual Machines 및 Virtual Machine Scale Sets에 사용 가능(일반 공급)

**유형:** 새 기능 **서비스 범주:** Azure 리소스의 관리 ID **제품 기능:** 개발자 환경

이제 사용자가 할당한 관리 ID는 Virtual Machines 및 Virtual Machine Scale Sets에 일반 공급됩니다. 이 과정에서 Azure는 사용 중인 구독에서 신뢰할 수 있는 Azure AD 테넌트에 ID를 만들고, 하나 이상의 Azure 서비스 인스턴스에 할당할 수 있습니다. 사용자가 할당한 관리 ID에 대한 자세한 내용은 [Azure 리소스용 관리 ID란?](../managed-identities-azure-resources/overview.md)을 참조하세요.

---

### <a name="users-can-reset-their-passwords-using-a-mobile-app-or-hardware-token-general-availability"></a>사용자가 모바일 앱 또는 하드웨어 토큰을 사용하여 암호를 재설정할 수 있음(일반 공급)

**유형:** 변경된 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 사용자 인증

모바일 앱을 조직에 등록한 사용자는 이제 Microsoft Authenticator 앱에서 알림을 승인하거나 모바일 앱 또는 하드웨어 토큰에서 코드를 입력하여 자신의 암호를 다시 설정할 수 있습니다.

자세한 내용은 [작동 방법: Azure AD 셀프 서비스 암호 재설정](../authentication/concept-sspr-howitworks.md)을 참조하세요. 사용자 환경에 대한 자세한 내용은 [회사 또는 학교 암호 재설정 개요](../user-help/active-directory-passwords-reset-register.md)를 참조하세요.

---

### <a name="adalnet-ignores-the-msalnet-shared-cache-for-on-behalf-of-scenarios"></a>ADAL.NET은 On-Behalf-Of 시나리오에 대한 MSAL.NET 공유 캐시를 무시

**유형:** 수정된 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

Azure AD 인증 라이브러리(ADAL.NET) 버전 5.0.0-preview부터 앱 개발자는 [웹앱 및 웹 API 계정당 캐시 하나를 직렬화](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#custom-token-cache-serialization-in-web-applications--web-api)해야 합니다. 그렇지 않으면의 특정 사용 사례와 함께 Java에 대 한 단계별 [흐름](../develop/scenario-web-api-call-api-app-configuration.md?tabs=java) 을 사용 하는 일부 시나리오에서 `UserAssertion` 권한 상승이 발생할 수 있습니다. 이 취약점을 방지 하기 위해 ADAL.NET는 이제 시나리오를 대신해 MSAL.NET (Microsoft Authentication Library for dotnet) 공유 캐시를 무시 합니다.

이 문제에 대한 자세한 내용은 [Azure Active Directory 인증 라이브러리 권한 상승 취약점](https://portal.msrc.microsoft.com/security-guidance/advisory/CVE-2019-1258)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---august-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 8월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 8월에 페더레이션이 지원되는 다음과 같은 신규 앱 26개가 앱 갤러리에 추가되었습니다.

[Civic Platform](../saas-apps/civic-platform-tutorial.md), [Amazon Business](../saas-apps/amazon-business-tutorial.md), [ProNovos Ops Manager](../saas-apps/pronovos-ops-manager-tutorial.md), [Cognidox](../saas-apps/cognidox-tutorial.md), [Viareport's Inativ Portal(Europe)](../saas-apps/viareports-inativ-portal-europe-tutorial.md), [Azure Databricks](https://azure.microsoft.com/services/databricks), [Robin](../saas-apps/robin-tutorial.md), [Academy Attendance](../saas-apps/academy-attendance-tutorial.md), [Priority Matrix](https://sync.appfluence.com/pmwebng/), [Cousto MySpace](https://cousto.platformers.be/account/login), [Uploadcare](https://uploadcare.com/accounts/signup/), [Carbonite Endpoint Backup](../saas-apps/carbonite-endpoint-backup-tutorial.md), [CPQSync by Cincom](../saas-apps/cpqsync-by-cincom-tutorial.md), [Chargebee](../saas-apps/chargebee-tutorial.md), [deliver.media&trade; Portal](https://portal.deliver.media), [Frontline Education](../saas-apps/frontline-education-tutorial.md), [F5](https://www.f5.com/products/security/access-policy-manager), [stashcat AD connect](https://www.stashcat.com), [Blink](../saas-apps/blink-tutorial.md), [Vocoli](../saas-apps/vocoli-tutorial.md), [ProNovos Analytics](../saas-apps/pronovos-analytics-tutorial.md), [Sigstr](../saas-apps/sigstr-tutorial.md), [Darwinbox](../saas-apps/darwinbox-tutorial.md), [Watch by Colors](../saas-apps/watch-by-colors-tutorial.md), [Harness](../saas-apps/harness-tutorial.md), [EAB Navigate Strategic Care](../saas-apps/eab-navigate-strategic-care-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-versions-of-the-azuread-powershell-and-azureadpreview-powershell-modules-are-available"></a>새 버전의 AzureAD PowerShell 및 AzureADPreview PowerShell 모듈 사용 가능

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** 디렉터리

AzureAD 및 AzureAD Preview PowerShell 모듈의 업데이트를 사용할 수 있습니다.

- AzureAD 모듈의 `Get-AzureADDirectoryRole` 매개 변수에 새 `-Filter` 매개 변수가 추가되었습니다. 이 매개 변수를 사용하여 cmdlet에서 반환되는 디렉터리 역할을 필터링할 수 있습니다.
- 다음을 포함하여 Azure AD에서 사용자 지정 역할을 정의하고 할당하는 데 도움이 되는 새 cmdlet이 AzureADPreview 모듈에 추가되었습니다.

    - `Get-AzureADMSRoleAssignment`
    - `Get-AzureADMSRoleDefinition`
    - `New-AzureADMSRoleAssignment`
    - `New-AzureADMSRoleDefinition`
    - `Remove-AzureADMSRoleAssignment`
    - `Remove-AzureADMSRoleDefinition`
    - `Set-AzureADMSRoleDefinition`

---

### <a name="improvements-to-the-ui-of-the-dynamic-group-rule-builder-in-the-azure-portal"></a>Azure Portal의 동적 그룹 규칙 작성기 UI에 대한 향상된 기능

**유형:** 변경된 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

보다 쉽게 새 규칙을 설정하거나 기존 규칙을 변경할 수 있도록 Azure Portal에 제공되는 동적 그룹 규칙 작성기의 UI가 일부 개선되었습니다. 디자인이 개선되면서 1개가 아닌 최대 5개의 식을 사용하여 규칙을 만들 수 있습니다. 또한 사용되지 않는 디바이스 속성을 제거하도록 디바이스 속성 목록이 업데이트되었습니다.

자세한 내용은 [동적 구성원 규칙 관리](../enterprise-users/groups-dynamic-membership.md)를 참조하세요.

---

### <a name="new-microsoft-graph-app-permission-available-for-use-with-access-reviews"></a>액세스 검토에 사용할 수 있는 새 Microsoft Graph 앱 권한

**유형:** 변경된 기능 **서비스 범주:** 액세스 검토 **제품 기능:** ID 거버넌스

앱에서 그룹 멤버 자격 및 앱 할당에 대한 액세스 검토를 자동으로 만들고 검색할 수 있는 새로운 Microsoft Graph 앱 권한 `AccessReview.ReadWrite.Membership`이 도입되었습니다. 로그인한 사용자 컨텍스트를 요구하지 않고, 이 권한을 예약된 작업에서 사용하거나 자동화의 일부로 사용할 수 있습니다.

자세한 내용은 [PowerShell에서 Microsoft Graph 앱 권한을 사용하여 Azure AD 액세스 검토를 만드는 방법 예제](https://techcommunity.microsoft.com/t5/Azure-Active-Directory/Example-how-to-create-Azure-AD-access-reviews-using-Microsoft/m-p/807241)를 참조하세요.

---

### <a name="azure-ad-activity-logs-are-now-available-for-government-cloud-instances-in-azure-monitor"></a>이제 Azure Monitor에서 정부 클라우드 인스턴스에 Azure AD 활동 로그 사용 가능

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

Azure Monitor에서 정부 클라우드 인스턴스에 Azure AD 활동 로그를 사용할 수 있다는 기쁜 소식을 전해드립니다. 이제 Azure AD 로그를 스토리지 계정 또는 이벤트 허브에 전송하여 [Sumologic](../reports-monitoring/howto-integrate-activity-logs-with-sumologic.md), [Splunk](../reports-monitoring/howto-integrate-activity-logs-with-splunk.md), [ArcSight](../reports-monitoring/howto-integrate-activity-logs-with-arcsight.md) 등의 SIEM 도구와 통합할 수 있습니다.

Azure Monitor 설정에 대한 자세한 내용은 [Azure Monitor의 Azure AD 활동 로그](../reports-monitoring/concept-activity-logs-azure-monitor.md#cost-considerations)를 참조하세요.

---

### <a name="update-your-users-to-the-new-enhanced-security-info-experience"></a>사용자를 새로운 향상된 보안 정보 환경으로 업데이트

**유형:** 변경된 기능 **서비스 범주:**  인증(로그인) **제품 기능:** 사용자 인증

2019년 9월 25일부터, 사용자 보안 정보를 등록 및 관리하는 이전의 보안 정보 환경을 사용 중단하고 새로운 [향상된 버전](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Cool-enhancements-to-the-Azure-AD-combined-MFA-and-password/ba-p/354271)만 사용됩니다. 즉, 사용자는 더 이상 이전 환경을 사용할 수 없습니다.

향상된 보안 정보 환경에 대한 자세한 내용은 [관리자 설명서](../authentication/concept-registration-mfa-sspr-combined.md) 및 [사용자 설명서](../user-help/security-info-setup-signin.md)를 참조하세요.

#### <a name="to-turn-on-this-new-experience-you-must"></a>이 새로운 환경을 사용하려면 다음 작업을 수행해야 합니다.

1. 전역 관리자 또는 사용자 관리자로 Azure Portal에 로그인합니다.

2. **Azure Active Directory > 사용자 설정 > 액세스 패널 미리 보기 기능의 설정 관리** 로 이동합니다.

3. **사용자가 보안 정보를 등록하고 관리하기 위한 미리 보기 기능을 사용 가능 - 향상됨** 영역에서 **선택됨** 을 선택한 다음, 사용자 그룹을 선택하거나 **모두** 를 선택하여 테넌트의 모든 사용자에 대해 이 기능을 켭니다.

4. **사용자가 보안 **정보**를 등록하고 관리하기 위한 미리 보기 기능을 사용 가능** 영역에서 **없음** 을 선택합니다.

5. 설정을 저장합니다.

    설정을 저장한 후에는 더 이상 이전 보안 정보 환경에 액세스할 수 없습니다.

>[!Important]
>2019년 9월 25일 전까지 이러한 단계를 완료하지 않으면 Azure Active Directory 테넌트가 자동으로 향상된 환경을 사용하도록 설정됩니다. 궁금한 점은 registrationpreview@microsoft.com으로 문의하세요.

---

### <a name="authentication-requests-using-post-logins-will-be-more-strictly-validated"></a>POST 로그인을 사용하는 인증 요청의 유효성 검사를 엄격하게 진행

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 표준

2019년 9월 2일부터 POST 메서드를 사용하는 인증 요청은 HTTP 표준과 비교하여 엄격하게 유효성이 검사됩니다. 특히 공백과 큰따옴표(")는 더 이상 요청 양식 값에서 제거되지 않습니다. 이번 변경으로 인해 기존 클라이언트가 중단되는 일은 없으며, Azure AD로 전송되는 요청을 매번 안정적으로 처리하는 데 도움이 됩니다.

자세한 내용은 [Azure AD 주요 변경 내용 공지](../develop/reference-breaking-changes.md#post-form-semantics-will-be-enforced-more-strictly---spaces-and-quotes-will-be-ignored)를 참조하세요.

---

## <a name="july-2019"></a>2019년 7월

### <a name="plan-for-change-application-proxy-service-update-to-support-only-tls-12"></a>변경 계획: TLS 1.2만 지원하도록 애플리케이션 프록시 서비스 업데이트

**유형:** 변경 계획 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

가장 강력한 암호화를 제공하기 위해, 애플리케이션 프록시 서비스가 TLS 1.2 프로토콜에만 액세스하도록 제한할 것입니다. 이 제한은 처음에는 이미 TLS 1.2 프로토콜을 사용하는 고객에게 적용되므로 영향을 미치지 않습니다. TLS 1.0 및 TLS 1.1 프로토콜은 2019년 8월 31일부터 완전히 사용 중단됩니다. 현재 TLS 1.0 및 TLS 1.1을 사용하는 고객은 이 변화에 대비하라는 사전 공지를 받게 됩니다.

이번 변화를 거친 후 애플리케이션 프록시 서비스에 대한 연결을 유지하려면 TLS 1.2를 사용하도록 클라이언트-서버 및 브라우저-서버 조합을 업데이트하는 것이 좋습니다. 또한 직원이 애플리케이션 프록시 서비스를 통해 게시된 앱에 액세스하는 데 사용하는 클라이언트 시스템을 포함하는 것이 좋습니다.

자세한 내용은 [Azure Active Directory에서 애플리케이션 프록시를 통한 원격 액세스를 위해 온-프레미스 애플리케이션 추가](../manage-apps/application-proxy-add-on-premises-application.md)를 참조하세요.

---

### <a name="plan-for-change-design-updates-are-coming-for-the-application-gallery"></a>변경 계획: 애플리케이션 갤러리의 디자인 업데이트 예정

**유형:** 변경 계획 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

**애플리케이션 추가** 블레이드에 있는 **갤러리에서 추가** 영역의 사용자 인터페이스 디자인이 변경될 예정입니다. 자동 프로비저닝, OpenID Connect, SAML(Security Assertion Markup Language) 및 암호 SSO(Single Sign-On)를 지원하는 앱을 더 쉽게 찾을 수 있도록 바뀝니다.

---

### <a name="plan-for-change-removal-of-the-mfa-server-ip-address-from-the-office-365-ip-address"></a>변경 계획: Office 365 IP 주소에서 MFA 서버 IP 주소 제거

**유형:** 변경 계획 **서비스 범주:** MFA **제품 기능:** ID 보안 및 보호

[Office 365 IP 주소 및 URL 웹 서비스](/office365/enterprise/office-365-ip-web-service)에서 MFA 서버 IP 주소를 제거할 것입니다. 현재 이러한 페이지를 사용하여 방화벽 설정을 업데이트하는 경우 [Azure Multi-Factor Authentication 서버 시작](../authentication/howto-mfaserver-deploy.md#azure-multi-factor-authentication-server-firewall-requirements) 문서의 **Azure Multi-Factor Authentication 서버 방화벽 요구 사항** 섹션에 설명된 IP 주소 목록도 포함해야 합니다.

---

### <a name="app-only-tokens-now-require-the-client-app-to-exist-in-the-resource-tenant"></a>이제 앱 전용 토큰을 사용하려면 클라이언트 앱이 리소스 테넌트에 있어야 함

**유형:** 수정된 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

2019년 7월 26일에 [클라이언트 자격 증명 부여](../azuread-dev/v1-oauth2-client-creds-grant-flow.md)를 통해 앱 전용 토큰을 제공하는 방식을 변경했습니다. 이전에는 클라이언트 앱이 테넌트에 있는지 여부에 관계없이, 앱에서 다른 앱을 호출하는 토큰을 가져올 수 있었습니다. 이 동작은 웹 API라고도 하는 단일 테넌트 리소스를 리소스 테넌트에 있는 클라이언트 앱만 호출할 수 있도록 업데이트되었습니다.

앱이 리소스 테넌트에 없으면 `The service principal named <app_name> was not found in the tenant named <tenant_name>. This can happen if the application has not been installed by the administrator of the tenant.` 오류 메시지가 수신됩니다. 이 문제를 해결하려면 [관리자 동의 엔드포인트](../develop/v2-permissions-and-consent.md#using-the-admin-consent-endpoint)를 사용하여 또는 [PowerShell을 통해](../develop/howto-authenticate-service-principal-powershell.md) 클라이언트 앱 서비스 주체를 만들어야 합니다. 이렇게 하면 테넌트 내에서 작동할 수 있도록 앱 권한이 부여됩니다.

자세한 내용은 [인증의 새로운 기능](../develop/reference-breaking-changes.md#app-only-tokens-for-single-tenant-applications-are-only-issued-if-the-client-app-exists-in-the-resource-tenant)을 참조하세요.

> [!NOTE]
> 클라이언트와 API 간의 기존 동의는 여전히 필요 없습니다. 앱에서 여전히 자체적으로 권한 부여 검사를 수행해야 합니다.

---

### <a name="new-passwordless-sign-in-to-azure-ad-using-fido2-security-keys"></a>FIDO2 보안 키를 사용한 Azure AD에 대한 새로운 암호 없는 로그인

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

이제 Azure AD 고객은 조직의 사용자 및 그룹에 대한 FIDO2 보안 키를 관리하는 정책을 설정할 수 있습니다. 또한 최종 사용자는 자신의 보안 키를 직접 등록하고, FIDO 지원 디바이스에 있는 동안 키를 사용하여 웹 사이트의 Microsoft 계정에 로그인하고, Azure AD에 조인된 Windows 10 디바이스에 로그인할 수 있습니다.

자세한 내용은 [Azure AD에 암호 없는 로그인 사용(미리 보기)](../authentication/concept-authentication-passwordless.md)에서 관리자 관련 정보를 확인하고, [보안 키를 사용하도록 보안 정보 설정(미리 보기)](../user-help/security-info-setup-security-key.md)에서 최종 사용자 관련 정보를 확인하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---july-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 7월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 7월에 페더레이션이 지원되는 다음과 같은 신규 앱 18개가 앱 갤러리에 추가되었습니다.

[Ungerboeck Software](../saas-apps/ungerboeck-software-tutorial.md), [Bright Pattern Omnichannel Contact Center](../saas-apps/bright-pattern-omnichannel-contact-center-tutorial.md), [Clever Nelly](../saas-apps/clever-nelly-tutorial.md), [AcquireIO](../saas-apps/acquireio-tutorial.md), [Looop](https://www.looop.co/schedule-a-demo/), [productboard](../saas-apps/productboard-tutorial.md), [MS Azure SSO Access for Ethidex Compliance Office&trade;](../saas-apps/ms-azure-sso-access-for-ethidex-compliance-office-tutorial.md), [Hype](../saas-apps/hype-tutorial.md), [Abstract](../saas-apps/abstract-tutorial.md), [Ascentis](../saas-apps/ascentis-tutorial.md), [Flipsnack](https://www.flipsnack.com/accounts/sign-in-sso.html), [Wandera](../saas-apps/wandera-tutorial.md), [TwineSocial](https://twinesocial.com/), [Kallidus](../saas-apps/kallidus-tutorial.md), [HyperAnna](../saas-apps/hyperanna-tutorial.md), [PharmID WasteWitness](https://pharmid.com/), [i2B Connect](https://www.i2b-online.com/sign-up-to-use-i2b-connect-here-sso-access/), [JFrog Artifactory](../saas-apps/jfrog-artifactory-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="automate-user-account-provisioning-for-these-newly-supported-saas-apps"></a>새로 지원되는 SaaS 앱에 대한 사용자 계정 프로비저닝 자동화

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 모니터링 및 보고

다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

- [다이얼패드](../saas-apps/dialpad-provisioning-tutorial.md)

- [페더레이션 디렉터리](../saas-apps/federated-directory-provisioning-tutorial.md)

- [Figma](../saas-apps/figma-provisioning-tutorial.md)

- [Leapsome](../saas-apps/leapsome-provisioning-tutorial.md)

- [Peakon](../saas-apps/peakon-provisioning-tutorial.md)

- [Smartsheet](../saas-apps/smartsheet-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="new-azure-ad-domain-services-service-tag-for-network-security-group"></a>네트워크 보안 그룹에 대한 새 Azure AD Domain Services 서비스 태그

**유형:** 새 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

긴 IP 주소 및 범위 목록을 관리하느라 지친 분들은 Azure 네트워크 보안 그룹의 새로운 **AzureActiveDirectoryDomainServices** 네트워크 서비스 태그를 사용하여 Azure AD Domain Services 가상 네트워크 서브넷에 대한 인바운드 트래픽을 보호할 수 있습니다.

이 새 서비스 태그에 대한 자세한 내용은 [Azure AD Domain Services에 대한 네트워크 보안 그룹](../../active-directory-domain-services/network-considerations.md#network-security-groups-and-required-ports)을 참조하세요.

---

### <a name="new-security-audits-for-azure-ad-domain-services-public-preview"></a>Azure AD Domain Services에 대한 새 보안 감사(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

Azure AD Domain Service 보안 감사를 공개 미리 보기로 사용할 수 있다는 기쁜 소식을 전해드립니다. 보안 감사는 Azure AD Domain Service 포털을 통해 Azure Storage, Azure Log Analytics 작업 영역, Azure Event Hub를 비롯한 대상 리소스에 보안 감사 이벤트를 스트리밍하여 인증 서비스에 대한 중요한 인사이트를 제공합니다.

자세한 내용은 [Azure AD Domain Services에 보안 감사 사용(미리 보기)](../../active-directory-domain-services/security-audit-events.md)를 참조하세요.

---

### <a name="new-authentication-methods-usage--insights-public-preview"></a>새 인증 방법 사용법 및 인사이트(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 모니터링 및 보고

새 인증 방법 & insights 보고서를 사용 하 여 조직에서 Azure AD Multi-Factor Authentication 및 셀프 서비스 암호 재설정과 같은 기능을 등록 하 고 사용 하는 방법을 이해할 수 있습니다. 각 기능에 대해 등록 된 사용자 수, 암호 재설정을 위해 셀프 서비스 암호 재설정을 사용 하는 빈도, 다시 설정이 수행 되는 방법 등을 포함 합니다.

자세한 내용은 [인증 방법 사용법 및 인사이트(미리 보기)](../authentication/howto-authentication-methods-usage-insights.md)를 참조하세요.

---

### <a name="new-security-reports-are-available-for-all-azure-ad-administrators-public-preview"></a>모든 Azure AD 관리자가 새 보안 보고서 사용 가능(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

이제 모든 Azure AD 관리자는 기존 보안 보고서(예: **위험 플래그가 지정된 사용자** 보고서)의 맨 위에 있는 배너를 선택하여 **위험한 사용자** 및 **위험한 로그인** 보고서에 표시된 것처럼 새로운 보안 환경을 사용할 수 있습니다. 시간이 지나면 모든 보안 보고서가 이전 버전에서 새 버전으로 전환될 것이며, 새 보고서는 다음과 같은 추가 기능을 제공합니다.

- 고급 데이터 필터링 및 분류

- 사용자 위험 해제와 같은 대량 작업

- 손상된 엔터티 또는 안전한 엔터티 확인

- 다음과 같은 위험 상태: 위험, 해제됨, 수정됨, 손상 확인됨

자세한 내용은 [위험한 사용자 보고서](../identity-protection/howto-identity-protection-investigate-risk.md#risky-users) 및 [위험한 로그인 보고서](../identity-protection/howto-identity-protection-investigate-risk.md#risky-sign-ins)를 참조하세요.

---

### <a name="new-security-audits-for-azure-ad-domain-services-public-preview"></a>Azure AD Domain Services에 대한 새 보안 감사(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

Azure AD Domain Service 보안 감사를 공개 미리 보기로 사용할 수 있다는 기쁜 소식을 전해드립니다. 보안 감사는 Azure AD Domain Service 포털을 통해 Azure Storage, Azure Log Analytics 작업 영역, Azure Event Hub를 비롯한 대상 리소스에 보안 감사 이벤트를 스트리밍하여 인증 서비스에 대한 중요한 인사이트를 제공합니다.

자세한 내용은 [Azure AD Domain Services에 보안 감사 사용(미리 보기)](../../active-directory-domain-services/security-audit-events.md)을 참조하세요.

---

### <a name="new-b2b-direct-federation-using-samlws-fed-public-preview"></a>SAML/WS-Fed를 사용하는 새로운 B2B 직접 페더레이션(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C

직접 페더레이션은 SAML 또는 WS-Fed 표준을 지원하는 ID 시스템을 사용하여 IT 관리 ID 솔루션이 Azure AD가 아닌 파트너와 보다 쉽게 협업할 수 있도록 도와줍니다. 파트너와의 직접 페더레이션 관계를 설정한 후에는 해당 도메인에서 초대하는 모든 새 게스트 사용자가 기존 조직 계정을 사용하여 협업할 수 있으므로 게스트의 사용자 환경을 더욱 원활하게 만들 수 있습니다.

자세한 내용은 [게스트 사용자를 위한 AD FS 및 타사 공급자와의 직접 페더레이션(미리 보기)](../external-identities/direct-federation.md)을 참조하세요.

---

### <a name="automate-user-account-provisioning-for-these-newly-supported-saas-apps"></a>새로 지원되는 SaaS 앱에 대한 사용자 계정 프로비저닝 자동화

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 모니터링 및 보고

다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

- [다이얼패드](../saas-apps/dialpad-provisioning-tutorial.md)

- [페더레이션 디렉터리](../saas-apps/federated-directory-provisioning-tutorial.md)

- [Figma](../saas-apps/figma-provisioning-tutorial.md)

- [Leapsome](../saas-apps/leapsome-provisioning-tutorial.md)

- [Peakon](../saas-apps/peakon-provisioning-tutorial.md)

- [Smartsheet](../saas-apps/smartsheet-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="new-check-for-duplicate-group-names-in-the-azure-ad-portal"></a>Azure AD 포털에서 중복 그룹 이름을 확인하는 새 기능

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이제 Azure AD 포털에서 그룹 이름을 만들거나 업데이트할 때 리소스에서 기존 그룹 이름이 중복되는지 확인하는 검사가 수행됩니다. 다른 그룹에서 이미 사용 중인 이름으로 확인되면 이름을 수정하라는 메시지가 표시됩니다.

자세한 내용은 [Azure AD 포털에서 그룹 관리](./active-directory-groups-create-azure-portal.md?context=azure%2factive-directory%2fusers-groups-roles%2fcontext%2fugr-context)를 참조하세요.

---

### <a name="azure-ad-now-supports-static-query-parameters-in-reply-redirect-uris"></a>이제 Azure AD는 회신(리디렉션) URI에서 정적 쿼리 매개 변수를 지원

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

이제 Azure AD 앱은 OAuth 2.0 요청에 대한 정적 쿼리 매개 변수(예: `https://contoso.com/oauth2?idp=microsoft`)가 포함된 회신(리디렉션) URI를 등록하고 사용할 수 있습니다. 회신 URI의 다른 부분과 마찬가지로, 정적 쿼리 매개 변수에도 회신 URI에 대한 문자열 일치가 적용됩니다. URL 디코딩 리디렉션 URI와 일치하는 등록된 문자열이 없는 경우 요청이 거부됩니다. 회신 URI가 있는 경우 정적 쿼리 매개 변수를 포함한 전체 문자열이 사용자를 리디렉션하는 데 사용됩니다.

동적 회신 URI는 보안 위험이 있기 때문에 여전히 금지되며 인증 요청에 대한 상태 정보를 유지하는 데 사용할 수 없습니다. 이 목적에는 `state` 매개 변수를 사용합니다.

현재 Azure Portal의 앱 등록 화면은 여전히 쿼리 매개 변수를 차단합니다. 그러나 앱 매니페스트를 수동으로 편집하여 앱에서 쿼리 매개 변수를 추가하고 테스트할 수 있습니다. 자세한 내용은 [인증의 새로운 기능](../develop/reference-breaking-changes.md#redirect-uris-can-now-contain-query-string-parameters)을 참조하세요.

---

### <a name="activity-logs-ms-graph-apis-for-azure-ad-are-now-available-through-powershell-cmdlets"></a>이제 PowerShell Cmdlet을 통해 Azure AD에 대한 활동 로그(MS Graph API)를 사용할 수 있음

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

이제 Azure AD PowerShell 모듈을 통해 Azure AD 활동 로그(감사 및 로그인 보고서)를 사용할 수 있다는 기쁜 소식을 전해드립니다. 이전에는 MS Graph API 엔드포인트를 사용하여 사용자 고유의 스크립트를 만들 수 있었으며, 이제 이 기능이 PowerShell cmdlet으로 확장되었습니다.

이러한 cmdlet을 사용하는 방법에 대한 자세한 내용은 [보고용 Azure AD PowerShell cmdlet](../reports-monitoring/reference-powershell-reporting.md)을 참조하세요.

---

### <a name="updated-filter-controls-for-audit-and-sign-in-logs-in-azure-ad"></a>Azure AD의 감사 및 로그인 로그에 대한 업데이트된 필터 컨트롤

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

보고서 화면에서 필터를 열로 추가하지 않고도 다양한 필터를 적용할 수 있도록 감사 및 로그인 로그 보고서가 업데이트되었습니다. 화면에 표시하려는 필터 수도 결정할 수 있습니다. 이러한 업데이트가 함께 작동하여 더 쉽게 읽을 수 있고 요구 사항에 더 적합한 보고서가 작성됩니다.

이러한 업데이트에 대한 자세한 내용은 [감사 로그 필터링](../reports-monitoring/concept-audit-logs.md#filtering-audit-logs) 및 [로그인 활동 필터링](../reports-monitoring/concept-sign-ins.md#filter-sign-in-activities)을 참조하세요.

---

## <a name="june-2019"></a>2019년 6월

### <a name="new-riskdetections-api-for-microsoft-graph-public-preview"></a>Microsoft Graph용 새 riskDetections API(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

Microsoft Graph용 새 riskDetections API를 공개 미리 보기로 사용할 수 있다는 기쁜 소식을 전해드립니다. 이 새 API를 사용하여 조직의 Identity Protection 관련 사용자 및 로그인 위험 검색 목록을 볼 수 있습니다. 또한 이 API를 사용하여 검색 유형, 상태, 수준 등에 대한 세부 정보를 포함하여 위험 검색을 보다 효율적으로 쿼리할 수 있습니다.

자세한 내용은 [위험 검색 API 참조 문서](/graph/api/resources/riskdetection?view=graph-rest-beta)를 확인하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---june-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 6월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 6월에 페더레이션이 지원되는 다음과 같은 신규 앱 22개가 앱 갤러리에 추가되었습니다.

[Azure AD SAML Toolkit](../saas-apps/saml-toolkit-tutorial.md), [Otsuka Shokai(大塚商会)](../saas-apps/otsuka-shokai-tutorial.md), [ANAQUA](../saas-apps/anaqua-tutorial.md), [Azure VPN Client](https://portal.azure.com/), [ExpenseIn](../saas-apps/expensein-tutorial.md), [Helper Helper](../saas-apps/helper-helper-tutorial.md), [Costpoint](../saas-apps/costpoint-tutorial.md), [GlobalOne](../saas-apps/globalone-tutorial.md), [Mercedes-Benz In-Car Office](https://me.secure.mercedes-benz.com/), [Skore](https://app.justskore.it/), [Oracle Cloud Infrastructure Console](../saas-apps/oracle-cloud-tutorial.md), [CyberArk SAML Authentication](../saas-apps/cyberark-saml-authentication-tutorial.md), [Scrible Edu](https://www.scrible.com/sign-in/#/create-account), [PandaDoc](../saas-apps/pandadoc-tutorial.md), [Perceptyx](https://apexdata.azurewebsites.net/docs.microsoft.com/azure/active-directory/saas-apps/perceptyx-tutorial), [Proptimise OS](https://proptimise.co.uk/software/), [Vtiger CRM(SAML)](../saas-apps/vtiger-crm-saml-tutorial.md), Oracle Access Manager for Oracle Retail Merchandising, Oracle Access Manager for Oracle E-Business Suite, Oracle IDCS for E-Business Suite, Oracle IDCS for PeopleSoft, Oracle IDCS for JD Edwards

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="automate-user-account-provisioning-for-these-newly-supported-saas-apps"></a>새로 지원되는 SaaS 앱에 대한 사용자 계정 프로비저닝 자동화

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 모니터링 및 보고

다음과 같은 통합된 새 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화할 수 있습니다.

- [Zoom](../saas-apps/zoom-provisioning-tutorial.md)

- [Envoy](../saas-apps/envoy-provisioning-tutorial.md)

- [Proxyclick](../saas-apps/proxyclick-provisioning-tutorial.md)

- [4me](../saas-apps/4me-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 사용하여 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="view-the-real-time-progress-of-the-azure-ad-provisioning-service"></a>Azure AD 프로비저닝 서비스의 실시간 진행률 보기

**유형:** 변경된 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** ID 수명 주기 관리

사용자 프로비저닝 프로세스가 얼마나 진행되었는지 보여주는 새 진행률 표시줄을 포함하도록 Azure AD 프로비저닝 환경이 업데이트되었습니다. 이 업데이트된 환경에서는 현재 주기 동안 프로비저닝된 사용자 수와 현재까지 프로비저닝된 사용자 수에 대한 정보도 제공합니다.

자세한 내용은 [사용자 프로비저닝 상태 확인](../app-provisioning/application-provisioning-when-will-provisioning-finish-specific-user.md)을 참조하세요.

---

### <a name="company-branding-now-appears-on-sign-out-and-error-screens"></a>이제 회사 브랜딩이 로그아웃 및 오류 화면에 표시됨

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

로그인 페이지뿐 아니라 로그아웃 및 오류 화면에도 회사 브랜딩이 표시되도록 Azure AD가 업데이트되었습니다. 이 기능을 사용하기 위해 어떤 작업도 수행할 필요가 없으며, Azure Portal의 **회사 브랜딩** 영역에 이미 설정된 자산을 Azure AD가 알아서 사용합니다.

회사 브랜딩 설정에 대한 자세한 내용은 [조직의 Azure Active Directory 페이지에 브랜딩 추가](./customize-branding.md)를 참조하세요.

---

### <a name="azure-multi-factor-authentication-mfa-server-is-no-longer-available-for-new-deployments"></a>Azure MFA(Multi-Factor Authentication) 서버를 새 배포에 더 이상 사용할 수 없음

**유형:** 사용되지 않는 **서비스 범주:** MFA **제품 기능:** ID 보안 및 보호

Microsoft는 2019년 7월 1일부터 더 이상 새 배포를 위한 MFA 서버를 제공하지 않습니다. 조직에서 multi-factor authentication을 요구 하려는 신규 고객은 이제 클라우드 기반 Azure AD Multi-Factor Authentication를 사용 해야 합니다. 7월 1일 전에 MFA 서버를 활성화한 고객은 달라지는 점이 없습니다. 여전히 최신 버전을 다운로드하고, 향후 업데이트를 가져오고, 활성화 자격 증명을 생성할 수 있습니다.

자세한 내용은 [Azure Multi-Factor Authentication 서버 시작](../authentication/howto-mfaserver-deploy.md)을 참조하세요. 클라우드 기반 Azure AD Multi-Factor Authentication에 대 한 자세한 내용은 [클라우드 기반 AZURE ad Multi-Factor Authentication 배포 계획](../authentication/howto-mfa-getstarted.md)을 참조 하세요.

---

## <a name="may-2019"></a>2019년 5월

### <a name="service-change-future-support-for-only-tls-12-protocols-on-the-application-proxy-service"></a>서비스 변경: 향후 애플리케이션 프록시 서비스의 TLS 1.2 프로토콜만 지원

**유형:** 변경 계획 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

고객에게 동급 최고의 암호화를 제공할 수 있도록 애플리케이션 프록시 서비스의 TLS 1.2 프로토콜에 대한 액세스만 제한될 예정입니다. 이미 TLS 1.2 프로토콜만 사용하는 고객에게는 이 변경 내용이 점진적으로 적용되므로 달라지는 점이 없습니다.

TLS 1.0 및 TLS 1.1의 사용 중단 날짜는 2019년 8월 31일이지만, 이번에 바뀌는 내용에 대비할 수 있도록 사전에 공지할 것입니다. 이번에 바뀌는 내용에 대비하려면 사용자가 애플리케이션 프록시를 통해 게시된 앱에 액세스하기 위해 사용하는 클라이언트를 포함하여 클라이언트-서버 및 브라우저-서버 조합이 TLS 1.2 프로토콜을 사용하여 애플리케이션 프록시 서비스에 대한 연결을 유지하도록 업데이트되었는지 확인합니다. 자세한 내용은 [Azure Active Directory에서 애플리케이션 프록시를 통한 원격 액세스를 위해 온-프레미스 애플리케이션 추가](../manage-apps/application-proxy-add-on-premises-application.md#prerequisites)를 참조하세요.

---

### <a name="use-the-usage-and-insights-report-to-view-your-app-related-sign-in-data"></a>사용량 및 인사이트 보고서를 사용하여 앱 관련 로그인 데이터 확인

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 모니터링 및 보고

이제 Azure Portal의 **엔터프라이즈 애플리케이션** 영역에 있는 사용량 및 인사이트 보고서를 사용하여 로그인 데이터의 애플리케이션 중심 보기를 가져올 수 있으며, 여기에는 다음 정보가 포함됩니다.

- 조직에서 가장 많이 사용되는 앱

- 실패한 로그인이 가장 많은 앱

- 각 앱의 주요 로그인 오류

이 기능에 대한 자세한 내용은 [Azure Active Directory 포털의 사용량 및 인사이트 보고서](../reports-monitoring/concept-usage-insights-report.md)를 참조하세요.

---

### <a name="automate-your-user-provisioning-to-cloud-apps-using-azure-ad"></a>Azure AD를 사용하여 클라우드 앱에 대한 사용자 프로비저닝 자동화

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 모니터링 및 보고

Azure AD 프로비저닝 서비스를 사용하여 다음 클라우드 기반 앱에 대한 사용자 계정의 생성, 삭제 및 업데이트를 자동화하려면 다음 새 자습서를 따르세요.

- [Comeet](../saas-apps/comeet-recruiting-software-provisioning-tutorial.md)

- [DynamicSignal](../saas-apps/dynamic-signal-provisioning-tutorial.md)

- [KeeperSecurity](../saas-apps/keeper-password-manager-digitalvault-provisioning-tutorial.md)

그룹 개체를 프로비저닝하는 방법에 대한 정보를 제공하는 새 [Dropbox 자습서](../saas-apps/dropboxforbusiness-provisioning-tutorial.md)를 수행할 수도 있습니다.

자동화된 사용자 계정 프로비저닝을 통해 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="identity-secure-score-is-now-available-in-azure-ad-general-availability"></a>Azure AD에서 ID 보안 점수 사용 가능(일반 공급)

**유형:** 새 기능 **서비스 범주:** 해당 없음 **제품 기능:** ID 보안 및 보호

이제 Azure AD의 ID 보안 점수 기능을 사용하여 ID 보안 상태를 모니터링하고 개선할 수 있습니다. ID 보안 점수 기능은 단일 대시보드를 사용하여 다음과 같은 도움을 줍니다.

- 1점~223점을 기준으로 ID 보안 상태를 객관적으로 측정

- ID 보안 개선 계획

- 보안 개선의 성공 여부 검토

ID 보안 점수 기능에 대한 자세한 내용은 [Azure Active Directory의 ID 보안 점수란?](./identity-secure-score.md)을 참조하세요.

---

### <a name="new-app-registrations-experience-is-now-available-general-availability"></a>이제 새로운 앱 등록 환경을 사용할 수 있습니다(일반 공급).

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 개발자 환경

이제 새로운 [앱 등록](https://aka.ms/appregistrations) 환경이 일반 공급됩니다. 새 환경은 Azure Portal 및 애플리케이션 등록 포털의 친숙한 주요 기능을 모두 포함하고 있으며 다음을 통해 개선됩니다.

- **효율적인 앱 관리.** 앱을 여러 포털에서 보는 대신, 이제 모든 앱을 한 곳에서 볼 수 있습니다.

- **앱 등록 간소화.** 향상된 탐색 환경부터 개선된 권한 선택 환경까지, 이제 더 쉽게 앱을 등록하고 관리할 수 있습니다.

- **자세한 정보** 빠른 시작 가이드를 포함하여 앱에 대한 자세한 정보를 찾을 수 있습니다.

자세한 내용은 [Microsoft ID 플랫폼](../develop/index.yml) 및 [앱 등록 환경이 이제 일반 공급됩니다.](https://developer.microsoft.com/identity/blogs/new-app-registrations-experience-is-now-generally-available/) 블로그 공지를 참조하세요.

---

### <a name="new-capabilities-available-in-the-risky-users-api-for-identity-protection"></a>Identity Protection용 위험한 사용자 API에 새 기능 제공

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

이제 위험한 사용자 API를 사용하여 사용자의 위험 기록을 검색하고, 위험한 사용자를 해제하고, 사용자가 손상된 것으로 확인할 수 있습니다. 이번 변화로 인해 사용자의 위험 상태를 보다 효율적으로 업데이트하고 위험 기록을 이해할 수 있게 되었습니다.

자세한 내용은 [위험 사용자 API 참조 문서](/graph/api/resources/riskyuser?view=graph-rest-beta)를 확인하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---may-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 5월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 5월에 페더레이션이 지원되는 다음과 같은 신규 앱 21개가 앱 갤러리에 추가되었습니다.

[Freedcamp](../saas-apps/freedcamp-tutorial.md), [Real Links](../saas-apps/real-links-tutorial.md), [Kianda](https://app.kianda.com/sso/OpenID/AzureAD/), [Simple Sign](../saas-apps/simple-sign-tutorial.md), [Braze](../saas-apps/braze-tutorial.md), [Displayr](../saas-apps/displayr-tutorial.md), [Templafy](../saas-apps/templafy-tutorial.md), [Marketo Sales Engage](https://toutapp.com/login), [ACLP](../saas-apps/aclp-tutorial.md), [OutSystems](../saas-apps/outsystems-tutorial.md), [Meta4 Global HR](../saas-apps/meta4-global-hr-tutorial.md), [Quantum Workplace](../saas-apps/quantum-workplace-tutorial.md), [Cobalt](../saas-apps/cobalt-tutorial.md), [webMethods API Cloud](../saas-apps/webmethods-integration-cloud-tutorial.md), [RedFlag](https://pocketstop.com/redflag/), [Whatfix](../saas-apps/whatfix-tutorial.md), [Control](../saas-apps/control-tutorial.md), [JOBHUB](../saas-apps/jobhub-tutorial.md), [NEOGOV](../saas-apps/neogov-tutorial.md), [Foodee](../saas-apps/foodee-tutorial.md), [MyVR](../saas-apps/myvr-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="improved-groups-creation-and-management-experiences-in-the-azure-ad-portal"></a>Azure AD 포털에서 그룹 생성 및 관리 환경 개선

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

Azure AD 포털의 그룹 관련 환경이 개선되었습니다. 이처럼 향상된 환경을 통해 관리자는 그룹 목록 및 멤버 목록을 보다 효율적으로 관리하고 더 많은 만들기 옵션을 제공할 수 있습니다.

향상된 기능은 다음과 같습니다.

- 멤버 자격 유형 및 그룹 유형별 기본 필터링

- 원본 및 이메일 주소와 같은 새 열 추가

- 쉽게 삭제할 수 있도록 그룹, 멤버 및 소유자 목록을 다중 선택하는 기능

- 그룹을 만드는 동안 이메일 주소를 선택하고 소유자를 추가하는 기능

자세한 내용은 [Azure Active Directory를 사용하여 기본 그룹 만들기 및 멤버 추가](./active-directory-groups-create-azure-portal.md)를 참조하세요.

---

### <a name="configure-a-naming-policy-for-office-365-groups-in-azure-ad-portal-general-availability"></a>Azure AD 포털에서 Office 365 그룹의 명명 정책 구성(일반 공급)

**유형:** 변경된 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이제 관리자는 Azure AD 포털을 사용하여 Office 365 그룹의 명명 정책을 구성할 수 있습니다. 이번에 바뀌는 내용은 조직의 사용자가 만들거나 편집하는 Office 365 그룹에 일관적인 명명 규칙을 적용하는 데 도움이 됩니다.

다음 두 가지 방법을 통해 Office 365 그룹에 대한 명명 정책을 구성할 수 있습니다.

- 그룹 이름에 자동으로 추가되는 접두사 또는 접미사를 정의합니다.

- 조직에서 금지된 사용자 지정 단어 세트를 업로드합니다. 이러한 단어(예: "CEO, 급여대장, HR")는 그룹 이름에 허용되지 않습니다.

자세한 내용은 [Office 365 그룹에 대한 명명 정책 적용](../enterprise-users/groups-naming-policy.md)을 참조하세요.

---

### <a name="microsoft-graph-api-endpoints-are-now-available-for-azure-ad-activity-logs-general-availability"></a>이제 Microsoft Graph API 엔드포인트를 Azure AD 활동 로그에 사용 가능(일반 공급)

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

Azure AD 활동 로그에 대한 Microsoft Graph API 엔드포인트 지원이 일반 공급으로 전환되었습니다. 이 릴리스에서는 Azure AD 감사 로그와 로그인 로그 API의 1.0 버전을 모두 사용할 수 있습니다.

자세한 내용은 [Azure AD 감사 로그 API 개요](/graph/api/resources/azure-ad-auditlog-overview)를 참조하세요.

---

### <a name="administrators-can-now-use-conditional-access-for-the-combined-registration-process-public-preview"></a>이제 관리자는 결합된 등록 프로세스에 조건부 액세스 사용 가능(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

이제 관리자는 결합된 등록 페이지에서 사용할 조건부 액세스 정책을 만들 수 있습니다. 여기에는 다음과 같은 경우에 등록을 허용하는 정책 적용이 포함됩니다.

- 사용자가 신뢰할 수 있는 네트워크에 있습니다.

- 사용자의 로그인 위험이 낮습니다.

- 사용자가 관리 디바이스에 있습니다.

- 사용자가 조직의 TOU(사용 약관)에 동의합니다.

조건부 액세스 및 암호 재설정에 대한 자세한 내용은 [Azure AD 결합 MFA 및 암호 재설정 등록 환경에 대한 조건부 액세스 블로그 게시물](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Conditional-access-for-the-Azure-AD-combined-MFA-and-password/ba-p/566348)을 참조하세요. 결합된 등록 프로세스에 대한 조건부 액세스 정책의 자세한 내용은 [결합된 등록에 대한 조건부 액세스 정책](../authentication/howto-registration-mfa-sspr-combined.md#conditional-access-policies-for-combined-registration)을 참조하세요. Azure AD 사용 약관 기능에 대한 자세한 내용은 [Azure Active Directory 사용 약관 기능](../conditional-access/terms-of-use.md)을 참조하세요.

---

## <a name="april-2019"></a>2019년 4월

### <a name="new-azure-ad-threat-intelligence-detection-is-now-available-as-part-of-azure-ad-identity-protection"></a>이제 Azure Active Directory Identity Protection의 일부로 새 Azure AD 위협 인텔리전스 검색 제공

**유형:** 새 기능 **서비스 범주:** Azure AD Identity Protection **제품 기능:** ID 보안 및 보호

업데이트된 Azure Active Directory Identity Protection 기능의 일부로 Azure AD 위협 인텔리전스 검색을 사용할 수 있습니다. 이 새 기능은 Microsoft의 내부 및 외부 위협 인텔리전스 소스를 기반으로 알려진 공격 패턴과 일치하는 특정 사용자 또는 활동에 대해 비정상적인 사용자 활동을 표시할 수 있습니다.

Azure Active Directory Identity Protection의 갱신된 버전에 대한 자세한 내용은 [현재 공개 미리 보기로 제공되는 Azure Active Directory Identity Protection의 4가지 주요 향상된 기능](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Four-major-Azure-AD-Identity-Protection-enhancements-are-now-in/ba-p/326935) 블로그 게시물 및 [Azure Active Directory Identity Protection(갱신된 버전)이란?](../identity-protection/overview-identity-protection.md) 문서를 참조하세요. Azure AD 위협 인텔리전스 검색에 대한 자세한 내용은 [Azure Active Directory Identity Protection 위험 검색](../identity-protection/concept-identity-protection-risks.md) 문서를 참조하세요.

---

### <a name="azure-ad-entitlement-management-is-now-available-public-preview"></a>Azure AD 권한 관리를 사용 가능(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** ID 거버넌스 **제품 기능:** ID 거버넌스

현재 공개 미리 보기로 제공되는 Azure AD 권한 관리를 통해 고객은 직원 및 비즈니스 파트너가 액세스를 요청하는 방법, 승인할 사람, 액세스할 수 있는 기간을 정의하는 액세스 패키지 관리를 위임할 수 있습니다. 액세스 패키지는 Azure AD 및 Office 365 그룹의 멤버 자격, 엔터프라이즈 애플리케이션의 역할 할당 및 SharePoint Online 사이트의 역할 할당을 관리할 수 있습니다. 권한 관리에 대한 자세한 내용은 [Azure AD 권한 관리 개요](../governance/entitlement-management-overview.md)를 참조하세요. Privileged Identity Management, 액세스 검토 및 사용 약관을 포함하여 다양한 Azure AD Identity Governance 기능에 대한 자세한 내용은 [Azure AD Identity Governance란?](../governance/identity-governance-overview.md)을 참조하세요.

---

### <a name="configure-a-naming-policy-for-office-365-groups-in-azure-ad-portal-public-preview"></a>Azure AD 포털에서 Office 365 그룹에 대한 명명 정책 구성(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이제 관리자는 Azure AD 포털을 사용하여 Office 365 그룹의 명명 정책을 구성할 수 있습니다. 이번에 바뀌는 내용은 조직의 사용자가 만들거나 편집하는 Office 365 그룹에 일관적인 명명 규칙을 적용하는 데 도움이 됩니다.

다음 두 가지 방법을 통해 Office 365 그룹에 대한 명명 정책을 구성할 수 있습니다.

- 그룹 이름에 자동으로 추가되는 접두사 또는 접미사를 정의합니다.

- 조직에서 금지된 사용자 지정 단어 세트를 업로드합니다. 이러한 단어(예: "CEO, 급여대장, HR")는 그룹 이름에 허용되지 않습니다.

자세한 내용은 [Office 365 그룹에 대한 명명 정책 적용](../enterprise-users/groups-naming-policy.md)을 참조하세요.

---

### <a name="azure-ad-activity-logs-are-now-available-in-azure-monitor-general-availability"></a>이제 Azure Monitor에 Azure AD 활동 로그가 제공됨(일반 공급)

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

Azure AD 활동 로그를 사용한 시각화에 대한 피드백을 해결하는 데 도움을 드리기 위해 Log Analytics에 새로운 인사이트 기능을 도입하는 중입니다. 이 기능을 사용하면 통합 문서라고 하는 대화형 템플릿을 사용하여 Azure AD 리소스에 대한 인사이트를 얻을 수 있습니다. 이러한 미리 작성된 통합 문서는 앱 또는 사용자에 대한 세부 정보를 제공할 수 있으며 다음을 포함합니다.

- **로그인.** 로그인 위치, 사용 중인 운영 체제 또는 브라우저 클라이언트 및 버전, 성공 또는 실패한 로그인 수를 포함하여 앱 및 사용자에 대한 세부 정보를 제공합니다.

- **레거시 인증 및 조건부 액세스.** 조건부 액세스 정책을 통해 트리거되는 Multi-Factor Authentication 사용, 조건부 액세스 정책을 사용하는 앱을 포함하여 레거시 인증을 사용하는 앱 및 사용자에 대한 세부 정보를 제공합니다.

- **로그인 실패 분석.** 사용자 작업, 정책 문제 또는 인프라로 인해 로그인 오류가 발생하는지 확인하는 데 도움이 됩니다.

- **사용자 지정 보고서.** 통합 문서를 새로 만들거나 기존 통합 문서를 편집하여 조직의 인사이트 기능을 사용자 지정할 수 있습니다.

자세한 내용은 [Azure Monitor 통합 문서를 Azure Active Directory 보고서에 사용하는 방법](../reports-monitoring/howto-use-azure-monitor-workbooks.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---april-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 4월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 4월에 페더레이션이 지원되는 다음과 같은 신규 앱 21개가 앱 갤러리에 추가되었습니다.

[SAP Fiori](../saas-apps/sap-fiori-tutorial.md), [HRworks Single Sign-On](../saas-apps/hrworks-single-sign-on-tutorial.md), [Percolate](../saas-apps/percolate-tutorial.md), [MobiControl](../saas-apps/mobicontrol-tutorial.md), [Citrix NetScaler](../saas-apps/citrix-netscaler-tutorial.md), [Shibumi](../saas-apps/shibumi-tutorial.md), [Benchling](../saas-apps/benchling-tutorial.md), [MileIQ](https://mileiq.onelink.me/991934284/7e980085), [PageDNA](../saas-apps/pagedna-tutorial.md), [EduBrite LMS](../saas-apps/edubrite-lms-tutorial.md), [RStudio Connect](../saas-apps/rstudio-connect-tutorial.md), [AMMS](../saas-apps/amms-tutorial.md), [Mitel Connect](../saas-apps/mitel-connect-tutorial.md), [Alibaba Cloud(역할 기반 SSO)](../saas-apps/alibaba-cloud-service-role-based-sso-tutorial.md), [Certent Equity Management](../saas-apps/certent-equity-management-tutorial.md), [Sectigo Certificate Manager](../saas-apps/sectigo-certificate-manager-tutorial.md), [GreenOrbit](../saas-apps/greenorbit-tutorial.md), [Workgrid](../saas-apps/workgrid-tutorial.md), [monday.com](../saas-apps/mondaycom-tutorial.md), [SurveyMonkey Enterprise](../saas-apps/surveymonkey-enterprise-tutorial.md), [Indiggo](https://indiggolead.com/)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-access-reviews-frequency-option-and-multiple-role-selection"></a>새로운 액세스 검토 빈도 옵션 및 여러 역할 선택

**유형:** 새 기능 **서비스 범주:** 액세스 검토 **제품 기능:** ID 거버넌스

새로 업데이트된 Azure AD 액세스 검토를 통해 다음을 수행할 수 있습니다.

- 액세스 검토 빈도를 **반기** 로 변경합니다. 기존 옵션은 매주, 매월, 분기별 및 매년입니다.

- 단일 액세스 검토를 만들 때 여러 Azure AD 및 Azure 리소스 역할을 선택합니다. 이 경우 모든 역할이 동일한 설정을 사용하고 모든 검토자에게 동시에 알림이 표시됩니다.

액세스 검토를 만드는 방법에 대한 자세한 내용은 [Azure AD 액세스 검토에서 그룹 또는 애플리케이션의 액세스 검토 만들기](../governance/create-access-review.md)를 참조하세요.

---

### <a name="azure-ad-connect-email-alert-systems-are-transitioning-sending-new-email-sender-information-for-some-customers"></a>Azure AD Connect 이메일 경고 시스템을 전환하는 중이며, 일부 고객에게는 새 이메일 보낸 사람 정보를 보내는 중

**유형:** 변경된 기능 **서비스 범주:** AD Sync **제품 기능:** 플랫폼

Azure AD Connect는 이메일 경고 시스템을 전환하는 중이며, 일부 고객에게 새 이메일 보낸 사람을 표시할 수도 있습니다. 이를 해결하려면 조직의 허용 목록에 `azure-noreply@microsoft.com`을 추가해야 합니다. 그렇지 않으면 Office 365, Azure 또는 동기화 서비스에서 중요한 경고를 계속 받을 수 없습니다.

---

### <a name="upn-suffix-changes-are-now-successful-between-federated-domains-in-azure-ad-connect"></a>이제 Azure AD Connect의 페더레이션된 도메인 간에 UPN 접미사가 성공적으로 변경됨

**유형:** 수정된 **서비스 범주:** AD Sync **제품 기능:** 플랫폼

이제 Azure AD Connect의 페더레이션 도메인 간에 사용자의 UPN 접미사를 성공적으로 변경할 수 있습니다. 이 픽스는 동기화 주기 중에 FederatedDomainChangeError 오류 메시지가 표시되거나 "[FederatedUser.UserPrincipalName] 특성이 올바르지 않아 Azure Active Directory에서 이 개체를 업데이트할 수 없습니다. 로컬 디렉터리 서비스에서 값을 업데이트하세요"라는 내용의 알림 이메일을 받는 일이 더 이상 없다는 것을 의미합니다.

자세한 내용은 [동기화 오류 해결](../hybrid/tshoot-connect-sync-errors.md#federateddomainchangeerror)을 참조하세요.

---

### <a name="increased-security-using-the-app-protection-based-conditional-access-policy-in-azure-ad-public-preview"></a>Azure AD에서 앱 보호 기반 조건부 액세스 정책을 사용하여 보안 강화(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

이제 **앱 보호 필요** 정책을 사용하여 앱 보호 기반 조건부 액세스를 적용할 수 있습니다. 이 새로운 정책은 다음을 방지하여 조직의 보안을 강화하는 데 도움이 됩니다.

- 사용자가 Microsoft Intune 라이선스 없이 앱에 액세스할 수 없도록 차단

- 사용자가 Microsoft Intune 앱 보호 정책을 가져올 수 없도록 차단

- 구성된 Microsoft Intune 앱 보호 정책이 없으면 사용자가 앱에 액세스할 수 없도록 차단

자세한 내용은 [조건부 액세스를 사용하여 클라우드 앱 액세스에 앱 보호 정책을 요구하는 방법](../conditional-access/app-protection-based-conditional-access.md)을 참조하세요.

---

### <a name="new-support-for-azure-ad-single-sign-on-and-conditional-access-in-microsoft-edge-public-preview"></a>Microsoft Edge에서 Azure AD Single Sign-On 및 조건부 액세스에 대한 새 지원 추가(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

Azure AD Single Sign-On 및 조건부 액세스에 대한 새 지원을 제공하는 것을 포함하여 Microsoft Edge에 대한 Azure AD 지원이 향상되었습니다. 이전에 Microsoft Intune Managed Browser를 사용하던 경우 이제 Microsoft Edge를 대신 사용할 수 있습니다.

조건부 액세스를 사용하여 디바이스와 앱을 설정하고 관리하는 방법에 대한 자세한 내용은 [조건부 액세스를 사용하는 클라우드 앱에 액세스하려면 관리 디바이스 필요](../conditional-access/require-managed-devices.md) 및 [조건부 액세스를 사용하는 클라우드 앱에 액세스하려면 클라이언트 앱 필요](../conditional-access/app-based-conditional-access.md)를 참조하세요. Microsoft Intune 정책과 함께 Microsoft Edge를 사용하여 액세스를 관리하는 방법에 대한 자세한 내용은 [Microsoft Intune 정책 보호 브라우저를 사용하여 인터넷 액세스 관리](/intune/app-configuration-managed-browser)를 참조하세요.

---

## <a name="march-2019"></a>2019년 3월

### <a name="identity-experience-framework-and-custom-policy-support-in-azure-active-directory-b2c-is-now-available-ga"></a>Azure Active Directory B2C에서 Identity Experience Framework 및 사용자 지정 정책 지원 제공(GA)

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 규모에 맞게 Azure SLA에 따라 지원되는 다음 작업을 포함하여 Azure AD B2C에서 사용자 지정 정책을 만들 수 있습니다.

- 사용자 지정 정책을 사용하여 사용자 지정 인증 사용자 경험을 만들고 업로드합니다.

- 클레임 공급자 간의 교환으로 사용자 경험을 단계별로 설명합니다.

- 사용자 경험에서 조건부 분기를 정의합니다.

- 실시간 의사 결정 및 통신에 사용할 클레임을 변환하고 매핑합니다.

- 사용자 지정 인증 사용자 경험에서 REST API 사용 서비스를 사용합니다. 이메일 공급자, CRM 및 독점적 권한 부여 시스템을 예로 들 수 있습니다.

- OpenIDConnect 프로토콜과 호환되는 ID 공급자와 페더레이션합니다. 예를 들어 다중 테넌트 Azure AD, 소셜 계정 공급자 또는 2단계 인증 공급자와 페더레이션합니다.

사용자 지정 정책을 만드는 방법에 대한 자세한 내용은 [Azure Active Directory B2C의 사용자 지정 정책에 대한 개발자 정보](../../active-directory-b2c/custom-policy-developer-notes.md) 및 [사례 연구가 포함된 Alex Simon의 블로그 게시물](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-AD-B2C-custom-policies-to-build-your-own-identity-journeys/ba-p/382791)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---march-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2019년 3월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 3월에 페더레이션이 지원되는 다음과 같은 신규 앱 14개가 앱 갤러리에 추가되었습니다.

[ISEC7 Mobile Exchange Delegate](https://www.isec7.com/english/), [MediusFlow](https://office365.cloudapp.mediusflow.com/), [ePlatform](../saas-apps/eplatform-tutorial.md), [Fulcrum](../saas-apps/fulcrum-tutorial.md), [ExcelityGlobal](../saas-apps/excelityglobal-tutorial.md), [Explanation-Based Auditing System](../saas-apps/explanation-based-auditing-system-tutorial.md), [Lean](../saas-apps/lean-tutorial.md), [Powerschool Performance Matters](../saas-apps/powerschool-performance-matters-tutorial.md), [Cinode](https://cinode.com/), [Iris Intranet](../saas-apps/iris-intranet-tutorial.md), [Empactis](../saas-apps/empactis-tutorial.md), [SmartDraw](../saas-apps/smartdraw-tutorial.md), [Confirmit Horizons](../saas-apps/confirmit-horizons-tutorial.md), [TAS](../saas-apps/tas-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-zscaler-and-atlassian-provisioning-connectors-in-the-azure-ad-gallery---march-2019"></a>Azure AD 갤러리의 새로운 Zscaler 및 Atlassian 프로비저닝 커넥터 - 2019년 3월

**유형:** 새 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** 타사 통합

다음과 같은 앱에 대한 사용자 계정을 만들고, 업데이트하고, 삭제하는 작업을 자동화합니다.

[Zscaler](../saas-apps/zscaler-provisioning-tutorial.md), [Zscaler Beta](../saas-apps/zscaler-beta-provisioning-tutorial.md), [Zscaler One](../saas-apps/zscaler-one-provisioning-tutorial.md), [Zscaler Two](../saas-apps/zscaler-two-provisioning-tutorial.md), [Zscaler Three](../saas-apps/zscaler-three-provisioning-tutorial.md), [Zscaler ZSCloud](../saas-apps/zscaler-zscloud-provisioning-tutorial.md), [Atlassian Cloud](../saas-apps/atlassian-cloud-provisioning-tutorial.md)

자동화된 사용자 계정 프로비저닝을 통해 조직의 보안을 강화하는 방법에 대한 자세한 내용은 [Azure AD를 사용하여 SaaS 애플리케이션에 대한 사용자 프로비저닝 자동화](../app-provisioning/user-provisioning.md)를 참조하세요.

---

### <a name="restore-and-manage-your-deleted-office-365-groups-in-the-azure-ad-portal"></a>Azure AD 포털에서 삭제된 Office 365 그룹 복원 및 관리

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이제 Azure AD 포털에서 삭제된 Office 365 그룹을 보고 관리할 수 있습니다. 이번에 바뀌는 기능을 활용하면 복원에 사용할 수 있는 그룹을 확인하고 조직에 필요 없는 그룹을 영구적으로 삭제할 수 있습니다.

자세한 내용은 [만료되거나 삭제된 그룹 복원](../enterprise-users/groups-restore-deleted.md#view-and-manage-the-deleted-microsoft-365-groups-that-are-available-to-restore)을 참조하세요.

---

### <a name="single-sign-on-is-now-available-for-azure-ad-saml-secured-on-premises-apps-through-application-proxy-public-preview"></a>이제 애플리케이션 프록시를 통해 Azure AD SAML로 보호되는 온-프레미스 앱에 Single Sign-On 사용 가능(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

이제 온-프레미스 SAML 인증 앱에 SSO(Single Sign-On) 환경을 제공하고 애플리케이션 프록시를 통해 이러한 앱에 원격으로 액세스할 수 있습니다. 온-프레미스 앱에서 SAML SSO를 설정하는 방법에 대한 자세한 내용은 [애플리케이션 프록시를 사용하여 온-프레미스 애플리케이션에 SAML Single Sign-On(미리 보기)](../manage-apps/application-proxy-configure-single-sign-on-on-premises-apps.md)을 참조하세요.

---

### <a name="client-apps-in-request-loops-will-be-interrupted-to-improve-reliability-and-user-experience"></a>안정성 및 사용자 환경을 개선하기 위해 요청 루프의 클라이언트 앱이 중단됩니다.

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

클라이언트 앱이 짧은 시간 동안 수백 개의 동일한 로그인 요청을 잘못 발행할 수 있습니다. 이러한 요청은 성공 여부에 관계 없이 사용자 환경의 성능을 저하시키고 IDP 워크로드를 늘리므로 모든 사용자의 대기 시간이 증가하고 IDP 가용성이 떨어집니다.

이 업데이트는 정상 작동 범위를 벗어난 짧은 시간 동안 중복 요청을 여러 번 실행하는 클라이언트 앱에 `invalid_grant` 오류: `AADSTS50196: The server terminated an operation because it encountered a loop while processing a request`를 보냅니다. 이 문제가 발생하는 클라이언트 앱은 사용자에게 다시 로그인할 것을 요구하는 대화형 프롬프트를 표시합니다. 이번에 바뀌는 내용과 이 오류가 발생할 경우 앱을 수정하는 방법에 대한 자세한 내용은 [인증의 새로운 기능](../develop/reference-breaking-changes.md#looping-clients-will-be-interrupted)을 참조하세요.

---

### <a name="new-audit-logs-user-experience-now-available"></a>새 감사 로그 사용자 환경 사용 가능

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

가독성을 높이고 정보 검색 방법을 개선하는 데 도움이 되는 새 Azure AD **감사 로그** 페이지를 만들었습니다. 새 **감사 로그** 페이지를 보려면 Azure AD의 **활동** 섹션에서 **감사 로그** 를 선택합니다.

![샘플 정보가 포함된 새 감사 로그 페이지](media/whats-new/audit-logs-page.png)

새 **감사 로그** 페이지에 대한 자세한 내용은 [Azure Active Directory 포털의 감사 활동 보고서](../reports-monitoring/concept-audit-logs.md#audit-logs)를 참조하세요.

---

### <a name="new-warnings-and-guidance-to-help-prevent-accidental-administrator-lockout-from-misconfigured-conditional-access-policies"></a>잘못 구성된 조건부 액세스 정책 때문에 의도치 않게 관리자가 잠기는 일이 없도록 새로운 경고 및 지침 도입

**유형:** 변경된 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

잘못 구성된 조건부 액세스 정책을 통해 관리자가 의도치 않게 테넌트에서 자신을 잠그는 일이 없도록, Azure Portal에 새로운 경고와 업데이트된 지침을 만들었습니다. 새 지침에 대한 자세한 내용은 [Azure Active Directory 조건부 액세스의 서비스 종속성](../conditional-access/service-dependencies.md)을 참조하세요.

---

### <a name="improved-end-user-terms-of-use-experiences-on-mobile-devices"></a>모바일 디바이스의 최종 사용자 사용 약관 환경 개선

**유형:** 변경된 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

모바일 디바이스에서 사용 약관을 검토하고 동의하는 방법을 개선하기 위해 기존 사용 약관 환경을 업데이트했습니다. 이제 화면을 확대/축소하고, 뒤로 돌아가고, 정보를 다운로드하고, 하이퍼링크를 선택할 수 있습니다. 업데이트된 사용 약관에 대한 자세한 내용은 [Azure Active Directory 사용 약관 기능](../conditional-access/terms-of-use.md#what-terms-of-use-looks-like-for-users)을 참조하세요.

---

### <a name="new-azure-ad-activity-logs-download-experience-available"></a>새 Azure AD 활동 로그 다운로드 환경 사용 가능

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

이제 Azure Portal에서 직접 대량의 활동 로그를 다운로드할 수 있습니다. 이 업데이트를 통해 다음을 수행할 수 있습니다.

- 최대 250,000개의 행을 다운로드합니다.

- 다운로드가 완료되면 알림을 받습니다.

- 파일 이름을 사용자 지정합니다.

- 출력 형식(JSON 또는 CSV)을 결정합니다.

이 기능에 대한 자세한 내용은 [빠른 시작: Azure Portal을 사용하여 감사 보고서 다운로드](../reports-monitoring/quickstart-download-audit-report.md)를 참조하세요.

---

### <a name="breaking-change-updates-to-condition-evaluation-by-exchange-activesync-eas"></a>호환성이 손상되는 변경 내용: EAS(Exchange ActiveSync)의 조건 평가 업데이트

**유형:** 변경 계획 **서비스 범주:** 조건부 액세스 **제품 기능:** Access Control

EAS(Exchange ActiveSync)에서 다음 조건을 평가하는 방법을 업데이트하는 중입니다.

- 국가, 지역 또는 IP 주소를 기준으로 하는 사용자 위치

- 로그인 위험

- 디바이스 플랫폼

이전에 조건부 액세스 정책에서 이러한 조건을 사용한 경우 조건 동작이 변경될 수 있다는 점에 유의해야 합니다. 예를 들어 이전에 정책에서 사용자 위치 조건을 사용한 경우 이제 사용자의 위치에 따라 정책을 건너뛰는 것을 볼 수 있습니다.

---

## <a name="february-2019"></a>2019년 2월

### <a name="configurable-azure-ad-saml-token-encryption-public-preview"></a>구성 가능한 Azure AD SAML 토큰 암호화(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

이제 암호화된 SAML 토큰을 수신하도록 지원되는 SAML 앱을 구성할 수 있습니다. 앱에서 Azure AD를 구성하고 사용하는 경우 Azure AD는 Azure AD에 저장된 인증서에서 얻은 공개 키를 사용하여 내보낸 SAML 어설션을 암호화합니다.

SAML 토큰 암호화 구성에 대한 자세한 내용은 [Azure AD SAML 토큰 암호화 구성](../manage-apps/howto-saml-token-encryption.md)을 참조하세요.

---

### <a name="create-an-access-review-for-groups-or-apps-using-azure-ad-access-reviews"></a>Azure AD 액세스 검토를 사용하여 그룹 또는 앱에 대한 액세스 검토 만들기

**유형:** 새 기능 **서비스 범주:** 액세스 검토 **제품 기능:** 거버넌스

이제 그룹 멤버 자격 또는 앱 할당에 대한 단일 Azure AD 액세스 검토에 여러 그룹 또는 앱을 포함할 수 있습니다. 여러 그룹 또는 앱을 사용하는 액세스 검토는 동일한 설정을 사용하여 지정되며 포함된 모든 검토자에게 동시에 알림이 제공됩니다.

Azure AD 액세스 검토를 사용하여 액세스 검토를 만드는 방법에 대한 자세한 내용은 [Azure AD 액세스 검토에서 그룹 또는 애플리케이션의 액세스 검토 만들기](../governance/create-access-review.md)를 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---february-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱 - 2019년 2월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 2월에 페더레이션이 지원되는 다음과 같은 신규 앱 27개가 앱 갤러리에 추가되었습니다.

[Euromonitor Passport](../saas-apps/euromonitor-passport-tutorial.md), [MindTickle](../saas-apps/mindtickle-tutorial.md), [FAT FINGER](https://seeforgetest-exxon.azurewebsites.net/Account/create?Length=7), [AirStack](../saas-apps/airstack-tutorial.md), [Oracle Fusion ERP](../saas-apps/oracle-fusion-erp-tutorial.md), [IDrive](../saas-apps/idrive-tutorial.md), [Skyward Qmlativ](../saas-apps/skyward-qmlativ-tutorial.md), [Brightidea](../saas-apps/brightidea-tutorial.md), [AlertOps](../saas-apps/alertops-tutorial.md), [Soloinsight-CloudGate SSO](../saas-apps/soloinsight-cloudgate-sso-tutorial.md), Permission Click, [Brandfolder](../saas-apps/brandfolder-tutorial.md), [StoregateSmartFile](../saas-apps/smartfile-tutorial.md), [Pexip](../saas-apps/pexip-tutorial.md), [Stormboard](../saas-apps/stormboard-tutorial.md), [Seismic](../saas-apps/seismic-tutorial.md), [Share A Dream](https://www.shareadream.org/how-it-works), [Bugsnag](../saas-apps/bugsnag-tutorial.md), [webMethods Integration Cloud](../saas-apps/webmethods-integration-cloud-tutorial.md), [Knowledge Anywhere LMS](../saas-apps/knowledge-anywhere-lms-tutorial.md), [OU Campus](../saas-apps/ou-campus-tutorial.md), [Periscope Data](../saas-apps/periscope-data-tutorial.md), [Netop Portal](../saas-apps/netop-portal-tutorial.md), [smartvid.io](../saas-apps/smartvid.io-tutorial.md), [PureCloud by Genesys](../saas-apps/purecloud-by-genesys-tutorial.md), [ClickUp Productivity Platform](../saas-apps/clickup-productivity-platform-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="enhanced-combined-mfasspr-registration"></a>향상된 통합 MFA/SSPR 등록

**유형:** 변경된 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 사용자 인증

고객 피드백에 대한 응답으로, 사용자가 MFA와 SSPR에 대한 보안 정보를 더 빠르게 등록할 수 있도록 통합 MFA/SSPR 등록 미리 보기 환경을 개선했습니다.

**현재 사용자에게 개선된 환경을 사용하려면 다음 단계를 수행합니다.**

1. 전역 관리자 또는 사용자 관리자로 Azure Portal에 로그인하고, **Azure Active Directory > 사용자 설정 > 액세스 패널 미리 보기 기능의 설정 관리** 로 이동합니다.

2. **미리 보기 기능을 사용하여 보안 정보를 등록하고 관리할 수 있는 사용자 - 새로 고침** 옵션에서 **선택한 사용자 그룹** 또는 **모든 사용자** 에 기능을 사용하도록 선택합니다.

앞으로 몇 주 동안, 기존의 통합 MFA/SSPR 등록 미리 보기 환경이 아직 켜지지 않은 테넌트에서 이 기능을 제거할 예정입니다.

**본인의 테넌트에 대한 컨트롤이 제거되는지 확인하려면 다음 단계를 수행합니다.**

1. 전역 관리자 또는 사용자 관리자로 Azure Portal에 로그인하고, **Azure Active Directory > 사용자 설정 > 액세스 패널 미리 보기 기능의 설정 관리** 로 이동합니다.

2. **미리 보기 기능을 사용하여 보안 정보를 등록하고 관리할 수 있는 사용자** 옵션이 **없음** 으로 설정되어 있으면 테넌트에서 해당 옵션이 제거됩니다.

사용자에게 기존의 통합 MFA/SSPR 등록 미리 보기 환경을 제공하도록 설정했는지 여부에 관계없이, 이전 환경은 언젠가는 해제됩니다. 따라서 향상된 새 환경으로 최대한 빨리 전환하는 것이 좋습니다.

향상된 등록 환경에 대한 자세한 내용은 [Azure AD 통합 MFA 및 암호 재설정 등록 환경의 향상된 기능](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Cool-enhancements-to-the-Azure-AD-combined-MFA-and-password/ba-p/354271)을 참조하세요.

---

### <a name="updated-policy-management-experience-for-user-flows"></a>사용자 흐름에 대한 정책 관리 환경 업데이트

**유형:** 변경된 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

사용자 흐름에 대한 정책 만들기 및 관리 프로세스(이전의 기본 제공 정책)를 더 쉽게 업데이트했습니다. 이 새로운 환경은 이제 모든 Azure AD 테넌트의 기본값입니다.

포털 화면 위쪽의 **피드백 보내기** 영역에서 웃는 얼굴 또는 찡그린 얼굴 아이콘을 사용하여 추가 피드백과 제안 사항을 보낼 수 있습니다.

새로운 정책 관리 환경에 대한 자세한 내용은 [Azure AD B2C now has JavaScript customization and many more new features(이제 JavaScript 사용자 지정 및 여러 가지 새 기능을 제공하는 Azure AD B2C)](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-AD-B2C-now-has-JavaScript-customization-and-many-more-new/ba-p/353595) 블로그를 참조하세요.

---

### <a name="choose-specific-page-element-versions-provided-by-azure-ad-b2c"></a>Azure AD B2C에서 제공하는 특정 페이지 요소 버전 선택

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 Azure AD B2C에서 제공하는 특정 버전의 페이지 요소를 선택할 수 있습니다. 특정 버전을 선택하여 페이지에 표시되기 전에 업데이트를 테스트하여 예측 가능한 동작을 얻을 수 있습니다. 또한 이제 특정 페이지 버전을 적용하여 JavaScript 사용자 지정을 허용하도록 선택할 수 있습니다. 이 기능을 켜려면 사용자 흐름에서 **속성** 페이지로 이동합니다.

페이지 요소의 특정 버전 선택에 대한 자세한 내용은 [Azure AD B2C now has JavaScript customization and many more new features(이제 JavaScript 사용자 지정 및 여러 가지 새 기능을 제공하는 Azure AD B2C)](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-AD-B2C-now-has-JavaScript-customization-and-many-more-new/ba-p/353595) 블로그를 참조하세요.

---

### <a name="configurable-end-user-password-requirements-for-b2c-ga"></a>B2C에 대한 구성 가능한 최종 사용자 암호 요구 사항(GA)

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 기본 Azure AD 암호 정책을 사용하는 대신, 최종 사용자에 대한 조직의 암호 복잡성을 설정할 수 있습니다. 사용자 흐름의 **속성** 블레이드(이전의 기본 제공 정책)에서 암호 복잡성을 **단순** 또는 **강력** 중에 선택할 수도 있고, **사용자 지정** 요구 사항 세트를 만들 수도 있습니다.

암호 복잡성 요구 사항 구성에 대한 자세한 내용은 [Azure Active Directory B2C에서 암호의 복잡성 요구 사항 구성](../../active-directory-b2c/user-flow-password-complexity.md)을 참조하세요.

---

### <a name="new-default-templates-for-custom-branded-authentication-experiences"></a>사용자 지정 브랜드 인증 환경의 새로운 기본 템플릿

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

사용자 흐름의 **페이지 레이아웃** 블레이드(이전의 기본 제공 정책)에 있는 새로운 기본 템플릿을 사용하여 사용자를 위한 사용자 지정 브랜드 인증 환경을 만들 수 있습니다.

템플릿 사용에 대한 자세한 내용은 [Azure AD B2C now has JavaScript customization and many more new features(이제 JavaScript 사용자 지정 및 여러 가지 새 기능을 제공하는 Azure AD B2C)](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-AD-B2C-now-has-JavaScript-customization-and-many-more-new/ba-p/353595) 블로그를 참조하세요.

---

## <a name="january-2019"></a>2019년 1월

### <a name="active-directory-b2b-collaboration-using-one-time-passcode-authentication-public-preview"></a>일회용 암호 인증을 사용하여 Active Directory B2B 협업(공용 미리 보기)

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C

Azure AD MSA(Microsoft 계정) 또는 Google 페더레이션 등의 다른 수단을 통해 인증할 수 없는 B2B 게스트 사용자를 위해 OTP(일회용 암호 인증)를 도입했습니다. 이 새로운 인증 방법을 사용하면 게스트 사용자가 새 Microsoft 계정을 만들 필요가 없습니다. 그 대신 초대를 사용하거나 공유 리소스에 액세스하는 동안 게스트 사용자는 임시 코드를 이메일 주소로 보내 줄 것을 요청할 수 있습니다. 게스트 사용자는 이 임시 코드를 사용하여 계속 로그인할 수 있습니다.

자세한 내용은 [이메일 일회용 암호 인증(미리 보기)](../external-identities/one-time-passcode.md) 및 [Azure AD가 계정이 있는 모든 사용자가 원활하게 공유 및 협업하도록 하는](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-AD-makes-sharing-and-collaboration-seamless-for-any-user/ba-p/325949) 블로그를 참조하세요.

### <a name="new-azure-ad-application-proxy-cookie-settings"></a>새 Azure AD 애플리케이션 프록시 쿠키 설정

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

애플리케이션 프록시를 통해 게시되는 앱에 사용 가능한 새 쿠키 설정 3개가 도입되었습니다.

- **HTTP 전용 쿠키 사용.** 애플리케이션 프록시 액세스 및 세션 쿠키에 **HTTPOnly** 플래그를 설정합니다. 이 설정을 켜면 클라이언트 쪽 스크립팅을 통한 쿠키 복사나 수정을 방지할 수 있는 등 추가적인 보안 이점이 제공됩니다. 추가 이점을 활용하려면 **예** 를 선택하여 이 플래그를 켜는 것이 좋습니다.

- **보안 쿠키 사용.** 애플리케이션 프록시 액세스 및 세션 쿠키에 **Secure** 플래그를 설정합니다. 이 설정을 켜면 HTTPS 등의 TLS 보안 채널을 통해서만 쿠키가 전송되므로 추가적인 보안 이점이 제공됩니다. 추가 이점을 활용하려면 **예** 를 선택하여 이 플래그를 켜는 것이 좋습니다.

- **영구적 쿠키 사용.** 웹 브라우저를 닫을 때 액세스 쿠키가 만료되지 않습니다. 이러한 쿠키는 액세스 토큰의 수명 동안 유지됩니다. 그러나 만료 시간이 되거나 사용자가 쿠키를 수동으로 삭제하면 쿠키가 재설정됩니다. 기본 설정인 **아니요** 를 유지하고 프로세스 간에 쿠키를 공유하지 않는 구형 앱에서만 설정을 켜는 것이 좋습니다.

새 쿠키에 대한 자세한 내용은 [Azure Active Directory에서 온-프레미스 애플리케이션에 액세스하기 위한 쿠키 설정](../manage-apps/application-proxy-configure-cookie-settings.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---january-2019"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새 페더레이션된 앱 - 2019년 1월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2019년 1월에 페더레이션이 지원되는 다음의 신규 앱 35개가 앱 갤러리에 추가되었습니다.

[Firstbird](../saas-apps/firstbird-tutorial.md), [Folloze](../saas-apps/folloze-tutorial.md), [Talent Palette](../saas-apps/talent-palette-tutorial.md), [Infor CloudSuite](../saas-apps/infor-cloud-suite-tutorial.md), [Cisco Umbrella](../saas-apps/cisco-umbrella-tutorial.md), [Zscaler Internet Access Administrator](../saas-apps/zscaler-internet-access-administrator-tutorial.md), [Expiration Reminder](../saas-apps/expiration-reminder-tutorial.md), [InstaVR Viewer](../saas-apps/instavr-viewer-tutorial.md), [CorpTax](../saas-apps/corptax-tutorial.md), [Verb](https://app.verb.net/login), [OpenLattice](https://openlattice.com/agora), [TheOrgWiki](https://www.theorgwiki.com/signup), [Pavaso Digital Close](../saas-apps/pavaso-digital-close-tutorial.md), [GoodPractice Toolkit](../saas-apps/goodpractice-toolkit-tutorial.md), [Cloud Service PICCO](../saas-apps/cloud-service-picco-tutorial.md), [AuditBoard](../saas-apps/auditboard-tutorial.md), [iProva](../saas-apps/iprova-tutorial.md), [Workable](../saas-apps/workable-tutorial.md), [CallPlease](https://webapp.callplease.com/create-account/create-account.html), [GTNexus SSO System](../saas-apps/gtnexus-sso-module-tutorial.md), [CBRE ServiceInsight](../saas-apps/cbre-serviceinsight-tutorial.md), [Deskradar](../saas-apps/deskradar-tutorial.md), [Coralogixv](../saas-apps/coralogix-tutorial.md), [Signagelive](../saas-apps/signagelive-tutorial.md), [ARES for Enterprise](../saas-apps/ares-for-enterprise-tutorial.md), [K2 for Office 365](https://www.k2.com/O365), [Xledger](https://www.xledger.net/), [iDiD Manager](../saas-apps/idid-manager-tutorial.md), [HighGear](../saas-apps/highgear-tutorial.md), [Visitly](../saas-apps/visitly-tutorial.md), [Korn Ferry ALP](../saas-apps/korn-ferry-alp-tutorial.md), [Acadia](../saas-apps/acadia-tutorial.md), [Adoddle cSaas Platform](../saas-apps/adoddle-csaas-platform-tutorial.md)<!-- , [CaféX Portal (Meetings)](https://docs.microsoft.com/azure/active-directory/saas-apps/cafexportal-meetings-tutorial), [MazeMap Link](https://docs.microsoft.com/azure/active-directory/saas-apps/mazemaplink-tutorial)-->

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-azure-ad-identity-protection-enhancements-public-preview"></a>새로운 Azure AD ID 보호 향상 기능(공개 미리 보기)

**유형:** 변경된 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

Azure AD ID 보호 공개 미리 보기 제품에는 다음과 같은 향상 기능이 추가되었습니다.

- 업데이트되고 더욱 긴밀하게 통합된 사용자 인터페이스

- 추가 API

- 기계 학습을 통해 향상된 위험 평가

- 제품 전반에 걸쳐 일관된 위험한 사용자 및 위험한 로그인 정보 제공

향상 기능에 대한 자세한 내용은 [갱신된 Azure Active Directory ID 보호 소개](../identity-protection/overview-identity-protection.md)를 참조하세요. 여기서 자세한 내용을 알아보고 제품 내 프롬프트를 통해 정보를 공유하는 방법을 파악할 수 있습니다.

---

### <a name="new-app-lock-feature-for-the-microsoft-authenticator-app-on-ios-and-android-devices"></a>iOS 및 Android 디바이스의 Microsoft Authenticator 앱용 신규 앱 잠금 기능

**유형:** 새 기능 **서비스 범주:** Microsoft Authenticator 앱 **제품 기능:** ID 보안 및 보호

일회용 암호, 앱 정보 및 앱 설정을 더욱 안전하게 유지하려는 경우 Microsoft Authenticator 앱에서 앱 잠금 기능을 설정하면 됩니다. 앱 잠금을 설정하면 Microsoft Authenticator 앱을 열 때마다 PIN이나 생체 인식 정보를 사용하여 인증을 하라는 메시지가 표시됩니다.

자세한 내용은 [Microsoft Authenticator 앱 FAQ](../user-help/user-help-auth-app-faq.md)를 참조하세요.

---

### <a name="enhanced-azure-ad-privileged-identity-management-pim-export-capabilities"></a>향상된 Azure AD PIM(Privileged Identity Management) 내보내기 기능

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

이제 PIM(Privileged Identity Management) 관리자는 특정 리소스에 대한 모든 활성/적격 역할 할당(모든 자식 리소스에 대한 역할 할당 포함)을 내보낼 수 있습니다. 이전에는 관리자가 구독의 역할 할당 전체 목록을 가져오기가 어려웠으며, 각 특정 리소스의 역할 할당을 내보내야 했습니다.

자세한 내용은 [PIM에서 Azure 리소스 역할에 대한 활동 및 감사 기록 보기](../privileged-identity-management/azure-pim-resource-rbac.md)를 참조하세요.

---

## <a name="novemberdecember-2018"></a>2018년 11월/12월

### <a name="users-removed-from-synchronization-scope-no-longer-switch-to-cloud-only-accounts"></a>동기화 범위에서 제거된 사용자는 더 이상 클라우드 전용 계정으로 전환되지 않습니다.

**유형:** 수정된 **서비스 범주:** 사용자 관리 **제품 기능:** 디렉터리

>[!Important]
>이 수정으로 인한 불편이 접수되어 해당 내용을 파악하였습니다. 따라서, 조직 내에서 더 쉽게 구현할 수 있게 수정할 수 있을 때까지 이 변경 사항을 다시 되돌렸습니다.

AD DS(Active Directory Domain Services) 개체가 동기화 범위에서 제외된 다음, 다음과 같은 동기화 주기에서 Azure AD의 휴지통으로 이동될 때 사용자의 DirSyncEnabled 플래그가 **False** 로 잘못 전환되는 버그를 수정했습니다. 이렇게 수정하면 사용자가 동기화 범위에서 제외되고 나중에 Azure AD 휴지통에서 복원되는 경우 인증 원본(SoA)이 온-프레미스 AD로 유지되므로 예상대로 사용자 계정은 온-프레미스 AD에서 동기화된 상태를 유지하고, 클라우드에서 관리될 수 없습니다.

이 문제를 해결하기 전에 DirSyncEnabled 플래그가 False로 전환되는 문제가 발생했습니다. 이로 인해 이러한 계정이 클라우드 전용 개체로 변환되고 클라우드에서 관리될 수 있다는 잘못된 인상을 주었습니다. 그러나 해당 계정은 해당 SoA를 온-프레미스 및 온-프레미스 AD에서 비롯되어 동기화된 모든 속성(섀도 특성)으로 보유했습니다. 이 조건으로 인해 이러한 계정을 AD에서 동기화되도록 처리하는 Azure AD 및 기타 클라우드 워크로드(예: Exchange Online)에서 여러 문제가 발생했지만 이제 클라우드 전용 계정처럼 작동하고 있습니다.

이때 AD의 동기화 계정을 클라우드 전용 계정으로 진정하게 변환하는 유일한 방법은 테넌트 수준에서 DirSync를 사용하지 않도록 설정하는 것입니다. 그러면 SoA를 전송하는 백 엔드 작업을 트리거하게 됩니다. 이러한 형식으로 SoA를 변경하려면 모든 온-프레미스 관련 특성(예: LastDirSyncTime 및 섀도 특성)을 정리하고 다른 클라우드 워크로드에 신호를 보내서 해당 개체를 클라우드 전용 계정으로 변환해야 합니다(단, 이에 국한되지 않음).

이렇게 수정하면 결과적으로 AD에서 동기화된 사용자의 ImmutableID 특성에 대한 직접 업데이트를 방지합니다. 이 작업은 과거의 일부 시나리오에 요구되었습니다. Azure AD에 있는 개체의 ImmutableID는 이름에서 알 수 있듯이 기본적으로 변경할 수 없습니다. Azure AD Connect Health 및 Azure AD Connect 동기화 클라이언트에서 구현된 새 기능은 다음과 같은 시나리오를 해결하기 위해 제공됩니다.

- **많은 사용자에 대한 단계별 접근 방식의 대규모 ImmutableID 업데이트**

  예를 들어, 오랫동안 AD DS 포리스트 간 마이그레이션을 수행해야 합니다. 해결 방법: Azure AD Connect를 사용하여 **원본 앵커를 구성** 하고 사용자가 마이그레이션한 대로 기존 ImmutableID 값을 Azure AD에서 새 포리스트에 있는 로컬 AD DS 사용자의 ms-DS-Consistency-Guid 특성으로 복사합니다. 자세한 내용은 [ms-DS-ConsistencyGuid를 sourceAnchor로 사용](../hybrid/plan-connect-design-concepts.md#using-ms-ds-consistencyguid-as-sourceanchor)을 참조하세요.

- **많은 사용자에 대한 동시 대규모 ImmutableID 업데이트**

  예를 들어, Azure AD Connect를 구현하는 동안 실수가 있었기 때문에 이제 SourceAnchor 특성을 변경해야 합니다. 해결 방법: 테넌트 수준에서 DirSync를 사용하지 않도록 설정하고 잘못된 모든 ImmutableID 값을 지웁니다. 자세한 내용은 [Office 365에서 디렉터리 동기화 끄기](/office365/enterprise/turn-off-directory-synchronization)를 참조하세요.

- **Azure AD에서 기존 사용자와 온-프레미스 사용자 다시 일치** 예를 들어 AD DS에서 다시 생성된 사용자가 기존 Azure AD 계정(분리된 개체)를 사용하여 다시 일치시키는 대신 Azure AD 계정에 중복을 생성합니다. 해결 방법: Azure Portal에서 Azure AD Connect Health를 사용하여 원본 앵커/ImmutableID를 다시 매핑합니다. 자세한 내용은 [분리된 개체 시나리오](../hybrid/how-to-connect-health-diagnose-sync-errors.md#orphaned-object-scenario)를 참조하세요.

### <a name="breaking-change-updates-to-the-audit-and-sign-in-logs-schema-through-azure-monitor"></a>주요 변경 내용: Azure Monitor를 통한 감사 및 로그인 로그 스키마에 대한 업데이트

**유형:** 변경된 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

현재 Azure Monitor를 통해 감사 및 로그인 로그 스트림을 둘 다 게시하고 있으므로 SIEM 도구나 Log Analytics를 사용하여 로그 파일을 원활하게 통합할 수 있습니다. 피드백에 따라, 그리고 이 기능의 일반 공급 알림에 대한 준비 작업으로 스키마를 다음과 같이 변경하고 있습니다. 이러한 스키마 변경 내용 및 관련된 문서 업데이트는 1월 첫째 주까지 수행될 예정입니다.

#### <a name="new-fields-in-the-audit-schema"></a>감사 스키마의 새 필드
리소스에 대해 수행된 작업 유형을 제공하기 위해 **작업 유형** 필드가 추가됩니다. 예를 들어 **추가**, **업데이트** 또는 **삭제** 입니다.

#### <a name="changed-fields-in-the-audit-schema"></a>감사 스키마의 변경된 필드
감사 스키마에서 다음 필드가 변경됩니다.

|필드 이름|변경 내용|이전 값|새 값|
|----------|------------|----------|----------|
|Category|이전에는 **서비스 이름** 필드였습니다. 이제 **감사 범주** 필드입니다. **서비스 이름** 이 **loggedByService** 필드로 이름이 변경되었습니다.|<ul><li>계정 프로비전</li><li>핵심 디렉터리</li><li>셀프 서비스 암호 재설정</li></ul>|<ul><li>사용자 관리</li><li>그룹 관리</li><li>앱 관리</li></ul>|
|targetResources|최상위 수준에 **TargetResourceType** 을 포함합니다.|&nbsp;|<ul><li>정책</li><li>앱</li><li>사용자</li><li>그룹</li></ul>|
|loggedByService|감사 로그를 생성한 서비스의 이름을 제공합니다.|Null|<ul><li>계정 프로비전</li><li>핵심 디렉터리</li><li>셀프 서비스 암호 재설정</li></ul>|
|결과|감사 로그의 결과를 제공합니다. 이전에는 열거형이었지만 이제 실제 값을 표시합니다.|<ul><li>0</li><li>1</li></ul>|<ul><li>Success</li><li>실패</li></ul>|

#### <a name="changed-fields-in-the-sign-in-schema"></a>로그인 스키마의 변경된 필드
로그인 스키마에서 다음 필드가 변경됩니다.

|필드 이름|변경 내용|이전 값|새 값|
|----------|------------|----------|----------|
|appliedConditionalAccessPolicies|이전에는 **conditionalaccessPolicies** 필드였습니다. 이제 **appliedConditionalAccessPolicies** 필드입니다.|변경 내용 없음|변경 내용 없음|
|conditionalAccessStatus|로그인 시 조건부 액세스 정책 상태의 결과를 제공합니다. 이전에는 열거형이었지만 이제 실제 값을 표시합니다.|<ul><li>0</li><li>1</li><li>2</li><li>3</li></ul>|<ul><li>Success</li><li>실패</li><li>적용되지 않음</li><li>사용 안 함</li></ul>|
|appliedConditionalAccessPolicies: 결과|로그인 시 개별 조건부 액세스 정책 상태의 결과를 제공합니다. 이전에는 열거형이었지만 이제 실제 값을 표시합니다.|<ul><li>0</li><li>1</li><li>2</li><li>3</li></ul>|<ul><li>Success</li><li>실패</li><li>적용되지 않음</li><li>사용 안 함</li></ul>|

스키마에 대한 자세한 내용은 [Azure Monitor(미리 보기)에서 Azure AD 감사 로그 스키마 해석](../reports-monitoring/reference-azure-monitor-audit-log-schema.md)을 참조하세요.

---

### <a name="identity-protection-improvements-to-the-supervised-machine-learning-model-and-the-risk-score-engine"></a>감독된 기계 학습 모델 및 위험 점수 엔진의 ID 보호 개선

**유형:** 변경된 기능 **서비스 범주:** Identity Protection **제품 기능:** 위험 점수

ID 보호 관련 사용자 및 로그인 위험 평가 엔진이 개선되어 사용자 위험 정확도 및 적용 범위를 향상하는 데 도움이 됩니다. 관리자는 사용자 위험 수준이 특정 검색의 위험 수준에 더 이상 직접 연결되지 않으며 위험한 로그인 이벤트 수와 수준이 증가함을 확인할 수도 있습니다.

이제 위험 검색이 감독된 기계 학습 모델에서 평가되며, 이 모델은 사용자 로그인 및 검색 패턴의 추가 기능을 사용하여 사용자 위험을 계산합니다. 이 모델을 기준으로, 관리자는 사용자와 관련된 검색 위험이 낮거나 중간 수준이더라도 위험 점수가 높은 사용자를 발견할 수 있습니다.

---

### <a name="administrators-can-reset-their-own-password-using-the-microsoft-authenticator-app-public-preview"></a>관리자는 Microsoft 인증자 앱(공개 미리 보기)을 사용하여 자신의 암호를 재설정할 수 있습니다.

**유형:** 변경된 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 사용자 인증

이제 Azure AD 관리자는 Microsoft 인증자 앱 알림이나 임의의 모바일 인증자 앱 또는 하드웨어 토큰의 코드를 사용하여 자신의 암호를 재설정할 수 있습니다. 자신의 암호를 재설정하기 위해 관리자는 이제 다음 두 가지 방법 중 하나를 사용할 수 있습니다.

- Microsoft 인증자 앱 알림

- 기타 모바일 인증자 앱/하드웨어 토큰 코드

- Email

- 전화 통화

- 문자 메시지

Microsoft 인증자 앱을 사용하여 암호를 재설정하는 방법에 대한 자세한 내용은 [Azure AD 셀프 서비스 암호 재설정 - 모바일 앱 및 SSPR(미리 보기)](../authentication/concept-sspr-howitworks.md#mobile-app-and-sspr)을 참조하세요.

---

### <a name="new-azure-ad-cloud-device-administrator-role-public-preview"></a>새 Azure AD 클라우드 디바이스 관리자 역할(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 디바이스 등록 및 관리 **제품 기능:** Access Control

관리자는 클라우드 디바이스 관리자 작업을 수행할 새 클라우드 디바이스 관리자 역할에 사용자를 할당할 수 있습니다. 클라우드 디바이스 관리자 역할이 할당된 사용자는 Azure AD에서 디바이스를 사용/사용하지 않도록 설정하고, 삭제하고, Azure Portal에서 Windows 10 BitLocker 키(있는 경우)를 읽을 수 있습니다.

역할 및 사용 권한에 대한 자세한 내용은 [Azure Active Directory에서 관리자 역할 할당](../roles/permissions-reference.md)을 참조하세요.

---

### <a name="manage-your-devices-using-the-new-activity-timestamp-in-azure-ad-public-preview"></a>Azure AD의 새 작업 타임스탬프(공개 미리 보기)를 사용하여 디바이스 관리

**유형:** 새 기능 **서비스 범주:** 디바이스 등록 및 관리 **제품 기능:** 디바이스 수명 주기 관리

사용자 환경에서 부실 디바이스가 사용되지 않도록 Azure AD에서 시간 경과에 따라 조직의 디바이스를 새로 고치고 사용 중지해야 한다는 것을 알게 되었습니다. 이 프로세스를 지원하기 위해 Azure AD는 이제 새 작업 타임스탬프로 디바이스를 업데이트하여 디바이스 수명 주기를 관리할 수 있도록 지원합니다.

이 타임스탬프를 가져오고 사용하는 방법에 대한 자세한 내용은 [방법: Azure AD에서 부실 디바이스 관리](../devices/manage-stale-devices.md)를 참조하세요.

---

### <a name="administrators-can-require-users-to-accept-a-terms-of-use-on-each-device"></a>관리자는 각 디바이스에서 사용 약관에 동의하도록 사용자에게 요구할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

이제 관리자는 **모든 디바이스에서 사용자 동의 요구** 옵션을 켜서 사용자가 테넌트에서 사용 중인 모든 디바이스에서 사용 약관에 동의하도록 요구할 수 있습니다.

자세한 내용은 [Azure Active Directory 사용 약관 기능의 디바이스별 사용 약관 섹션](../conditional-access/terms-of-use.md#per-device-terms-of-use)을 참조하세요.

---

### <a name="administrators-can-configure-a-terms-of-use-to-expire-based-on-a-recurring-schedule"></a>관리자는 되풀이 일정에 따라 만료되도록 사용 약관을 구성할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스


이제 관리자는 **콘텐츠 만료** 옵션을 켜서 지정된 되풀이 일정에 따라 모든 사용자에 대해 사용 약관이 만료되도록 설정할 수 있습니다. 일정은 매년, 6개월마다, 매분기 또는 매월일 수 있습니다. 사용 약관이 만료되면 사용자가 다시 동의해야 합니다.

자세한 내용은 [Azure Active Directory 사용 약관 기능의 사용 약관 추가 섹션](../conditional-access/terms-of-use.md#add-terms-of-use)을 참조하세요.

---

### <a name="administrators-can-configure-a-terms-of-use-to-expire-based-on-each-users-schedule"></a>관리자는 각 사용자의 일정에 따라 만료되도록 사용 약관을 구성할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

이제 관리자는 사용자가 사용 약관에 다시 동의해야 하는 기간을 지정할 수 있습니다. 예를 들어 관리자는 사용자가 90일마다 사용 약관에 다시 동의해야 하도록 지정할 수 있습니다.

자세한 내용은 [Azure Active Directory 사용 약관 기능의 사용 약관 추가 섹션](../conditional-access/terms-of-use.md#add-terms-of-use)을 참조하세요.

---

### <a name="new-azure-ad-privileged-identity-management-pim-emails-for-azure-active-directory-roles"></a>Azure Active Directory 역할에 대한 새 Azure AD PIM(Privileged Identity Management) 메일

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

Azure AD PIM(Privileged Identity Management)를 사용하는 고객은 이제 지난 7일간의 다음 정보를 포함하여 매주 요약 메일을 받을 수 있습니다.

- 상위 적격 및 영구 역할 할당 개요

- 역할을 활성화하는 사용자 수

- PIM의 역할에 할당된 사용자 수

- PIM 외부의 역할에 할당된 사용자 수

- PIM의 “영구적” 사용자 수

PIM 및 사용 가능한 메일 알림에 대한 자세한 내용은 [PIM의 메일 알림](../privileged-identity-management/pim-email-notifications.md)을 참조하세요.

---

### <a name="group-based-licensing-is-now-generally-available"></a>그룹 기반 라이선스 출시

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** 디렉터리

그룹 기반 라이선스의 공개 미리 보기가 종료되고 이제 일반 공급됩니다. 이 일반 릴리스의 일부로, 이 기능의 확장성이 개선되었으며 단일 사용자에 대한 그룹 기반 라이선스 할당을 다시 처리하는 기능과 Office 365 E3/A3 라이선스로 그룹 기반 라이선스를 사용하는 기능이 추가되었습니다.

그룹 기반 라이선스에 대한 자세한 내용은 [Azure Active Directory의 그룹 기반 라이선스란?](./active-directory-licensing-whatis-azure-portal.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---november-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 11월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 11월에 페더레이션이 지원되는 신규 앱 26개가 앱 갤러리에 추가되었습니다.

[CoreStack](https://cloud.corestack.io/site/login), [HubSpot](../saas-apps/hubspot-tutorial.md), [GetThere](../saas-apps/getthere-tutorial.md), [Gra-Pe](../saas-apps/grape-tutorial.md), [eHour](https://getehour.com/try-now), [Consent2Go](../saas-apps/consent2go-tutorial.md), [Appinux](../saas-apps/appinux-tutorial.md), [DriveDollar](https://azuremarketplace.microsoft.com/marketplace/apps/savitas.drivedollar-azuread?tab=Overview), [Useall](../saas-apps/useall-tutorial.md), [Infinite Campus](../saas-apps/infinitecampus-tutorial.md), [Alaya](https://alayagood.com), [HeyBuddy](../saas-apps/heybuddy-tutorial.md), [Wrike SAML](../saas-apps/wrike-tutorial.md), [Drift](../saas-apps/drift-tutorial.md), [Zenegy for Business Central 365](https://accounting.zenegy.com/), [Everbridge Member Portal](../saas-apps/everbridge-tutorial.md), [IDEO](https://profile.ideo.com/users/sign_up), [Ivanti Service Manager(ISM)](../saas-apps/ivanti-service-manager-tutorial.md), [Peakon](../saas-apps/peakon-tutorial.md), [Allbound SSO](../saas-apps/allbound-sso-tutorial.md), [Plex Apps - Classic Test](https://test.plexonline.com/signon), [Plex Apps – Classic](https://www.plexonline.com/signon), [Plex Apps - UX Test](https://test.cloud.plex.com/sso), [Plex Apps – UX](https://cloud.plex.com/sso), [Plex Apps – IAM](https://accounts.plex.com/), [CRAFTS - Childcare Records, Attendance, & Financial Tracking System](https://getcrafts.ca/craftsregistration)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

## <a name="october-2018"></a>2018년 10월

### <a name="azure-ad-logs-now-work-with-azure-log-analytics-public-preview"></a>Azure AD 로그는 이제 Azure Log Analytics(공개 미리 보기)에서 사용됩니다.

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

이제 Azure Log Analytics에 Azure AD 로그를 전달할 수 있게 되었습니다. 많은 요청이 있었던 이 기능은 인프라를 모니터링하는 데 도움이 줄 뿐만 아니라 비즈니스, 작업 및 보안을 위해 분석에 보다 쉽게 액세스할 수 있도록 합니다. 자세한 내용은 [Azure Active Directory Activity logs in Azure Log Analytics now available](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-Active-Directory-Activity-logs-in-Azure-Log-Analytics-now/ba-p/274843)(이제 Azure Log Analytics에서 Azure Active Directory 활동 로그를 사용할 수 있음) 블로그를 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---october-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 10월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 10월에 페더레이션이 지원되는 다음과 같은 신규 앱 14개가 앱 갤러리에 추가되었습니다.

[My Award Points](../saas-apps/myawardpoints-tutorial.md), [Vibe HCM](../saas-apps/vibehcm-tutorial.md), ambyint, [MyWorkDrive](../saas-apps/myworkdrive-tutorial.md), [BorrowBox](../saas-apps/borrowbox-tutorial.md), Dialpad, [ON24 Virtual Environment](../saas-apps/on24-tutorial.md), [RingCentral](../saas-apps/ringcentral-tutorial.md), [Zscaler Three](../saas-apps/zscaler-three-tutorial.md), [Phraseanet](../saas-apps/phraseanet-tutorial.md), [Appraisd](../saas-apps/appraisd-tutorial.md), [Workspot Control](../saas-apps/workspotcontrol-tutorial.md), [Shuccho Navi](../saas-apps/shucchonavi-tutorial.md), [Glassfrog](../saas-apps/glassfrog-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="azure-ad-domain-services-email-notifications"></a>Azure AD Domain Services 이메일 알림

**유형:** 새 기능 **서비스 범주:** Azure AD Domain Services **제품 기능:** Azure AD Domain Services

Azure AD Domain Services는 관리되는 도메인의 구성 오류 또는 문제점에 대한 경고를 Azure Portal에 제공합니다. 이러한 경고에는 지원 서비스에 문의하지 않고 문제를 해결할 수 있는 단계별 가이드가 포함됩니다.

10월부터, 관리되는 도메인에 대한 알림 설정을 사용자 지정할 수 있으므로 새 경고가 발생할 때 지정된 사용자 그룹으로 이메일이 전송됩니다. 따라서 포털에서 업데이트를 지속적으로 확인할 필요가 없습니다.

자세한 내용은 [Azure AD Domain Services의 알림 설정](../../active-directory-domain-services/notifications.md)을 참조하세요.

---

### <a name="azure-ad-portal-supports-using-the-forcedelete-domain-api-to-delete-custom-domains"></a>Azure AD 포털에서는 ForceDelete 도메인 API를 사용하여 사용자 지정 도메인을 삭제하도록 지원합니다.

**유형:** 변경된 기능 **서비스 범주:** 디렉터리 관리 **제품 기능:** 디렉터리

이제 사용자, 그룹 및 앱과 같은 참조의 이름을 사용자 지정 도메인 이름(contoso.com)에서 초기 기본 도메인 이름(contoso.onmicrosoft.com)으로 비동기식으로 다시 바꾸는 방식으로, ForceDelete 도메인 API를 통해 사용자 지정 도메인 이름을 삭제할 수 있습니다.

이러한 변경을 통해 조직이 더 이상 해당 이름을 사용하지 않는 경우 또는 다른 Azure AD와 해당 도메인 이름을 사용해야 하는 경우, 사용자 지정 도메인 이름을 보다 신속하게 삭제할 수 있습니다.

자세한 내용은 [사용자 지정 도메인 이름 삭제](../enterprise-users/domains-manage.md#delete-a-custom-domain-name)를 참조하세요.

---

## <a name="september-2018"></a>2018년 9월

### <a name="updated-administrator-role-permissions-for-dynamic-groups"></a>동적 그룹에 대한 관리자 역할 권한 업데이트

**유형:** 수정된 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이제 그룹의 소유자가 되지 않아도 특정 관리자 역할이 동적 구성원 규칙을 만들고 업데이트할 수 있도록 문제가 해결되었습니다.

역할은 다음과 같습니다.

- 전역 관리자

- Intune 관리자

- 사용자 관리자

자세한 내용은 [동적 그룹 만들기 및 상태 확인](../enterprise-users/groups-create-rule.md)을 참조하세요.

---

### <a name="simplified-single-sign-on-sso-configuration-settings-for-some-third-party-apps"></a>일부 타사 앱에 대한 간소화된 SSO(Single Sign-On) 구성 설정

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

각 앱 구성의 고유한 특성 때문에 SaaS(Software as a Service) 앱에 대한 SSO(Single Sign-On)를 설정하기란 쉽지 않은 일입니다. Microsoft는 다음 타사 SaaS 앱의 SSO 구성 설정을 자동으로 채우도록 간소화된 구성 환경을 빌드했습니다.

- Zendesk

- ArcGis Online

- Jamf Pro

이 원클릭 환경을 사용하려면 앱의 **Azure Portal** > **SSO 구성** 페이지로 이동합니다. 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

---

### <a name="azure-active-directory---where-is-your-data-located-page"></a>Azure Active Directory - 데이터가 있는 위치 페이지

**유형:** 새 기능 **서비스 범주:** 기타 **제품 기능:** GoLocal

**Azure Active Directory - 데이터가 있는 위치** 페이지에서 회사가 있는 지역을 선택하고, 모든 Azure AD 서비스의 Azure AD 미사용 데이터를 저장하는 Azure 데이터 센터가 어디인지 살펴봅니다. 회사가 있는 지역의 특정 Azure AD 서비스를 기준으로 정보를 필터링할 수 있습니다.

이 기능 및 자세한 정보에 액세스하려면 [Azure Active Directory - 데이터가 있는 위치](https://aka.ms/AADDataMap)를 참조하세요.

---

### <a name="new-deployment-plan-available-for-the-my-apps-access-panel"></a>내 앱 액세스 패널에 사용할 수 있는 새 배포 계획

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** SSO

내 앱 액세스 패널에 사용할 수 있는 새 배포 계획을 확인하세요(https://aka.ms/deploymentplans).
내 앱 액세스 패널은 사용자에게 앱을 찾고 액세스할 수 있는 단일 위치를 제공합니다. 또한 이 포털은 앱 및 그룹에 대한 액세스 권한 요청, 다른 사람을 대신하여 리소스에 대한 액세스 권한 관리와 같은 셀프 서비스 기회를 사용자에게 제공합니다.

자세한 내용은 [My Apps 포털이란?](../user-help/my-apps-portal-end-user-access.md)을 참조하세요.

---

### <a name="new-troubleshooting-and-support-tab-on-the-sign-ins-logs-page-of-the-azure-portal"></a>Azure Portal의 [로그인 로그] 페이지에 있는 새로운 [문제 해결 및 지원] 탭

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

Azure Portal의 **로그인** 페이지에 있는 새로운 **문제 해결 및 지원** 탭의 목적은 관리자 및 지원 엔지니어가 Azure AD 로그인 관련 문제를 해결할 수 있게 도와주는 것입니다. 이 새 탭은 문제 해결에 도움이 되는 오류 코드, 오류 메시지 및 수정 권장 사항(있는 경우)을 제공합니다. 문제를 해결할 수 없는 경우 지원 티켓의 로그 파일에 대한 **요청 ID** 및 **날짜(UTC)** 필드를 채우는 **클립보드에 복사** 환경을 사용하여 지원 티켓을 만들 수 있는 새로운 방법을 제공합니다.

![새 탭을 보여주는 로그인 로그](media/whats-new/troubleshooting-and-support.png)

---

### <a name="enhanced-support-for-custom-extension-properties-used-to-create-dynamic-membership-rules"></a>동적 구성원 규칙을 만드는 데 사용되는 사용자 지정 확장 속성에 대한 향상된 지원

**유형:** 변경된 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

이 업데이트부터는 동적 사용자 그룹 규칙 작성기에서 **사용자 지정 확장 속성 가져오기** 를 클릭하고, 고유한 앱 ID를 입력하고, 사용자에 대한 동적 구성원 규칙을 만들 때 사용할 사용자 지정 확장 속성 전체 목록을 받을 수 있습니다. 이 목록을 새로 고침하여 해당 앱에 대한 새로운 사용자 지정 확장 속성을 가져올 수도 있습니다.

동적 구성원 규칙에 대한 사용자 지정 확장 속성을 사용하는 방법에 대한 자세한 내용은 [확장 속성 및 사용자 지정 확장 속성](../enterprise-users/groups-dynamic-membership.md#extension-properties-and-custom-extension-properties)을 참조하세요.

---

### <a name="new-approved-client-apps-for-azure-ad-app-based-conditional-access"></a>Azure AD 앱 기반 조건부 액세스의 새로운 승인된 클라이언트 앱

**유형:** 변경 계획 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

[승인된 클라이언트 앱](../conditional-access/concept-conditional-access-conditions.md#client-apps) 목록에는 다음과 같은 앱이 있습니다.

- Microsoft To-Do

- Microsoft Stream

자세한 내용은 다음을 참조하세요.

- [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)

---

### <a name="new-support-for-self-service-password-reset-from-the-windows-7881-lock-screen"></a>Windows 7/8/8.1 잠금 화면에서 셀프 서비스 암호 재설정에 대한 새로운 지원

**유형:** 새 기능 **서비스 범주:** SSPR **제품 기능:** 사용자 인증

이 새 기능을 설치하면 Windows 7, Windows 8 또는 Windows 8.1을 실행하는 디바이스의 **잠금** 화면에 사용자가 암호를 다시 설정할 수 있는 링크가 표시됩니다. 이 링크를 클릭하면 웹 브라우저와 동일한 암호 재설정 흐름이 사용자에게 제공됩니다.

자세한 내용은 [Windows 7, 8 및 8.1에서 암호 재설정을 사용하는 방법](../authentication/howto-sspr-windows.md)을 참조하세요.

---

### <a name="change-notice-authorization-codes-will-no-longer-be-available-for-reuse"></a>변경 알림: 인증 코드를 더 이상 다시 사용할 수 없습니다.

**유형:** 변경 계획 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

2018년 11월 15일부터 Azure AD는 앱에서 이전에 사용된 인증 코드를 더 이상 수락하지 않습니다. 이 보안 변경은 Azure AD를 OAuth 사양에 맞추는 데 도움이 되며 v1 및 v2 엔드포인트 모두에 적용됩니다.

앱에서 여러 리소스에 대한 토큰을 얻기 위해 인증 코드를 재사용하는 경우에는 코드를 사용하여 새로 고침 토큰을 얻은 다음, 이 새로 고침 토큰을 사용하여 다른 리소스에 대한 추가 토큰을 얻는 것이 좋습니다. 인증 코드는 한 번만 사용할 수 있지만 새로 고침 토큰은 여러 리소스에서 여러 번 사용할 수 있습니다. OAuth 코드 흐름 중에 인증 코드를 다시 사용하려고 하는 앱에서는 invalid_grant 오류가 발생합니다.

이 변경 내용 및 기타 프로토콜 관련 변경 내용은 [인증 관련 새 기능 전체 목록](../develop/reference-breaking-changes.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---september-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 9월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 9월에 페더레이션이 지원되는 신규 앱 16개가 앱 갤러리에 추가되었습니다.

[Uberflip](../saas-apps/uberflip-tutorial.md), [Comeet Recruiting Software](../saas-apps/comeetrecruitingsoftware-tutorial.md), [Workteam](../saas-apps/workteam-tutorial.md), [ArcGIS Enterprise](../saas-apps/arcgisenterprise-tutorial.md), [Nuclino](../saas-apps/nuclino-tutorial.md), [JDA Cloud](../saas-apps/jdacloud-tutorial.md), [Snowflake](../saas-apps/snowflake-tutorial.md), NavigoCloud, [Figma](../saas-apps/figma-tutorial.md), join.me, [ZephyrSSO](../saas-apps/zephyrsso-tutorial.md), [Silverback](../saas-apps/silverback-tutorial.md), Riverbed Xirrus EasyPass, [Rackspace SSO](../saas-apps/rackspacesso-tutorial.md), Enlyft SSO for Azure, SurveyMonkey, [Convene](../saas-apps/convene-tutorial.md), [dmarcian](../saas-apps/dmarcian-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="support-for-additional-claims-transformations-methods"></a>추가 클레임 변환 메서드 지원

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

SAML 기반 **Single Sign-On 구성** 페이지에서 SAML 토큰에 적용할 수 있는 새로운 클레임 변환 메서드 ToLower() 및 ToUpper()가 도입되었습니다.

자세한 내용은 [Azure AD의 엔터프라이즈 애플리케이션에 대한 SAML 토큰에 발급된 클레임을 사용자 지정하는 방법](../develop/active-directory-saml-claims-customization.md)을 참조하세요.

---

### <a name="updated-saml-based-app-configuration-ui-preview"></a>업데이트된 SAML 기반 앱 구성 UI(미리 보기)

**유형:** 변경된 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

업데이트된 SAML 기반 앱 구성 UI의 일부로 다음이 제공됩니다.

- SAML 기반 앱을 구성하는 업데이트된 연습 환경.

- 누락되거나 잘못된 구성에 대한 향상된 가시성.

- 만료 인증서 알림에 대한 여러 이메일 주소를 추가하는 기능.

- 새로운 클레임 변환 메서드 ToLower(), ToUpper() 등.

- 엔터프라이즈 앱의 고유한 토큰 서명 인증서를 업로드하는 방법.

- SAML 앱의 NameID 형식을 설정하는 방법 및 NameID 값을 디렉터리 확장으로 설정하는 방법.

이 업데이트된 보기를 켜려면 **Single Sign-On** 페이지 맨 위에서 **새 환경 사용해 보기** 링크를 클릭합니다. 자세한 내용은 [자습서: Azure Active Directory에서 애플리케이션에 대한 SAML 기반 Single Sign-On 구성](../manage-apps/view-applications-portal.md)을 참조하세요.

---

## <a name="august-2018"></a>2018년 8월

### <a name="changes-to-azure-active-directory-ip-address-ranges"></a>Azure Active Directory IP 주소 범위 변경

**유형:** 변경 계획 **서비스 범주:** 기타 **제품 기능:** 플랫폼

Azure AD에 더 큰 IP 범위를 도입하려고 합니다. 따라서 방화벽, 라우터 또는 네트워크 보안 그룹에 대한 Azure AD IP 주소 범위를 구성한 경우 업데이트해야 합니다. 이 업데이트는 Azure AD에서 새 엔드포인트를 추가하는 경우에 방화벽, 라우터 또는 네트워크 보안 그룹 IP 범위 구성을 다시 변경할 필요가 없도록 하기 위해 진행하고 있습니다.

네트워크 트래픽은 향후 2개월에 걸쳐 이러한 새 범위로 이동될 것입니다. 서비스를 중단 없이 계속 사용하려면 2018년 9월 10일 전에 이러한 업데이트된 값을 IP 주소에 추가해야 합니다.

- 20.190.128.0/18

- 40.126.0.0/18

모든 네트워크 트래픽이 새 범위로 이동될 때까지 이전 IP 주소 범위를 제거하지 않는 것이 좋습니다. 이러한 이동에 대한 업데이트 내용을 확인하고 이전 범위를 제거할 수 있는 시기를 알아보려면 [Office 365 URL 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)를 참조하세요.

---

### <a name="change-notice-authorization-codes-will-no-longer-be-available-for-reuse"></a>변경 알림: 인증 코드를 더 이상 다시 사용할 수 없습니다.

**유형:** 변경 계획 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

2018년 11월 15일부터 Azure AD는 앱에서 이전에 사용된 인증 코드를 더 이상 수락하지 않습니다. 이 보안 변경은 Azure AD를 OAuth 사양에 맞추는 데 도움이 되며 v1 및 v2 엔드포인트 모두에 적용됩니다.

앱에서 여러 리소스에 대한 토큰을 얻기 위해 인증 코드를 재사용하는 경우에는 코드를 사용하여 새로 고침 토큰을 얻은 다음, 이 새로 고침 토큰을 사용하여 다른 리소스에 대한 추가 토큰을 얻는 것이 좋습니다. 인증 코드는 한 번만 사용할 수 있지만 새로 고침 토큰은 여러 리소스에서 여러 번 사용할 수 있습니다. OAuth 코드 흐름 중에 인증 코드를 다시 사용하려고 하는 앱에서는 invalid_grant 오류가 발생합니다.

이 변경 내용 및 기타 프로토콜 관련 변경 내용은 [인증 관련 새 기능 전체 목록](../develop/reference-breaking-changes.md)을 참조하세요.

---

### <a name="converged-security-info-management-for-self-service-password-sspr-and-multi-factor-authentication-mfa"></a>SSPR(셀프 서비스 암호) 및 MFA(Multi-Factor Authentication)를 위한 융합형 보안 정보 관리

**유형:** 새 기능 **서비스 범주:** SSPR **제품 기능:** 사용자 인증

이 기능을 사용하면 SSPR 및 MFA에 대한 보안 정보(예: 전화 번호, 모바일 앱 등)를 두 개의 다른 위치에서 관리하던 이전 방식과 달리, 단일 위치 및 환경에서 관리할 수 있습니다.

융합형 환경은 SSPR 또는 MFA 사용자에게도 유용합니다. 또한 조직에서 MFA 또는 SSPR 등록이 적용되지 않는 경우에도 내 앱 포털의 조직에 허용되는 MFA 또는 SSPR 보안 정보 메서드를 사용자가 등록할 수 있습니다.

이 기능은 옵트인 공개 미리 보기입니다. 관리자는 선택한 그룹 또는 테넌트의 모든 사용자에게 원하는 경우 환경을 적용할 수 있습니다. 융합형 환경에 대한 자세한 내용은 [융합형 환경 블로그](https://cloudblogs.microsoft.com/enterprisemobility/2018/08/06/mfa-and-sspr-updates-now-in-public-preview/)를 참조하세요.

---

### <a name="new-http-only-cookies-setting-in-azure-ad-application-proxy-apps"></a>Azure AD 애플리케이션 프록시 앱에서 새로운 HTTP 전용 쿠키 설정

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

애플리케이션 프록시 앱에는 **HTTP 전용 쿠키** 라는 새로운 설정이 있습니다. 이 설정을 사용하면 애플리케이션 프록시 액세스 및 세션 쿠키 모두에 대한 HTTP 응답 헤더에 HTTPOnly 플래그를 포함시켜서 추가 보안을 제공하여 클라이언트 쪽 스크립트에서 쿠키에 대한 액세스를 중지하고 쿠키 복사 또는 수정과 같은 작업을 방지할 수 있습니다. 전에는 이 플래그가 사용되지 않았지만 부적절한 수정을 방지하기 위해 TLS 연결을 사용하여 항상 쿠키가 암호화되고 전송되었습니다.

이 설정은 원격 데스크톱과 같은 ActiveX 컨트롤을 사용하는 응용 프로그램과 호환되지 않습니다. 이런 경우에 해당하면 이 설정을 해제하는 것이 좋습니다.

HTTP 전용 쿠키 설정에 대한 자세한 내용은 [Azure AD 애플리케이션 프록시를 사용하여 애플리케이션 게시](../manage-apps/application-proxy-add-on-premises-application.md)를 참조하세요.

---

### <a name="privileged-identity-management-pim-for-azure-resources-supports-management-group-resource-types"></a>Azure 리소스에 대한 PIM(Privileged Identity Management)은 관리 그룹 리소스 종류를 지원합니다.

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

이제 Just-In-Time 활성화 및 할당 설정을 구독, 리소스 그룹 및 리소스(예: VM, App Services 등)에 적용하듯이 관리 그룹 리소스 종류에 적용할 수 있습니다. 또한 관리 그룹에 대한 관리자 액세스를 제공하는 역할이 있는 사람은 PIM에서 해당 리소스를 검색하고 관리할 수 있습니다.

PIM 및 Azure 리소스에 대한 자세한 내용은 [Privileged Identity Management를 사용하여 Azure 리소스 검색 및 관리](../privileged-identity-management/pim-resource-roles-discover-resources.md)를 참조하세요.

---

### <a name="application-access-preview-provides-faster-access-to-the-azure-ad-portal"></a>애플리케이션 액세스(미리 보기)를 사용하면 Azure AD 포털에 빠르게 액세스할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

현재 PIM을 사용하여 역할을 활성화하는 경우 권한이 적용되려면 10분 넘게 걸릴 수 있습니다. 현재 미리 보기 상태인 애플리케이션 액세스를 사용하도록 선택하면 활성화 요청이 완료되자마자 관리자가 Azure AD 포털에 액세스할 수 있습니다.

현재 애플리케이션 액세스는 Azure AD 포털 환경과 Azure 리소스만 지원합니다. PIM 및 애플리케이션 액세스에 대한 자세한 내용은 [Azure AD Privileged Identity Management란?](../privileged-identity-management/pim-configure.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---august-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 8월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 8월에 페더레이션이 지원되는 신규 앱 16개가 앱 갤러리에 추가되었습니다.

[Hornbill](../saas-apps/hornbill-tutorial.md), [Bridgeline Unbound](../saas-apps/bridgelineunbound-tutorial.md), [Sauce Labs - Mobile and Web Testing](../saas-apps/saucelabs-mobileandwebtesting-tutorial.md), [Meta Networks Connector](../saas-apps/metanetworksconnector-tutorial.md), [Way We Do](../saas-apps/waywedo-tutorial.md), [Spotinst](../saas-apps/spotinst-tutorial.md), [ProMaster (by Inlogik)](../saas-apps/promaster-tutorial.md), SchoolBooking, [4me](../saas-apps/4me-tutorial.md), [Dossier](../saas-apps/dossier-tutorial.md), [N2F - Expense reports](../saas-apps/n2f-expensereports-tutorial.md), [Comm100 Live Chat](../saas-apps/comm100livechat-tutorial.md), [SafeConnect](../saas-apps/safeconnect-tutorial.md), [ZenQMS](../saas-apps/zenqms-tutorial.md), [eLuminate](../saas-apps/eluminate-tutorial.md), [Dovetale](../saas-apps/dovetale-tutorial.md).

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="native-tableau-support-is-now-available-in-azure-ad-application-proxy"></a>이제 Azure AD 애플리케이션 프록시에 Native Tableau 지원이 제공됩니다.

**유형:** 변경된 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

사전 인증 프로토콜을 위해 OpenID Connect가 OAuth 2.0 코드 권한 부여 프로토콜로 업데이트되었기 때문에 애플리케이션 프록시와 Tableau를 사용하기 위해 추가 구성을 수행할 필요가 없습니다. 프로토콜이 변경됨으로써 애플리케이션 프록시가 HTTP 리디렉션(JavaScript 및 HTML 태그에서 일반적으로 지원됨)만 사용하여 최신 앱을 더 잘 지원할 수 있습니다.

---

### <a name="new-support-to-add-google-as-an-identity-provider-for-b2b-guest-users-in-azure-active-directory-preview"></a>Azure Active Directory에서 Google을 B2B 게스트 사용자에 대한 ID 공급자로 추가하도록 지원(미리 보기)

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C

조직에 Google과의 페더레이션을 설정하면 초대받은 Gmail 사용자가 MSA(개인 Microsoft 계정)나 Azure AD 계정을 만들 필요 없이 기존 Google 계정을 사용하여 공유 앱 및 리소스에 로그인하도록 할 수 있습니다.

이 기능은 옵트인 공개 미리 보기입니다. Google 페더레이션에 대한 자세한 내용은 [Google을 B2B 게스트 사용자에 대한 ID 공급자로 추가](../external-identities/google-federation.md)를 참조하세요.

---

## <a name="july-2018"></a>2018년 7월

### <a name="improvements-to-azure-active-directory-email-notifications"></a>Azure Active Directory 메일 알림에 대한 개선

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** ID 수명 주기 관리

이제 Azure AD(Azure Active Directory) 이메일은 다음 서비스에서 전송된 경우, 보낸 사람 이메일 주소 및 보낸 사람 표시 이름을 변경하고 업데이트된 디자인을 사용합니다.

- Azure AD 액세스 검토
- Azure AD Connect Health
- Azure AD ID 보호
- Azure AD Privileged Identity Management
- 엔터프라이즈 앱 인증서 만료 알림
- 엔터프라이즈 앱 서비스 프로비저닝 알림

메일 알림은 다음 메일 주소 및 표시 이름에서 전송됩니다.

- 메일 주소: azure-noreply@microsoft.com
- 표시 이름: Microsoft Azure

새 메일 디자인의 몇 가지 예제와 자세한 내용은 [Azure AD PIM의 메일 알림](../privileged-identity-management/pim-email-notifications.md)을 참조하세요.

---

### <a name="azure-ad-activity-logs-are-now-available-through-azure-monitor"></a>Azure AD 활동 로그는 이제 Azure Monitor를 통해 제공됩니다.

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

이제 Azure Monitor(Azure의 플랫폼 수준 모니터링 서비스)를 위한 공개 미리 보기에서 Azure AD 활동 로그를 사용할 수 있습니다. Azure Monitor는 장기 보존 및 매끄러운 통합 외에도 다음과 같은 향상된 기능을 제공합니다.

- 로그 파일을 사용자 고유의 Azure Storage 계정에 라우팅하여 장기 보존.

- 사용자 지정 스크립트를 작성하거나 유지 관리할 필요 없이 매끄럽게 SIEM 통합.

- 사용자 고유의 사용자 지정 솔루션, 분석 도구 또는 인시던트 관리 솔루션과 매끄럽게 통합.

이러한 새 기능에 대한 자세한 내용은 [Azure Monitor 진단에서 Azure AD 활동 로그를 공개 미리 보기로 제공](https://cloudblogs.microsoft.com/enterprisemobility/2018/07/26/azure-ad-activity-logs-in-azure-monitor-diagnostics-now-in-public-preview/) 블로그 및 [Azure Monitor의 Azure Active Directory 활동 로그(미리 보기)](../reports-monitoring/concept-activity-logs-azure-monitor.md) 문서를 참조하세요.

---

### <a name="conditional-access-information-added-to-the-azure-ad-sign-ins-report"></a>Azure AD 로그인 보고서에 추가된 조건부 액세스 정보

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** ID 보안 및 보호

이 업데이트는 정책 결과와 함께 사용자가 로그인할 때 어떤 정책이 평가되는지 볼 수 있게 해줍니다. 또한 이제 보고서에 사용자가 사용한 클라이언트 앱 유형이 포함되므로 레거시 프로토콜 트래픽을 식별할 수 있습니다. 또한 이제 보고서 항목에서 상관 관계 ID를 검색할 수 있습니다. 이 ID는 사용자에게 표시되는 오류 메시지에서 찾을 수 있으며 일치하는 로그인 요청을 찾아서 해결하는 데 사용할 수 있습니다.

---

### <a name="view-legacy-authentications-through-sign-ins-activity-logs"></a>로그인 활동 로그를 통해 레거시 인증 보기

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

로그인 활동 로그에 **클라이언트 앱** 필드가 도입되어 레거시 인증을 사용하는 사용자를 고객이 볼 수 있습니다. 고객은 로그인 Microsoft Graph API를 사용하거나 **클라이언트 앱** 컨트롤을 사용하여 레거시 인증을 필터링할 수 있는 Azure AD 포털에서 로그인 활동 로그를 통해 이 정보에 액세스할 수 있습니다. 자세한 내용은 설명서를 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---july-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 7월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 7월에 페더레이션이 지원되는 신규 앱 16개가 앱 갤러리에 추가되었습니다.

[Innovation Hub](../saas-apps/innovationhub-tutorial.md), [Leapsome](../saas-apps/leapsome-tutorial.md), [Certain Admin SSO](../saas-apps/certainadminsso-tutorial.md), PSUC Staging, [iPass SmartConnect](../saas-apps/ipasssmartconnect-tutorial.md), [Screencast-O-Matic](../saas-apps/screencast-tutorial.md), PowerSchool Unified Classroom, [Eli Onboarding](../saas-apps/elionboarding-tutorial.md), [Bomgar Remote Support](../saas-apps/bomgarremotesupport-tutorial.md), [Nimblex](../saas-apps/nimblex-tutorial.md), [Imagineer WebVision](../saas-apps/imagineerwebvision-tutorial.md), [Insight4GRC](../saas-apps/insight4grc-tutorial.md), [SecureW2 JoinNow Connector](../saas-apps/securejoinnow-tutorial.md), [Kanbanize](../saas-apps/kanbanize-tutorial.md), [SmartLPA](../saas-apps/smartlpa-tutorial.md), [Skills Base](../saas-apps/skillsbase-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-user-provisioning-saas-app-integrations---july-2018"></a>새 사용자 프로비전 SaaS 앱 통합 - 2018년 7월

**유형:** 새 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** 타사 통합

Azure AD를 사용하면 Dropbox, Salesforce, ServiceNow 등과 같은 SaaS 애플리케이션에서 사용자 ID 만들기, 유지 관리 및 제거를 자동화할 수 있습니다. 2018년 7월에 Azure AD 앱 갤러리에서 다음 애플리케이션에 대한 사용자 프로비전 지원을 추가했습니다.

- [Cisco WebEx](../saas-apps/cisco-webex-provisioning-tutorial.md)

- [Bonusly](../saas-apps/bonusly-provisioning-tutorial.md)

Azure AD 갤러리에서 사용자 프로비전을 지원하는 모든 애플리케이션 목록은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

---

### <a name="connect-health-for-sync---an-easier-way-to-fix-orphaned-and-duplicate-attribute-sync-errors"></a>동기화용 Connect Health - 분리되고 중복되는 특성 동기화 오류를 간단하게 해결할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** AD Connect **제품 기능:** 모니터링 및 보고

Azure AD Connect Health는 동기화 오류를 강조하고 해결할 수 있는 셀프 서비스 업데이트 관리를 도입합니다. 이 기능은 중복된 특성 동기화 오류를 해결하고 Azure AD에서 분리된 개체를 수정합니다. 이 진단은 다음과 같은 이점이 있습니다.

- 중복된 특성 동기화 오류의 범위를 좁혀서 특정 픽스 제공

- 전용 Azure AD 시나리오용 픽스를 적용하여 한 단계로 오류 해결

- 이 기능을 사용하기 위한 별도의 업그레이드 또는 구성이 필요 없음

자세한 내용은 [중복된 특성 동기화 오류 진단 및 수정](../hybrid/how-to-connect-health-diagnose-sync-errors.md) 참조

---

### <a name="visual-updates-to-the-azure-ad-and-msa-sign-in-experiences"></a>Azure AD 및 MSA 로그인 환경으로 시각적 업데이트

**유형:** 변경된 기능 **서비스 범주:** Azure AD **제품 기능:** 사용자 인증

Office 365, Azure 등의 Microsoft 온라인 서비스 로그인 환경용 UI를 업데이트했습니다. 이 변화로 화면이 더욱 깔끔하게 정리되고 더 쉬워졌습니다. 이 변화에 대한 자세한 내용은 [Azure AD 로그인 환경에 예정된 기능 개선](https://cloudblogs.microsoft.com/enterprisemobility/2018/04/04/upcoming-improvements-to-the-azure-ad-sign-in-experience/) 블로그를 참조하세요.

---

### <a name="new-release-of-azure-ad-connect---july-2018"></a>Azure AD Connect의 새 릴리스 - 2018년 7월

**유형:** 변경된 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** ID 수명 주기 관리

Azure AD Connect의 최신 릴리스에는 다음이 포함되어 있습니다.

- 버그 수정 및 지원 가능성 업데이트

- Ping Federate 통합의 일반 공급

- 최신 SQL 2012 클라이언트의 업데이트

이 업데이트에 대한 자세한 내용은 [Azure AD Connect: 버전 릴리스 기록](../hybrid/reference-connect-version-history.md)을 참조하세요.

---

### <a name="updates-to-the-terms-of-use-end-user-ui"></a>최종 사용자 UI 사용 약관 업데이트

**유형:** 변경된 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

TOU 최종 사용자 UI의 동의 문자열을 업데이트할 것입니다.

**현재 텍스트.** [tenantName] 리소스에 액세스하려면 사용 약관에 동의해야 합니다.<br>**새 텍스트.** [tenantName] 리소스에 액세스하려면 사용 약관을 읽어야 합니다.

**현재 텍스트:** 동의를 선택하면 위의 모든 사용 약관에 동의하는 것입니다.<br>**새 텍스트:** 사용 약관을 읽고 이해한 것을 확인하려면 동의를 클릭합니다.

---

### <a name="pass-through-authentication-supports-legacy-protocols-and-applications"></a>통과 인증은 레거시 프로토콜 및 애플리케이션 지원

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

이제 통과 인증은 레거시 프로토콜 및 응용 프로그램을 지원합니다. 이제 다음 제한 사항이 완전히 지원됩니다.

- 사용자가 최신 인증 없이 레거시 Office 클라이언트 애플리케이션, Office 2010 및 Office 2013에 로그인.

- Office 2010의 Exchange 하이브리드 환경에서만 일정 공유 및 약속 있음/없음 정보에 액세스하세요.

- 사용자가 최신 인증 없이 비즈니스용 Skype 클라이언트 애플리케이션에 로그인.

- 사용자가 PowerShell 버전 1.0에 로그인.

- iOS 설정 도우미를 사용하는 Apple DEP(Apple 장비 등록 프로그램).

---

### <a name="converged-security-info-management-for-self-service-password-reset-and-multi-factor-authentication"></a>셀프 서비스 암호 재설정 및 Multi-Factor Authentication을 위한 융합형 보안 정보

**유형:** 새 기능 **서비스 범주:** SSPR **제품 기능:** 사용자 인증

사용자는 이 새로운 기능을 통해 SSPR(셀프 서비스 암호 재설정) 및 MFA(Multi-Factor Authentication)에 대한 보안 정보(예: 전화 번호, 이메일 주소, 모바일 앱 및 등)를 단일 환경에서 관리할 수 있습니다. 사용자는 더 이상 SSPR 및 MFA에 대한 동일한 보안 정보를 서로 다른 두 환경에 등록할 필요가 없습니다. 이 새로운 환경은 SSPR 또는 MFA를 사용하는 사용자에게도 적용됩니다.

조직에서 MFA 또는 SSPR 등록을 강제로 적용하지 않는 경우 사용자는 **My Apps** 포털을 통해 보안 정보를 등록할 수 있습니다. 여기서 사용자는 MFA 또는 SSPR에 대해 설정된 방법을 등록할 수 있습니다.

이 기능은 옵트인 공개 미리 보기입니다. 관리자는 원하는 경우 테넌트의 특정 사용자 그룹 또는 모든 사용자에게 새 환경을 적용할 수 있습니다.

---

### <a name="use-the-microsoft-authenticator-app-to-verify-your-identity-when-you-reset-your-password"></a>암호를 재설정할 때 Microsoft Authenticator 앱을 사용하여 ID 확인

**유형:** 변경된 기능 **서비스 범주:** SSPR **제품 기능:** 사용자 인증

관리자가 아닌 사용자는 이 기능을 통해 Microsoft Authenticator(또는 다른 인증 앱)에서 알림 또는 코드를 사용하여 암호를 재설정하는 동안 자신의 ID를 확인할 수 있습니다. 관리자가 이 셀프 서비스 암호 재설정 방법을 설정하면 aka.ms/mfasetup 또는 aka.ms/setupsecurityinfo를 통해 모바일 앱을 등록한 사용자는 암호를 재설정하는 동안 모바일 앱을 인증 방법으로 사용할 수 있습니다.

모바일 앱 알림은 암호를 재설정하는 두 가지 방법을 요구하는 정책의 일부로만 설정할 수 있습니다.

---

## <a name="june-2018"></a>2018년 6월

### <a name="change-notice-security-fix-to-the-delegated-authorization-flow-for-apps-using-azure-ad-activity-logs-api"></a>변경 알림: Azure AD 활동 로그 API를 사용하여 앱에 대한 위임된 사용 권한 부여 흐름의 보안 수정

**유형:** 변경 계획 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

더 강력한 보안 적용으로 인해 [Azure AD 활동 로그 API](../reports-monitoring/concept-reporting-api.md)에 액세스하는 데 위임된 사용 권한 부여 흐름을 사용하는 앱에 대한 사용 권한을 변경해야 했습니다. 이 변경 내용은 **2018년 6월 26일** 에 발생합니다.

앱이 Azure AD 활동 로그 API를 사용하는 경우 다음 단계를 따라 변경 내용이 발생한 후에 앱이 중단되지 않는지 확인합니다.

**앱 사용 권한을 업데이트하려면**

1. Azure Portal에 로그인하고 **Azure Active Directory** 를 선택한 다음, **앱 등록** 을 선택합니다.
2. Azure AD 활동 로그 API를 사용하는 앱을 선택하고 **설정** 을 선택하고 **필수 권한** 을 선택한 다음, **Windows Azure Active Directory** API를 선택합니다.
3. **액세스 활성화** 블레이드의 **위임된 사용 권한** 영역에서 **디렉터리 읽기** 데이터 옆의 상자를 선택한 다음, **저장** 을 선택합니다.
4. **사용 권한 부여** 를 선택한 다음, **예** 를 선택합니다.

    >[!Note]
    >앱에 사용 권한을 부여하려면 전역 관리자여야 합니다.

자세한 내용은 Azure AD Reporting API에 액세스하기 위한 필수 구성 요소 문서에서 [권한 부여](../reports-monitoring/howto-configure-prerequisites-for-reporting-api.md#grant-permissions) 영역을 참조하세요.

---

### <a name="configure-tls-settings-to-connect-to-azure-ad-services-for-pci-dss-compliance"></a>PCI DSS 준수를 위해 Azure AD 서비스에 연결하도록 TLS 설정 구성

**유형:** 새 기능 **서비스 범주:** 해당 없음 **제품 기능:** 플랫폼

TLS(전송 계층 보안)는 통신하는 두 애플리케이션 간에 개인 정보 보호 및 데이터 무결성을 제공하는 프로토콜이며 현재 가장 널리 사용되는 보안 프로토콜입니다.

[PCI Security Standards Council](https://www.pcisecuritystandards.org/)에서는 **2018년 6월 30일** 부터 보다 새롭고 안전한 앱 프로토콜을 사용하기 위해 TLS 및 SSL(Secure Sockets Layer)의 초기 버전을 사용하지 않기로 결정했습니다. 따라서 Azure AD 서비스에 연결하고 PCI DSS를 준수해야 하는 경우 TLS 1.0을 사용하지 않도록 설정해야 합니다. 여러 가지 버전의 TLS를 사용할 수 있지만 Azure Active Directory 서비스에서 사용할 수 있는 최신 버전은 TLS 1.2입니다. 클라이언트/서버 및 브라우저/서버 조합 모두를 TLS 1.2로 바로 변경하는 것이 좋습니다.

오래된 브라우저에서는 TLS 1.2와 같은 새로운 TLS 버전이 지원되지 않을 수도 있습니다. 브라우저에서 지원되는 TLS 버전을 확인하려면 [Qualys SSL Labs](https://www.ssllabs.com/) 사이트로 이동하여 **Test your browser**(브라우저 테스트)클릭하세요. 최신 버전의 웹 브라우저로 업그레이드하고 TLS 1.2만 사용하도록 설정하는 것이 좋습니다.

**TLS 1.2를 사용하도록 설정하려면, 브라우저별로**

- **Microsoft Edge 및 Internet Explorer(두 가지 모두 Internet Explorer를 사용하여 설정)**

    1. Internet Explorer를 열고 **도구** > **인터넷 옵션** > **고급** 을 선택합니다.
    2. **보안** 영역에서 **TLS 1.2 사용** 을 선택한 다음, **확인** 을 선택합니다.
    3. 브라우저 창을 모두 닫고 Internet Explorer를 다시 시작합니다.

- **Google Chrome**

    1. Google Chrome을 열고 주소 표시줄에 *chrome://settings/* 을 입력하고 **Enter** 키를 누릅니다.
    2. **고급** 옵션을 펼치고 **시스템** 영역으로 이동하여 **프록시 설정 열기** 를 선택합니다.
    3. **인터넷 속성** 상자에서 **고급** 탭을 선택하고 **보안** 영역으로 이동하여 **TLS 1.2 사용** 을 선택한 다음, **확인** 을 선택합니다.
    4. 브라우저 창을 모두 닫고 Google Chrome을 다시 시작합니다.

- **Mozilla Firefox**

    1. Firefox를 열어서 주소 표시줄에 *about:config* 를 입력한 다음, **Enter** 키를 누릅니다.
    2. *TLS* 라는 용어를 검색한 다음, **security.tls.version.max** 항목을 선택합니다.
    3. 값을 **3** 으로 설정하여 브라우저에서 TLS 1.2 버전까지 사용하도록 하고 **확인** 을 선택합니다.

        >[!NOTE]
        >Firefox 버전 60.0은 TLS 1.3을 지원하므로 security.tls.version.max 값을 **4** 로 설정할 수도 있습니다.

    4. 브라우저 창을 모두 닫고 Mozilla Firefox를 다시 시작합니다.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---june-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 6월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 6월에 페더레이션이 지원되는 신규 앱 15개가 앱 갤러리에 추가되었습니다.

[Skytap](../saas-apps/skytap-tutorial.md), [Settling music](../saas-apps/settlingmusic-tutorial.md), [SAML 1.1 토큰 사용 LOB 앱](../saas-apps/saml-tutorial.md), [Supermood](../saas-apps/supermood-tutorial.md), [Autotask](../saas-apps/autotaskendpointbackup-tutorial.md), [Endpoint Backup](../saas-apps/autotaskendpointbackup-tutorial.md), [Skyhigh Networks](../saas-apps/skyhighnetworks-tutorial.md), Smartway2, [TonicDM](../saas-apps/tonicdm-tutorial.md), [Moconavi](../saas-apps/moconavi-tutorial.md), [Zoho One](../saas-apps/zohoone-tutorial.md), [SharePoint 온-프레미스](../saas-apps/sharepoint-on-premises-tutorial.md), [ForeSee CX Suite](../saas-apps/foreseecxsuite-tutorial.md), [Vidyard](../saas-apps/vidyard-tutorial.md), [ChronicX](../saas-apps/chronicx-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요. Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="azure-ad-password-protection-is-available-in-public-preview"></a>Azure AD 암호 보호가 공개 미리 보기로 제공됩니다.

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** 사용자 인증

Azure AD 암호 보호를 사용하면 쉽게 추측되는 암호를 환경에서 제거하는 데 도움이 됩니다. 이러한 암호를 제거하면 암호 스프레이 유형의 공격으로 인해 손상될 위험을 줄일 수 있습니다.

구체적으로는, Azure AD 암호 보호는 다음과 같은 이점을 제공합니다.

- Azure AD와 Windows Server AD(Active Directory) 모두에서 조직의 계정이 보호됩니다.
- 가장 일반적으로 사용되는 500개를 초과하는 암호 목록과 이러한 암호에 대한 백만개가 넘는 문자 대체 변형에 포함된 암호의 사용이 금지됩니다.
- Azure AD 포털의 단일 위치에서 또는 Azure AD와 온-프레미스 Windows Server AD 모두에서 Azure AD 암호 보호를 관리할 수 있습니다.

Azure AD 암호 보호에 대한 자세한 내용은 [조직에서 잘못된 암호 제거](../authentication/concept-password-ban-bad.md)를 참조하세요.

---

### <a name="new-all-guests-conditional-access-policy-template-created-during-terms-of-use-creation"></a>사용 약관을 만드는 동안 "모든 게스트" 조건부 액세스 정책 템플릿 생성

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

사용 약관을 만드는 동안 "모든 게스트"와 "모드 앱"에 대한 조건부 액세스 정책 템플릿이 새로 만들어집니다. 새로운 정책 템플릿은 새로 만들어진 ToU를 적용하며 게스트에 대한 생성 및 적용 프로세스를 간소화합니다.

자세한 내용은 [Azure Active Directory 사용 약관 기능](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="new-custom-conditional-access-policy-template-created-during-terms-of-use-creation"></a>사용 약관을 만드는 동안 "사용자 지정" 조건부 액세스 정책 템플릿 생성

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 거버넌스

사용 약관을 만드는 동안 "사용자 지정" 조건부 액세스 정책 템플릿도 새로 만들어집니다. 새 정책 템플릿을 사용하면 ToU를 만든 다음, 수동으로 포털을 탐색할 필요 없이 조건부 액세스 정책 생성 블레이드로 즉시 이동할 수 있습니다.

자세한 내용은 [Azure Active Directory 사용 약관 기능](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="new-and-comprehensive-guidance-about-deploying-azure-ad-multi-factor-authentication"></a>Azure AD Multi-Factor Authentication 배포에 대 한 새로운 및 포괄적인 지침

**유형:** 새 기능 **서비스 범주:** 기타 **제품 기능:** ID 보안 및 보호

조직에서 MFA (Azure AD Multi-Factor Authentication)를 배포 하는 방법에 대 한 단계별 지침이 새로 출시 되었습니다.

MFA 배포 가이드를 보려면 GitHub의 [Identity Deployment Guides](./active-directory-deployment-plans.md)(ID 배포 가이드) 리포지토리로 이동하세요. 배포 가이드에 대한 피드백을 제공하려면 [배포 계획 사용자 의견 양식](https://aka.ms/deploymentplanfeedback)을 참조하세요. 배포 가이드에 대한 질문이 있는 경우 [IDGitDeploy](mailto:idgitdeploy@microsoft.com)에 문의하세요.

---

### <a name="azure-ad-delegated-app-management-roles-are-in-public-preview"></a>Azure AD 위임된 앱 관리 역할이 공개 미리 보기 상태입니다.

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** Access Control

관리자는 전역 관리자 역할을 할당하지 않고도 앱 관리 작업을 위임할 수 있습니다. 새로운 역할과 기능은 다음과 같습니다.

- **새로운 표준 Azure AD 관리자 역할:**

    - **애플리케이션 관리자.** 모든 앱의 모든 측면(예: 등록, SSO 설정, 앱 할당 및 라이선싱, 앱 프록시 설정 및 승인)을 관리하는 기능을 부여합니다(Azure AD 리소스 제외).

    - **클라우드 애플리케이션 관리자.** 모든 애플리케이션 관리자 권한을 부여합니다. 앱 프록시는 온-프레미스 액세스를 제공하지 않기 때문에 예외입니다.

    - **애플리케이션 개발자.** **사용자가 앱을 등록하도록 허용** 하는 옵션이 꺼져 있는 경우에도 앱 등록을 만들 수 있는 권한을 부여합니다.

- **소유권(그룹 소유권 프로세스와 유사하게 앱별 등록 및 엔터프라이즈별 앱을 설정합니다.):**

    - **앱 등록 소유자.** 앱 매니페스트를 비롯하여 소유한 앱 등록의 모든 측면을 관리하고 소유자를 더 추가할 수 있는 권한을 부여합니다.

    - **엔터프라이즈 앱 소유자.** 소유한 엔터프라이즈 앱의 많은 측면(예: SSO 설정, 앱 할당 및 동의)을 관리할 수 있는 권한을 부여합니다(Azure AD 리소스 제외).

공개 미리 보기에 대한 자세한 내용은 [Azure AD 위임된 애플리케이션 관리 역할이 공개 미리 보기 상태입니다!](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/13/hallelujah-azure-ad-delegated-application-management-roles-are-in-public-preview/) 블로그를 참조하세요. 역할 및 권한에 대한 자세한 내용은 [Azure Active Directory에서 관리자 역할 할당](../roles/permissions-reference.md)을 참조하세요.

---

## <a name="may-2018"></a>2018년 5월

### <a name="expressroute-support-changes"></a>ExpressRoute 지원 변경

**유형:** 변경 계획 **서비스 범주:** 인증(로그인) **제품 기능:** 플랫폼

Azure AD(Azure Active Directory)와 같은 서비스 제공으로 소프트웨어는 ExpressRoute 또는 다른 프라이빗 VPN 터널의 필요 없이 인터넷을 통해 직접 이동하여 가장 잘 작동하도록 설계됩니다. 이로 인해 **2018년 8월 1일** 에 Azure 공용 피어링 및 Microsoft 피어링의 Microsoft 커뮤니티를 사용하여 Azure AD 서비스에 대한 ExpressRoute 지원을 중지합니다. 이러한 변경 내용의 영향을 받는 모든 서비스는 Azure AD 트래픽이 ExpressRoute에서 인터넷으로 점차적으로 이동하는 것을 확인할 수 있습니다.

지원을 변경하는 동안 인증 트래픽에 대해 전용 회로 집합을 사용해야 할 수 있는 상황이 여전히 있다는 것을 알고 있습니다. 이로 인해 Azure AD는 ExpressRoute 및 "기타 Office 365 온라인 서비스" 커뮤니티와 함께 Microsoft 피어링에 이미 있는 서비스를 사용하여 테넌트당 IP 범위 제한을 계속해서 지원할 예정입니다. 서비스가 영향을 받지만 ExpressRoute가 필요한 경우 다음을 수행해야 합니다.

- **Azure 공용 피어링에 있는 경우** Microsoft 피어링으로 이동하고 **기타 Office 365 온라인 서비스(12076:5100)** 커뮤니티에 등록합니다. Azure 공용 피어링에서 Microsoft 피어링으로 이동하는 방법에 대한 자세한 내용은 [Microsoft 피어링으로 공용 피어링 이동](../../expressroute/how-to-move-peering.md) 문서를 참조하세요.

- **Microsoft 피어링에 있는 경우** **기타 Office 365 온라인 서비스(12076:5100)** 커뮤니티에 등록합니다. 라우팅 요구 사항에 대한 자세한 내용은 ExpressRoute 라우팅 요구 사항 문서의 [BGP 커뮤니티에 대한 지원 섹션](../../expressroute/expressroute-routing.md#bgp)을 참조하세요.

전용 회로를 계속해서 사용해야 하는 경우 **기타 Office 365 온라인 서비스(12076:5100)** 커뮤니티를 사용하도록 권한을 얻는 방법에 대해 Microsoft 계정 팀에게 문의해야 합니다. MS Office 관리 검토 위원회는 해당 회로가 필요한지 여부를 확인하고 이를 유지하는 기술적 의미를 이해하도록 합니다. Office 365에 대한 경로 필터를 만들도록 시도하는 인증되지 않은 구독은 오류 메시지를 받습니다.

---

### <a name="microsoft-graph-apis-for-administrative-scenarios-for-tou"></a>TOU의 관리 시나리오를 위한 Microsoft Graph API

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 개발자 환경

Azure AD 사용 약관의 관리 작업에 대한 Microsoft Graph API가 추가되었습니다. 사용 약관 개체를 만들고, 업데이트하고, 삭제할 수 있습니다.

---

### <a name="add-azure-ad-multi-tenant-endpoint-as-an-identity-provider-in-azure-ad-b2c"></a>Azure AD 다중 테넌트 엔드포인트를 Azure AD B2C의 ID 공급자로 추가

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

사용자 지정 정책을 사용하여 이제 Azure AD B2C에서 ID 공급자로 Azure AD 공용 엔드포인트를 추가할 수 있습니다. 이를 통해 애플리케이션에 로그인하는 모든 Azure AD 사용자에 대한 항목의 단일 지점을 가질 수 있습니다. 자세한 내용은 [Azure Active Directory B2C: 사용자 지정 정책을 사용하여 사용자가 다중 테넌트 Azure AD ID 공급자에 로그인하도록 허용](../../active-directory-b2c/identity-provider-azure-ad-multi-tenant.md)을 참조하세요.

---

### <a name="use-internal-urls-to-access-apps-from-anywhere-with-our-my-apps-sign-in-extension-and-the-azure-ad-application-proxy"></a>내 앱 로그인 확장 및 Azure AD 애플리케이션 프록시를 통해 내부 URL을 사용하여 어디서나 앱에 액세스

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** SSO

사용자는 이제 Azure AD에 대한 내 앱 보안 로그인 확장을 사용하여 회사 네트워크 외부에서도 내부 URL을 통해 애플리케이션에 액세스할 수 있습니다. 이는 액세스 패널 브라우저 확장이 설치되어 있는 모든 브라우저에서 Azure AD 애플리케이션 프록시를 사용하여 게시한 모든 애플리케이션에 사용할 수 있습니다. URL 리디렉션 기능은 사용자가 확장에 로그인하면 자동으로 활성화됩니다. 확장은 [Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=845176), [Chrome](https://go.microsoft.com/fwlink/?linkid=866367) 및 [Firefox](https://go.microsoft.com/fwlink/?linkid=866366)에서 다운로드에 사용할 수 있습니다.

---

### <a name="azure-active-directory---data-in-europe-for-europe-customers"></a>Azure Active Directory - 유럽 고객을 위한 유럽의 데이터

**유형:** 새 기능 **서비스 범주:** 기타 **제품 기능:** GoLocal

유럽의 고객은 데이터를 유럽에 유지해야 하며 개인 정보 보호 및 유럽 법을 충족하도록 유럽 데이터 센터 외부에서 복제되지 않습니다. 이 [문서](./active-directory-data-storage-eu.md)는 유럽 내에서 저장되는 ID 정보에 대한 특정 세부 정보를 제공하고 유럽 데이터 센터 외부에 저장되는 정보에 대한 세부 정보도 제공합니다.

---

### <a name="new-user-provisioning-saas-app-integrations---may-2018"></a>새 사용자 프로비저닝 SaaS 앱 통합 - 2018년 5월

**유형:** 새 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** 타사 통합

Azure AD를 사용하면 Dropbox, Salesforce, ServiceNow 등과 같은 SaaS 애플리케이션에서 사용자 ID 만들기, 유지 관리 및 제거를 자동화할 수 있습니다. 2018년 5월에 Azure AD 앱 갤러리에서 다음 애플리케이션에 대한 사용자 프로비저닝 지원을 추가했습니다.

- [BlueJeans](../saas-apps/bluejeans-provisioning-tutorial.md)

- [Cornerstone OnDemand](../saas-apps/cornerstone-ondemand-provisioning-tutorial.md)

- [Zendesk](../saas-apps/zendesk-provisioning-tutorial.md)

Azure AD 갤러리에서 사용자 프로비저닝을 지원하는 모든 애플리케이션의 목록은 [https://aka.ms/appstutorial](../saas-apps/tutorial-list.md)을 참조하세요.

---

### <a name="azure-ad-access-reviews-of-groups-and-app-access-now-provides-recurring-reviews"></a>이제 그룹 및 앱 액세스에 대한 Azure AD 액세스 검토가 반복 검토 제공

**유형:** 새 기능 **서비스 범주:** 액세스 검토 **제품 기능:** 거버넌스

이제 Azure AD Premium P2의 일부로 그룹 및 앱에 대한 액세스 검토를 일반적으로 사용할 수 있습니다.  관리자는 월간 또는 분기별과 같은 정기적인 간격으로 그룹 멤버 자격 및 애플리케이션 할당에 대한 액세스 검토를 자동으로 반복하도록 구성할 수 있습니다.

---

### <a name="azure-ad-activity-logs-sign-ins-and-audit-are-now-available-through-ms-graph"></a>이제 Azure AD 활동 로그(로그인 및 감사)를 MS Graph를 통해 사용 가능

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

이제 Microsoft Graph API를 통해 Azure AD 활동 로그(로그인 및 감사 로그 포함)를 사용할 수 있습니다. 이러한 로그에 액세스하도록 Microsoft Graph API를 통해 2개의 엔드포인트를 공개했습니다. Azure AD Reporting API에 프로그래밍 방식으로 액세스하여 시작하려면 [문서](../reports-monitoring/concept-reporting-api.md)를 참조하세요.

---

### <a name="improvements-to-the-b2b-redemption-experience-and-leave-an-org"></a>B2B 상환 환경 및 조직 떠나기에 대한 개선

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C

**JIT(Just in time) 상환:** B2B API를 사용하여 게스트 사용자와 리소스를 공유하면 특별한 초대 이메일을 보낼 필요가 없습니다. 대부분의 경우에서 게스트 사용자는 리소스에 액세스할 수 있으며 필요한 때에 상환 환경을 통해 제거됩니다. 누락된 이메일로 인한 영향이 더 이상 없습니다. 게스트 사용자에게 "시스템이 보낸 해당 상환 링크를 클릭했나요?"라고 더 이상 묻지 않습니다. 즉, SPO에서 초대 관리자를 사용하면 흐린 첨부 파일은 모든 상환 상태에서 내부 및 외부 모든 사용자에 대해 동일한 정식 URL을 가질 수 있습니다.

**최신 상환 환경:** 더 이상 화면 상환 방문 페이지를 분할하지 않습니다. 사용자는 타사 앱에 대해 수행하는 것과 같이 초대 조직의 개인정보처리방침과 함께 최신 동의 환경을 봅니다.

**게스트 사용자는 조직을 떠날 수 있음:** 조직과 사용자의 관계가 끝나면 사용자는 스스로 조직을 떠날 수 있습니다. "제거되는" 초대 조직의 관리자를 더 이상 호출하지 않고, 지원 티켓을 더 이상 발생하지 않습니다.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---may-2018"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱 - 2018년 5월

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 5월에 페더레이션이 지원되는 신규 앱 18개가 앱 갤러리에 추가되었습니다.

[AwardSpring](../saas-apps/awardspring-tutorial.md), Infogix Data3Sixty Govern, [Yodeck](../saas-apps/infogix-tutorial.md), [Jamf Pro](../saas-apps/jamfprosamlconnector-tutorial.md), [KnowledgeOwl](../saas-apps/knowledgeowl-tutorial.md), [Envi MMIS](../saas-apps/envimmis-tutorial.md), [LaunchDarkly](../saas-apps/launchdarkly-tutorial.md), [Adobe Captivate Prime](../saas-apps/adobecaptivateprime-tutorial.md), [Montage Online](../saas-apps/montageonline-tutorial.md), [まなびポケット](../saas-apps/manabipocket-tutorial.md), OpenReel, [Arc Publishing - SSO](../saas-apps/arc-tutorial.md), [PlanGrid](../saas-apps/plangrid-tutorial.md), [iWellnessNow](../saas-apps/iwellnessnow-tutorial.md), [Proxyclick](../saas-apps/proxyclick-tutorial.md), [Riskware](../saas-apps/riskware-tutorial.md), [Flock](../saas-apps/flock-tutorial.md), [Reviewsnap](../saas-apps/reviewsnap-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="new-step-by-step-deployment-guides-for-azure-active-directory"></a>Azure Active Directory에 대한 새로운 단계별 배포 가이드

**유형:** 새 기능 **서비스 범주:** 기타 **제품 기능:** 디렉터리

Azure AD(Azure Active Directory)를 배포하는 방법에 대한 새로운 단계별 가이드이며 SSPR(셀프 서비스 암호 재설정), SSO(Single Sign-On), CA(조건부 액세스), 앱 프록시, 사용자 프로비저닝, PTA(통과 인증)에 대한 ADFS(Active Directory Federation Services), PHS(암호 해시 동기화)에 대한 ADFS가 포함됩니다.

배포 가이드를 보려면 GitHub의 [Identity Deployment Guides](./active-directory-deployment-plans.md)(ID 배포 가이드) 리포지토리로 이동하세요. 배포 가이드에 대한 피드백을 제공하려면 [배포 계획 사용자 의견 양식](https://aka.ms/deploymentplanfeedback)을 참조하세요. 배포 가이드에 대한 질문이 있는 경우 [IDGitDeploy](mailto:idgitdeploy@microsoft.com)에 문의하세요.

---

### <a name="enterprise-applications-search---load-more-apps"></a>Enterprise 애플리케이션 검색 - 앱 추가 로드

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

애플리케이션/서비스 사용자를 찾는 데 문제가 있나요? 엔터프라이즈 애플리케이션 모든 애플리케이션 목록에 더 많은 애플리케이션을 로드하는 기능을 추가했습니다. 기본적으로 20개의 애플리케이션을 표시합니다. 이제 **추가 로드** 를 클릭하여 추가 애플리케이션을 볼 수 있습니다.

---

### <a name="the-may-release-of-aadconnect-contains-a-public-preview-of-the-integration-with-pingfederate-important-security-updates-many-bug-fixes-and-new-great-new-troubleshooting-tools"></a>AADConnect의 5월 릴리스에는 PingFederate와의 통합, 중요 보안 업데이트, 여러 가지 버그 수정 및 뛰어난 새 문제 해결 도구에 대한 공개 미리 보기가 포함되어 있습니다.

**유형:** 변경된 기능 **서비스 범주:** AD Connect **제품 기능:** ID 수명 주기 관리

AADConnect의 5월 릴리스에는 PingFederate와의 통합, 중요 보안 업데이트, 여러 가지 버그 수정 및 뛰어난 새 문제 해결 도구에 대한 공개 미리 보기가 포함되어 있습니다. [여기](../hybrid/reference-connect-version-history.md)에서 릴리스 정보를 찾을 수 있습니다.

---

### <a name="azure-ad-access-reviews-auto-apply"></a>Azure AD 액세스 검토: 자동 적용

**유형:** 변경된 기능 **서비스 범주:** 액세스 검토 **제품 기능:** 거버넌스

이제 Azure AD Premium P2의 일부로 그룹 및 앱에 대한 액세스 검토를 일반적으로 사용할 수 있습니다. 관리자는 액세스 검토가 완료되면 검토자의 변경 내용을 해당 그룹 또는 앱에 자동으로 적용하도록 구성할 수 있습니다. 관리자는 검토자가 응답하지 않는 경우 사용자가 지속적으로 액세스하면 어떤 상황이 발생하는지 지정하고, 액세스를 제거하고, 액세스를 유지하거나 시스템 권장 사항을 사용할 수도 있습니다.

---

### <a name="id-tokens-can-no-longer-be-returned-using-the-query-response_mode-for-new-apps"></a>ID 토큰은 새 앱의 response_mode 쿼리를 사용하여 더 이상 반환할 수 없습니다.

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

2018년 4월 25일 이후에 생성되는 앱은 더 이상 response_mode **쿼리** 를 사용하여 **id_token** 을 요청할 수 없습니다.  OIDC 사양으로 Azure AD 인라인을 가져오고 앱 공격 노출 영역을 줄일 수 있습니다.  2018년 4월 25일 이전에 생성되는 앱은 **id_token** 의 response_type으로 response_mode **쿼리** 사용이 차단됩니다.  Azure AD에서 id_token를 요청 하는 경우 반환 되는 오류는 **AADSTS70007: 토큰을 요청할 때 ' query '는 ' response_mode '의 지원** 되는 값이 아닙니다.

새 애플리케이션 개체(예: 앱 프록시 사용)를 만들 때 **fragment** 및 **form_post** response_mode는 계속해서 작동합니다. 새 애플리케이션을 만들기 전에 이러한 response_mode 중 하나를 사용하는지 확인합니다.

---

## <a name="april-2018"></a>2018년 4월

### <a name="azure-ad-b2c-access-token-are-ga"></a>Azure AD B2C 액세스 토큰이 GA 상태입니다.

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 액세스 토큰을 사용하여 Azure AD B2C로 보호된 Web API에 액세스할 수 있습니다. 기능은 공개 미리 보기에서 GA로 전환되고 있습니다. Azure AD B2C 애플리케이션 및 웹 API를 구성하는 UI 환경이 향상되었고 기타 사소한 사항이 개선되었습니다.

자세한 내용은 [Azure AD B2C: 액세스 토큰 요청](../../active-directory-b2c/access-tokens.md)을 참조하세요.

---

### <a name="test-single-sign-on-configuration-for-saml-based-applications"></a>SAML 기반 애플리케이션에 대한 Single Sign-On 구성 테스트

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

SAML 기반 SSO 애플리케이션을 구성하는 경우 구성 페이지에서 통합을 테스트할 수 있습니다. 로그인하는 동안 오류가 발생하면 테스트 환경에서 오류를 제공할 수 있으며 Azure AD는 특정 문제를 해결하는 해결 단계를 제공합니다.

자세한 내용은 다음을 참조하세요.

- [Azure Active Directory 애플리케이션 갤러리에 있지 않은 애플리케이션에 Single Sign-On 구성](../manage-apps/view-applications-portal.md)
- [Azure Active Directory에서 SAML 기반 Single Sign-On을 애플리케이션에 디버그하는 방법](../manage-apps/debug-saml-sso-issues.md)

---

### <a name="azure-ad-terms-of-use-now-has-per-user-reporting"></a>이제 Azure AD 사용 약관에 사용자별 보고 사용

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

이제 관리자는 지정된 ToU를 선택하고 해당 ToU에 동의한 사용자 및 발생한 날짜/시간을 확인할 수 있습니다.

자세한 내용은 [Azure AD 사용 약관 기능](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="azure-ad-connect-health-risky-ip-for-ad-fs-extranet-lockout-protection"></a>Azure AD Connect Health: AD FS 엑스트라넷 잠금 보호를 위한 위험한 IP

**유형:** 새 기능 **서비스 범주:** 기타 **제품 기능:** 모니터링 및 보고

Connect Health는 이제 매시간 또는 매일 별로 실패한 U/P 로그인의 임계값을 초과하는 IP 주소를 검색하는 기능을 지원합니다. 이 기능에서 제공하는 기능은 다음과 같습니다.

- IP 주소 및 사용자 지정 가능한 임계값으로 매시간/매일 별로 생성된 로그인 실패 횟수를 보여주는 포괄적인 보고서
- 매시간/매일 별로 특정 IP 주소가 실패한 U/P 로그인의 임계값을 초과한 경우를 보여주는 이메일 기반 경고
- 데이터의 상세한 분석을 수행하는 다운로드 옵션

자세한 내용은 [위험한 IP 보고서](../hybrid/how-to-connect-health-adfs.md)를 참조하세요.

---

### <a name="easy-app-config-with-metadata-file-or-url"></a>메타데이터 파일 또는 URL을 사용한 간편한 앱 구성

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

엔터프라이즈 응용 프로그램 페이지에서 관리자는 SAML 메타 데이터 파일을 업로드 하 여 Azure AD 갤러리 및 비 갤러리 응용 프로그램에 대 한 SAML 기반 로그온을 구성할 수 있습니다.

또한 Azure AD 애플리케이션 페더레이션 메타데이터 URL을 사용하여 대상 애플리케이션으로 SSO를 구성할 수 있습니다.

자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 있지 않은 애플리케이션에 Single Sign-On 구성](../manage-apps/view-applications-portal.md)을 참조하세요.

---

### <a name="azure-ad-terms-of-use-now-generally-available"></a>이제 Azure AD 사용 약관을 일반적으로 사용할 수 있습니다.

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수


Azure AD 사용 약관은 공개 미리 보기에서 일반 공급으로 이동했습니다.

자세한 내용은 [Azure AD 사용 약관 기능](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="allow-or-block-invitations-to-b2b-users-from-specific-organizations"></a>특정 조직의 B2B 사용자 초대 허용 또는 차단

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C


이제 Azure AD B2B 협업에서 공유하고 협업하려는 파트너 조직을 지정할 수 있습니다. 이를 위해 특정 허용 또는 거부 도메인의 목록을 만들도록 선택할 수 있습니다. 이러한 기능을 사용하여 도메인이 차단되면 직원은 해당 도메인의 사용자에게 더 이상 초대를 보낼 수 없습니다.

이렇게 하면 승인된 사용자를 위해 부드러운 환경을 활성화하는 동안 리소스에 대한 액세스를 제어할 수 있습니다.

이 B2B 협업 기능은 모든 Azure Active Directory 고객에 대해 사용할 수 있으며 외부 비즈니스 사용자가 로그인하고 액세스를 획득하는 시기 및 방법의 더욱 세부적인 제어를 위해 조건부 액세스 및 ID 보호와 같은 Azure AD Premium 기능과 함께 사용할 수 있습니다.

자세한 내용은 [특정 조직의 B2B 사용자 초대 허용 또는 차단](../external-identities/allow-deny-list.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 4월에 페더레이션이 지원되는 신규 앱 13개가 앱 갤러리에 추가되었습니다.

조건 HCM, [FiscalNote](../saas-apps/fiscalnote-tutorial.md), [Secret Server (On-Premises)](../saas-apps/secretserver-on-premises-tutorial.md), [Dynamic Signal](../saas-apps/dynamicsignal-tutorial.md), [mindWireless](../saas-apps/mindwireless-tutorial.md), [조직도 Now](../saas-apps/orgchartnow-tutorial.md), [Ziflow](../saas-apps/ziflow-tutorial.md), [appneta Performance Monitor](../saas-apps/appneta-tutorial.md), [Elium](../saas-apps/elium-tutorial.md), [Fluxx Labs](../saas-apps/fluxxlabs-tutorial.md), [Cisco Cloud](../saas-apps/ciscocloud-tutorial.md), 선반, [etynet](../saas-apps/safetynet-tutorial.md)

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="grant-b2b-users-in-azure-ad-access-to-your-on-premises-applications-public-preview"></a>Azure AD의 B2B 사용자에게 온-프레미스 애플리케이션에 대한 액세스 권한 부여(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** B2B **제품 기능:** B2B/B2C

Azure AD(Azure Active Directory) B2B 협업 기능을 사용하여 파트너 조직의 게스트 사용자를 Azure AD로 초대하는 조직의 경우 이제 이러한 B2B 사용자에게 온-프레미스 앱에 대한 액세스를 제공할 수 있습니다. 이러한 온-프레미스 앱은 SAML 기반 인증 또는 KCD(Kerberos 제한 위임)과 함께 IWA(Windows 통합 인증)를 사용할 수 있습니다.

자세한 내용은 [Azure AD의 B2B 사용자에게 온-프레미스 애플리케이션에 대한 액세스 권한 부여](../external-identities/hybrid-cloud-to-on-premises.md)를 참조하세요.

---

### <a name="get-sso-integration-tutorials-from-the-azure-marketplace"></a>Azure Marketplace에서 SSO 통합 자습서 가져오기

**유형:** 변경된 기능 **서비스 범주:** 기타 **제품 기능:** 타사 통합

[Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps?page=1)에 나열된 애플리케이션이 SAML 기반 Single Sign-On을 지원하는 경우 **지금 사용해 보세요** 를 클릭하면 해당 애플리케이션과 관련된 통합 자습서가 제공됩니다.

---

### <a name="faster-performance-of-azure-ad-automatic-user-provisioning-to-saas-applications"></a>더 빨라진 SaaS 애플리케이션에 대한 Azure AD 자동 사용자 프로비저닝 성능

**유형:** 변경된 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** 타사 통합

이전에는 고객이 SaaS 애플리케이션용 Azure Active Directory 사용자 프로비저닝 커넥터(예: Salesforce, ServiceNow 및 Box)를 사용할 때 Azure AD 테넌트에 100,000개 이상의 결합된 사용자 및 그룹이 포함된 경우 성능이 저하되었으며 프로비전할 사용자를 결정하기 위해 사용자 및 그룹 할당이 사용되었습니다.

2018년 4월 2일에 Azure Active Directory와 대상 SaaS 애플리케이션 간의 초기 동기화를 수행하는 데 필요한 시간을 크게 줄이는 매우 중요한 성능 향상이 Azure AD 프로비저닝 서비스에 배포되었습니다.

따라서 앱에 대한 초기 동기화를 수행하는 데 수 일이 걸리거나 완료되지 않았던 많은 고객은 이제 몇 분 또는 몇 시간 내에 이를 완료합니다.

자세한 내용은 [프로비전하는 동안 어떻게 됩니까?](../..//active-directory/app-provisioning/how-provisioning-works.md)를 참조하세요.

---

### <a name="self-service-password-reset-from-windows-10-lock-screen-for-hybrid-azure-ad-joined-machines"></a>하이브리드 Azure AD 가입 컴퓨터에 대해 Windows 10 잠금 화면에서 셀프 서비스 암호 재설정

**유형:** 변경된 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 사용자 인증

하이브리드 Azure AD에 가입된 컴퓨터에 대한 지원을 포함하도록 Windows 10 SSPR 기능을 업데이트했습니다. 이 기능은 사용자가 Windows 10 컴퓨터의 잠금 화면에서 암호를 재설정하도록 허용하는 Windows 10 RS4에서 사용할 수 있습니다. 셀프 서비스 암호 재설정에 대해 활성화되거나 등록된 사용자는 이 기능을 활용할 수 있습니다.

자세한 내용은 [로그인 화면에서 Azure AD 암호 재설정](../authentication/howto-sspr-windows.md)을 참조하세요.

---

## <a name="march-2018"></a>2018년 3월

### <a name="certificate-expire-notification"></a>인증서 만료 알림

**유형:** 수정된 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

Azure AD는 갤러리 및 비갤러리 애플리케이션에 대한 인증서가 만료되려고 할 때 알림을 전송합니다.

일부 사용자에게 SAML 기반 Single Sign On에 대해 구성된 엔터프라이즈 애플리케이션에 대한 알림이 수신되지 않았습니다. 이 문제가 해결되었습니다. Azure AD는 7, 30 및 60일 후에 만료되는 인증서에 대한 알림을 보냅니다. 감사 로그에서 이 이벤트를 볼 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Azure Active Directory에서 페더레이션된 Single Sign-On에 대한 인증서 관리](../manage-apps/manage-certificates-for-federated-single-sign-on.md)
- [Azure Active Directory 포털의 감사 활동 보고서](../reports-monitoring/concept-audit-logs.md)

---

### <a name="twitter-and-github-identity-providers-in-azure-ad-b2c"></a>Azure AD B2C의 Twitter 및 GitHub ID 공급자

**유형:** 새 기능 **서비스 범주:** B2C - 소비자 ID 관리 **제품 기능:** B2B/B2C

이제 Azure AD B2C에서 ID 공급자로 Twitter 또는 GitHub를 추가할 수 있습니다. Twitter는 공개 미리 보기에서 GA로 전환되고 있습니다. GitHub는 공개 미리 보기로 릴리스되고 있습니다.

자세한 내용은 [Azure AD B2B 협업이란?](../external-identities/what-is-b2b.md)을 참조하세요.

---

### <a name="restrict-browser-access-using-intune-managed-browser-with-azure-ad-application-based-conditional-access-for-ios-and-android"></a>iOS 및 Android용 Azure AD 애플리케이션 기반 조건부 액세스와 함께 Intune Managed Browser를 사용하여 브라우저 액세스를 제한합니다.

**유형:** 새 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

**현재 공개 미리 보기 상태입니다.**

**Intune Managed Browser SSO:** 직원은 모든 Azure AD 연결 앱에 대한 기본 클라이언트(예: Microsoft Outlook)와 Intune Managed Browser에서 Single Sign-On을 사용할 수 있습니다.

**Intune Managed Browser 조건부 액세스 지원:** 이제 직원이 애플리케이션 기반 조건부 액세스 정책을 사용하여 Intune Managed Browser를 사용하도록 할 수 있습니다.

[블로그 게시물](https://cloudblogs.microsoft.com/enterprisemobility/2018/03/15/the-intune-managed-browser-now-supports-azure-ad-sso-and-conditional-access/)에서 이에 대해 자세히 읽어보세요.

자세한 내용은 다음을 참조하세요.

- [애플리케이션 기반 조건부 액세스 설정](../conditional-access/app-based-conditional-access.md)

- [Managed Browser 정책 구성](/mem/intune/apps/manage-microsoft-edge)

---

### <a name="app-proxy-cmdlets-in-powershell-ga-module"></a>PowerShell GA 모듈의 앱 프록시 Cmdlet

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** Access Control

이제 PowerShell GA 모듈에 애플리케이션 프록시 cmdlet에 대한 지원이 포함됩니다. 따라서 PowerShell 모듈을 최신 상태로 유지해야 합니다. 버전이 1년보다 오래되면 일부 cmdlet이 작동하지 않을 수 있습니다.

자세한 내용은 [AzureAD](/powershell/module/Azuread/)를 참조하세요.

---

### <a name="office-365-native-clients-are-supported-by-seamless-sso-using-a-non-interactive-protocol"></a>Office 365 네이티브 클라이언트는 비대화형 프로토콜을 사용하여 Seamless SSO에서 지원됨

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

Office 365 네이티브 클라이언트(버전 16.0.8730.xxxx 이상)를 사용하는 사용자는 Seamless SSO를 통해 자동 로그온 환경을 사용할 수 있게 됩니다. 이러한 지원은 비대화형 프로토콜(WS-Trust)을 Azure AD에 추가하여 제공됩니다.

자세한 내용은 [네이티브 클라이언트에서 Seamless SSO로 로그인하는 방식](../hybrid/how-to-connect-sso-how-it-works.md#how-does-sign-in-on-a-native-client-with-seamless-sso-work)을 참조하세요.

---

### <a name="users-get-a-silent-sign-on-experience-with-seamless-sso-if-an-application-sends-sign-in-requests-to-azure-ads-tenant-endpoints"></a>애플리케이션이 Azure AD의 테넌트 엔드포인트로 로그인 요청을 전송할 경우 Seamless SSO를 사용하여 자동 로그온 환경을 사용할 수 있음

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

애플리케이션(예: `https://contoso.sharepoint.com`)이 Azure AD의 공통 엔드포인트(`https://login.microsoftonline.com/common/<...>`) 대신 Azure AD의 테넌트 엔드포인트(즉, `https://login.microsoftonline.com/contoso.com/<..>` 또는 `https://login.microsoftonline.com/<tenant_ID>/<..>`)로 로그인 요청을 전송할 경우 사용자는 Seamless SSO를 사용하여 자동 로그온 환경을 사용할 수 있습니다.

자세한 내용은 [Azure Active Directory Seamless Single Sign-On](../hybrid/how-to-connect-sso.md)을 참조하세요.

---

### <a name="need-to-add-only-one-azure-ad-url-instead-of-two-urls-previously-to-users-intranet-zone-settings-to-roll-out-seamless-sso"></a>Seamless SSO를 롤아웃하기 위해 사용자의 인트라넷 영역 설정에 이전의 두 URL 대신 하나의 Azure AD URL만 추가해야 함

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

사용자에게 Seamless SSO를 롤아웃하려면 Active Directory의 그룹 정책을 사용하여 사용자의 인트라넷 영역 설정에 하나의 Azure AD URL만 추가해야합 니다. `https://autologon.microsoftazuread-sso.com` 이전에는 고객이 두 개의 URL을 추가해야 했습니다.

자세한 내용은 [Azure Active Directory Seamless Single Sign-On](../hybrid/how-to-connect-sso.md)을 참조하세요.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 3월에 페더레이션이 지원되는 신규 앱 15개가 앱 갤러리에 추가되었습니다.

[Boxcryptor](../saas-apps/boxcryptor-tutorial.md), [CylancePROTECT](../saas-apps/cylanceprotect-tutorial.md), Wrike, [SignalFx](../saas-apps/signalfx-tutorial.md), Assistant by FirstAgenda, [YardiOne](../saas-apps/yardione-tutorial.md), Vtiger CRM, inwink, [Amplitude](../saas-apps/amplitude-tutorial.md), [Spacio](../saas-apps/spacio-tutorial.md), [ContractWorks](../saas-apps/contractworks-tutorial.md), [Bersin](../saas-apps/bersin-tutorial.md), [Mercell](../saas-apps/mercell-tutorial.md), [Trisotech Digital Enterprise Server](../saas-apps/trisotechdigitalenterpriseserver-tutorial.md), [Qumu Cloud](../saas-apps/qumucloud-tutorial.md).

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="pim-for-azure-resources-is-generally-available"></a>Azure 리소스에 대한 PIM은 일반 공급됩니다.

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

디렉터리 역할에 대한 Azure AD Privileged Identity Management를 사용하는 경우, 이제 구독, 리소스 그룹, VIrtual Machines 등과 같은 Azure 리소스 역할 및 Azure Resource Manager에서 지원하는 기타 리소스에 대해 PIM의 시간 제한 액세스 및 할당 기능을 사용할 수 있습니다. Just-In-Time에 역할을 활성화할 경우 Multi-Factor Authentication을 적용하고 승인된 변경 기간에 맞춰 활성화를 예약합니다. 또한 이 릴리스에서는 업데이트 UI, 승인 워크플로 및 곧 만료되는 역할을 확장하고 만료된 역할을 갱신하는 기능을 비롯하여 공개 미리 보기 기간 동안 사용할 수 없는 개선 기능을 추가적으로 제공합니다.

자세한 내용은 [Azure 리소스에 대한 PIM(미리 보기)](../privileged-identity-management/azure-pim-resource-rbac.md)을 참조하세요.

---

### <a name="adding-optional-claims-to-your-apps-tokens-public-preview"></a>앱 토큰에 선택적 클레임 추가(공개 미리 보기)

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

이제 Azure AD 앱은 JWT 또는 SAML 토큰에서 사용자 지정 또는 선택적 클레임을 요청할 수 있습니다.  이러한 클레임은 크기 또는 적용 가능한 제약으로 인해 토큰에 기본적으로 포함되지 않는 사용자 또는 테넌트에 대한 클레임입니다.  현재는 v1.0 및 v2.0 엔드포인트에서 Azure AD 앱에 대한 공개 미리 보기로 사용됩니다.  추가될 수 있는 클레임과 해당 클레임을 요청하도록 애플리케이션 매니페스트를 편집하는 방법에 대한 내용은 해당 설명서를 참조하세요.

자세한 내용은 [Azure AD의 선택적 클레임](../develop/active-directory-optional-claims.md)을 참조하세요.

---

### <a name="azure-ad-supports-pkce-for-more-secure-oauth-flows"></a>Azure AD에서 보다 안전한 OAuth 흐름을 위해 PKCE를 지원함

**유형:** 새 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

Azure AD 설명서가 OAuth 2.0 권한 부여 코드 부여 흐름 동안 좀 더 안전한 통신을 허용하는 PKCE에 대한 지원 내용을 포함하도록 업데이트되었습니다.  S256 및 일반 텍스트 code_challenges 둘 다 v1.0 및 v2.0 엔드포인트에서 지원됩니다.

자세한 내용은 [권한 부여 코드 요청](../develop/v2-oauth2-auth-code-flow.md#request-an-authorization-code)을 참조하세요.

---

### <a name="support-for-provisioning-all-user-attribute-values-available-in-the-workday-get_workers-api"></a>Workday Get_Workers API에서 사용할 수 있는 모든 사용자 특성 값을 프로비전하도록 지원

**유형:** 새 기능 **서비스 범주:** 앱 프로비저닝 **제품 기능:** 타사 통합

Workday에서 Active Directory 및 Azure AD로의 인바운드 프로비전에 대한 공개 미리 보기는 이제 Workday Get_Workers API에서 사용할 수 있는 모든 특성 값을 추출하고 프로비전하는 기능을 지원합니다. 이를 통해 Workday 인바운드 프로비전 커넥터의 초기 버전에 제공된 특성 외에, 수백 개의 추가 표준 및 사용자 지정 특성이 추가적으로 지원됩니다.

자세한 내용은 다음을 참조하세요. [Workday 사용자 특성 목록 사용자 지정](../saas-apps/workday-inbound-tutorial.md#customizing-the-list-of-workday-user-attributes)

---

### <a name="changing-group-membership-from-dynamic-to-static-and-vice-versa"></a>그룹 멤버 자격을 동적에서 정적으로 또는 그 반대로 변경

**유형:** 새 기능 **서비스 범주:** 그룹 관리 **제품 기능:** 협업

그룹에서 멤버 자격을 관리하는 방식을 변경할 수 있습니다. 이것은 시스템에 동일한 그룹 이름과 ID를 유지하려는 경우에 유용하므로 그룹에 대한 기존 참조는 여전히 유효합니다. 새 그룹을 만들면 해당 참조를 업데이트해야 합니다.
이 기능을 지원하도록 Azure AD 관리 센터가 업데이트되었습니다. 이제, 고객은 기존 그룹을 동적 멤버 자격에서 할당된 멤버 자격으로 또는 그 반대로 변환할 수 있습니다. 기존 PowerShell cmdlet도 계속 사용할 수 있습니다.

자세한 내용은 [Azure Active Directory의 그룹에 대한 동적 멤버 자격 규칙](../enterprise-users/groups-dynamic-membership.md)을 참조하세요.

---

### <a name="improved-sign-out-behavior-with-seamless-sso"></a>Seamless SSO로 로그아웃 동작 개선

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

이전에는 사용자가 Azure AD로 보호되는 애플리케이션에서 명시적으로 로그아웃하더라도 도메인에 가입된 디바이스에서 corpnet 내의 Azure AD 애플리케이션에 다시 액세스하려고 하면 Seamless SSO를 사용하여 자동으로 다시 로그인되었습니다. 이러한 변경으로 인해 이제 로그아웃이 지원됩니다.  따라서 사용자는 Seamless SSO를 사용하여 자동으로 로그인되는 대신, 다시 로그인하는 데 사용할 같거나 다른 Azure AD 계정을 선택할 수 있습니다.

자세한 내용은 [Azure Active Directory Seamless Single Sign-On](../hybrid/how-to-connect-sso.md)을 참조하세요.

---

### <a name="application-proxy-connector-version-154020-released"></a>애플리케이션 프록시 커넥터 버전 1.5.402.0이 릴리스됨

**유형:** 변경된 기능 **서비스 범주:** 앱 프록시 **제품 기능:** ID 보안 및 보호

이 커넥터 버전은 11월까지 점진적으로 롤아웃될 예정입니다. 이 새 커넥터 버전에는 다음과 같은 변경 내용이 포함되어 있습니다.

- 이제 커넥터는 하위 도메인 수준 대신, 도메인 수준 쿠키를 설정합니다. 이를 통해 SSO 환경이 좀 더 원활하게 진행되고 불필요한 인증 프롬프트가 방지됩니다.
- 청크 인코딩 요청 지원
- 향상된 커넥터 상태 모니터링
- 몇 가지 버그 수정 및 안정성 개선

자세한 내용은 [Azure AD 애플리케이션 프록시 커넥터 이해](../manage-apps/application-proxy-connectors.md)를 참조하세요.

---

## <a name="february-2018"></a>2018년 2월

### <a name="improved-navigation-for-managing-users-and-groups"></a>사용자 및 그룹 관리를 위한 향상된 탐색

**유형:** 변경 계획 **서비스 범주:** 디렉터리 관리 **제품 기능:** 디렉터리

사용자 및 그룹 관리를 위한 탐색 환경이 간소화되었습니다. 이제 디렉터리 개요에서 직접 모든 사용자 목록으로 이동하여 삭제된 사용자 목록에 더 쉽게 액세스할 수 있습니다. 디렉터리 개요에서 모든 그룹 목록으로 직접 이동하여 그룹 관리 설정에 쉽게 액세스할 수 있습니다. 또한 디렉터리 개요 페이지에서 사용자, 그룹, 엔터프라이즈 애플리케이션 또는 앱 등록을 검색할 수 있습니다.

---

### <a name="availability-of-sign-ins-and-audit-reports-in-microsoft-azure-operated-by-21vianet-azure-china-21vianet"></a>21Vianet(Azure China 21Vianet)에서 운영하는 Microsoft Azure의 로그인 및 감사 보고서에 대한 가용성

**유형:** 새 기능 **서비스 범주:** Azure Stack **제품 기능:** 모니터링 및 보고

Azure AD 활동 로그 보고서는 이제 21Vianet(Azure China 21Vianet) 인스턴스로 운영되는 Microsoft Azure에서 사용할 수 있습니다. 포함되는 로그는 다음과 같습니다.

- **로그인 활동 로그** - 테넌트와 관련된 모든 로그인 로그를 포함합니다.

- **셀프 서비스 암호 감사 로그** - 모든 SSPR 감사 로그를 포함합니다.

- **디렉터리 관리 감사 로그** - 사용자 관리, 앱 관리 등과 같은 디렉터리 관리와 관련된 모든 감사 로그를 포함합니다.

이러한 로그를 사용하면 환경이 작동하는 방식에 대한 인사이트를 얻을 수 있습니다. 제공된 데이터를 통해 다음을 수행할 수 있습니다.

- 사용자가 앱 및 서비스를 어떻게 활용하는지 정확히 파악할 수 있습니다.

- 사용자의 작업 진행에 장애가 되는 문제를 해결합니다.

이러한 보고서를 사용하는 방법에 대한 자세한 내용은 [Azure Active Directory 보고](../reports-monitoring/overview-reports.md)를 참조하세요.

---

### <a name="use-report-reader-role-non-admin-role-to-view-azure-ad-activity-reports"></a>"보고서 구독자" 역할(관리자가 아닌 역할)을 사용하여 Azure AD 활동 보고서 보기

**유형:** 새 기능 **서비스 범주:** 보고 **제품 기능:** 모니터링 및 보고

관리자가 아닌 역할을 통해 Azure AD 활동 로그에 액세스할 수 있도록 하는 고객 의견의 일환으로, "보고서 구독자" 역할에 속한 사용자가 Azure Portal 내에서 로그인 및 감사 활동에 액세스하고 Microsoft Graph API를 사용할 수 있게 되었습니다.

이러한 보고서를 사용하는 방법에 대한 자세한 내용은 [Azure Active Directory 보고](../reports-monitoring/overview-reports.md)를 참조하세요.

---

### <a name="employeeid-claim-available-as-user-attribute-and-user-identifier"></a>EmployeeID 클레임을 사용자 특성 및 사용자 식별자로 사용할 수 있음

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** SSO

엔터프라이즈 애플리케이션 UI의 SAML 기반 로그온 애플리케이션에서 **EmployeeID** 를 멤버 사용자 및 B2B 게스트에 대한 사용자 식별자 및 사용자 특성으로 구성할 수 있습니다.

자세한 내용은 [Azure Active Directory의 엔터프라이즈 애플리케이션에 대한 SAML 토큰에서 발급된 클레임 사용자 지정](../develop/active-directory-saml-claims-customization.md)을 참조하세요.

---

### <a name="simplified-application-management-using-wildcards-in-azure-ad-application-proxy"></a>Azure AD 애플리케이션 프록시에서 와일드카드를 사용하여 간소화된 애플리케이션 관리

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** 사용자 인증

애플리케이션을 더 쉽게 배포하고 관리 오버헤드를 줄이기 위해 이제 와일드카드를 사용하여 애플리케이션을 게시하는 기능을 지원합니다. 와일드카드 애플리케이션을 게시하려면 표준 애플리케이션 게시 흐름을 따르지만 내부 및 외부 URL에 와일드카드를 사용할 수 있습니다.

자세한 내용은 [Azure Active Directory 애플리케이션 프록시의 와일드카드 애플리케이션](../manage-apps/application-proxy-wildcard.md)을 참조하세요.

---

### <a name="new-cmdlets-to-support-configuration-of-application-proxy"></a>애플리케이션 프록시 구성을 지원하는 새로운 cmdlet

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** 플랫폼

AzureAD PowerShell 미리 보기 모듈의 최신 릴리스에는 고객이 PowerShell을 사용하여 애플리케이션 프록시 애플리케이션을 구성할 수 있는 새로운 cmdlet이 포함되어 있습니다.

새로운 cmdlet은 다음과 같습니다.

- Get-AzureADApplicationProxyApplication
- Get-AzureADApplicationProxyApplicationConnectorGroup
- Get-AzureADApplicationProxyConnector
- Get-AzureADApplicationProxyConnectorGroup
- Get-AzureADApplicationProxyConnectorGroupMembers
- Get-AzureADApplicationProxyConnectorMemberOf
- New-AzureADApplicationProxyApplication
- New-AzureADApplicationProxyConnectorGroup
- Remove-AzureADApplicationProxyApplication
- Remove-AzureADApplicationProxyApplicationConnectorGroup
- Remove-AzureADApplicationProxyConnectorGroup
- Set-AzureADApplicationProxyApplication
- Set-AzureADApplicationProxyApplicationConnectorGroup
- Set-AzureADApplicationProxyApplicationCustomDomainCertificate
- Set-AzureADApplicationProxyApplicationSingleSignOn
- Set-AzureADApplicationProxyConnector
- Set-AzureADApplicationProxyConnectorGroup

---

### <a name="new-cmdlets-to-support-configuration-of-groups"></a>그룹 구성을 지원하는 새로운 cmdlet

**유형:** 새 기능 **서비스 범주:** 앱 프록시 **제품 기능:** 플랫폼

AzureAD PowerShell 모듈의 최신 릴리스에는 Azure AD에서 그룹을 관리하는 cmdlet이 포함되어 있습니다. 이러한 cmdlet은 이전에 AzureADPreview 모듈에서 사용할 수 있었지만, 이제는 AzureAD 모듈에 추가되었습니다

현재 일반 공급으로 릴리스된 Group cmdlet은 다음과 같습니다.

- Get-AzureADMSGroup
- New-AzureADMSGroup
- Remove-AzureADMSGroup
- Set-AzureADMSGroup
- Get-AzureADMSGroupLifecyclePolicy
- New-AzureADMSGroupLifecyclePolicy
- Remove-AzureADMSGroupLifecyclePolicy
- Add-AzureADMSLifecyclePolicyGroup
- Remove-AzureADMSLifecyclePolicyGroup
- Reset-AzureADMSLifeCycleGroup
- Get-AzureADMSLifecyclePolicyGroup

---

### <a name="a-new-release-of-azure-ad-connect-is-available"></a>Azure AD Connect의 새 릴리스를 사용할 수 있음

**유형:** 새 기능 **서비스 범주:** AD Sync **제품 기능:** 플랫폼

Azure AD Connect는 Windows Server Active Directory 및 LDAP를 포함하여 Azure AD와 온-프레미스 데이터 원본 간에 데이터를 동기화하는 기본 설정 도구입니다.

>[!Important]
>이 빌드는 스키마 및 동기화 규칙 변경 내용을 도입했습니다. Azure AD Connect 동기화 서비스는 업그레이드 후에 전체 가져오기 및 전체 동기화 단계를 트리거합니다. 이 동작을 변경하는 방법에 대한 자세한 내용은 [업그레이드 후 전체 동기화를 연기하는 방법](../hybrid/how-to-upgrade-previous-version.md#how-to-defer-full-synchronization-after-upgrade)을 참조하세요.

이 릴리스에 포함된 업데이트 및 변경 내용은 다음과 같습니다.

**수정된 문제**

- 다음 페이지로 전환할 때 파티션 필터링 페이지에 대한 백그라운드 작업에서 타이밍 창 수정

- ConfigDB 사용자 지정 작업을 수행하는 동안 액세스 위반이 발생하는 버그가 수정되었습니다.

- SQL 연결 시간 제한에서 복구할 버그가 수정되었습니다.

- SAN 와일드카드가 포함된 인증서에서 필수 구성 요소 검사에 실패하는 버그가 수정되었습니다.

- Azure AD 커넥터를 내보내는 동안 miiserver.exe 충돌을 일으키는 버그를 수정 했습니다.

- 실행 시 DC에 잘못 된 암호 시도가 발생 하 여 Azure AD connect 마법사에서 구성을 변경 하는 버그가 수정 되었습니다.

**새 기능 및 향상된 기능**

- 애플리케이션 원격 분석 - 관리자가 이 데이터 클래스를 설정/해제할 수 있습니다.

- Azure AD 상태 데이터 - 관리자가 상태 포털을 방문하여 상태 설정을 제어해야 합니다. 서비스 정책이 변경되고 나면 에이전트에서 읽고 적용합니다.

- 디바이스 쓰기 저장 구성 작업 및 페이지 초기화에 대한 진행률 표시줄이 추가되었습니다.

- ZIP 텍스트/HTML 보고서에서 HTML 보고서 및 전체 데이터 수집을 통해 일반 진단 기능이 향상되었습니다.

- 자동 업그레이드의 안정성이 향상되고, 서버의 상태를 확인할 수 있도록 추가 원격 분석이 추가되었습니다.

- AD 커넥터 계정에서 권한 있는 계정에 사용할 수 있는 권한이 제한되었습니다. 새로 설치하는 경우 마법사는 MSOL 계정을 만든 후 권한 있는 계정이 MSOL 계정에 대해 갖는 권한을 제한합니다. 이 변경 내용은 자동 생성 계정을 통한 빠른 설치 및 사용자 지정 설치에 영향을 줍니다.

- AAD Connect를 새로 설치할 때 SA 권한이 필요하지 않도록 설치 관리자가 변경되었습니다.

- 특정 개체에 대한 동기화 문제를 해결하는 새로운 유틸리티가 추가되었습니다. 현재 유틸리티는 다음 사항을 확인합니다.

    - 동기화된 사용자 개체와 Azure AD 테넌트의 사용자 계정 간의 UserPrincipalName이 일치하지 않습니다.

    - 도메인 필터링으로 인해 개체가 동기화에서 필터링된 경우

    - OU(조직 구성 단위) 필터링으로 인해 개체가 동기화에서 필터링된 경우

- 특정 사용자 계정에 대해 온-프레미스 Active Directory에 저장된 현재 암호 해시를 동기화하는 새로운 유틸리티가 추가되었습니다. 유틸리티는 암호 변경이 필요하지 않습니다.

---

### <a name="applications-supporting-intune-app-protection-policies-added-for-use-with-azure-ad-application-based-conditional-access"></a>Azure AD 애플리케이션 기반 조건부 액세스에서 사용하기 위해 추가된 Intune 앱 보호 정책을 지원하는 애플리케이션

**유형:** 변경된 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

애플리케이션 기반 조건부 액세스를 지원하는 애플리케이션을 더 많이 추가했습니다. 이제 승인된 이러한 클라이언트 응용 프로그램을 사용하여 Office 365 및 기타 Azure AD 연결 클라우드 응용 프로그램에 액세스할 수 있습니다.

2월 말까지 추가될 애플리케이션은 다음과 같습니다.

- Microsoft Power BI

- Microsoft Launcher

- Microsoft Invoicing

자세한 내용은 다음을 참조하세요.

- [승인된 클라이언트 앱 요구 사항](../conditional-access/concept-conditional-access-conditions.md#client-apps)
- [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)

---

### <a name="terms-of-use-update-to-mobile-experience"></a>모바일 환경의 사용 약관 업데이트

**유형:** 변경된 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

사용 약관이 표시되면 **보는 데 문제가 있나요? 여기를 클릭하세요.** 를 클릭할 수 있습니다. 이 링크를 클릭하면 디바이스에서 기본적으로 사용 약관이 열립니다. 문서의 글꼴 크기 또는 디바이스의 화면 크기에 관계없이 필요에 따라 문서를 확대/축소하고 읽을 수 있습니다.

---

## <a name="january-2018"></a>2018년 1월

### <a name="new-federated-apps-available-in-azure-ad-app-gallery"></a>Azure AD 앱 갤러리에서 사용할 수 있는 새로 페더레이션된 앱

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2018년 1월에 페더레이션이 지원되는 다음과 같은 신규 앱이 앱 갤러리에 추가되었습니다.

[IBM OpenPages](../saas-apps/ibmopenpages-tutorial.md), [OneTrust Privacy Management Software](../saas-apps/onetrust-tutorial.md), [Dealpath](../saas-apps/dealpath-tutorial.md), [IriusRisk Federated Directory 및 [Fidelity NetBenefits](../saas-apps/fidelitynetbenefits-tutorial.md).

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="sign-in-with-additional-risk-detected"></a>추가 위험이 있는 로그인이 감지됨

**유형:** 새 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

감지된 위험 이벤트에 대해 얻은 인사이트는 Azure AD 구독에 연결됩니다. Azure AD Premium P2 버전에서 모든 기본 감지에 대한 가장 자세한 정보를 가져옵니다.

Azure AD Premium P1 버전에서는 라이선스 범위에 포함되지 않는 검색 항목은 추가 위험이 감지된 위험 검색 로그인으로 표시됩니다.

자세한 내용은 [Azure Active Directory 위험 탐지](../identity-protection/overview-identity-protection.md)를 참조하세요.

---

### <a name="hide-office-365-applications-from-end-users-access-panels"></a>최종 사용자의 액세스 패널에서 Office 365 애플리케이션 숨기기

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** SSO

새로운 사용자 설정을 통해 Office 365 애플리케이션을 사용자의 액세스 패널에 표시하는 방법을 보다 효과적으로 관리할 수 있습니다. Office 포털에 Office 앱만 표시하려는 경우, 이 옵션은 사용자의 액세스 패널에 있는 앱의 수를 줄이는 데 유용합니다. 이 설정은 **사용자 설정** 아래에 있으며 **사용자가 Office 365 포털에서 Office 365 앱만 볼 수 있음** 이라는 레이블이 지정되어 있습니다.

자세한 내용은 [Azure Active Directory의 사용자 환경에서 애플리케이션 숨기기](../manage-apps/hide-application-from-user-portal.md)를 참조하세요.

---

### <a name="seamless-sign-into-apps-enabled-for-password-sso-directly-from-apps-url"></a>앱의 URL을 통해 암호 SSO가 가능한 앱에 간편하게 로그인

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** SSO

내 앱 SSO(Single-Sign On) 기능을 브라우저의 바로 가기로 제공하는 간편한 도구를 통해 내 앱 브라우저 확장을 사용할 수 있습니다. 앱을 설치하면 앱에 빠른 액세스를 제공하는 와플 아이콘이 브라우저에 표시됩니다. 사용자는 이제 다음과 같은 이점을 활용할 수 있습니다.

- 앱의 로그인 페이지에서 암호-SSO 기반 앱에 직접 로그인할 수 있는 기능
- 빠른 검색 기능을 사용하여 원하는 앱 실행
- 확장 프로그램의 최근 사용한 앱에 대한 바로 가기
- Microsoft Edge, Chrome 및 Firefox에 대한 확장을 사용할 수 있습니다.

자세한 내용은 [내 앱 보안 로그인 확장](../user-help/my-apps-portal-end-user-access.md#download-and-install-the-my-apps-secure-sign-in-extension)을 참조하세요.

---

### <a name="azure-ad-administration-experience-in-azure-classic-portal-has-been-retired"></a>Azure 클래식 포털에서 Azure AD 관리 환경 사용 중지

**유형:** 사용되지 않는 **서비스 범주:** Azure AD **제품 기능:** 디렉터리

2018년 1월 8일부터 Azure 클래식 포털의 Azure AD 관리 환경 사용이 중지됩니다. Azure 클래식 포털의 사용 중지와 함께 적용됩니다. 앞으로 Azure AD의 포털 기반 관리를 위해서는 [Azure AD 관리 센터](https://aad.portal.azure.com)를 사용해야 합니다.

---

### <a name="the-phonefactor-web-portal-has-been-retired"></a>PhoneFactor 웹 포털의 사용이 중지됩니다.

**유형:** 사용되지 않는 **서비스 범주:** Azure AD **제품 기능:** 디렉터리

2018년 1월 8일부터 PhoneFactor 웹 포털의 사용이 중지됩니다. 이 포털은 MFA 서버 관리에 사용되었으며, 해당 기능은 Azure Portal(portal.azure.com)로 이동되었습니다.

MFA 구성 위치: **Azure Active Directory \> MFA 서버**

---

### <a name="deprecate-azure-ad-reports"></a>Azure AD 보고서 사용 중지

**유형:** 사용되지 않는 **서비스 범주:** 보고 **제품 기능:** ID 수명 주기 관리


새로운 Azure Active Directory 관리 콘솔이 일반 공급되고 활동 및 보안 보고서를 위해 새로운 API가 제공됨에 따라서, 2017년 12월 31일부로 "/reports" 엔드포인트에 있는 보고서 API 사용이 중지되었습니다.

**사용할 수 있는 기능은 무엇인가요?**

새 관리 콘솔로 전환하면서 Azure AD 활동 로그를 검색할 수 있는 2개의 새로운 API를 만들었습니다. 새로 적용된 API는 다양한 감사 및 로그인 활동에 더해 다양한 필터링 및 정렬 기능을 제공합니다. 이전에 보안 보고서를 통해 사용 가능했던 데이터를 이제 Microsoft Graph의 Identity Protection 위험 검색 API를 통해 액세스할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Azure Active Directory 보고 API를 시작](../reports-monitoring/concept-reporting-api.md)

- [Azure Active Directory ID 보호 및 Microsoft Graph 시작](../identity-protection/howto-identity-protection-graph-api.md)

---

## <a name="december-2017"></a>2017년 12월

### <a name="terms-of-use-in-the-access-panel"></a>액세스 패널의 사용 약관

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

이제 액세스 패널로 이동하면 이전에 수락한 사용 약관을 볼 수 있습니다.

다음 단계를 수행하세요.

1. [MyApps 포털](https://myapps.microsoft.com)로 이동하고 로그인합니다.

2. 오른쪽 위 모서리에서 자신의 이름을 선택한 다음 목록에서 **프로필** 을 선택합니다.

3. **프로필** 에서 **사용 약관 검토** 를 클릭합니다.

4. 이제 내가 동의한 사용 약관을 검토할 수 있습니다.

자세한 내용은 [Azure AD 사용 약관 기능(미리 보기)](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="new-azure-ad-sign-in-experience"></a>새 Azure AD 로그인 환경

**유형:** 새 기능 **서비스 범주:** Azure AD **제품 기능:** 사용자 인증

Azure AD와 Microsoft 계정 ID 시스템의 UI 모양과 느낌이 일관된 스타일로 새롭게 디자인되었습니다. 또한 Azure AD 로그인 페이지에서는 먼저 사용자 이름을 수집하고 두 번째 화면에서 자격 증명을 수집합니다.

자세한 내용은 [The new Azure AD Signin Experience is now in Public Preview](https://cloudblogs.microsoft.com/enterprisemobility/2017/08/02/the-new-azure-ad-signin-experience-is-now-in-public-preview/)(새 Azure AD 로그인 환경을 공개 미리 보기로 제공)를 참조하세요.

---

### <a name="fewer-sign-in-prompts-a-new-keep-me-signed-in-experience-for-azure-ad-sign-in"></a>로그인 프롬프트 감소: Azure AD 로그인을 위한 새로운 "로그인 유지" 환경

**유형:** 새 기능 **서비스 범주:** Azure AD **제품 기능:** 사용자 인증

Azure AD 로그인 페이지의 **로그인 상태 유지** 확인란을 사용자가 인증된 후에 표시되는 새 프롬프트로 바꾸었습니다.

이 프롬프트에 사용자가 **예** 로 응답하면 영구 새로 고침 토큰이 제공됩니다. 이 동작은 사용자가 이전 환경에서 **로그인 유지** 확인란을 선택할 때와 동일합니다. 페더레이션 된 테넌트에게는 페더레이션된 서비스로 인증이 성공한 후에 이 프롬프트가 표시됩니다.

자세한 내용은 [로그인 프롬프트 감소: Azure AD 로그인을 위한 새로운 "로그인 유지" 환경이 미리 보기로 제공됨](https://cloudblogs.microsoft.com/enterprisemobility/2017/09/19/fewer-login-prompts-the-new-keep-me-signed-in-experience-for-azure-ad-is-in-preview/)을 참조하세요.

---

### <a name="add-configuration-to-require-the-terms-of-use-to-be-expanded-prior-to-accepting"></a>동의하기 전에 사용 약관을 펼치도록 하는 구성 추가

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

사용 약관을 수락하기 전에 사용 약관을 펼치도록 사용자에게 요구하는 옵션이 관리자에게 필요합니다.

사용자에게 사용 약관을 펼치도록 요구하려면 **On** 또는 **Off** 중 하나를 선택합니다. **On** 설정은 사용 약관을 수락하기 전에 확인하도록 사용자에게 요구합니다.

자세한 내용은 [Azure AD 사용 약관 기능(미리 보기)](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="scoped-activation-for-eligible-role-assignments"></a>적격 역할 할당에 대한 범위 지정 활성화

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

범위가 지정된 활성화를 사용하면 원래 할당 기본값보다 낮은 자율성을 적용하여 적절한 Azure 리소스 역할 할당을 활성화할 수 있습니다. 예를 들어, 테넌트의 구독 소유자로 할당되는 경우가 있습니다. 범위가 지정된 활성화를 사용하면 구독 내에 포함된 리소스 최대 5개에 대해 소유자 역할을 활성화할 수 있습니다(예: 리소스 그룹, 가상 머신). 활성화의 범위를 지정하면 중요한 Azure 리소스가 원치 않게 변경될 가능성을 줄일 수 있습니다.

자세한 내용은 [Azure AD Privileged Identity Management란?](../privileged-identity-management/pim-configure.md)을 참조하세요.

---

### <a name="new-federated-apps-in-the-azure-ad-app-gallery"></a>Azure AD 앱 갤러리의 새로운 페더레이션된 앱

**유형:** 새 기능 **서비스 범주:** 엔터프라이즈 앱 **제품 기능:** 타사 통합

2017년 12월에 페더레이션이 지원되는 다음과 같은 신규 앱이 앱 갤러리에 추가되었습니다.

[Accredible](../saas-apps/accredible-tutorial.md), Adobe Experience Manager, [EFI Digital StoreFront](../saas-apps/efidigitalstorefront-tutorial.md), [Communifire](../saas-apps/communifire-tutorial.md) CybSafe, [FactSet](../saas-apps/factset-tutorial.md), [IMAGE WORKS](../saas-apps/imageworks-tutorial.md), [MOBI](../saas-apps/mobi-tutorial.md), [MobileIron Azure AD integration](../saas-apps/mobileiron-tutorial.md), [Reflektive](../saas-apps/reflektive-tutorial.md), [SAML SSO for Bamboo by resolution GmbH](../saas-apps/bamboo-tutorial.md), [SAML SSO for Bitbucket by resolution GmbH](../saas-apps/bitbucket-tutorial.md), [Vodeclic](../saas-apps/vodeclic-tutorial.md), WebHR, Zenegy Azure AD Integration.

앱에 대한 자세한 내용은 [Azure Active Directory와 SaaS 애플리케이션 통합](../saas-apps/tutorial-list.md)을 참조하세요.

Azure AD 앱 갤러리에 애플리케이션을 나열하는 방법에 대한 자세한 내용은 [Azure Active Directory 애플리케이션 갤러리에 애플리케이션 나열](../develop/v2-howto-app-gallery-listing.md)을 참조하세요.

---

### <a name="approval-workflows-for-azure-ad-directory-roles"></a>Azure AD 디렉터리 역할에 대한 승인 워크플로

**유형:** 변경된 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

Azure AD 디렉터리 역할의 승인 워크플로가 일반 공급됩니다.

승인 워크플로를 통해, 권한 있는 역할 관리자는 자격을 갖춘 역할 멤버가 권한 있는 역할을 사용하려면 그 전에 역할 활성화를 요청하도록 요청할 수 있습니다. 여러 사용자와 그룹이 승인 책임을 위임 받을 수 있습니다. 승인이 완료되고 역할이 활성화되면 자격을 갖춘 역할 멤버에게 알림이 전송됩니다.

---

### <a name="pass-through-authentication-skype-for-business-support"></a>통과 인증: 비즈니스용 Skype 지원

**유형:** 변경된 기능 **서비스 범주:** 인증(로그인) **제품 기능:** 사용자 인증

통과 인증은 사용자가 온라인 및 하이브리드 토폴로지를 비롯한 최신 인증을 지원하는 비즈니스용 Skype 클라이언트 애플리케이션에 로그인하도록 지원합니다.

자세한 내용은 [Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)(최신 인증에서 비즈니스용 Skype 토폴로지 지원됨)을 참조하세요.

---

### <a name="updates-to-azure-ad-privileged-identity-management-for-azure-rbac-preview"></a>Azure RBAC에 대한 Azure AD Privileged Identity Management 업데이트(미리 보기)

**유형:** 변경된 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

Azure RBAC (역할 기반 액세스 제어)에 대 한 PIM (Azure AD Privileged Identity Management)의 공개 미리 보기 새로 고침을 사용 하 여 이제 다음을 수행할 수 있습니다.

* Just Enough Administration을 사용할 수 있습니다.
* 리소스 역할을 활성화하기 위한 승인을 요청할 수 있습니다.
* Azure AD 및 Azure 역할에 대 한 승인이 필요한 역할의 향후 활성화를 예약 합니다.

자세한 내용은 [Azure 리소스용 Privileged Identity Management(미리 보기)](../privileged-identity-management/azure-pim-resource-rbac.md)를 참조하세요.

---

## <a name="november-2017"></a>2017년 11월

### <a name="access-control-service-retirement"></a>Access Control Service사용 중지

**유형:** 변경 계획 **서비스 범주:** Access Control 서비스 **제품 기능:** Access Control Service

Azure Active Directory Access Control(또는 Access Control Service)은 2018년 말에 사용이 중지됩니다. 자세한 일정과 개괄적인 마이그레이션 지침을 비롯한 자세한 정보가 몇 주 내에 제공될 예정입니다. Access Control Service에 대한 질문이 있으면 이 페이지에 의견을 남겨주세요. 팀 멤버가 연락 드리겠습니다.

---

### <a name="restrict-browser-access-to-the-intune-managed-browser"></a>Intune Managed Browser에 대한 브라우저 액세스 제한

**유형:** 변경 계획 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

Intune Managed Browser를 승인된 앱으로 사용하면 Office 365 및 기타 Azure AD 연결 클라우드 앱에 대한 브라우저 액세스를 제한할 수 있습니다.

애플리케이션 기반 조건부 액세스에 대해 다음과 같은 조건을 구성할 수 있습니다.

**클라이언트 앱:** 브라우저

**변경되면 무엇이 달라지나요?**

현재는 이 조건을 사용하면 액세스가 차단됩니다. 미리 보기를 사용할 수 있게 되면 모든 액세스에는 관리되는 브라우저 애플리케이션을 사용해야 합니다.

앞으로 공개될 블로그와 릴리스 정보에서도 이 기능과 자세한 정보를 찾아볼 수 있습니다.

자세한 내용은 [Azure AD의 조건부 액세스](../conditional-access/overview.md)를 참조하세요.

---

### <a name="new-approved-client-apps-for-azure-ad-app-based-conditional-access"></a>Azure AD 앱 기반 조건부 액세스의 새로운 승인된 클라이언트 앱

**유형:** 변경 계획 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

[승인된 클라이언트 앱](../conditional-access/concept-conditional-access-conditions.md#client-apps) 목록에는 다음과 같은 앱이 있습니다.

- [Microsoft Kaizala](https://www.microsoft.com/garage/profiles/kaizala/)
- Microsoft StaffHub

자세한 내용은 다음을 참조하세요.

- [승인된 클라이언트 앱 요구 사항](../conditional-access/concept-conditional-access-conditions.md#client-apps)
- [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)

---

### <a name="terms-of-use-support-for-multiple-languages"></a>사용 약관을 여러 언어로 제공

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

이제 관리자가 여러 PDF 문서가 포함된 새로운 사용 약관을 작성할 수 있습니다. PDF 문서에는 문서에서 사용된 언어를 태그로 지정할 수 있습니다. 사용자 기본 설정에 따라 사용자에게 일치하는 언어로 된 PDF가 표시됩니다. 일치하는 언어가 없으면 기본 언어가 표시됩니다.

---

### <a name="real-time-password-writeback-client-status"></a>실시간 비밀번호 쓰기 저장 클라이언트 상태

**유형:** 새 기능 **서비스 범주:** 셀프 서비스 암호 재설정 **제품 기능:** 사용자 인증

이제 온-프레미스 비밀번호 쓰기 저장 클라이언트의 상태를 검토할 수 있습니다. 이 옵션은 [암호 재설정](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/PasswordReset) 페이지의 **온-프레미스 통합** 섹션에서 확인할 수 있습니다.

온-프레미스 쓰기 저장 클라이언트와의 연결에 문제가 있는 경우 다음과 같은 정보를 제공하는 오류 메시지가 표시됩니다.

- 온-프레미스 쓰기 저장 클라이언트에 연결할 수 없는 이유
- 문제 해결에 도움이 되는 설명서 링크

자세한 내용은 [온-프레미스 통합](../authentication/concept-sspr-howitworks.md#on-premises-integration)을 참조하세요.

---

### <a name="azure-ad-app-based-conditional-access"></a>Azure AD 앱 기반 조건부 액세스

**유형:** 새 기능 **서비스 범주:** Azure AD **제품 기능:** ID 보안 및 보호

이제 [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)를 사용하여 Intune 앱 보호 정책을 지원하는 [승인된 클라이언트 앱](../conditional-access/concept-conditional-access-conditions.md#client-apps)으로 Office 365 및 기타 Azure AD에 연결된 클라우드 앱의 액세스를 제한할 수 있습니다. 승인된 클라이언트 애플리케이션에서 기업 데이터를 구성하고 보호하는 데 Intune 앱 보호 정책이 사용됩니다.

[앱 기반](../conditional-access/app-based-conditional-access.md) 조건부 액세스 정책과 [디바이스 기반](../conditional-access/require-managed-devices.md) 조건부 액세스 정책이 결합됨으로써 개인 디바이스와 기업 디바이스의 데이터를 유연하게 보호할 수 있게 됩니다.

다음은 앱 기반 조건부 액세스에 사용 가능한 조건과 컨트롤입니다.

**지원되는 플랫폼 조건**

- iOS
- Android

**클라이언트 앱 조건**

- 모바일 앱 및 데스크톱 클라이언트

**액세스 제어**

- 승인된 클라이언트 앱 필요

자세한 내용은 [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)를 참조하세요.

---

### <a name="manage-azure-ad-devices-in-the-azure-portal"></a>Azure Portal에서 Azure AD 디바이스 관리

**유형:** 새 기능 **서비스 범주:** 디바이스 등록 및 관리 **제품 기능:** ID 보안 및 보호

이제 Azure AD에 연결된 디바이스와 디바이스 관련 활동을 모두 한 곳에서 확인할 수 있습니다. Microsoft는 Azure Portal에서 모든 디바이스 ID와 설정을 한 번에 관리할 수 있는 새로운 관리 환경을 선보입니다. 이 릴리스에서는 다음과 같은 기능을 수행할 수 있습니다.

- Azure AD의 조건부 액세스에 사용할 수 있는 모든 디바이스 보기
- 하이브리드 Azure AD 조인 디바이스를 비롯한 속성 보기
- Azure AD 조인 디바이스의 BitLocker 키 찾기, Intune을 사용하여 디바이스 관리하기
- Azure AD 디바이스 관련 설정을 관리합니다.

자세한 내용은 [Azure Portal을 사용하여 디바이스 관리](../devices/device-management-azure-portal.md)를 참조하세요.

---

### <a name="support-for-macos-as-a-device-platform-for-azure-ad-conditional-access"></a>Azure AD 조건부 액세스의 디바이스 플랫폼으로서 macOS 지원

**유형:** 새 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

이제 Azure AD 조건부 액세스 정책에서 디바이스 플랫폼 조건으로서 macOS를 추가 또는 제외할 수 있습니다. 지원되는 디바이스 플랫폼에 macOS가 추가되어 다음과 같은 기능이 지원됩니다.

- **Intune을 사용하여 macOS 디바이스를 등록하고 관리합니다.** iOS, Android와 같은 여타 플랫폼과 마찬가지로 macOS의 경우에도 통합 등록을 수행하는 기업 포털 애플리케이션이 제공됩니다. 새로운 macOS용 기업 포털 앱을 이용하면 Intune을 사용하여 디바이스를 등록하고 등록한 디바이스를 Azure AD에 등록할 수 있습니다.
- **macOS 디바이스가 Intune에 정의된 조직의 준수 정책을 준수하는지 확인합니다.** 이제 Azure Portal의 Intune에서 macOS 디바이스에 대한 준수 정책을 설정할 수 있습니다.
- **Azure AD에서 애플리케이션에 대한 액세스를 호환 가능한 macOS 디바이스로 제한합니다.** 조건부 액세스 정책을 작성할 때 macOS가 별도의 디바이스 플랫폼 옵션으로 제공됩니다. 이제 Azure에 설정된 대상 애플리케이션에 대해 macOS 전용 조건부 액세스 정책을 작성할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Intune을 사용하여 macOS를 위한 디바이스 준수 정책 만들기](/mem/intune/protect/compliance-policy-create-mac-os)
- [Azure AD의 조건부 액세스](../conditional-access/overview.md)

---

### <a name="network-policy-server-extension-for-azure-ad-multi-factor-authentication"></a>Azure AD Multi-Factor Authentication의 네트워크 정책 서버 확장

**유형:** 새 기능 **서비스 범주:**  다단계 인증 **제품 기능:** 사용자 인증

Azure AD Multi-Factor Authentication의 네트워크 정책 서버 확장은 기존 서버를 사용 하 여 인증 인프라에 클라우드 기반 Multi-Factor Authentication 기능을 추가 합니다. 네트워크 정책 서버 확장을 사용하면, 전화 통화, 문자 메시지 또는 휴대폰 앱 확인을 기존 인증 흐름에 추가할 수 있습니다. 새 서버를 설치, 구성 및 유지 관리할 필요가 없습니다.

이 확장은 Azure Multi-Factor Authentication 서버를 배포하지 않고 가상 사설망 연결을 보호하려는 조직을 위해 작성되었습니다. 네트워크 정책 서버 확장은 페더레이션 사용자 또는 동기화 된 사용자에 대 한 두 번째 인증 단계를 제공 하기 위해 RADIUS 및 클라우드 기반 Azure AD Multi-Factor Authentication 간의 어댑터 역할을 합니다.

자세한 내용은 [기존 네트워크 정책 서버 인프라와 AZURE AD Multi-Factor Authentication 통합](../authentication/howto-mfa-nps-extension.md)을 참조 하세요.

---

### <a name="restore-or-permanently-remove-deleted-users"></a>삭제된 사용자 복원 또는 영구 제거

**유형:** 새 기능 **서비스 범주:** 사용자 관리 **제품 기능:** 디렉터리

이제 Azure AD 관리 센터에서 다음과 같은 기능을 수행할 수 있습니다.

- 삭제된 사용자 복원
- 사용자 영구 삭제

**기능 사용해 보기:**

1. Azure AD 관리 센터의 **관리** 섹션에서 [모든 사용자](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/All)를 선택합니다.

2. **표시** 목록에서 **최근 삭제된 사용자** 를 선택합니다.

3. 최근 삭제된 사용자를 하나 이상 선택한 다음 복원하거나 영구 삭제합니다.

---

### <a name="new-approved-client-apps-for-azure-ad-app-based-conditional-access"></a>Azure AD 앱 기반 조건부 액세스의 새로운 승인된 클라이언트 앱

**유형:** 변경된 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

[승인된 클라이언트 앱](../conditional-access/concept-conditional-access-conditions.md#client-apps)에 다음과 같은 앱이 추가되어 있습니다.

- Microsoft Planner
- Azure Information Protection

자세한 내용은 다음을 참조하세요.

- [승인된 클라이언트 앱 요구 사항](../conditional-access/concept-conditional-access-conditions.md#client-apps)
- [Azure AD 앱 기반 조건부 액세스](../conditional-access/app-based-conditional-access.md)

---

### <a name="use-or-between-controls-in-a-conditional-access-policy"></a>조건부 액세스 정책에서 여러 컨트롤 사이에 "OR" 사용

**유형:** 변경된 기능 **서비스 범주:** 조건부 액세스 **제품 기능:** ID 보안 및 보호

이제 조건부 액세스 제어에 "OR"(선택한 컨트롤 중 하나 필요) 연산자를 사용할 수 있습니다. 이 기능을 사용하여 액세스 제어 사이에 "OR"이 있는 정책을 만들 수 있습니다. 사용자가 다단계 인증을 사용하거나 규정을 준수하는 디바이스를 사용하도록 요구하려는 경우 "OR" 연산자를 사용하여 정책을 만들 수 있습니다.

자세한 내용은 [Azure AD 조건부 액세스의 컨트롤](../conditional-access/controls.md)을 참조하세요.

---

### <a name="aggregation-of-real-time-risk-detections"></a>실시간 위험 검색 집계

**유형:** 변경된 기능 **서비스 범주:** Identity Protection **제품 기능:** ID 보안 및 보호

Azure Active Directory Identity Protection에서는 특정 날짜에 동일한 IP 주소에서 발생한 모든 실시간 위험 검색이 위험 이벤트 유형별로 집계됩니다. 이렇게 바뀐 내용이 사용자 보안에 영향을 주지는 않지만, 표시되는 위험 검색의 양이 제한됩니다.

사용자가 로그인할 때마다 기반 실시간 감지가 작동합니다. Multi-Factor Authentication 또는 액세스 차단이 설정된 로그인 위험 보안 정책이 있어도 위험한 로그인이 있을 때마다 계속 트리거됩니다.

---

## <a name="october-2017"></a>2017년 10월

### <a name="deprecate-azure-ad-reports"></a>Azure AD 보고서 사용 중지

**유형:** 변경 계획 **서비스 범주:** 보고 **제품 기능:** ID 수명 주기 관리

Azure Portal은 다음을 제공합니다.

- 새로운 Azure AD 관리 콘솔
- 활동 및 보안 보고서를 위한 새로운 API

새로운 기능으로 인해 /reports 엔드포인트의 보고서 API는 2017년 12월 10일에 사용 중지됩니다.

---

### <a name="automatic-sign-in-field-detection"></a>자동 로그인 필드 감지

**유형:** 수정된 **서비스 범주:** 내 앱 **제품 기능:** SSO(Single sign-on)

Azure AD는 HTML 사용자 이름 및 암호 필드를 렌더링하는 애플리케이션의 자동 로그인 필드 검색을 지원합니다. 이 단계는 [애플리케이션에 대한 로그인 필드를 자동으로 캡처하는 방법](../manage-apps/troubleshoot-password-based-sso.md#manually-capture-sign-in-fields-for-an-app)에 설명되어 있습니다. 이 기능은 [Azure Portal](https://aad.portal.azure.com)의 **엔터프라이즈 애플리케이션** 페이지에 *비갤러리* 애플리케이션을 추가하여 찾을 수 있습니다. 또한 이 새 애플리케이션의 **Single Sign-On** 모드를 **암호 기반 Single Sign-on** 으로 구성하고 웹 URL을 입력한 다음, 페이지를 저장할 수 있습니다.

서비스 문제로 인해 이 기능은 일시적으로 사용하지 않도록 설정되어 있었습니다. 이제 문제가 해결되어 자동 로그인 필드 검색을 다시 사용할 수 있습니다.

---

### <a name="new-multi-factor-authentication-features"></a>새로운 Multi-Factor Authentication 기능

**유형:** 새 기능 **서비스 범주:** 다단계 인증 **제품 기능:** ID 보안 및 보호

MFA(Multi-Factor Authentication)는 조직을 보호하기 위한 필수적인 요소입니다. 자격 증명의 적응성을 향상시키고 MFA 환경을 더욱 원활하게 만들기 위해 다음과 같은 기능이 추가되어 있습니다.

- 다단계 인증 결과는 Azure AD 로그인 보고서에 직접 통합되며, 여기에는 MFA 결과에 대한 프로그래밍 방식의 액세스가 포함됩니다.
- MFA 구성이 Azure Portal의 Azure AD 구성 환경에 보다 깊숙이 통합되었습니다.

이 공개 미리 보기에서는 핵심 Azure AD 구성 환경에 통합된 MFA 관리와 보고 기능을 경험할 수 있습니다. 이제 Azure AD 환경에서 MFA 관리 포털 기능을 관리할 수 있습니다.

자세한 내용은 [Azure Portal의 MFA보고에 대한 참조](../authentication/howto-mfa-reporting.md)를 참조하세요.

---

### <a name="terms-of-use"></a>사용 약관

**유형:** 새 기능 **서비스 범주:** 사용 약관 **제품 기능:** 규정 준수

Azure AD 이용 약관을 사용하여 법률 요구 사항 또는 규정 준수 요구 사항에 대한 관련 면책 조항과 같은 정보를 사용자에게 제공할 수 있습니다.

다음 시나리오에서 Azure AD 사용 약관을 사용할 수 있습니다.

- 조직의 모든 사용자에 대한 일반 사용 약관
- 사용자의 특성에 기반한 특정 사용 약관(예: 의사 및 간호사 또는 국내 및 해외 직원, 동적 그룹에 의한 수행)
- Salesforce와 같은 영향력이 높은 비즈니스 앱에 액세스하기 위한 특정 이용 약관

자세한 내용은 [Azure AD 사용 약관](../conditional-access/terms-of-use.md)을 참조하세요.

---

### <a name="enhancements-to-privileged-identity-management"></a>Privileged Identity Management의 기능 개선

**유형:** 새 기능 **서비스 범주:** Privileged Identity Management **제품 기능:** Privileged Identity Management

이제 Azure AD Privileged Identity Management를 사용하여 조직에서 Azure Resources(미리 보기)에 대한 액세스를 관리, 제어 및 모니터링할 수 있습니다.

- Subscriptions
- 리소스 그룹
- 가상 머신

Azure Portal에서 Azure RBAC 기능을 사용하는 모든 리소스는 Azure AD Privileged Identity Management가 제공하는 보안 및 수명 주기 관리 기능을 모두 사용할 수 있습니다.

자세한 내용은 [Azure 리소스용 Privileged Identity Management](../privileged-identity-management/azure-pim-resource-rbac.md)를 참조하세요.

---

### <a name="access-reviews"></a>액세스 검토

**유형:** 새 기능 **서비스 범주:** 액세스 검토 **제품 기능:** 규정 준수

조직은 액세스 검토(미리 보기)를 통해 그룹 멤버 자격을 효율적으로 관리하고 엔터프라이즈 애플리케이션에 액세스할 수 있습니다.

- 애플리케이션 및 그룹 멤버 자격의 액세스 권한에 대한 액세스 검토를 사용하여 게스트 사용자 액세스를 다시 인증할 수 있습니다. 검토자는 액세스 검토로 제공되는 통찰력을 기반으로 게스트에게 계속 액세스를 허용할지를 효율적으로 결정할 수 있습니다.
- 액세스 검토를 사용하여 애플리케이션 및 그룹 멤버 자격에 대한 직원 액세스를 다시 인증할 수 있습니다.

액세스 검토 컨트롤을 조직과 관련된 프로그램으로 수집하여 규정 준수 또는 위험 감지 애플리케이션에 대한 검토를 추적할 수 있습니다.

자세한 내용은 [Azure AD 액세스 검토](../governance/access-reviews-overview.md)를 참조하세요.

---

### <a name="hide-third-party-applications-from-my-apps-and-the-office-365-app-launcher"></a>내 앱 및 Office 365 앱 시작 관리자에서 타사 애플리케이션 숨기기

**유형:** 새 기능 **서비스 범주:** 내 앱 **제품 기능:** SSO(Single sign-on)

이제 새 **앱 숨기기** 속성을 통해 사용자 포털에 표시되는 앱을 더 잘 관리할 수 있습니다. 백 엔드 서비스를 위해 앱 타일이 표시되거나 타일이 중복되고 사용자의 앱 시작 관리자가 복잡하게 표시되는 경우 앱을 숨기면 도움이 됩니다. 토글은 타사 앱 섹션의 **속성** 섹션에 있으며 **사용자가 볼 수 있습니까?** 라는 레이블이 지정되어 있습니다. PowerShell을 통해 프로그래밍 방식으로 앱을 숨길 수도 있습니다.

자세한 내용은 [Hide a third-party application from user's experience in Azure AD](../manage-apps/hide-application-from-user-portal.md)(Azure AD의 사용자 환경에서 타사 애플리케이션 숨기기)를 참조하세요.


**사용할 수 있는 기능은 무엇인가요?**

 새 관리 콘솔로 전환하면서 Azure AD 활동 로그를 가져오는 2개의 API가 새롭게 제공됩니다. 새로 적용된 API는 다양한 감사 및 로그인 활동에 더해 다양한 필터링 및 정렬 기능을 제공합니다. 이전에 보안 보고서를 통해 사용 가능했던 데이터를 이제 Microsoft Graph의 Identity Protection 위험 검색 API를 통해 액세스할 수 있습니다.


## <a name="september-2017"></a>2017년 9월

### <a name="hotfix-for-identity-manager"></a>Identity Manager용 핫픽스

**유형:** 변경된 기능 **서비스 범주:** ID 관리자 **제품 기능:** ID 수명 주기 관리

핫픽스 롤업 패키지(빌드 4.4.1642.0)는 2017년 9월 25일부터 Identity Manager 2016 서비스 팩 1용으로 사용할 수 있습니다. 이 롤업 패키지는 다음과 같습니다.

- 문제를 해결하고 개선 사항을 추가합니다.
- Identity Manager 2016용 빌드 4.4.1459.0까지 모든 Identity Manager 2016 서비스 팩 1 업데이트를 대체하는 누적 업데이트입니다.
- Identity Manager 2016 빌드 4.4.1302.0이 필요합니다.

자세한 내용은 [Identity Manager 2016 서비스 팩 1용 핫픽스 롤업 패키지(빌드 4.4.1642.0) 사용 가능](https://support.microsoft.com/help/4021562)을 참조하세요.

---
