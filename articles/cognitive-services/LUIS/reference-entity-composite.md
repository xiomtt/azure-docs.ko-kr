---
title: 복합 엔터티 형식-LUIS
titleSuffix: Azure Cognitive Services
description: 복합 엔터티는 미리 작성 된 엔터티, 단순, 정규식, 목록 엔터티 등의 다른 엔터티로 구성 됩니다. 개별 엔터티가 전체 엔터티를 형성합니다.
services: cognitive-services
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-understanding
ms.topic: reference
ms.date: 04/14/2020
ms.openlocfilehash: 97bd079034a39f158e3ca438c484929cb6f00363
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91542260"
---
# <a name="composite-entity"></a>복합 엔터티

복합 엔터티는 미리 작성 된 엔터티, 단순, 정규식, 목록 엔터티 등의 다른 엔터티로 구성 됩니다. 개별 엔터티가 전체 엔터티를 형성합니다.

> [!CAUTION]
> 이 엔터티는 **더 이상 사용 되지**않습니다. [Machine learning 엔터티로](reference-entity-machine-learned-entity.md)마이그레이션 하세요.

**데이터의 상태가 다음과 같은 경우 이 엔터티가 적합합니다.**

* 서로 관련이 있습니다.
* 발언의 컨텍스트에서 서로 관련되어 있습니다.
* 다양한 엔터티 형식을 사용합니다.
* 클라이언트 애플리케이션에서 정보 단위로 그룹화되고 처리되어야 합니다.
* 기계 학습을 요구하는 다양한 사용자 발언이 포함됩니다.

![복합 엔터티](./media/luis-concept-entities/composite-entity.png)

## <a name="example-json"></a>예제 JSON

다음 utterance을 사용 하 여 미리 작성 된의 복합 엔터티를 고려 합니다 `number` `Location::ToLocation` .

`book 2 tickets to cairo`

`2`(number)와 `cairo`(ToLocation) 사이에 엔터티에 속하지 않는 단어가 있음을 알 수 있습니다. [LUIS](luis-reference-regions.md) 웹 사이트의 레이블이 지정된 발화에서 사용된 녹색 밑줄은 복합 엔터티를 나타냅니다.

![복합 엔터티](./media/luis-concept-data-extraction/composite-entity.png)

#### <a name="v2-prediction-endpoint-response"></a>[V2 예측 엔드포인트 응답](#tab/V2)

복합 엔터티는 `compositeEntities` 배열로 반환되고 복합 내의 모든 엔터티도 `entities` 배열로 반환됩니다.

```JSON
  "entities": [
    {
      "entity": "2 tickets to cairo",
      "type": "ticketinfo",
      "startIndex": 5,
      "endIndex": 22,
      "score": 0.9214487
    },
    {
      "entity": "cairo",
      "type": "builtin.geographyV2.city",
      "startIndex": 18,
      "endIndex": 22
    },
    {
      "entity": "2",
      "type": "builtin.number",
      "startIndex": 5,
      "endIndex": 5,
      "resolution": {
        "subtype": "integer",
        "value": "2"
      }
    }
  ],
  "compositeEntities": [
    {
      "parentType": "ticketinfo",
      "value": "2 tickets to cairo",
      "children": [
        {
          "type": "builtin.number",
          "value": "2"
        },
        {
          "type": "builtin.geographyV2.city",
          "value": "cairo"
        }
      ]
    }
  ]
```

#### <a name="v3-prediction-endpoint-response"></a>[V3 예측 엔드포인트 응답](#tab/V3)

이는 `verbose=false` 쿼리 문자열에가 설정 된 경우 JSON입니다.

```json
"entities": {
    "ticketinfo": [
        {
            "number": [
                2
            ],
            "geographyV2": [
                "cairo"
            ]
        }
    ]
}
```

이는 `verbose=true` 쿼리 문자열에가 설정 된 경우 JSON입니다.

```json
"entities": {
    "ticketinfo": [
        {
            "number": [
                2
            ],
            "geographyV2": [
                "cairo"
            ],
            "$instance": {
                "number": [
                    {
                        "type": "builtin.number",
                        "text": "2",
                        "startIndex": 5,
                        "length": 1,
                        "modelTypeId": 2,
                        "modelType": "Prebuilt Entity Extractor",
                        "recognitionSources": [
                            "model"
                        ]
                    }
                ],
                "geographyV2": [
                    {
                        "type": "builtin.geographyV2.city",
                        "text": "cairo",
                        "startIndex": 18,
                        "length": 5,
                        "modelTypeId": 2,
                        "modelType": "Prebuilt Entity Extractor",
                        "recognitionSources": [
                            "model"
                        ]
                    }
                ]
            }
        }
    ],
    "$instance": {
        "ticketinfo": [
            {
                "type": "ticketinfo",
                "text": "2 tickets to cairo",
                "startIndex": 5,
                "length": 18,
                "score": 0.9214487,
                "modelTypeId": 4,
                "modelType": "Composite Entity Extractor",
                "recognitionSources": [
                    "model"
                ]
            }
        ]
    }
}
```

* * *


|데이터 개체|엔터티 이름|값|
|--|--|--|
|미리 빌드된 엔터티 - number|“builtin.number”|“2”|
|미리 작성 한 엔터티-GeographyV2|“Location::ToLocation”|카이로|

## <a name="next-steps"></a>다음 단계

엔터티에 대 한 자세한 정보:

* [개념](luis-concept-entity-types.md)
* [만드는 방법](luis-how-to-add-entities.md)
