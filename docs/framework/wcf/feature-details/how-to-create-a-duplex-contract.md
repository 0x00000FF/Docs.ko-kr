---
title: '방법: 이중 계약 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: 002c94f2cb69e330e8d2796a9f93d977b10f53f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078176"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="ee5ba-102">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="ee5ba-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="ee5ba-103">이 항목에서는 이중(양방향) 계약을 사용하는 메서드를 만드는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="ee5ba-104">이중 계약을 사용하면 클라이언트와 서버가 각각 독립적으로 통신하므로 서로 호출을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="ee5ba-105">이중 계약에는 Windows Communication Foundation (WCF) 서비스를 사용할 수 있는 세 가지 메시지 패턴 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="ee5ba-106">다른 두 가지 메시지 패턴은 단방향과 요청-회신입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="ee5ba-107">이중 계약은 클라이언트와 서버 간 두 개의 단방향 계약으로 구성되며, 메서드 호출을 상호 관련시키지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="ee5ba-108">서비스가 클라이언트에 세부 정보를 쿼리하거나 클라이언트에서 이벤트를 명시적으로 발생시킬 때 이러한 종류의 계약을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="ee5ba-109">이중 계약에 대 한 클라이언트 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 이중 계약을 사용 하 여 서비스에 액세스할](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="ee5ba-110">작업 예제를 참조 하세요. 합니다 [이중](../../../../docs/framework/wcf/samples/duplex.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-110">For a working sample, see the [Duplex](../../../../docs/framework/wcf/samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="ee5ba-111">이중 계약을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ee5ba-111">To create a duplex contract</span></span>  
  
1.  <span data-ttu-id="ee5ba-112">이중 계약의 서버 측을 구성하는 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2.  <span data-ttu-id="ee5ba-113">인터페이스에 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  <span data-ttu-id="ee5ba-114">인터페이스에 메서드 서명을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-114">Declare the method signatures in the interface.</span></span>  
  
4.  <span data-ttu-id="ee5ba-115">공용 계약의 일부여야 하는 각 메서드 서명에 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5.  <span data-ttu-id="ee5ba-116">서비스가 클라이언트에서 호출할 수 있는 작업 집합을 정의하는 콜백 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  <span data-ttu-id="ee5ba-117">콜백 인터페이스에 메서드 서명을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-117">Declare the method signatures in the callback interface.</span></span>  
  
7.  <span data-ttu-id="ee5ba-118">공용 계약의 일부여야 하는 각 메서드 서명에 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8.  <span data-ttu-id="ee5ba-119">기본 인터페이스의 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> 속성을 콜백 인터페이스의 형식으로 설정하여 이중 계약에 두 개의 인터페이스를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="ee5ba-120">클라이언트에서 메서드를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="ee5ba-120">To call methods on the client</span></span>  
  
1.  <span data-ttu-id="ee5ba-121">기본 계약의 서비스 구현에서 콜백 인터페이스에 대한 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2.  <span data-ttu-id="ee5ba-122">변수를 <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> 클래스의 <xref:System.ServiceModel.OperationContext> 메서드에서 반환한 개체 참조로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  <span data-ttu-id="ee5ba-123">콜백 인터페이스에서 정의한 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee5ba-124">예제</span><span class="sxs-lookup"><span data-stu-id="ee5ba-124">Example</span></span>  
 <span data-ttu-id="ee5ba-125">다음 코드 예제에서는 이중 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="ee5ba-126">서비스의 계약에는 앞뒤로 이동하기 위한 서비스 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="ee5ba-127">클라이언트의 계약에는 해당 위치를 보고하는 서비스 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   <span data-ttu-id="ee5ba-128"><xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.OperationContractAttribute> 특성을 적용하면 WSDL(웹 서비스 기술 언어)에서 서비스 계약 정의를 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
-   <span data-ttu-id="ee5ba-129">사용 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSDL 문서 및 (선택 사항) 코드 및 클라이언트에 대 한 구성을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
-   <span data-ttu-id="ee5ba-130">이중 서비스를 노출하는 엔드포인트를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="ee5ba-131">서비스가 이중 메시지를 받으면 들어오는 해당 메시지에서 ReplyTo를 확인하여 회신을 보낼 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="ee5ba-132">채널이 보안되지 않으면 신뢰할 수 없는 클라이언트가 대상 컴퓨터의 ReplyTo를 사용하여 악의적인 메시지를 보낼 수 있으므로 해당 대상 컴퓨터의 서비스 거부가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="ee5ba-133">정규 요청-회신 메시지를 사용하는 경우에는 ReplyTo가 무시되고 원래 메시지가 들어온 채널에서 응답이 보내지므로 이러한 문제가 생기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ba-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5ba-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee5ba-134">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="ee5ba-135">방법: 이중 계약을 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="ee5ba-135">How to: Access Services with a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="ee5ba-136">이중</span><span class="sxs-lookup"><span data-stu-id="ee5ba-136">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)
- [<span data-ttu-id="ee5ba-137">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="ee5ba-137">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="ee5ba-138">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="ee5ba-138">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="ee5ba-139">세션</span><span class="sxs-lookup"><span data-stu-id="ee5ba-139">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)
