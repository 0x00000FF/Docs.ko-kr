---
title: '&lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7d9d19c4ea5ecd5dc7a7329eb3fdad657567864
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="b8811-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="b8811-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="b8811-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="b8811-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b8811-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b8811-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b8811-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b8811-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="b8811-106">\<tracking></span></span>  
<span data-ttu-id="b8811-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b8811-107">\<trackingProfile></span></span>  
<span data-ttu-id="b8811-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="b8811-108">\<workflow></span></span>  
<span data-ttu-id="b8811-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="b8811-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b8811-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="b8811-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8811-111">구문</span><span class="sxs-lookup"><span data-stu-id="b8811-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8811-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8811-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b8811-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8811-114">특성</span><span class="sxs-lookup"><span data-stu-id="b8811-114">Attributes</span></span>  
 <span data-ttu-id="b8811-115">없음</span><span class="sxs-lookup"><span data-stu-id="b8811-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8811-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8811-116">Child Elements</span></span>  
  
|<span data-ttu-id="b8811-117">요소</span><span class="sxs-lookup"><span data-stu-id="b8811-117">Element</span></span>|<span data-ttu-id="b8811-118">설명</span><span class="sxs-lookup"><span data-stu-id="b8811-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8811-119">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="b8811-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="b8811-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8811-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8811-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b8811-122">요소</span><span class="sxs-lookup"><span data-stu-id="b8811-122">Element</span></span>|<span data-ttu-id="b8811-123">설명</span><span class="sxs-lookup"><span data-stu-id="b8811-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8811-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="b8811-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="b8811-125">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8811-126">설명</span><span class="sxs-lookup"><span data-stu-id="b8811-126">Remarks</span></span>  
 <span data-ttu-id="b8811-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b8811-128">예제</span><span class="sxs-lookup"><span data-stu-id="b8811-128">Example</span></span>  
 <span data-ttu-id="b8811-129">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="b8811-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8811-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8811-130">See Also</span></span>  
 <span data-ttu-id="b8811-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b8811-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b8811-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b8811-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b8811-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b8811-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b8811-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b8811-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
