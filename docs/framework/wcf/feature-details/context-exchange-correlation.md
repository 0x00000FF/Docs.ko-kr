---
title: 컨텍스트 교환 상관 관계
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: d9de111fa08b4a398bba52bc903ea1fec8c7f298
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519734"
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="053ea-102">컨텍스트 교환 상관 관계</span><span class="sxs-lookup"><span data-stu-id="053ea-102">Context Exchange Correlation</span></span>
<span data-ttu-id="053ea-103">컨텍스트 상관 관계에 설명 된 컨텍스트 교환 메커니즘을 기반으로 합니다 [.NET Context Exchange Protocol Specification](https://go.microsoft.com/fwlink/?LinkId=166059)합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](https://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="053ea-104">컨텍스트 상관 관계는 잘 알려진 컨텍스트 헤더나 쿠키를 사용하여 메시지를 올바른 인스턴스와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="053ea-105">컨텍스트 상관 관계를 사용하려면 <xref:System.ServiceModel.BasicHttpContextBinding>에 제공된 엔드포인트에서 <xref:System.ServiceModel.WSHttpContextBinding>, <xref:System.ServiceModel.NetTcpContextBinding> 또는 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 같은 컨텍스트 기반 바인딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="053ea-106">이 항목에서는 워크플로 서비스의 메시징 작업에 컨텍스트 상관 관계를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="053ea-107">컨텍스트 상관 관계 사용</span><span class="sxs-lookup"><span data-stu-id="053ea-107">Using Context Correlation</span></span>  
 <span data-ttu-id="053ea-108">컨텍스트 상관 관계는 클라이언트가 컨텍스트 바인딩 중 하나를 사용하여 호스팅되는 워크플로 서비스를 반복하여 호출해야 하는 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="053ea-109">이 유형의 상관 관계에 의해 초기화 됩니다는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 워크플로 서비스의 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="053ea-110">컨텍스트는 회신과 함께 클라이언트로 다시 전송됩니다. 그러면 클라이언트는 이 컨텍스트를 서비스에 대한 후속 호출에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="053ea-111">워크플로 서비스에서 컨텍스트 상관 관계 구성</span><span class="sxs-lookup"><span data-stu-id="053ea-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="053ea-112">컨텍스트 상관 관계는 초기 들어오는 메시지에 회신하는 <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> 작업과 연결된 <xref:System.ServiceModel.Activities.SendReply>를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="053ea-113">다음 예제에서는 <xref:System.ServiceModel.Activities.SendReply>가 컨텍스트 상관 관계를 초기화하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  <span data-ttu-id="053ea-114">이 예제에서는 컨텍스트 상관 관계와 요청-회신 상관 관계라는 두 가지 상관 관계가 실제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="053ea-115">컨텍스트 상관 관계는 클라이언트에서의 호출이 올바른 인스턴스로 라우트되도록 하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="053ea-116">요청-회신 상관 관계는 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 작업을 통해 모델링된 양방향 작업을 구현하기 위해 이러한 두 작업에서 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="053ea-117">이 예제에서는 컨텍스트 상관 관계만 명시적으로 구성 하며 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍은 암시적으로 제공 되는 기본 요청-회신 상관 관계를 사용 하 여 <xref:System.ServiceModel.Activities.CorrelationHandle> 관리 <xref:System.ServiceModel.Activities.WorkflowServiceHost>합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="053ea-118">사용 하는 경우는 **ReceiveAndSendReply** 작업 템플릿 워크플로 디자이너, 요청-회신 상관 관계에서 명시적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> <span data-ttu-id="053ea-119">요청-회신 상관 관계와 암시적 상관 관계 핸들 관리 하는 방법에 대 한 자세한 내용은 참조 하십시오 [요청-회신](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) 하 고 [상관 관계 개요](../../../../docs/framework/wcf/feature-details/correlation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-119">For more information about request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> <span data-ttu-id="053ea-120">에 대 한 자세한 내용은 합니다 **ReceiveAndSendReply** 작업 템플릿 참조 [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-120">For more information about the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="053ea-121">워크플로 서비스의 후속 <xref:System.ServiceModel.Activities.Receive> 작업은 이전 예제에서 <xref:System.ServiceModel.Activities.CorrelationHandle>에 의해 초기화된 <xref:System.ServiceModel.Activities.SendReply>을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="053ea-122">그러면 엔드포인트가 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 <xref:System.ServiceModel.BasicHttpContextBinding> 같은 컨텍스트 기반 바인딩을 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="053ea-123">워크플로 클라이언트에서 컨텍스트 상관 관계 구성</span><span class="sxs-lookup"><span data-stu-id="053ea-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="053ea-124">클라이언트도 워크플로이면 클라이언트에서도 컨텍스트 상관 관계를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="053ea-125">클라이언트 워크플로 <xref:System.ServiceModel.Activities.ReceiveReply> 의 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 워크플로 서비스에 대 한 초기 호출 하는 쌍으로 구성 되어야 합니다는 <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 <span data-ttu-id="053ea-126">상관 관계가 초기화된 후 후속 <xref:System.ServiceModel.Activities.Send> 작업에서 <xref:System.ServiceModel.Activities.CorrelationHandle>을 사용하여 동일한 서비스 인스턴스에 대한 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="053ea-127">위에 나온 예제들에서는 컨텍스트 상관 관계가 명시적으로 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="053ea-128">클라이언트 워크플로도 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되지 않는 경우 해당 작업이 <xref:System.ServiceModel.Activities.CorrelationScope> 작업 내에 포함되어 있지 않으면 상관 관계를 명시적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="053ea-129">컨텍스트 상관 관계에 대 한 자세한 내용은 참조는 [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-129">For more information about context correlation, see the [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="053ea-130">워크플로 서비스를 호출하는 클라이언트가 워크플로가 아닌 경우 해당 클라이언트가 첫 번째 호출에서 반환되는 컨텍스트를 워크플로 서비스에 명시적으로 다시 전달한다면 워크플로 서비스를 반복하여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="053ea-131">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서비스 참조를 추가하여 생성된 프록시는 기본적으로 이 컨텍스트를 저장하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="053ea-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
