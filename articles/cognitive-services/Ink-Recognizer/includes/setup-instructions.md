---
author: aahill
ms.author: aahi
ms.service: cognitive-services
ms.subservice: ink-recognizer
ms.topic: include
ms.date: 06/20/2019
ms.openlocfilehash: c68e5b7ab24e2d7e7f30ddc356ae3c4382137507
ms.sourcegitcommit: 22da82c32accf97a82919bf50b9901668dc55c97
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2020
ms.locfileid: "94369086"
---
>[!NOTE]
> 2019년 7월 1일 이후에 생성된 리소스의 엔드포인트는 아래에 표시된 사용자 지정 하위 도메인 형식을 사용합니다. 자세한 내용 및 지역별 엔드포인트의 전체 목록은 [Cognitive Services에 대한 사용자 지정 하위 도메인 이름](../../cognitive-services-custom-subdomains.md)을 참조하세요. 

Azure Cognitive Services는 구독하는 Azure 리소스로 표시됩니다. [Azure Portal](../../cognitive-services-apis-create-account.md)을 사용하여 잉크 인식기에 대한 리소스를 만듭니다.

리소스를 만든 후 [Azure Portal](https://ms.portal.azure.com#blade/HubsExtension/BrowseResourceGroupBlade)에서 리소스를 열고 **빠른 시작** 을 클릭하여 엔드포인트와 키를 가져옵니다.

두 개의 [환경 변수](../../cognitive-services-apis-create-account.md#get-the-keys-for-your-resource)를 만듭니다.

* `INK_RECOGNITION_SUBSCRIPTION_KEY` - 요청을 인증하기 위한 구독 키입니다. 

* `INK_RECOGNITION_ENDPOINT` - 리소스에 대한 엔드포인트입니다. 다음과 같이 표시됩니다. <br> `https://<your-custom-subdomain>.api.cognitive.microsoft.com`