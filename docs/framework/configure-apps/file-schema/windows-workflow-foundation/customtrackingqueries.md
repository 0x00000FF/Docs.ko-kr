---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 757bbe500ec3edccef465b7ff23b2c974e4a5011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598843"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="6c5f7-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6c5f7-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="6c5f7-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c5f7-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6c5f7-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5f7-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6c5f7-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6c5f7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6c5f7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c5f7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6c5f7-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6c5f7-107">\<tracking></span></span>  
<span data-ttu-id="6c5f7-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6c5f7-108">\<trackingProfile></span></span>  
<span data-ttu-id="6c5f7-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6c5f7-109">\<workflow></span></span>  
<span data-ttu-id="6c5f7-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6c5f7-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c5f7-111">구문</span><span class="sxs-lookup"><span data-stu-id="6c5f7-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c5f7-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6c5f7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c5f7-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5f7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c5f7-114">특성</span><span class="sxs-lookup"><span data-stu-id="6c5f7-114">Attributes</span></span>  
 <span data-ttu-id="6c5f7-115">없음</span><span class="sxs-lookup"><span data-stu-id="6c5f7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c5f7-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6c5f7-116">Child Elements</span></span>  
  
|<span data-ttu-id="6c5f7-117">요소</span><span class="sxs-lookup"><span data-stu-id="6c5f7-117">Element</span></span>|<span data-ttu-id="6c5f7-118">설명</span><span class="sxs-lookup"><span data-stu-id="6c5f7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c5f7-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6c5f7-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="6c5f7-120">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5f7-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c5f7-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6c5f7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6c5f7-122">요소</span><span class="sxs-lookup"><span data-stu-id="6c5f7-122">Element</span></span>|<span data-ttu-id="6c5f7-123">설명</span><span class="sxs-lookup"><span data-stu-id="6c5f7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c5f7-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6c5f7-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6c5f7-125">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소를 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5f7-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c5f7-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c5f7-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c5f7-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="6c5f7-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c5f7-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="6c5f7-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
