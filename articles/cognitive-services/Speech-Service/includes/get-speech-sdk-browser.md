---
author: trevorbye
ms.service: cognitive-services
ms.topic: include
ms.date: 03/27/2020
ms.author: trbye
ms.custom: devx-track-js
ms.openlocfilehash: f8c7b9ee90e947534d6f938b1eb22f58b57270e6
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91376364"
---
:::row:::
    :::column span="3":::
        JavaScript 용 Speech SDK는 npm 패키지로 사용할 수 있습니다. cognitiveservices account- <a href="https://www.npmjs.com/package/microsoft-cognitiveservices-speech-sdk" target="_blank">speech-sdk <span class="docon docon-navigate-external x-hidden-focus"></span> </a> 및 해당 하는 GitHub 리포지토리 <a href="https://github.com/Microsoft/cognitive-services-speech-sdk-js" target="_blank">인식 <span class="docon docon-navigate-external x-hidden-focus"></span> </a>
    :::column-end:::
    :::column:::
        <br>
        <div class="icon is-large">
            <img alt="JavaScript" src="https://docs.microsoft.com/media/logos/logo_js.svg"  width="60px">
        </div>
    :::column-end:::
:::row-end:::

> [!TIP]
> JavaScript 용 Speech SDK는 npm 패키지로 사용할 수 있으므로 클라이언트 웹 브라우저와 Node.js 모두 사용할 수 있습니다. 각 환경에서 다양 한 아키텍처의 영향을 고려 합니다. 예를 들어 클라이언트 쪽 응용 프로그램에서 <a href="https://nodejs.org/api/fs.html" target="_blank">파일 시스템 <span class="docon docon-navigate-external x-hidden-focus"></span> </a> 을 사용할 수 없는 경우와 마찬가지로 서버 쪽 응용 프로그램에서는 <a href="https://en.wikipedia.org/wiki/Document_Object_Model" target="_blank">DOM (문서 개체 모델) <span class="docon docon-navigate-external x-hidden-focus"></span> </a> 을 사용할 수 없습니다.

### <a name="nodejs-package-manager-npm"></a>Node.js 패키지 관리자 (NPM)

JavaScript 용 Speech SDK를 설치 하려면 `npm install` 아래 명령을 실행 합니다.

```nodejs
npm install microsoft-cognitiveservices-speech-sdk
```

### <a name="html-script-tag"></a>HTML 스크립트 태그

또는 `<script>` HTMLs 요소에 태그를 직접 포함 하 `<head>` 여 <a href="https://www.jsdelivr.com/package/npm/microsoft-cognitiveservices-speech-sdk" target="_blank"> **JSDelivr** NPM 게시 <span class="docon docon-navigate-external x-hidden-focus"></span> </a>를 사용할 수 있습니다.

```html
<script src="https://cdn.jsdelivr.net/npm/microsoft-cognitiveservices-speech-sdk@latest/distrib/browser/microsoft.cognitiveservices.speech.sdk.bundle-min.js">
</script>
```

자세한 내용은 <a href="https://github.com/Azure-Samples/cognitive-services-speech-sdk/tree/master/quickstart/javascript/browser" target="_blank">웹 브라우저 음성 SDK 퀵 스타트 <span class="docon docon-navigate-external x-hidden-focus"></span> </a>를 참조 하세요.
