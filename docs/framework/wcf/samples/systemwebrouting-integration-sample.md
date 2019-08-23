---
title: SystemWebRouting Integration 샘플
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 032be700beaa38ed6c08ed1940aab558b2106591
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964489"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="46eda-102">SystemWebRouting Integration 샘플</span><span class="sxs-lookup"><span data-stu-id="46eda-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="46eda-103">이 샘플에서는 호스팅 계층과 <xref:System.Web.Routing> 네임스페이스에 있는 클래스의 통합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="46eda-104"><xref:System.Web.Routing> 네임스페이스의 클래스를 사용하면 애플리케이션에서 실제 리소스에 직접적으로 해당하지 않는 URL을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="46eda-105">개발자는 웹 라우팅을 사용 하 여 HTTP에 대 한 가상 주소를 만든 다음 실제 WCF 서비스에 다시 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="46eda-106">이렇게 하면 실제 파일 또는 리소스 없이 WCF 서비스를 호스트해야 하거나 .html 또는 .aspx와 같은 파일 확장명이 포함되지 않은 URL을 사용하여 서비스에 액세스해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="46eda-107">이 샘플에서는 <xref:System.Web.Routing.RouteTable> 클래스를 사용하여 global.asax에 정의된 실행 중인 서비스에 매핑되는 가상 URI를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
> <span data-ttu-id="46eda-108"><xref:System.Web.Routing> 네임스페이스의 클래스는 HTTP를 통해 호스트되는 서비스에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="46eda-109">이 예제에서는 WCF를 사용 하 여 `movies` 피드 `channels` 및 피드의 두 RSS 피드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="46eda-110">서비스를 활성화 하는 url은 확장을 포함 하지 않으며 `Application_Start` <xref:System.Web.HttpApplication> 클래스에서 파생 된 `Global` 클래스의 메서드에 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46eda-111">IIS 6.0에서 확장 Url을 지원 하기 위해 다른 방법을 사용 하므로이 샘플은 인터넷 정보 서비스 (IIS) 7.0 이상 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="46eda-112">이 샘플을 다운로드 하려면</span><span class="sxs-lookup"><span data-stu-id="46eda-112">To download this sample</span></span>
  
<span data-ttu-id="46eda-113">이 샘플은 컴퓨터에 이미 설치 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="46eda-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="46eda-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="46eda-115">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 로 이동 하 여 모든 Windows Communication Foundation (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="46eda-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="46eda-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="46eda-117">To use this sample</span></span>  
  
1. <span data-ttu-id="46eda-118">Visual Studio를 사용 하 여 WebRoutingIntegration .sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="46eda-119">F5 키를 눌러 솔루션을 실행하고 웹 개발 서버를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="46eda-120">샘플의 디렉터리 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="46eda-121">파일 확장명이 .svc인 파일은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="46eda-122">주소 표시줄에서 URL에를 `movies` 추가 하 여를 읽고 `http://localhost:[port]/movies` enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="46eda-123">movies 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="46eda-124">주소 표시줄에서을 (를 `channels` ) 읽도록 `http://localhost:[port]/channels` URL에를 추가 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="46eda-125">channels 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="46eda-126">Alt+F4를 눌러 웹 브라우저를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="46eda-127">개발 서버가 종료 되지 않은 경우 알림 영역 아이콘을 마우스 오른쪽 단추로 클릭 하 고 **중지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="46eda-128">IIS에서 호스트될 때 이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="46eda-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="46eda-129">Visual Studio를 사용 하 여 WebRoutingIntegration .sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="46eda-130">Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="46eda-131">IIS(인터넷 정보 서비스) 관리자에서 웹 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="46eda-132">IIS 관리자에서 **기본 웹 사이트** 를 마우스 오른쪽 단추로 클릭 하 고 **응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="46eda-133">**별칭**에 대해를 입력 `WebRoutingIntegration`합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="46eda-134">**실제 경로**의 경우 프로젝트 내에서 서비스 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="46eda-135">**확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="46eda-136">웹 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 **응용 프로그램 관리** 를 선택한 다음 **찾아보기**를 선택 하 여 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="46eda-137">주소 표시줄에서을 (를 `movies` ) 읽도록 `http://localhost:[port]/movies` URL에를 추가 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="46eda-138">movies 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="46eda-139">주소 표시줄에서을 (를 `channels` ) 읽도록 `http://localhost:[port]/channels` URL에를 추가 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="46eda-140">channels 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="46eda-141">Alt+F4를 눌러 웹 브라우저를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="46eda-142">이 샘플에서는 HTTP를 통해 호스트되는 서비스의 요청을 라우트하기 위해 <xref:System.Web.Routing> 네임스페이스의 클래스를 사용하여 호스팅 계층을 작성할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46eda-143">버전 2로 설정 된 경우 기본 응용 프로그램 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 풀 버전을로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46eda-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46eda-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="46eda-144">See also</span></span>

- [<span data-ttu-id="46eda-145">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="46eda-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
