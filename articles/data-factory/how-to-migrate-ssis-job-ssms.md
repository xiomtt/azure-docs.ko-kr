---
title: 온-프레미스 SQL Server Integration Services (SSIS) 작업을 Azure Data Factory로 마이그레이션
description: 이 문서에서는 SQL Server Management Studio를 사용 하 여 SSIS (SQL Server Integration Services) 작업을 Azure Data Factory 파이프라인/활동/트리거로 마이그레이션하는 방법에 대해 설명 합니다.
services: data-factory
documentationcenter: ''
author: chugugrace
ms.author: chugu
ms.reviewer: ''
manager: ''
ms.service: data-factory
ms.workload: data-services
ms.topic: conceptual
ms.date: 4/7/2020
ms.openlocfilehash: 5566717387f6da375129a0e70c9ad825198d66b7
ms.sourcegitcommit: a43a59e44c14d349d597c3d2fd2bc779989c71d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96005710"
---
# <a name="migrate-sql-server-agent-jobs-to-adf-with-ssms"></a>SSMS를 사용 하 여 ADF로 SQL Server 에이전트 작업 마이그레이션

[!INCLUDE[appliesto-adf-xxx-md](includes/appliesto-adf-xxx-md.md)]

Ssis ( [온-프레미스 SQL Server Integration Services) 워크 로드를 ADF에서 ssis로 마이그레이션할](scenario-ssis-migration-overview.md)때 ssis 패키지를 마이그레이션한 후에 SQL Server Integration Services 패키지의 작업 단계 유형을 사용 하 여 SQL Server 에이전트 작업을 일괄 마이그레이션할 수 있습니다. 패키지를 AZURE DATA FACTORY (ADF) 파이프라인/작업/SQL SERVER MANAGEMENT STUDIO (SSMS) **SSIS 작업 마이그레이션 마법사** 를 통해 예약할 수 있습니다.

일반적으로 적용 가능한 작업 단계 유형을 사용 하 여 선택한 SQL 에이전트 작업에 대해 **SSIS 작업 마이그레이션 마법사** 는 다음을 수행할 수 있습니다.

- 온-프레미스 SSIS 패키지 위치를 패키지를 마이그레이션할 위치에 매핑합니다 .이 위치는 ADF의 SSIS에서 액세스할 수 있습니다.
    > [!NOTE]
    > 파일 시스템의 패키지 위치만 지원 됩니다.
- 해당 하는 작업 단계를 사용 하 여 해당 하는 작업을 아래와 같은 해당 ADF 리소스로 마이그레이션합니다.

|SQL 에이전트 작업 개체  |ADF 리소스  |참고|
|---------|---------|---------|
|SQL 에이전트 작업|pipeline     |*에 대해 \<job name> 생성* 되는 파이프라인의 이름입니다. <br> <br> 기본 제공 에이전트 작업은 적용 되지 않습니다. <li> SSIS 서버 유지 관리 작업 <li> syspolicy_purge_history <li> collection_set_ * <li> mdw_purge_data_ * <li> sysutility_ *|
|SSIS 작업 단계|SSIS 패키지 실행 작업|<li> 활동의 이름은 \<step name> 입니다. <li> 작업 단계에서 사용 되는 프록시 계정이이 작업의 Windows 인증으로 마이그레이션됩니다. <li> 작업 단계에서 정의한 *32 비트 런타임 사용* 을 제외한 *실행 옵션* 은 마이그레이션에서 무시 됩니다. <li> 작업 단계에서 정의 된 *확인* 은 마이그레이션하는 동안 무시 됩니다.|
|schedule      |일정 트리거        |*에 대해 \<schedule name> 생성* 되는 일정 트리거의 이름입니다. <br> <br> SQL 에이전트 작업 일정의 다음 옵션은 마이그레이션에서 무시 됩니다. <li> 두 번째 수준 간격입니다. <li> *SQL Server 에이전트가 시작될 때 자동으로 시작* <li> *CPU가 유휴 상태로 될 때마다 시작* <li> *평일* 및 *주말*<time zone> <br> SQL 에이전트 작업 일정이 ADF 일정 트리거로 마이그레이션된 후의 차이점은 다음과 같습니다. <li> ADF 일정 트리거 후속 실행은 실행 된 선행 작업의 실행 상태와는 독립적입니다. <li> ADF 일정 트리거 되풀이 구성은 SQL 에이전트 작업의 일별 빈도와 다릅니다.|

- 로컬 출력 폴더에 Azure Resource Manager (ARM) 템플릿을 생성 하 고 직접 또는 나중에 데이터 팩터리에 직접 배포 합니다. ADF 리소스 관리자 템플릿에 대 한 자세한 내용은 [DataFactory 리소스 유형](/azure/templates/microsoft.datafactory/allversions)을 참조 하세요.

## <a name="prerequisites"></a>필수 조건

이 문서에서 설명 하는 기능을 사용 하려면 SQL Server Management Studio 버전 18.5 이상이 필요 합니다. SSMS의 최신 버전을 다운로드하려면 [Download SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)(SSMS(SQL Server Management Studio) 다운로드)를 참조하세요.

## <a name="migrate-ssis-jobs-to-adf"></a>SSIS 작업을 ADF로 마이그레이션

1. SSMS의 개체 탐색기에서 SQL Server 에이전트를 선택 하 고 작업을 선택한 다음 마우스 오른쪽 단추를 클릭 하 고 **ADF로 SSIS 작업 마이그레이션** 을 선택 합니다.
![작업을 선택 하 고 s s 작업을 D F로 마이그레이션할 수 있는 SQL Server Management Studio 개체 탐색기를 보여 주는 스크린샷](media/how-to-migrate-ssis-job-ssms/menu.png)

1. Azure에 로그인 하 고 Azure 구독, Data Factory 및 Integration Runtime를 선택 합니다. 마이그레이션할 SSIS 작업에 SSIS 파일 시스템 패키지가 있는 경우 패키지 위치 매핑 단계에서 사용 되는 Azure Storage 선택 사항입니다.
![메뉴가](media/how-to-migrate-ssis-job-ssms/step1.png)

1. Ssis 패키지의 경로와 SSIS 작업의 구성 파일을 마이그레이션된 파이프라인이 액세스할 수 있는 대상 경로에 매핑합니다. 이 매핑 단계에서는 다음을 수행할 수 있습니다.

    1. 원본 폴더를 선택 하 고 **매핑 추가** 를 선택 합니다.
    1. 원본 폴더 경로를 업데이트 합니다. 올바른 경로는 패키지의 폴더 경로 또는 부모 폴더 경로입니다.
    1. 대상 폴더 경로를 업데이트 합니다. 기본값은 1 단계에서 선택 된 기본 저장소 계정에 대 한 상대 경로입니다.
    1. **삭제 매핑을** 통해 선택한 매핑을 삭제 합니다.
![캡처는 매핑을 추가할 수 있는 Map S I s 패키지 및 구성 경로 페이지를 표시 합니다. ](media/how-to-migrate-ssis-job-ssms/step2.png)
 ![ 원본 및 대상 폴더 경로를 업데이트할 수 있는 Map S I s 패키지 및 구성 경로 페이지가 스크린샷에 표시 됩니다.](media/how-to-migrate-ssis-job-ssms/step2-1.png)

1. 마이그레이션할 적용 가능한 작업을 선택 하 고 해당 하는 *실행 된 SSIS 패키지 작업* 의 설정을 구성 합니다.

    - 기본 *설정은* 기본적으로 선택한 모든 단계에 적용 됩니다. 각 속성에 대 한 자세한 내용은 패키지 위치가 *파일 시스템 (패키지)* 일 때 [SSIS 패키지 실행 작업](how-to-invoke-ssis-package-ssis-activity.md) 의 *설정 탭* 을 참조 하세요.
    ![해당 하는 실행 중인 SSIS 패키지 작업의 설정을 구성할 수 있는 작업 (Job)의 작업 페이지를 보여 주는 스크린샷](media/how-to-migrate-ssis-job-ssms/step3-1.png)
    - *단계 설정*, 선택한 단계에 대 한 설정 구성
        
        **기본 설정 적용**: 기본값이 선택 되어 있습니다. 선택한 단계에 대해서만 설정을 구성 하려면 선택 취소 합니다.  
        기타 속성에 대 한 자세한 내용은 패키지 위치가 *파일 시스템 (패키지)* 일 때 [SSIS 패키지 작업 실행](how-to-invoke-ssis-package-ssis-activity.md) 에 대 한 *설정 탭* 을 참조 하세요.
    ![기본 설정을 적용할 수 있는 작업 선택 페이지를 보여 주는 스크린샷](media/how-to-migrate-ssis-job-ssms/step3-2.png)

1. ARM 템플릿을 생성 하 고 배포 합니다.
    1. 마이그레이션된 ADF 파이프라인의 ARM 템플릿에 대 한 출력 경로를 선택 하거나 입력 합니다. 폴더가 없으면 자동으로 생성 됩니다.
    2. **데이터 팩터리에 ARM 템플릿 배포** 옵션을 선택 합니다.
        - 기본값은 선택 되지 않습니다. 나중에 생성 된 ARM 템플릿을 수동으로 배포할 수 있습니다.
        - 생성 된 ARM 템플릿을 데이터 팩터리에 직접 배포 하려면 선택 합니다.
    ![스크린샷에는 마이그레이션 구성 페이지가 표시 됩니다. 여기서 마이그레이션된 ADF 파이프라인의 ARM 템플릿에 대 한 출력 경로를 선택 하거나 입력 하 고 데이터 팩터리에 ARM 템플릿 배포 옵션을 선택할 수 있습니다.](media/how-to-migrate-ssis-job-ssms/step4.png)

1. 마이그레이션 후 결과를 확인 합니다.
![마이그레이션 진행 상황을 표시 하는 마이그레이션 결과 페이지가 스크린샷에 표시 됩니다.](media/how-to-migrate-ssis-job-ssms/step5.png)

## <a name="next-steps"></a>다음 단계

[파이프라인 실행 및 모니터링](how-to-invoke-ssis-package-ssis-activity.md)