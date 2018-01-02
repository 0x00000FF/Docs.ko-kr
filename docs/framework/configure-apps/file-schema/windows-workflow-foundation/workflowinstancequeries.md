---
title: '&lt;workflowInstanceQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a65f6b888e210c1786395bbbb9f60050fe8e2c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="bdba3-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="bdba3-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="bdba3-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="bdba3-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bdba3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bdba3-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bdba3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bdba3-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="bdba3-106">\<tracking></span></span>  
<span data-ttu-id="bdba3-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bdba3-107">\<trackingProfile></span></span>  
<span data-ttu-id="bdba3-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="bdba3-108">\<workflow></span></span>  
<span data-ttu-id="bdba3-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="bdba3-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdba3-110">구문</span><span class="sxs-lookup"><span data-stu-id="bdba3-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdba3-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bdba3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bdba3-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdba3-113">특성</span><span class="sxs-lookup"><span data-stu-id="bdba3-113">Attributes</span></span>  
 <span data-ttu-id="bdba3-114">없음</span><span class="sxs-lookup"><span data-stu-id="bdba3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bdba3-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bdba3-115">Child Elements</span></span>  
  
|<span data-ttu-id="bdba3-116">요소</span><span class="sxs-lookup"><span data-stu-id="bdba3-116">Element</span></span>|<span data-ttu-id="bdba3-117">설명</span><span class="sxs-lookup"><span data-stu-id="bdba3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdba3-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="bdba3-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="bdba3-119">워크플로 인스턴스 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdba3-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bdba3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bdba3-121">요소</span><span class="sxs-lookup"><span data-stu-id="bdba3-121">Element</span></span>|<span data-ttu-id="bdba3-122">설명</span><span class="sxs-lookup"><span data-stu-id="bdba3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdba3-123">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="bdba3-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="bdba3-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdba3-125">설명</span><span class="sxs-lookup"><span data-stu-id="bdba3-125">Remarks</span></span>  
 <span data-ttu-id="bdba3-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="bdba3-127">예</span><span class="sxs-lookup"><span data-stu-id="bdba3-127">Example</span></span>  
 <span data-ttu-id="bdba3-128">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="bdba3-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdba3-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdba3-129">See Also</span></span>  
 <span data-ttu-id="bdba3-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bdba3-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="bdba3-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bdba3-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="bdba3-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="bdba3-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bdba3-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="bdba3-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
