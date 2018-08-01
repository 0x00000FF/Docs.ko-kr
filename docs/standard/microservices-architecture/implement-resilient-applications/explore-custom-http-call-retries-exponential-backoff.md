---
title: 지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 탐색
description: 가능한 HTTP 오류 시나리오를 처리하기 위해 지수 백오프를 사용하여 HTTP 호출 다시 시도를 처음부터 구현하는 방법을 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: c323b8c4e783ed18c601562cfb25e1ca4986d499
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878750"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="7dec4-103">지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 탐색</span><span class="sxs-lookup"><span data-stu-id="7dec4-103">Explore custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="7dec4-104">복원력 있는 마이크로 서비스를 만들려면 가능한 HTTP 오류 시나리오를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-104">To create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="7dec4-105">권장되지는 않지만 이러한 오류를 처리하는 한 가지 방법은 지수 백오프를 사용하여 다시 시도를 직접 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-105">One way of handling those failures, although not recommended, is to create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="7dec4-106">**중요 참고:** 이 섹션에서는 HTTP 호출 다시 시도를 구현하는 사용자 고유의 사용자 지정 코드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-106">**Important note:** This section shows you how you could create your own custom code to implement HTTP call retries.</span></span> <span data-ttu-id="7dec4-107">그러나 사용자가 직접 수행하는 것은 권장되지 않으며, .NET Core 2.1부터 사용할 수 있는 Polly가 있는 `HttpClientFactory`와 같이 더 강력하고 신뢰할 수 있지만 간단한 메커니즘을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-107">However, it is not recommended to do it by your own but to use more powerful and reliable while simpler to use mechanisms, such as `HttpClientFactory` with Polly, available since .NET Core 2.1.</span></span> <span data-ttu-id="7dec4-108">다음 섹션에서는 이러한 권장 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-108">Those recommended approaches are explained in the next sections.</span></span> 

<span data-ttu-id="7dec4-109">초기 탐색에서 [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260)와 같이 지수 백오프에 대한 유틸리티 클래스를 사용하여 사용자 고유의 코드를 구현할 뿐만 아니라 다음과 같은 코드(이 [GitHub 리포지토리](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)에서 제공됨)도 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available at this [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="7dec4-110">클라이언트 C\# 응용 프로그램(다른 웹 API 클라이언트 마이크로 서비스, ASP.NET MVC 응용 프로그램 또는 C\# Xamarin 응용 프로그램)에서 쉽게 이 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="7dec4-111">다음 예제에서는 HttpClient 클래스를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-111">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="7dec4-112">이 코드는 개념 증명으로만 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-112">Remember that this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="7dec4-113">다음 섹션에서는 HttpClientFactory를 사용하여 더 정교하지만 간단하게 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-113">The next sections explain how to use more sophisticated approaches while simpler, by using HttpClientFactory.</span></span>
<span data-ttu-id="7dec4-114">HttpClientFactory는 Polly와 같이 입증된 복원력 라이브러리가 있는 .NET Core 2.1부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dec4-114">HttpClientFactory is available since .NET Core 2.1, with proven resiliency libraries like Polly.</span></span> 


>[!div class="step-by-step"]
<span data-ttu-id="7dec4-115">[이전](implement-resilient-entity-framework-core-sql-connections.md)
[다음](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="7dec4-115">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>