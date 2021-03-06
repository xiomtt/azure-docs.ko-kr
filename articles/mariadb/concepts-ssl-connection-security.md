---
title: SSL/TLS 연결-Azure Database for MariaDB
description: SSL 연결을 올바르게 사용하도록 Azure Database for MariaDB 및 연결된 애플리케이션을 구성하는 방법에 대한 정보
author: savjani
ms.author: pariks
ms.service: mariadb
ms.topic: conceptual
ms.date: 07/09/2020
ms.openlocfilehash: d2d916f3cba27f6b38a781b81e403ee9b6f0fab3
ms.sourcegitcommit: a43a59e44c14d349d597c3d2fd2bc779989c71d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96011475"
---
# <a name="ssltls-connectivity-in-azure-database-for-mariadb"></a>Azure Database for MariaDB의 SSL/TLS 연결
Azure Database for MariaDB는 SSL(Secure Sockets Layer)을 사용하여 데이터베이스 서버를 클라이언트 애플리케이션에 연결하도록 지원합니다. 데이터베이스 서버와 클라이언트 애플리케이션 간 SSL 연결을 적용하면 서버와 애플리케이션 간 데이터 스트림을 암호화함으로써 “메시지 가로채기(man in the middle)” 공격으로부터 보호할 수 있습니다.

>[!NOTE]
> 고객의 의견에 따라 2021 (02/15/2021)까지 기존 Baltimore 루트 CA에 대 한 루트 인증서 사용 중단을 연장 했습니다.

> [!IMPORTANT] 
> SSL 루트 인증서가 2021 (02/15/2021)부터 만료 되도록 설정 되어 있습니다. [새 인증서](https://cacerts.digicert.com/DigiCertGlobalRootG2.crt.pem)를 사용 하도록 응용 프로그램을 업데이트 하십시오. 자세히 알아보려면 [계획 된 인증서 업데이트](concepts-certificate-rotation.md) 를 참조 하세요.

## <a name="default-settings"></a>기본 설정
기본적으로 데이터베이스 서비스는 MariaDB에 연결할 때 SSL 연결이 필요하도록 구성되어야 합니다.  가능하면 SSL 옵션을 해제하지 않는 것이 좋습니다.

Azure Portal 및 CLI를 통해 새로운 Azure Database for MariaDB 서버를 프로비전할 때 SSL 연결 적용이 기본적으로 활성화됩니다.

경우에 따라 응용 프로그램은 신뢰할 수 있는 CA (인증 기관) 인증서 파일에서 생성 된 로컬 인증서 파일을 안전 하 게 연결 해야 합니다. 현재 고객은 미리 정의 된 인증서 **만 사용** 하 여에 있는 Azure Database for MariaDB 서버에 연결할 수 있습니다 https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt.pem . 

마찬가지로, 다음 링크는 소 버린 클라우드의 서버에 대 한 인증서 ( [Azure Government](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt.pem), [Azure 중국](https://dl.cacerts.digicert.com/DigiCertGlobalRootCA.crt.pem)및 [azure 독일](https://www.d-trust.net/cgi-bin/D-TRUST_Root_Class_3_CA_2_2009.crt))를 가리킵니다.

다양한 프로그래밍 언어에 대한 연결 문자열이 Azure Portal에 표시됩니다. 이러한 연결 문자열에는 데이터베이스에 연결하는 데 필요한 SSL 매개 변수가 포함되어 있습니다. Azure Portal에서 VM을 선택합니다. **설정** 제목 아래에서 **연결 문자열** 을 선택합니다. SSL 매개 변수는 “ssl=true” 또는 “sslmode=require” 또는 “sslmode=required” 및 다른 변형과 같은 커넥터에 따라 달라집니다.

애플리케이션을 개발할 때 SSL 연결을 사용하거나 사용하지 않도록 설정하는 방법을 알아보려면 [SSL 구성 방법](howto-configure-ssl.md)을 참조하세요.

## <a name="tls-enforcement-in-azure-database-for-mariadb"></a>Azure Database for MariaDB에서 TLS 적용

Azure Database for MariaDB는 TLS (전송 계층 보안)를 사용 하 여 데이터베이스 서버에 연결 하는 클라이언트에 대 한 암호화를 지원 합니다. TLS는 데이터베이스 서버와 클라이언트 응용 프로그램 간에 보안 네트워크 연결을 보장 하 여 규정 준수 요구 사항을 준수할 수 있게 해 주는 업계 표준 프로토콜입니다.

### <a name="tls-settings"></a>TLS 설정

Azure Database for MariaDB은 클라이언트 연결에 TLS 버전을 적용할 수 있는 기능을 제공 합니다. TLS 버전을 적용 하려면 **최소 tls 버전** 옵션 설정을 사용 합니다. 이 옵션 설정에 허용 되는 값은 다음과 같습니다.

|  최소 TLS 설정             | 지원 되는 클라이언트 TLS 버전                |
|:---------------------------------|-------------------------------------:|
| TLSEnforcementDisabled (기본값) | TLS 필요 없음                      |
| TLS1_0                           | TLS 1.0, TLS 1.1, TLS 1.2 이상         |
| TLS1_1                           | TLS 1.1, TLS 1.2 이상              |
| TLS1_2                           | TLS 버전 1.2 이상                  |


예를 들어 최소 TLS 설정 버전 값을 TLS 1.0로 설정 하면 서버에서 TLS 1.0, 1.1 및 1.2 +를 사용 하는 클라이언트의 연결을 허용 한다는 의미입니다. 또는이를 1.2로 설정 하면 TLS 1.2 +를 사용 하는 클라이언트만 연결을 허용 하 고 TLS 1.0 및 TLS 1.1를 사용 하는 모든 연결이 거부 됩니다.

> [!Note] 
> 기본적으로 Azure Database for MariaDB는 최소 TLS 버전 (설정)을 적용 하지 않습니다 `TLSEnforcementDisabled` .
>
> 최소 TLS 버전을 적용 한 후에는 나중에 최소 버전 적용을 사용 하지 않도록 설정할 수 없습니다.

Azure Database for MariaDB에 대 한 TLS 설정을 설정 하는 방법에 대 한 자세한 내용은 [tls 설정을 구성 하는 방법](howto-tls-configurations.md)을 참조 하세요.

## <a name="cipher-support-by-azure-database-for-mariadb"></a>Azure Database for MariaDB에서 암호화 지원

SSL/TLS 통신의 일부로 암호 그룹의 유효성을 검사 하 고 암호화 짝패만 데이터베이스 서비스와 통신할 수 있습니다. 암호 그룹 유효성 검사는 [게이트웨이 계층](concepts-connectivity-architecture.md#connectivity-architecture) 에서 제어 되며 노드 자체에서 명시적으로 제어 되지 않습니다. 암호 그룹이 아래 나열 된 도구 모음 중 하 나와 일치 하지 않으면 들어오는 클라이언트 연결이 거부 됩니다.

### <a name="cipher-suite-supported"></a>지원 되는 암호 그룹

*   TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
*   TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
*   TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
*   TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256

## <a name="next-steps"></a>다음 단계
- [서버 방화벽 규칙](concepts-firewall-rules.md)에 대해 자세히 알아보기
- [SSL을 구성](howto-configure-ssl.md) 하는 방법 알아보기
- [TLS를 구성](howto-tls-configurations.md) 하는 방법 알아보기
