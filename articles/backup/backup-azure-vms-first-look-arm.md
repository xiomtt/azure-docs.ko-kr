---
title: VM 설정에서 Azure VM 백업
description: 이 문서에서는 Azure Backup 서비스를 사용 하 여 단일 Azure VM 또는 여러 Azure vm을 백업 하는 방법에 대해 알아봅니다.
ms.topic: conceptual
ms.date: 06/13/2019
ms.openlocfilehash: 55b71d2a2901cdde984df3ebfd68a2a643b78b74
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "89667509"
---
# <a name="back-up-an-azure-vm-from-the-vm-settings"></a>VM 설정에서 Azure VM 백업

이 문서에서는 [Azure Backup](backup-overview.md) 서비스를 사용하여 Azure VM을 백업하는 방법을 설명합니다. 다음과 같은 몇 가지 방법을 사용하여 Azure VM을 백업할 수 있습니다.

- 단일 Azure VM:이 문서의 지침은 VM 설정에서 직접 Azure VM을 백업 하는 방법을 설명 합니다.
- 여러 Azure Vm: Recovery Services 자격 증명 모음을 설정 하 고 여러 Azure Vm에 대 한 백업을 구성할 수 있습니다. 이 시나리오에 대해서는 [이 문서](backup-azure-arm-vms-prepare.md)의 지침을 따르세요.

## <a name="before-you-start"></a>시작하기 전에

1. 백업 작동 방식을 [알아보고](backup-architecture.md#how-does-azure-backup-work) 지원 요구 사항을 [확인](backup-support-matrix.md#azure-vm-backup-support)합니다.
2. Azure VM 백업의 [개요를 살펴봅니다](backup-azure-vms-introduction.md).

### <a name="azure-vm-agent-installation"></a>Azure VM 에이전트 설치

Azure Vm을 백업 하기 위해 Azure Backup는 컴퓨터에서 실행 되는 VM 에이전트에 확장을 설치 합니다. Azure Marketplace 이미지에서 VM을 만든 경우 에이전트가 실행 됩니다. 예를 들어 사용자 지정 VM을 만들거나 온-프레미스에서 컴퓨터를 마이그레이션하는 경우에는 에이전트를 수동으로 설치 해야 할 수도 있습니다.

- VM 에이전트를 수동으로 설치해야 하는 경우 [Windows](../virtual-machines/extensions/agent-windows.md) 또는 [Linux](../virtual-machines/extensions/agent-linux.md) VM에 대한 지침을 따릅니다.
- 에이전트를 설치한 후 백업을 사용하도록 설정하면, Azure Backup은 에이전트에 백업 확장을 설치합니다. 사용자 개입 없이 확장을 업데이트하고 패치합니다.

## <a name="back-up-from-azure-vm-settings"></a>Azure VM 설정에서 백업

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.
2. **모든 서비스** 를 선택 하 고 필터에 **가상 컴퓨터**를 입력 한 다음 **가상 컴퓨터**를 선택 합니다.
3. Vm 목록에서 백업 하려는 VM을 선택 합니다.
4. VM 메뉴에서 **백업**을 선택 합니다.
5. **Recovery Services 자격 증명 모음**에서 다음을 수행합니다.
   - 자격 증명 모음이 이미 있는 경우 **기존 선택**을 선택 하 고 자격 증명 모음을 선택 합니다.
   - 자격 증명 모음이 없는 경우 **새로 만들기**를 선택 합니다. 자격 증명 모음의 이름을 지정합니다. 해당 자격 증명 모음은 VM과 동일한 지역 및 리소스 그룹에 생성됩니다. VM 설정에서 직접 백업을 사용하도록 설정하면 이러한 설정을 수정할 수 없습니다.

        ![Backup 마법사 사용](./media/backup-azure-vms-first-look-arm/vm-menu-enable-backup-small.png)

6. **백업 정책 선택**에서 다음 중 하나를 수행 합니다.

   - 기본 정책을 그대로 둡니다. 이렇게 하면 지정된 시간에 하루 1번 VM이 백업되고, 30일 동안 자격 증명 모음에 백업이 유지됩니다.
   - 기존 백업 정책이 있는 경우 선택 합니다.
   - 새 정책을 만들고 정책 설정을 정의합니다.  

       ![백업 정책 선택](./media/backup-azure-vms-first-look-arm/set-backup-policy.png)

7. **백업 사용**을 선택합니다. 이렇게 하면 백업 정책이 VM에 연결됩니다.

    ![Backup 사용 단추](./media/backup-azure-vms-first-look-arm/vm-management-menu-enable-backup-button.png)

8. 포털 알림에서 구성 진행률을 추적할 수 있습니다.
9. 작업이 완료 되 면 VM 메뉴에서 **백업**을 선택 합니다. 이 페이지는 VM의 백업 상태, 복구 지점에 대한 정보, 실행 중인 작업 및 발생한 경고를 표시합니다.

   ![백업 상태](./media/backup-azure-vms-first-look-arm/backup-item-view-update.png)

10. 백업을 사용하도록 설정하면 초기 백업이 실행됩니다. 초기 백업을 즉시 시작하거나, 백업 일정에 따라 시작될 때까지 기다릴 수 있습니다.
    - 초기 백업이 완료될 때까지 **마지막 백업 상태**는 **경고(초기 백업 보류 중)** 으로 표시됩니다.
    - 다음 예약 된 백업이 실행 되는 시기를 확인 하려면 백업 정책 이름을 선택 합니다.

## <a name="run-a-backup-immediately"></a>백업 즉시 실행

1. 백업을 즉시 실행 하려면 VM 메뉴에서 지금 **백업 백업을 선택**  >  **Backup now**합니다.

    ![백업 실행](./media/backup-azure-vms-first-look-arm/backup-now-update.png)

2. **지금 백업**에서 달력 컨트롤을 사용 하 여 복구 지점이 보존 될 때까지 선택한 다음 **확인**을 > 합니다.

    ![백업 보존일](./media/backup-azure-vms-first-look-arm/backup-now-blade-calendar.png)

3. 포털 알림을 통해 백업 작업이 트리거되었는지 알 수 있습니다. 백업 진행률을 모니터링 하려면 **모든 작업 보기**를 선택 합니다.

## <a name="back-up-from-the-recovery-services-vault"></a>Recovery Services 자격 증명 모음에서 백업

[이 문서의](backup-azure-arm-vms-prepare.md) 지침에 따라 Azure Backup Recovery Services 자격 증명 모음을 설정 하 고 자격 증명 모음에서 백업을 사용 하도록 설정 하 여 Azure vm에 대 한 백업을 사용 하도록 설정 합니다.

## <a name="next-steps"></a>다음 단계

- 이 문서의 절차를 수행하는 데 문제가 있으면 [문제 해결 가이드](backup-azure-vms-troubleshoot.md)를 참조하세요.
- 백업 관리에 대해 [자세히 알아봅니다](backup-azure-manage-vms.md).
