---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 018ea20342475de40a8392a9272724e37902ecb9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257722"
---
# <a name="states"></a><span data-ttu-id="6433f-101">\<states></span><span class="sxs-lookup"><span data-stu-id="6433f-101">\<states></span></span>
<span data-ttu-id="6433f-102">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="6433f-103">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6433f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6433f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6433f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6433f-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6433f-105">\<tracking></span></span>  
<span data-ttu-id="6433f-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6433f-106">\<trackingProfile></span></span>  
<span data-ttu-id="6433f-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6433f-107">\<workflow></span></span>  
<span data-ttu-id="6433f-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="6433f-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="6433f-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="6433f-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="6433f-110">\<states></span><span class="sxs-lookup"><span data-stu-id="6433f-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6433f-111">구문</span><span class="sxs-lookup"><span data-stu-id="6433f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6433f-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6433f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6433f-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6433f-114">특성</span><span class="sxs-lookup"><span data-stu-id="6433f-114">Attributes</span></span>  
 <span data-ttu-id="6433f-115">없음</span><span class="sxs-lookup"><span data-stu-id="6433f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6433f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6433f-116">Child Elements</span></span>  
  
|<span data-ttu-id="6433f-117">요소</span><span class="sxs-lookup"><span data-stu-id="6433f-117">Element</span></span>|<span data-ttu-id="6433f-118">설명</span><span class="sxs-lookup"><span data-stu-id="6433f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6433f-119">\<state></span><span class="sxs-lookup"><span data-stu-id="6433f-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="6433f-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6433f-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6433f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6433f-122">요소</span><span class="sxs-lookup"><span data-stu-id="6433f-122">Element</span></span>|<span data-ttu-id="6433f-123">설명</span><span class="sxs-lookup"><span data-stu-id="6433f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6433f-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="6433f-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="6433f-125">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6433f-126">설명</span><span class="sxs-lookup"><span data-stu-id="6433f-126">Remarks</span></span>  
 <span data-ttu-id="6433f-127">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="6433f-128">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="6433f-129">상태</span><span class="sxs-lookup"><span data-stu-id="6433f-129">State</span></span>|<span data-ttu-id="6433f-130">설명</span><span class="sxs-lookup"><span data-stu-id="6433f-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6433f-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="6433f-131">Aborted</span></span>|<span data-ttu-id="6433f-132">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="6433f-133">Completed</span><span class="sxs-lookup"><span data-stu-id="6433f-133">Completed</span></span>|<span data-ttu-id="6433f-134">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="6433f-135">삭제됨</span><span class="sxs-lookup"><span data-stu-id="6433f-135">Deleted</span></span>|<span data-ttu-id="6433f-136">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="6433f-137">Idle</span><span class="sxs-lookup"><span data-stu-id="6433f-137">Idle</span></span>|<span data-ttu-id="6433f-138">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="6433f-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="6433f-139">Persisted</span></span>|<span data-ttu-id="6433f-140">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="6433f-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="6433f-141">Resumed</span></span>|<span data-ttu-id="6433f-142">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="6433f-143">시작됨</span><span class="sxs-lookup"><span data-stu-id="6433f-143">Started</span></span>|<span data-ttu-id="6433f-144">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="6433f-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="6433f-145">UnhandledException</span></span>|<span data-ttu-id="6433f-146">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="6433f-147">Unloaded</span><span class="sxs-lookup"><span data-stu-id="6433f-147">Unloaded</span></span>|<span data-ttu-id="6433f-148">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="6433f-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="6433f-149">Canceled</span></span>|<span data-ttu-id="6433f-150">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="6433f-151">일시 중단됨</span><span class="sxs-lookup"><span data-stu-id="6433f-151">Suspended</span></span>|<span data-ttu-id="6433f-152">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="6433f-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="6433f-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="6433f-153">Terminated</span></span>|<span data-ttu-id="6433f-154">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="6433f-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="6433f-155">Unsuspended</span></span>|<span data-ttu-id="6433f-156">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6433f-157">예제</span><span class="sxs-lookup"><span data-stu-id="6433f-157">Example</span></span>  
 <span data-ttu-id="6433f-158">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="6433f-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6433f-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="6433f-159">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6433f-160">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="6433f-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6433f-161">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="6433f-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
