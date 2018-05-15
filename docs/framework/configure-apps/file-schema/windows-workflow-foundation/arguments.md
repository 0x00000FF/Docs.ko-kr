---
title: '&lt;인수&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: ae2fd4a05cc8ca93cd74ccceb08a7a077b504f0c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltargumentsgt"></a><span data-ttu-id="8ebea-102">&lt;인수&gt;</span><span class="sxs-lookup"><span data-stu-id="8ebea-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="8ebea-103">활동 상태 쿼리와 연결되는 인수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="8ebea-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8ebea-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8ebea-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8ebea-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8ebea-106">\<tracking></span></span>  
<span data-ttu-id="8ebea-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8ebea-107">\<trackingProfile></span></span>  
<span data-ttu-id="8ebea-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8ebea-108">\<workflow></span></span>  
<span data-ttu-id="8ebea-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8ebea-109">\<activityStateQueries></span></span>  
<span data-ttu-id="8ebea-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8ebea-110">\<activityStateQuery></span></span>  
<span data-ttu-id="8ebea-111">\<인수 ></span><span class="sxs-lookup"><span data-stu-id="8ebea-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebea-112">구문</span><span class="sxs-lookup"><span data-stu-id="8ebea-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ebea-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ebea-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8ebea-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ebea-115">특성</span><span class="sxs-lookup"><span data-stu-id="8ebea-115">Attributes</span></span>  
 <span data-ttu-id="8ebea-116">없음</span><span class="sxs-lookup"><span data-stu-id="8ebea-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ebea-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ebea-117">Child Elements</span></span>  
  
|<span data-ttu-id="8ebea-118">요소</span><span class="sxs-lookup"><span data-stu-id="8ebea-118">Element</span></span>|<span data-ttu-id="8ebea-119">설명</span><span class="sxs-lookup"><span data-stu-id="8ebea-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ebea-120">\<인수 ></span><span class="sxs-lookup"><span data-stu-id="8ebea-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="8ebea-121">활동 상태 쿼리와 연결되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ebea-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ebea-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8ebea-123">요소</span><span class="sxs-lookup"><span data-stu-id="8ebea-123">Element</span></span>|<span data-ttu-id="8ebea-124">설명</span><span class="sxs-lookup"><span data-stu-id="8ebea-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ebea-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8ebea-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="8ebea-126">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8ebea-127">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ebea-128">설명</span><span class="sxs-lookup"><span data-stu-id="8ebea-128">Remarks</span></span>  
 <span data-ttu-id="8ebea-129">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8ebea-130">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8ebea-131">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 및 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 임의의 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다. 다음 예에서는 변수 및 인수를 추출 하는 활동 상태 쿼리 때 활동의 `Closed` 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8ebea-132">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebea-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ebea-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ebea-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="8ebea-134">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="8ebea-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8ebea-135">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="8ebea-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
