---
title: '방법: WCF 엔드포인트와 대기 중인 메시지 교환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 09b21c9483b4f2716409b560dbbb478fe5a6badd
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972217"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="b0576-102">방법: WCF 엔드포인트와 대기 중인 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="b0576-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="b0576-103">큐는 통신할 때 서비스를 사용할 수 없는 경우에도 클라이언트와 WCF (Windows Communication Foundation) 서비스 간에 신뢰할 수 있는 메시징을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="b0576-104">다음 절차에서는 WCF 서비스를 구현할 때 대기 중인 표준 바인딩을 사용 하 여 클라이언트와 서비스 간의 지속적인 통신을 보장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="b0576-105">이 섹션에서는 wcf 클라이언트와 <xref:System.ServiceModel.NetMsmqBinding> wcf 서비스 간의 대기 중인 통신에를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="b0576-106">WCF 서비스에서 큐를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b0576-106">To use queuing in a WCF service</span></span>  
  
1. <span data-ttu-id="b0576-107"><xref:System.ServiceModel.ServiceContractAttribute>로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="b0576-108"><xref:System.ServiceModel.OperationContractAttribute>가 있는 서비스 계약의 일부인 인터페이스에서 작업을 표시하고, 메서드에 대한 응답이 반환되지 않으므로 해당 작업을 단방향으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="b0576-109">다음 코드에서는 예제 서비스 계약 및 작업 정의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. <span data-ttu-id="b0576-110">서비스 계약에서 사용자 정의 형식을 전달하는 경우 해당 형식의 데이터 계약을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="b0576-111">다음 코드에서는 `PurchaseOrder` 및 `PurchaseOrderLineItem`의 두 데이터 계약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="b0576-112">이 두 형식은 서비스로 전송되는 데이터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="b0576-113">또한 이 데이터 계약을 정의하는 클래스에서 여러 메서드도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="b0576-114">이러한 메서드는 데이터 계약의 일부로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="b0576-115"><xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 사용하여 선언된 해당 멤버만이 데이터 계약의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-115">Only those members that are declared with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. <span data-ttu-id="b0576-116">클래스에서 인터페이스에 정의된 서비스 계약의 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="b0576-117"><xref:System.ServiceModel.OperationBehaviorAttribute>는 `SubmitPurchaseOrder` 메서드에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="b0576-118">따라서 이 작업은 트랜잭션 내에서 호출해야 하며 메서드가 완료되면 트랜잭션도 자동으로 완료되도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4. <span data-ttu-id="b0576-119"><xref:System.Messaging>을 사용하여 트랜잭션 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="b0576-120">MSMQ(Microsoft Message Queuing) MMC(Microsoft Management Console)를 대신 사용하여 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="b0576-121">이 경우에는 트랜잭션 큐를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. <span data-ttu-id="b0576-122">서비스 주소를 지정하고 표준 <xref:System.ServiceModel.Description.ServiceEndpoint> 바인딩을 사용하는 구성에 <xref:System.ServiceModel.NetMsmqBinding>를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="b0576-123">WCF 구성을 사용 하는 방법에 대 한 자세한 내용은 [wcf 서비스 구성](../configuring-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0576-123">For more information about using WCF configuration, see [Configuring WCF services](../configuring-services.md).</span></span>  

6. <span data-ttu-id="b0576-124">큐에서 메시지를 읽어 이를 처리하는 `OrderProcessing`를 사용하여 <xref:System.ServiceModel.ServiceHost> 서비스의 호스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="b0576-125">서비스를 사용할 수 있도록 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-125">Open the service host to make the service available.</span></span> <span data-ttu-id="b0576-126">사용자에게 아무 키나 누르면 서비스를 종료할 수 있음을 알리는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="b0576-127">`ReadLine`을 호출하여 키를 누를 때까지 기다린 후에 서비스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="b0576-128">대기 중인 서비스의 클라이언트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b0576-128">To create a client for the queued service</span></span>  
  
1. <span data-ttu-id="b0576-129">다음 예제에서는 호스팅 응용 프로그램을 실행 하 고 Svcutil.exe 도구를 사용 하 여 WCF 클라이언트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```console
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. <span data-ttu-id="b0576-130">다음 예제와 같이 주소를 지정하고 표준 <xref:System.ServiceModel.Description.ServiceEndpoint> 바인딩을 사용하는 구성에서 <xref:System.ServiceModel.NetMsmqBinding>를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  

3. <span data-ttu-id="b0576-131">트랜잭션 큐에 쓸 트랜잭션 범위를 만들고, `SubmitPurchaseOrder` 작업을 호출 하 고, 다음 예제와 같이 WCF 클라이언트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="b0576-132">예제</span><span class="sxs-lookup"><span data-stu-id="b0576-132">Example</span></span>  
 <span data-ttu-id="b0576-133">다음 예제에서는 이 예제에 포함된 서비스 코드, 호스팅 애플리케이션, App.config 파일 및 클라이언트 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0576-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  

 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  

## <a name="see-also"></a><span data-ttu-id="b0576-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0576-134">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- [<span data-ttu-id="b0576-135">트랜잭션된 MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0576-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)
- [<span data-ttu-id="b0576-136">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="b0576-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [<span data-ttu-id="b0576-137">방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="b0576-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [<span data-ttu-id="b0576-138">Windows Communication Foundation에서 메시지 큐로</span><span class="sxs-lookup"><span data-stu-id="b0576-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="b0576-139">메시지 큐(MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="b0576-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="b0576-140">메시지 큐에서 indows Communication Foundation으로</span><span class="sxs-lookup"><span data-stu-id="b0576-140">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="b0576-141">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="b0576-141">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
