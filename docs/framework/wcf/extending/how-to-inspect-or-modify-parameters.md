---
title: "방법: 매개 변수 검사 또는 수정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c974e37856fff60cd90ec435b1501393654253c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="3f159-102">방법: 매개 변수 검사 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3f159-102">How to: Inspect or Modify Parameters</span></span>
<span data-ttu-id="3f159-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 개체 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> 인터페이스를 구현한 다음 클라이언트 또는 서비스 런타임에 삽입하여 단일 작업의 들어오는 메시지나 나가는 메시지를 검사 또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-103">You can inspect or modify the incoming or outgoing messages for a single operation on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client object or a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="3f159-104">일반적으로 작업 동작을 사용하여 단일 작업에 매개 변수 검사자를 추가하지만, 다른 동작을 사용하여 더 넓은 범위의 런타임에 쉬운 액세스를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="3f159-105">자세한 내용은 참조 [클라이언트 확장](../../../../docs/framework/wcf/extending/extending-clients.md) 및 [디스패처 확장](../../../../docs/framework/wcf/extending/extending-dispatchers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-105">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md) and [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="3f159-106">매개 변수 검사 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3f159-106">Inspecting or Modifying Parameters</span></span>  
  
1.  <span data-ttu-id="3f159-107"><xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="3f159-108">필요한 범위에 따라 <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>를 구현하여 매개 변수 검사자를 <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3.  <span data-ttu-id="3f159-109"><xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 메서드를 호출하기 전에 동작을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3f159-110">자세한 내용은 참조 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f159-111">예제</span><span class="sxs-lookup"><span data-stu-id="3f159-111">Example</span></span>  
 <span data-ttu-id="3f159-112">다음 코드 예제는 아래 순서대로 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f159-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="3f159-113">매개 변수 검사자 구현.</span><span class="sxs-lookup"><span data-stu-id="3f159-113">A parameter inspector implementation.</span></span>  
  
-   <span data-ttu-id="3f159-114"><xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> 및 <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>를 사용하여 매개 변수 검사자를 삽입하는 동작 구현.</span><span class="sxs-lookup"><span data-stu-id="3f159-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="3f159-115">클라이언트 응용 프로그램에서 끝점 동작을 로드하고 실행하여 클라이언트에 매개 변수 검사자를 삽입하는 구성 파일.</span><span class="sxs-lookup"><span data-stu-id="3f159-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3f159-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f159-116">See Also</span></span>  
 [<span data-ttu-id="3f159-117">구성 하 고 런타임 동작을 확장</span><span class="sxs-lookup"><span data-stu-id="3f159-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
