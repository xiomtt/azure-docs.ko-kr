---
title: Azure Table 스토리지 개요
description: Azure Table Storage를 사용하여 웹 애플리케이션, 주소록, 디바이스 정보 또는 기타 유형의 메타데이터에 대한 사용자 데이터와 같은 유연한 데이터 세트을 저장하는 방법을 알아봅니다.
ms.service: cosmos-db
ms.subservice: cosmosdb-table
ms.devlang: dotnet
ms.topic: overview
ms.date: 05/20/2019
author: sakash279
ms.author: akshanka
ms.reviewer: sngun
ms.openlocfilehash: 42d0b2c5d39ea7b5c44b7004f65f13e07067cdc7
ms.sourcegitcommit: 3bdeb546890a740384a8ef383cf915e84bd7e91e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93079515"
---
# <a name="azure-table-storage-overview"></a>Azure Table Storage 개요
[!INCLUDE[appliesto-table-api](includes/appliesto-table-api.md)]

[!INCLUDE [storage-table-cosmos-db-tip-include](../../includes/storage-table-cosmos-db-tip-include.md)]

Azure Table Storage는 클라우드에 구조화된 NoSQL 데이터를 저장하는 서비스로, 스키마 없이 디자인된 키/특성 저장소를 제공합니다. Table Storage는 스키마가 없기 때문에 애플리케이션의 요구 사항이 변화함에 따라 데이터를 쉽게 적응시킬 수 있습니다. Table Storage 데이터에 대한 액세스는 많은 애플리케이션 유형에 대해 빠르고 비용 효율적이며 비슷한 양의 데이터일 때 일반적으로 전통적인 SQL에 비해 비용이 매우 낮습니다.

Table Storage를 사용하여 웹 애플리케이션의 사용자 데이터, 주소록, 디바이스 정보 및 서비스에 필요한 다른 유형의 메타데이터와 같은 유연한 데이터 세트을 저장할 수 있습니다. 테이블에 저장할 수 있는 엔터티 수에는 제한이 없으며, 스토리지 계정에 포함할 수 있는 테이블의 수에는 스토리지 계정의 최대 용량 한도까지 제한이 없습니다.

[!INCLUDE [storage-table-concepts-include](../../includes/storage-table-concepts-include.md)]

## <a name="next-steps"></a>다음 단계

* [Microsoft Azure Storage Explorer](../vs-azure-tools-storage-manage-with-storage-explorer.md)는 Windows, macOS 및 Linux에서 Azure Storage 데이터로 시각적으로 작업할 수 있도록 해주는 Microsoft의 독립 실행형 무료 앱입니다.

* [.NET SDK를 사용하여 Azure Cosmos DB Table API 및 Azure Table Storage 시작](./tutorial-develop-table-dotnet.md)

* 사용 가능한 API에 대한 자세한 내용은 Table service 참조 설명서를 참조하세요.

    * [Storage Client Library for .NET 참조](/dotnet/api/overview/azure/storage)

    * [REST API 참조](/rest/api/storageservices/)