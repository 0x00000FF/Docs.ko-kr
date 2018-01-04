---
title: "텍스트 파일 사용 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1d4b3f319d86dd463dabc8b71be7c76c7fef41f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="bcbca-102">텍스트 파일 사용 추적</span><span class="sxs-lookup"><span data-stu-id="bcbca-102">Tracking Using a Text File</span></span>
<span data-ttu-id="bcbca-103">이 샘플에서는 사용자 지정 추적 참가자를 만들어 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 추적을 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-103">This sample demonstrates how to extend tracking in [!INCLUDE[wf](../../../../includes/wf-md.md)] by creating a custom tracking participant.</span></span> <span data-ttu-id="bcbca-104">추적 참가자는 추적 레코드를 내보낼 때 런타임에서 추적 레코드를 받는 .NET Framework 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="bcbca-105">시나리오에 필요한 대상에 추적 이벤트를 전송하는 추적 참가자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="bcbca-106">예를 들어 ETW(Windows용 이벤트 추적) 추적 참가자는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="bcbca-107">이 샘플의 추적 참가자는 XML 형식의 레코드를 텍스트 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="bcbca-108">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="bcbca-108">Sample details</span></span>  
 <span data-ttu-id="bcbca-109">추적 참가자의 유용성과 견고성을 최적화하려면 추적 참가자를 런타임에 올바르게 연결하기 위한 몇 가지 추가 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="bcbca-110">다음 표에서는 이 샘플에서 최선의 방법을 따르는 추적 참가자를 만드는 데 사용된 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="bcbca-111">클래스</span><span class="sxs-lookup"><span data-stu-id="bcbca-111">Class</span></span>|<span data-ttu-id="bcbca-112">설명</span><span class="sxs-lookup"><span data-stu-id="bcbca-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="bcbca-113"><xref:System.ServiceModel.Configuration.BehaviorExtensionElement>는 텍스트 파일 추적 참가자를 구성하는 데 사용되는 구성 섹션을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="bcbca-114">이 클래스를 사용하면 사용자가 표준 .NET Framework 구성 파일을 사용하여 로그 파일의 대상을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="bcbca-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동작을 통해 사용자는 확장을 런타임에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-115">Behaviors in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="bcbca-116">이 동작은 서비스가 시작될 때 추적 참가자를 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="bcbca-117">런타임에 추적 참가자를 받아 로그 파일에 XML로 저장하는 추적 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="bcbca-118">동작 확장 요소 구성</span><span class="sxs-lookup"><span data-stu-id="bcbca-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="bcbca-119">.NET Framework 구성 파일을 사용하여 이전에 설명한 동작 확장 요소를 사용하려면 하나의 단계가 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="bcbca-120">확장이 사용될 구성 파일에 다음 구성을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="bcbca-121">동작 확장 요소 구성의 자세한 예제 사용법을 보려면 샘플에 있는 Web.config 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcbca-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="bcbca-122">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="bcbca-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="bcbca-123">GetStockPrices.cs 파일에서는 <xref:System.Activities.CodeActivity> 내에서 사용자 지정 추적 레코드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="bcbca-124">샘플을 실행할 때 이 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bcbca-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="bcbca-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="bcbca-126">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WFStockPriceApplication.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="bcbca-127">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bcbca-128">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="bcbca-129">브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="bcbca-130">브라우저에서 StockPriceService.xamlx를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="bcbca-131">브라우저 표시는 **StockPriceService** 로컬 서비스 wsdl 주소가 포함 된 페이지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="bcbca-132">이 주소를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-132">Copy this address.</span></span>  
  
     <span data-ttu-id="bcbca-133">로컬 서비스 wsdl 주소의 예로는 http://localhost:53797/StockPriceService.xamlx?wsdl이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="bcbca-134">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 폴더로 이동합니다. 기본 설치 폴더는 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="bcbca-135">그런 다음 Common7\IDE\ 하위 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="bcbca-136">WcfTestClient.exe 파일을 두 번 클릭하여 WCF 테스트 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="bcbca-137">WCF 테스트 클라이언트에서 선택 **서비스 추가...**</span><span class="sxs-lookup"><span data-stu-id="bcbca-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="bcbca-138">**파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bcbca-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="bcbca-139">방금 복사한 URL을 텍스트 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="bcbca-140">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="bcbca-141">WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="bcbca-142">WCF 테스트 클라이언트에서 두 번 클릭 **getstockprice ()** 아래는 **IStockPriceService** 노드.</span><span class="sxs-lookup"><span data-stu-id="bcbca-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="bcbca-143">**getstockprice ()** 메서드가 매개 변수를 사용 하 고 오른쪽 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="bcbca-144">매개 변수 값으로 Contoso를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="bcbca-145">클릭 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="bcbca-146">응용 프로그램 데이터 디렉터리에 있는 로그 파일(%APPDATA%\trackingRecords.log)에서 추적된 이벤트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcbca-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcbca-147">% APPDATA %는 %SystemDrive%\Users 확인 되는 환경 변수\\< 사용자 이름\>에 \AppData\Roaming [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], 또는 Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bcbca-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bcbca-148">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bcbca-149">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bcbca-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bcbca-150">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bcbca-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bcbca-151">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbca-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="bcbca-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcbca-152">See Also</span></span>  
 [<span data-ttu-id="bcbca-153">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="bcbca-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
