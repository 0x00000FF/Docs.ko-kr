---
title: '방법: WorkflowServiceHost를 사용 하 여 유휴 동작 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: dff9145954084d0f299edc1e3f2f6c0d7ea1a80e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727393"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="9e7d0-102">방법: WorkflowServiceHost를 사용 하 여 유휴 동작 구성</span><span class="sxs-lookup"><span data-stu-id="9e7d0-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="9e7d0-103">워크플로 인스턴스가 <xref:System.ServiceModel.Activities.Receive> 동작을 사용하여 메시지가 전달될 때까지 기다리는 경우와 같이 워크플로는 일부 외부 자극에 의해 다시 시작되어야 하는 책갈피를 만나면 유휴 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="9e7d0-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> 는 서비스 인스턴스가 유휴 상태가 되는 시점과 인스턴스가 지속되거나 언로드되는 시점 사이의 기간을 지정할 수 있는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="9e7d0-105">이러한 기간을 설정할 수 있는 두 가지 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="9e7d0-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> 는 워크플로 서비스 인스턴스가 유휴 상태가 되는 때와 워크플로 서비스 인스턴스가 지속되는 때 사이의 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="9e7d0-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> 는 워크플로 서비스 인스턴스가 유휴 상태가 되는 때와 워크플로 서비스 인스턴스가 언로드되는 때 사이의 시간을 지정합니다. 여기서, 언로드란 인스턴스를 인스턴스 스토어에 유지하고 메모리에서 제거하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="9e7d0-108">이 항목에서는 구성 파일에서 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> 를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="9e7d0-109">WorkflowIdleBehavior를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="9e7d0-109">To configure WorkflowIdleBehavior</span></span>  
  
1.  <span data-ttu-id="9e7d0-110">다음 예제와 같이 <`workflowIdle`> 요소를 <`serviceBehaviors`> 요소 내의 <`behavior`> 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="9e7d0-111">`timeToUnload` 특성은 워크플로 서비스 인스턴스가 유휴 상태가 되는 때와 워크플로 서비스 인스턴스가 언로드되는 때 사이의 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="9e7d0-112">`timeToPersist` 특성은 워크플로 서비스 인스턴스가 유휴 상태가 되는 때와 워크플로 서비스 인스턴스가 지속되는 때 사이의 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="9e7d0-113">`timeToUnload` 의 기본값은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="9e7d0-114">`timeToPersist` 의 기본값은 <xref:System.TimeSpan.MaxValue>입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="9e7d0-115">유휴 인스턴스를 메모리에 유지하지만 견고성을 위해 지속시키려는 경우 `timeToPersist` < `timeToUnload`입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="9e7d0-116">유휴 인스턴스가 언로드되지 않도록 하려면 `timeToUnload` 를 <xref:System.TimeSpan.MaxValue>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="9e7d0-117">에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>를 참조 하세요 [워크플로 서비스 호스트 확장성](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="9e7d0-117">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e7d0-118">위의 샘플에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-118">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="9e7d0-119">자세한 내용은 [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-119">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="9e7d0-120">코드에서 유휴 동작을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="9e7d0-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="9e7d0-121">다음 예제에서는 프로그래밍 방식으로 지속 및 언로드 전에 대기할 시간을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7d0-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9e7d0-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e7d0-122">See also</span></span>
- [<span data-ttu-id="9e7d0-123">워크플로 서비스 호스트 확장성</span><span class="sxs-lookup"><span data-stu-id="9e7d0-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="9e7d0-124">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="9e7d0-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="9e7d0-125">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="9e7d0-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
