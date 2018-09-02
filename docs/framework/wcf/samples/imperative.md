---
title: 명령적
ms.date: 03/30/2017
ms.assetid: 4f7ce807-c0e4-407a-92a6-22abafb40b51
ms.openlocfilehash: 9039e2f0d13baefb8b0c2abcfb63dd11ce15ffd7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406715"
---
# <a name="imperative"></a><span data-ttu-id="d133e-102">명령적</span><span class="sxs-lookup"><span data-stu-id="d133e-102">Imperative</span></span>
<span data-ttu-id="d133e-103">이 샘플에는 정의 하는 방법을 보여 줍니다.는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 정의 하는 대신 코드를 사용 하는 서비스에 대 한는 `wsHttpBinding` 구성의 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d133e-103">This sample demonstrates how to define a <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span> <span data-ttu-id="d133e-104">이 샘플은 기반 합니다 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d133e-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d133e-106">다음 코드는 코드에서 명령적으로 바인딩을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-106">The following code demonstrates how to define a binding imperatively in code.</span></span>  
  
```  
public static void Main()  
{  
    WSHttpBinding binding = new WSHttpBinding();  
    binding.Name = "binding1";  
    binding.HostNameComparisonMode =  
        HostNameComparisonMode.StrongWildcard;  
    binding.Security.Mode = SecurityMode.Message;  
    binding.ReliableSession.Enabled = false;  
    binding.TransactionFlow = false;  
  
    Uri baseAddress =   
        new Uri("http://localhost:8000/servicemodelsamples/service");  
  
    // Create a ServiceHost for the CalculatorService type and provide the base address.  
    using(ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
    {  
        serviceHost.AddServiceEndpoint(typeof(ICalculator),   
                                       binding, baseAddress);  
        // Open the ServiceHostBase to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
        // Close the ServiceHostBase to shutdown the service.  
        serviceHost.Close();                        
    }             
}  
```  
  
 <span data-ttu-id="d133e-107">클라이언트는 다음 샘플 코드에서와 같이 서비스와 통신하기 위해 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-107">The client creates a channel to communicate with the service as shown in the following sample code.</span></span>  
  
```  
WSHttpBinding binding = new WSHttpBinding();  
binding.Name = "binding1";  
binding.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
binding.Security.Mode = SecurityMode.Message;  
binding.ReliableSession.Enabled = false;  
binding.TransactionFlow = false;  
  
String url = "http://localhost:8000/servicemodelsamples/service";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding,address);  
ICalculator channel = channelFactory.CreateChannel();  
```  
  
 <span data-ttu-id="d133e-108">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-108">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d133e-109">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-109">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d133e-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d133e-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d133e-111">수행 해야 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-111">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d133e-112">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-112">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d133e-113">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-113">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d133e-114">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d133e-115">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d133e-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d133e-116">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="d133e-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d133e-117">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d133e-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Imperative`  
  
## <a name="see-also"></a><span data-ttu-id="d133e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d133e-118">See Also</span></span>
