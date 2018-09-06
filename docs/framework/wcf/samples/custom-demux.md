---
title: 사용자 지정 Demux
ms.date: 03/30/2017
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
ms.openlocfilehash: 1542743a6e1658bad162d7ee9ca73e6b9b0444e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732370"
---
# <a name="custom-demux"></a><span data-ttu-id="dd1ce-102">사용자 지정 Demux</span><span class="sxs-lookup"><span data-stu-id="dd1ce-102">Custom Demux</span></span>
<span data-ttu-id="dd1ce-103">이 샘플에서는 MSMQ 메시지 헤더 매핑할 수 있는 방법을 다양 한 서비스 작업에는 Windows Communication Foundation (WCF) 사용 하는 서비스 설명 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 에 설명 된 대로 하나의 서비스 작업을 사용 하도록 제한 되지는 [ 메시지 큐를 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) 하 고 [Windows Communication Foundation에서 메시지 큐로](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that Windows Communication Foundation (WCF) services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="dd1ce-104">이 샘플의 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 대기 중인 메시지를 받는 서비스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="dd1ce-105">서비스 계약은 `IOrderProcessor`이며, 큐에서 사용하는 데 적합한 단방향 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 <span data-ttu-id="dd1ce-106">MSMQ 메시지에는 Action 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="dd1ce-107">다양한 MSMQ 메시지를 작업 계약에 자동으로 매핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="dd1ce-108">따라서 작업 계약이 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="dd1ce-109">이러한 제한을 해결하기 위해 서비스에서는 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 인터페이스의 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="dd1ce-110"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 메서드를 사용하여 서비스는 지정된 메시지 헤더를 특정 서비스 작업에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="dd1ce-111">이 샘플에서는 메시지의 레이블 헤더를 서비스 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="dd1ce-112">작업 계약의 `Name` 매개 변수는 지정된 메시지 레이블에 대해 디스패치되어야 하는 서비스 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="dd1ce-113">예를 들어 메시지의 레이블 헤더에 "SubmitPurchaseOrder"가 포함되어 있으면 "SubmitPurchaseOrder" 서비스 작업이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 <span data-ttu-id="dd1ce-114">서비스는 다음 샘플 코드와 같이 <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> 인터페이스의 <xref:System.ServiceModel.Description.IContractBehavior> 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="dd1ce-115">이렇게 하면 사용자 지정 `OperationSelector`가 서비스 프레임워크 디스패치 런타임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 <span data-ttu-id="dd1ce-116">메시지는 OperationSelector에 도달하기 전에 디스패처의 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>를 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="dd1ce-117">기본적으로 서비스에 의해 구현된 계약에서 해당 동작을 찾을 수 없으면 메시지가 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="dd1ce-118">이러한 문제를 방지하기 위해 다음과 같이 <xref:System.ServiceModel.Description.IEndpointBehavior>를 적용하여 모든 메시지가 `MatchAllFilterBehavior`를 통과할 수 있도록 하는 `ContractFilter`라는 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 <span data-ttu-id="dd1ce-119">서비스에서 메시지를 받으면 레이블 헤더에서 제공하는 정보를 사용하여 적합한 서비스 작업이 디스패치됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="dd1ce-120">다음 샘플 코드와 같이 메시지 본문은 `PurchaseOrder` 개체로 deserialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 <span data-ttu-id="dd1ce-121">서비스는 자체 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-121">The service is self-hosted.</span></span> <span data-ttu-id="dd1ce-122">MSMQ를 사용할 때 사용되는 큐는 미리 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="dd1ce-123">수동으로 또는 코드를 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-123">This can be done manually or through code.</span></span> <span data-ttu-id="dd1ce-124">이 샘플의 서비스에는 큐가 있는지 확인하고 없을 경우 큐를 만드는 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="dd1ce-125">큐 이름은 구성 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-125">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```

 <span data-ttu-id="dd1ce-126">MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd1ce-127">큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="dd1ce-128">WCF 끝점 주소는 msmq.formatname 체계를 지정 하 고 로컬 컴퓨터에 대 한 localhost를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-128">The WCF endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="dd1ce-129">이 체계를 따르는 주소는 MSMQ 형식 이름 주소 지정 지침에 따라 형식이 올바르게 지정된 큐 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="dd1ce-130">이 샘플을 설치 해야 [메시지 큐](https://go.microsoft.com/fwlink/?LinkId=95143)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-130">This sample requires the installation of [Message Queuing](https://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="dd1ce-131">서비스를 시작하고 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="dd1ce-132">다음과 같은 출력이 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="dd1ce-133">서비스에는 다음과 같은 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dd1ce-134">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dd1ce-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dd1ce-135">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="dd1ce-136">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="dd1ce-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="dd1ce-137">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="dd1ce-138">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="dd1ce-139">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="dd1ce-140">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="dd1ce-141">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="dd1ce-142">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**, 선택한 **새로 만들기**합니다 **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="dd1ce-143">확인 합니다 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="dd1ce-144">입력 `ServiceModelSamplesTransacted` 새 대기열의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="dd1ce-145">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="dd1ce-146">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="dd1ce-147">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dd1ce-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="dd1ce-148">언어별 폴더의 \service\bin\ 폴더에서 서비스 컴퓨터로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="dd1ce-149">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="dd1ce-150">Client.exe.config 파일에서 orderQueueName을 변경하여 "." 대신 서비스 컴퓨터 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="dd1ce-151">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="dd1ce-152">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd1ce-153">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dd1ce-154">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd1ce-155">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd1ce-156">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd1ce-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="dd1ce-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd1ce-157">See Also</span></span>  
 [<span data-ttu-id="dd1ce-158">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="dd1ce-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="dd1ce-159">메시지 큐</span><span class="sxs-lookup"><span data-stu-id="dd1ce-159">Message Queuing</span></span>](https://go.microsoft.com/fwlink/?LinkId=95143)
