---
title: Bing Web Search Python 클라이언트 라이브러리 빠른 시작
titleSuffix: Azure Cognitive Services
services: cognitive-services
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.topic: include
ms.date: 03/05/2020
ms.author: aahi
ms.openlocfilehash: 13e08d2c273b242a902203abf0879fd11fbdf801
ms.sourcegitcommit: 8a1ba1ebc76635b643b6634cc64e137f74a1e4da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94386472"
---
Bing Web Search 클라이언트 라이브러리를 사용하면 Bing Web Search를 Python 애플리케이션에 쉽게 통합할 수 있습니다. 이 빠른 시작에서는 요청을 보내고, JSON 응답을 받고, 결과를 필터링 및 구문 분석하는 방법에 대해 알아봅니다.

지금 코드를 보시겠나요? [Python용 Bing Search 클라이언트 라이브러리](https://github.com/Azure-Samples/cognitive-services-python-sdk-samples/tree/master/samples/search) 샘플은 GitHub에서 사용할 수 있습니다.


## <a name="prerequisites"></a>필수 구성 요소
Bing Web Search SDK는 Python 2.7 3.3, 3.4, 3.5 및 3.6과 호환됩니다. 이 빠른 시작에서는 가상 환경을 사용하는 것이 좋습니다.

* Python 2.7, 3.3, 3.4, 3.5 또는 3.6
* Python 2.7의 경우 [virtualenv](https://docs.python.org/3/tutorial/venv.html)
* Python 3.x의 경우 [venv](https://pypi.python.org/pypi/virtualenv)

[!INCLUDE [bing-web-search-quickstart-signup](~/includes/bing-web-search-quickstart-signup.md)]

## <a name="create-and-configure-your-virtual-environment"></a>가상 환경 만들기 및 구성

Python 2.x 및 Python 3.x에 대한 가상 환경을 설정하고 구성하는 지침은 다릅니다. 아래 단계에 따라 가상 환경을 만들고 초기화합니다.

### <a name="python-2x"></a>Python 2.x

Python 2.7의 경우 `virtualenv`를 사용하여 가상 환경을 만듭니다.

```console
virtualenv mytestenv
```

환경을 활성화합니다.

```console
cd mytestenv
source bin/activate
```

Bing Web Search SDK 종속성을 설치합니다.

```console
python -m pip install azure-cognitiveservices-search-websearch
```

### <a name="python-3x"></a>Python 3.x

Python 3.x의 경우 `venv`를 사용하여 가상 환경을 만듭니다.

```console
python -m venv mytestenv
```

환경을 활성화합니다.

```console
mytestenv\Scripts\activate.bat
```

Bing Web Search SDK 종속성을 설치합니다.

```console
cd mytestenv
python -m pip install azure-cognitiveservices-search-websearch
```

## <a name="create-a-client-and-print-your-first-results"></a>클라이언트 만들기 및 첫 번째 결과 출력

이제 가상 환경이 설정되고 종속성이 설치되었으므로 클라이언트를 만들어 보겠습니다. 클라이언트는 Bing Web Search API의 요청과 응답을 처리합니다.

응답에 웹 페이지, 이미지, 뉴스 또는 비디오가 포함되면 각각에 대한 첫 번째 결과를 출력합니다.

1. 즐겨찾는 IDE 또는 편집기를 사용하여 새 Python 프로젝트를 만듭니다.

1. 이 샘플 코드를 프로젝트에 복사합니다. `endpoint`는 아래의 글로벌 엔드포인트이거나 리소스의 Azure Portal에 표시되는 [사용자 지정 하위 도메인](~/articles/cognitive-services/cognitive-services-custom-subdomains.md) 엔드포인트일 수 있습니다.  

    ```python
    # Import required modules.
    from azure.cognitiveservices.search.websearch import WebSearchClient
    from azure.cognitiveservices.search.websearch.models import SafeSearch
    from msrest.authentication import CognitiveServicesCredentials

    # Replace with your subscription key.
    subscription_key = "YOUR_SUBSCRIPTION_KEY"

    # Instantiate the client and replace with your endpoint.
    client = WebSearchClient(endpoint="YOUR_ENDPOINT", credentials=CognitiveServicesCredentials(subscription_key))

    # Make a request. Replace Yosemite if you'd like.
    web_data = client.web.search(query="Yosemite")
    print("\r\nSearched for Query# \" Yosemite \"")

    '''
    Web pages
    If the search response contains web pages, the first result's name and url
    are printed.
    '''
    if hasattr(web_data.web_pages, 'value'):

        print("\r\nWebpage Results#{}".format(len(web_data.web_pages.value)))

        first_web_page = web_data.web_pages.value[0]
        print("First web page name: {} ".format(first_web_page.name))
        print("First web page URL: {} ".format(first_web_page.url))

    else:
        print("Didn't find any web pages...")

    '''
    Images
    If the search response contains images, the first result's name and url
    are printed.
    '''
    if hasattr(web_data.images, 'value'):

        print("\r\nImage Results#{}".format(len(web_data.images.value)))

        first_image = web_data.images.value[0]
        print("First Image name: {} ".format(first_image.name))
        print("First Image URL: {} ".format(first_image.url))

    else:
        print("Didn't find any images...")

    '''
    News
    If the search response contains news, the first result's name and url
    are printed.
    '''
    if hasattr(web_data.news, 'value'):

        print("\r\nNews Results#{}".format(len(web_data.news.value)))

        first_news = web_data.news.value[0]
        print("First News name: {} ".format(first_news.name))
        print("First News URL: {} ".format(first_news.url))

    else:
        print("Didn't find any news...")

    '''
    If the search response contains videos, the first result's name and url
    are printed.
    '''
    if hasattr(web_data.videos, 'value'):

        print("\r\nVideos Results#{}".format(len(web_data.videos.value)))

        first_video = web_data.videos.value[0]
        print("First Videos name: {} ".format(first_video.name))
        print("First Videos URL: {} ".format(first_video.url))

    else:
        print("Didn't find any videos...")
    ```

1. `SUBSCRIPTION_KEY`를 유효한 구독 키로 바꿉니다.

1. `YOUR_ENDPOINT`를 포털의 엔드포인트 URL로 바꾸고 엔드포인트에서 "bing/v7.0" 섹션을 제거합니다.

1. 프로그램을 실행합니다. 예: `python your_program.py`

## <a name="define-functions-and-filter-results"></a>함수 정의 및 결과 필터링

지금까지 처음으로 Bing Web Search API를 호출했으므로 몇 가지 함수를 살펴보겠습니다. 다음 섹션에서는 쿼리를 구체화하고 결과를 필터링하기 위한 SDK 기능을 중점적으로 설명합니다. 각 함수는 이전 섹션에서 만든 Python 프로그램에 추가할 수 있습니다.

### <a name="limit-the-number-of-results-returned-by-bing"></a>Bing에서 반환하는 결과 수 제한

이 샘플에서는 `count` 및 `offset` 매개 변수를 사용하여 SDK의 [`search` 메서드](/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations?view=azure-python)를 통해 반환되는 결과의 수를 제한합니다. 첫 번째 결과에 대한 `name` 및 `url`이 출력됩니다.

1. 이 코드를 Python 프로젝트에 추가합니다.

   ```python
    # Declare the function.
    def web_results_with_count_and_offset(subscription_key):
        client = WebSearchAPI(CognitiveServicesCredentials(subscription_key))

        try:
            '''
            Set the query, offset, and count using the SDK's search method. See:
            https://docs.microsoft.com/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations?view=azure-python.
            '''
            web_data = client.web.search(query="Best restaurants in Seattle", offset=10, count=20)
            print("\r\nSearching for \"Best restaurants in Seattle\"")

            if web_data.web_pages.value:
                '''
                If web pages are available, print the # of responses, and the first and second
                web pages returned.
                '''
                print("Webpage Results#{}".format(len(web_data.web_pages.value)))

                first_web_page = web_data.web_pages.value[0]
                print("First web page name: {} ".format(first_web_page.name))
                print("First web page URL: {} ".format(first_web_page.url))

            else:
                print("Didn't find any web pages...")

        except Exception as err:
            print("Encountered exception. {}".format(err))
    ```

1. 프로그램을 실행합니다.

### <a name="filter-for-news-and-freshness"></a>뉴스 및 새로 고침 필터링

이 샘플에서는 `response_filter` 및 `freshness` 매개 변수를 사용하여 SDK의 [`search` 메서드](/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations)를 통해 검색 결과를 필터링합니다. 반환되는 검색 결과는 Bing에서 지난 24시간 이내에 검색한 뉴스 기사 및 페이지로 제한됩니다. 첫 번째 결과에 대한 `name` 및 `url`이 출력됩니다.

1. 이 코드를 Python 프로젝트에 추가합니다.

    ```python
    # Declare the function.
    def web_search_with_response_filter(subscription_key):
        client = WebSearchAPI(CognitiveServicesCredentials(subscription_key))
        try:
            '''
            Set the query, response_filter, and freshness using the SDK's search method. See:
            https://docs.microsoft.com/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations?view=azure-python.
            '''
            web_data = client.web.search(query="xbox",
                response_filter=["News"],
                freshness="Day")
            print("\r\nSearching for \"xbox\" with the response filter set to \"News\" and freshness filter set to \"Day\".")

            '''
            If news articles are available, print the # of responses, and the first and second
            articles returned.
            '''
            if web_data.news.value:

                print("# of news results: {}".format(len(web_data.news.value)))

                first_web_page = web_data.news.value[0]
                print("First article name: {} ".format(first_web_page.name))
                print("First article URL: {} ".format(first_web_page.url))

                print("")

                second_web_page = web_data.news.value[1]
                print("\nSecond article name: {} ".format(second_web_page.name))
                print("Second article URL: {} ".format(second_web_page.url))

            else:
                print("Didn't find any news articles...")

        except Exception as err:
            print("Encountered exception. {}".format(err))

    # Call the function.
    web_search_with_response_filter(subscription_key)
    ```

1. 프로그램을 실행합니다.

### <a name="use-safe-search-answer-count-and-the-promote-filter"></a>안전 검색, 응답 수 및 승격 필터 사용

이 샘플에서는 `answer_count`, `promote` 및 `safe_search` 매개 변수를 사용하여 SDK의 [`search` 메서드](/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations?view=azure-python)를 통해 검색 결과를 필터링합니다. 첫 번째 결과에 대한 `name` 및 `url`이 표시됩니다.

1. 이 코드를 Python 프로젝트에 추가합니다.

    ```python
    # Declare the function.
    def web_search_with_answer_count_promote_and_safe_search(subscription_key):

        client = WebSearchAPI(CognitiveServicesCredentials(subscription_key))

        try:
            '''
            Set the query, answer_count, promote, and safe_search parameters using the SDK's search method. See:
            https://docs.microsoft.com/python/api/azure-cognitiveservices-search-websearch/azure.cognitiveservices.search.websearch.operations.weboperations?view=azure-python.
            '''
            web_data = client.web.search(
                query="Niagara Falls",
                answer_count=2,
                promote=["videos"],
                safe_search=SafeSearch.strict  # or directly "Strict"
            )
            print("\r\nSearching for \"Niagara Falls\"")

            '''
            If results are available, print the # of responses, and the first result returned.
            '''
            if web_data.web_pages.value:

                print("Webpage Results#{}".format(len(web_data.web_pages.value)))

                first_web_page = web_data.web_pages.value[0]
                print("First web page name: {} ".format(first_web_page.name))
                print("First web page URL: {} ".format(first_web_page.url))

            else:
                print("Didn't see any Web data..")

        except Exception as err:
            print("Encountered exception. {}".format(err))
    ```

1. 프로그램을 실행합니다.

## <a name="clean-up-resources"></a>리소스 정리

이 프로젝트가 완료되면 프로그램의 코드에서 구독 키를 제거하고 가상 환경을 비활성화해야 합니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [Cognitive Services Python SDK 샘플](https://github.com/Azure-Samples/cognitive-services-python-sdk-samples)

## <a name="see-also"></a>참고 항목

* [Azure Python SDK 참조](/python/api/azure-cognitiveservices-search-websearch/?view=azure-python)
