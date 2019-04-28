---
title: <activityStateQuery> WCF의
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704533"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="334f5-102">\<activityStateQuery > WCF의</span><span class="sxs-lookup"><span data-stu-id="334f5-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="334f5-103">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="334f5-104">예를 들어 다음 워크플로 인스턴스 내에 "전자 메일 보내기" 활동이 완료 될 때마다 추적 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="334f5-105">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="334f5-106">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="334f5-107">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="334f5-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="334f5-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="334f5-109">\<profiles> \<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="334f5-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="334f5-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="334f5-110">\<workflow></span></span>  
<span data-ttu-id="334f5-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="334f5-111">\<activityStateQueries></span></span>  
<span data-ttu-id="334f5-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="334f5-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334f5-113">구문</span><span class="sxs-lookup"><span data-stu-id="334f5-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="334f5-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="334f5-114">Attributes and elements</span></span>  

<span data-ttu-id="334f5-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="334f5-116">특성</span><span class="sxs-lookup"><span data-stu-id="334f5-116">Attributes</span></span>  
  
|<span data-ttu-id="334f5-117">특성</span><span class="sxs-lookup"><span data-stu-id="334f5-117">Attribute</span></span>|<span data-ttu-id="334f5-118">설명</span><span class="sxs-lookup"><span data-stu-id="334f5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="334f5-119">activityName</span><span class="sxs-lookup"><span data-stu-id="334f5-119">activityName</span></span>|<span data-ttu-id="334f5-120"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="334f5-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="334f5-121">Child elements</span></span>  
  
|<span data-ttu-id="334f5-122">요소</span><span class="sxs-lookup"><span data-stu-id="334f5-122">Element</span></span>|<span data-ttu-id="334f5-123">설명</span><span class="sxs-lookup"><span data-stu-id="334f5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="334f5-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="334f5-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="334f5-125">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="334f5-126">\<states></span><span class="sxs-lookup"><span data-stu-id="334f5-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="334f5-127">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="334f5-128">\<states></span><span class="sxs-lookup"><span data-stu-id="334f5-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="334f5-129">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="334f5-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="334f5-130">Parent elements</span></span>  
  
|<span data-ttu-id="334f5-131">요소</span><span class="sxs-lookup"><span data-stu-id="334f5-131">Element</span></span>|<span data-ttu-id="334f5-132">설명</span><span class="sxs-lookup"><span data-stu-id="334f5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="334f5-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="334f5-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="334f5-134">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="334f5-135">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="334f5-136">설명</span><span class="sxs-lookup"><span data-stu-id="334f5-136">Remarks</span></span>

<span data-ttu-id="334f5-137">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="334f5-138">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="334f5-139">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)를 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 고 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다. 다음 예제에서는 변수 및 인수를 추출 하는 활동 상태 쿼리를 때 활동의 `Closed` 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="334f5-140">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="334f5-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="334f5-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="334f5-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="334f5-142">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="334f5-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="334f5-143">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="334f5-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
