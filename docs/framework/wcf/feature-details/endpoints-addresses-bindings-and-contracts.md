---
title: '엔드포인트: 주소, 바인딩 및 계약'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207528"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="73561-102">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="73561-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="73561-103">Windows Communication Foundation (WCF) 서비스와 모든 통신을 통해 발생 합니다 *끝점* 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="73561-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="73561-104">끝점 클라이언트는 WCF 서비스에서 제공 하는 기능에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="73561-105">각 엔드포인트는 다음 네 가지 속성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73561-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="73561-106">엔드포인트를 찾을 위치를 나타내는 주소</span><span class="sxs-lookup"><span data-stu-id="73561-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="73561-107">클라이언트가 엔드포인트와 통신할 수 있는 방법을 지정하는 바인딩</span><span class="sxs-lookup"><span data-stu-id="73561-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="73561-108">사용 가능한 작업을 식별하는 계약</span><span class="sxs-lookup"><span data-stu-id="73561-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="73561-109">엔드포인트의 로컬 구현 세부 정보를 지정하는 동작 집합</span><span class="sxs-lookup"><span data-stu-id="73561-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="73561-110">이 항목에서는이 끝점 구조에 설명 하 고 WCF 개체 모델에서 나타나는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="73561-111">엔드포인트의 구조</span><span class="sxs-lookup"><span data-stu-id="73561-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="73561-112">각 엔드포인트는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73561-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="73561-113">주소: 주소에서 고유 하 게 끝점을 식별 하 고 가능성을 알려 줍니다 위치한 서비스의 소비자입니다.</span><span class="sxs-lookup"><span data-stu-id="73561-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="73561-114">WCF 개체 모델에서 표시 됩니다는 <xref:System.ServiceModel.EndpointAddress> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="73561-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="73561-115"><xref:System.ServiceModel.EndpointAddress> 클래스에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="73561-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="73561-116">서비스의 주소를 나타내는 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="73561-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="73561-117">서비스의 보안 ID 및 선택적 메시지 헤더의 컬렉션을 나타내는 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="73561-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="73561-118">선택적 메시지 헤더는 엔드포인트 확인 및 엔드포인트와의 상호 작용을 위해 자세한 추가 주소 지정 정보를 제공하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="73561-119">자세한 내용은 [끝점 주소 지정](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="73561-120">바인딩: 바인딩은 엔드포인트와 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="73561-121">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="73561-121">This includes:</span></span>  
  
    -   <span data-ttu-id="73561-122">사용할 전송 프로토콜(예: TCP 또는 HTTP)</span><span class="sxs-lookup"><span data-stu-id="73561-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="73561-123">메시지에 사용할 인코딩(예: 텍스트 또는 이진)</span><span class="sxs-lookup"><span data-stu-id="73561-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="73561-124">필요한 보안 요구 사항(예: SSL 또는 SOAP 메시지 보안)</span><span class="sxs-lookup"><span data-stu-id="73561-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="73561-125">자세한 내용은 [WCF 바인딩 개요](../../../../docs/framework/wcf/bindings-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="73561-126">바인딩을 WCF 개체 모델 추상 기본 클래스에 의해 표현 됩니다 <xref:System.ServiceModel.Channels.Binding>합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="73561-127">대부분의 시나리오의 경우 사용자는 시스템 제공 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73561-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="73561-128">자세한 내용은 [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="73561-129">계약: 계약에서는 끝점이 클라이언트에 노출 하는 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="73561-130">계약에서는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="73561-131">클라이언트가 호출할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="73561-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="73561-132">메시지 형식</span><span class="sxs-lookup"><span data-stu-id="73561-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="73561-133">작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73561-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="73561-134">클라이언트가 예상할 수 있는 처리 또는 응답 메시지 형식</span><span class="sxs-lookup"><span data-stu-id="73561-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="73561-135">계약을 정의 하는 방법에 대 한 자세한 내용은 참조 하세요. [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="73561-136">동작: 서비스 끝점의 로컬 동작을 사용자 지정 끝점 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73561-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="73561-137">끝점 동작을 WCFruntime 빌드 프로세스에 참여 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="73561-138">엔드포인트 동작의 예는 <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> 속성이며, 이 속성을 사용하여 SOAP 또는 WSDL(웹 서비스 기술 언어) 주소 이외의 다른 수신 대기 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73561-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="73561-139">자세한 내용은 [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="73561-140">엔드포인트 정의</span><span class="sxs-lookup"><span data-stu-id="73561-140">Defining Endpoints</span></span>  
 <span data-ttu-id="73561-141">구성을 통해 코드를 명령적으로 또는 선언적으로 사용하여 서비스의 엔드포인트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73561-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="73561-142">자세한 내용은 [방법: 구성에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) 고 [방법: 코드에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73561-143">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="73561-143">In This Section</span></span>  
 <span data-ttu-id="73561-144">이 단원에서는 바인딩, 엔드포인트 및 주소의 용도에 대해 설명하고 바인딩 및 엔드포인트를 구성하는 방법과 `ClientVia` 동작 및 `ListenUri` 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73561-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="73561-145">주소</span><span class="sxs-lookup"><span data-stu-id="73561-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="73561-146">WCF의 끝점 주소를 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="73561-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="73561-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="73561-148">바인딩을 사용하여 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="73561-149">계약</span><span class="sxs-lookup"><span data-stu-id="73561-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="73561-150">계약이 서비스 메서드를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="73561-151">방법: 구성에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="73561-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="73561-152">구성에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="73561-153">방법: 코드에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="73561-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="73561-154">코드에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="73561-155">방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="73561-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="73561-156">사용 하 여 서비스를 호스트 하지 않고 서비스 구현과 구성에서 오류를 검색 하는 방법에 설명 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73561-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73561-157">참고자료</span><span class="sxs-lookup"><span data-stu-id="73561-157">See also</span></span>

- [<span data-ttu-id="73561-158">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="73561-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="73561-159">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="73561-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
