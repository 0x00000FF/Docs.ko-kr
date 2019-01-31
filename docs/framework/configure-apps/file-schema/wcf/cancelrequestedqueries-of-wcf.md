---
title: <cancelRequestedQueries> WCF의
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: a9364fc53c7eb62a240206f6c81bd434b25c3f40
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289473"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="9cf0c-102">\<cancelRequestedQueries > WCF의</span><span class="sxs-lookup"><span data-stu-id="9cf0c-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="9cf0c-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9cf0c-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9cf0c-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf0c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="9cf0c-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9cf0c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9cf0c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9cf0c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9cf0c-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9cf0c-107">\<tracking></span></span>  
<span data-ttu-id="9cf0c-108">\<profiles> \<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9cf0c-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="9cf0c-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9cf0c-109">\<workflow></span></span>  
<span data-ttu-id="9cf0c-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="9cf0c-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf0c-111">구문</span><span class="sxs-lookup"><span data-stu-id="9cf0c-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf0c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9cf0c-112">Attributes and elements</span></span>  

<span data-ttu-id="9cf0c-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf0c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf0c-114">특성</span><span class="sxs-lookup"><span data-stu-id="9cf0c-114">Attributes</span></span>

<span data-ttu-id="9cf0c-115">없음</span><span class="sxs-lookup"><span data-stu-id="9cf0c-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9cf0c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9cf0c-116">Child elements</span></span>
  
|<span data-ttu-id="9cf0c-117">요소</span><span class="sxs-lookup"><span data-stu-id="9cf0c-117">Element</span></span>|<span data-ttu-id="9cf0c-118">설명</span><span class="sxs-lookup"><span data-stu-id="9cf0c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf0c-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="9cf0c-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="9cf0c-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="9cf0c-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf0c-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9cf0c-121">Parent elements</span></span>  
  
|<span data-ttu-id="9cf0c-122">요소</span><span class="sxs-lookup"><span data-stu-id="9cf0c-122">Element</span></span>|<span data-ttu-id="9cf0c-123">설명</span><span class="sxs-lookup"><span data-stu-id="9cf0c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf0c-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9cf0c-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9cf0c-125"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9cf0c-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cf0c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="9cf0c-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="9cf0c-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9cf0c-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9cf0c-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9cf0c-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
