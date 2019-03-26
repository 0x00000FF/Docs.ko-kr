---
title: WS 다중 Http
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: d5c6309a183c0bf0b666fd39aea3d760eb7008ad
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332158"
---
# <a name="ws-dual-http"></a><span data-ttu-id="0e94b-102">WS 다중 Http</span><span class="sxs-lookup"><span data-stu-id="0e94b-102">WS Dual Http</span></span>
<span data-ttu-id="0e94b-103">Dual Http 샘플에서는 `WSDualHttpBinding` 바인딩을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-103">The Dual Http sample demonstrates how to configure the `WSDualHttpBinding` binding.</span></span> <span data-ttu-id="0e94b-104">이 샘플은 IIS(인터넷 정보 서비스)에 의해 호스트되는 클라이언트 콘솔 프로그램(.exe) 및 서비스 라이브러리(.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-104">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="0e94b-105">서비스는 이중 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-105">The service implements a duplex contract.</span></span> <span data-ttu-id="0e94b-106">계약은 수학 연산(Add, Subtract, Multiply 및 Divide)을 노출시키는 `ICalculatorDuplex` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-106">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="0e94b-107">이 샘플에서 클라이언트는 `ICalculatorDuplex` 인터페이스를 통해 수학 연산을 수행하고 세션 중에 실행 결과를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over the session.</span></span> <span data-ttu-id="0e94b-108">서비스는 독립적으로 `ICalculatorDuplexCallback` 인터페이스에 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-108">Independently, the service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="0e94b-109">클라이언트와 서비스 간에 전송되는 메시지 집합을 서로 연결하기 위해 컨텍스트를 설정해야 하므로 이중 계약에는 세션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between client and service.</span></span> <span data-ttu-id="0e94b-110">`WSDualHttpBinding` 바인딩은 이중 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-110">The `WSDualHttpBinding` binding supports duplex communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e94b-111">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e94b-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0e94b-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0e94b-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0e94b-114">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="0e94b-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e94b-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`  
  
 <span data-ttu-id="0e94b-116">`WSDualHttpBinding`을 사용하여 서비스 엔드포인트를 구성하려면 다음과 같이 엔드포인트 구성에 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-116">To configure a service endpoint with the `WSDualHttpBinding`, specify the binding in the endpoint configuration as shown.</span></span>  
  
```xml  
<endpoint address=""  
         binding="wsDualHttpBinding"  
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
```  
  
 <span data-ttu-id="0e94b-117">클라이언트에서는 다음 샘플 구성과 같이 서버가 클라이언트에 연결하는 데 사용할 수 있는 주소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-117">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
         "http://localhost/servicemodelsamples/service.svc"   
         binding="wsDualHttpBinding"   
         bindingConfiguration="Binding1"   
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
  </client>  
  
  <bindings>  
    <!-- Configure a WSDualHttpBinding that supports duplex -->  
    <!-- communication. -->  
    <wsDualHttpBinding>  
      <binding name="Binding1"  
               clientBaseAddress="http://localhost:8000/myClient/"  
               useDefaultWebProxy="true"  
               bypassProxyOnLocal="false">  
      </binding>  
    </wsDualHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0e94b-118">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0e94b-119">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Press <ENTER> to terminate client once the output is displayed.  
  
Result(100)  
Result(50)  
Result(882.5)  
Result(441.25)  
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)  
```  
  
 <span data-ttu-id="0e94b-120">샘플을 실행하면 서비스에서 전송된 콜백 인터페이스에서 클라이언트에 반환된 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-120">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="0e94b-121">각 중간 결과가 표시된 다음 모든 작업이 완료되면 전체 수식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-121">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="0e94b-122">클라이언트를 종료하려면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-122">Press ENTER to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e94b-123">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0e94b-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0e94b-124">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-124">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="0e94b-125">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="0e94b-126">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="0e94b-127">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e94b-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0e94b-128">다중 컴퓨터 구성에서 클라이언트를 실행 하는 경우 대체 해야에서 localhost를 `address` 특성을 [ \<끝점 >의 \<클라이언트 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) 요소와 `clientBaseAddress` 특성을 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소의 합니다 [ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) 표시 된 것 처럼 적절 한 컴퓨터의 이름 사용 하 여 요소:</span><span class="sxs-lookup"><span data-stu-id="0e94b-128">When running the client in a cross-machine configuration, be sure to replace localhost in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown:</span></span>  
  
    ```xml  
    <client>  
        <endpoint name = ""  
          address=  
         "http://service_machine_name/servicemodelsamples/service.svc"  
        />  
    </client>  
    ...  
    <wsDualHttpBinding>  
        <binding name="DuplexBinding" clientBaseAddress=  
            "http://client_machine_name:8000/myClient/">  
        </binding>  
    </wsDualHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0e94b-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e94b-129">See also</span></span>
