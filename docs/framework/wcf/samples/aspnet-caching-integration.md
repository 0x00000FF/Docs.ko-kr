---
title: ASP.NET 캐싱 통합
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 55e6213bf0c4c212ebcf4e68882d16532c0e4229
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43555762"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="ed184-102">ASP.NET 캐싱 통합</span><span class="sxs-lookup"><span data-stu-id="ed184-102">ASP.NET Caching Integration</span></span>
<span data-ttu-id="ed184-103">이 샘플에서는 WCF 웹 HTTP 프로그래밍 모델을 사용하여 ASP.NET 출력 캐시를 활용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="ed184-104">참조 하십시오 합니다 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 방어에서 서비스 구현에 설명 하는이 시나리오의 자체 호스팅된 버전에 대 한 샘플.</span><span class="sxs-lookup"><span data-stu-id="ed184-104">Please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample for a self-hosted version of this scenario that discusses the service implementation in depth.</span></span> <span data-ttu-id="ed184-105">이 항목에서는 ASP.NET 출력 캐시 통합 기능을 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ed184-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="ed184-106">Demonstrates</span></span>  
 <span data-ttu-id="ed184-107">ASP.NET 출력 캐시와 통합</span><span class="sxs-lookup"><span data-stu-id="ed184-107">Integration with the ASP.NET Output Cache</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed184-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed184-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ed184-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed184-110">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ed184-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed184-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a><span data-ttu-id="ed184-112">토론</span><span class="sxs-lookup"><span data-stu-id="ed184-112">Discussion</span></span>  
 <span data-ttu-id="ed184-113">샘플을 사용 합니다 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> ASP.NET을 활용 하는 Windows Communication Foundation (WCF) 서비스를 사용 하 여 캐시를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="ed184-114"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>는 서비스 작업에 적용되며, 구성 파일에서 지정된 작업의 응답에 적용해야 하는 캐시 프로필의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>  
  
 <span data-ttu-id="ed184-115">샘플 Service 프로젝트의 Service.cs 파일에서 모두를 `GetCustomer` 하 고 `GetCustomers` 작업으로 표시 됩니다는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, 캐시 프로필 이름 "Cachefor60seconds"를 제공 하는.</span><span class="sxs-lookup"><span data-stu-id="ed184-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="ed184-116">서비스 프로젝트의 Web.config 파일에서 캐시 프로필 "Cachefor60seconds"는에서 제공 되는 <`caching`> 요소의 <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="ed184-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="ed184-117">이 캐시 프로필의 경우 값에 대 한는 `duration` 특성 이므로 "60"이이 프로필과 연결 된 응답은 60 초 동안 ASP.NET 출력 캐시에 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="ed184-118">이 캐시 프로필의 경우에, 합니다 `varmByParam` 특성에 대해 다른 값을 사용 하 여 하므로 요청 "format"으로 설정 되어를 `format` 쿼리 문자열 매개 변수에서는 응답이 별도로 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="ed184-119">마지막으로 캐시 프로필의 `varyByHeader` Accept 헤더 값이 다른 요청에서는 응답이 별도로 캐시를 갖도록 특성은 "Accept"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>  
  
 <span data-ttu-id="ed184-120">Client 프로젝트의 Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="ed184-121">이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="ed184-122">WCF 채널 팩터리와 같은 다른.NET Framework 클래스를 사용 하는 서비스에 액세스할 수 이기도 한 <xref:System.Net.WebClient>합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-122">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="ed184-123">SDK의 다른 샘플 (같은 합니다 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [선택 영역 자동 서식 지정](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플)에서는 이러한 클래스를 사용 하 여 WCF 서비스와 통신 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-123">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>  
  
## <a name="to-run-the-sample"></a><span data-ttu-id="ed184-124">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ed184-124">To run the sample</span></span>  
 <span data-ttu-id="ed184-125">이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-125">The sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="ed184-126">**서비스**: ASP.NET에서 호스팅되는 WCF HTTP 서비스가 포함 하는 웹 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
-   <span data-ttu-id="ed184-127">**클라이언트**: 서비스를 호출 하는 콘솔 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-127">**Client**: A console application project that makes calls to the service.</span></span>  
  
-   <span data-ttu-id="ed184-128">**일반적인**: 클라이언트와 서비스에서 사용 하는 고객 형식을 포함 하는 공유 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>  
  
 <span data-ttu-id="ed184-129">Client 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="ed184-130">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ed184-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="ed184-131">ASP.NET Caching Integration 샘플의 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>  
  
2.  <span data-ttu-id="ed184-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="ed184-133">경우는 **솔루션 탐색기** 창이 아직 열려 있지 않으면, CTRL + W + S를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>  
  
4.  <span data-ttu-id="ed184-134">**솔루션 탐색기** 창에서 마우스 오른쪽 단추로 클릭 합니다 **Service** 프로젝트를 마우스 **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="ed184-135">그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-135">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="ed184-136">**솔루션 탐색기** 창에서 마우스 오른쪽 단추로 클릭 합니다 **클라이언트** 프로젝트를 마우스 **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="ed184-137">클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="ed184-138">언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="ed184-139">샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-139">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="ed184-140">아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-140">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="ed184-141">Shift+F5를 눌러 서비스 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-141">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="ed184-142">Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="ed184-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
