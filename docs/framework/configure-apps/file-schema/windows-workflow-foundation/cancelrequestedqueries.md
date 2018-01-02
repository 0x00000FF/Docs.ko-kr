---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 774012a0a64342bbd21832213a6c41fe41fdaef5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="0a1ef-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="0a1ef-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="0a1ef-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0a1ef-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0a1ef-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0a1ef-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0a1ef-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0a1ef-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-107">\<tracking></span></span>  
<span data-ttu-id="0a1ef-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-108">\<trackingProfile></span></span>  
<span data-ttu-id="0a1ef-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-109">\<workflow></span></span>  
<span data-ttu-id="0a1ef-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a1ef-111">구문</span><span class="sxs-lookup"><span data-stu-id="0a1ef-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a1ef-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0a1ef-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0a1ef-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a1ef-114">특성</span><span class="sxs-lookup"><span data-stu-id="0a1ef-114">Attributes</span></span>  
 <span data-ttu-id="0a1ef-115">없음</span><span class="sxs-lookup"><span data-stu-id="0a1ef-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a1ef-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a1ef-116">Child Elements</span></span>  
  
|<span data-ttu-id="0a1ef-117">요소</span><span class="sxs-lookup"><span data-stu-id="0a1ef-117">Element</span></span>|<span data-ttu-id="0a1ef-118">설명</span><span class="sxs-lookup"><span data-stu-id="0a1ef-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a1ef-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="0a1ef-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a1ef-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a1ef-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0a1ef-122">요소</span><span class="sxs-lookup"><span data-stu-id="0a1ef-122">Element</span></span>|<span data-ttu-id="0a1ef-123">설명</span><span class="sxs-lookup"><span data-stu-id="0a1ef-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a1ef-124">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="0a1ef-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0a1ef-125">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0a1ef-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a1ef-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a1ef-126">See Also</span></span>  
 [<span data-ttu-id="0a1ef-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="0a1ef-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0a1ef-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="0a1ef-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
