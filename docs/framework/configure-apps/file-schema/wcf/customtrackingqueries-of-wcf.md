---
title: "WCF의 &lt;customTrackingQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a64a155f435fb61c19a50f1b047c7dd28b603716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="e517e-102">WCF의 &lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="e517e-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="e517e-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e517e-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e517e-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e517e-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e517e-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e517e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="e517e-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e517e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e517e-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="e517e-107">\<tracking></span></span>  
<span data-ttu-id="e517e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e517e-108">\<trackingProfile></span></span>  
<span data-ttu-id="e517e-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="e517e-109">\<workflow></span></span>  
<span data-ttu-id="e517e-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="e517e-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e517e-111">구문</span><span class="sxs-lookup"><span data-stu-id="e517e-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e517e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e517e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e517e-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e517e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e517e-114">특성</span><span class="sxs-lookup"><span data-stu-id="e517e-114">Attributes</span></span>  
 <span data-ttu-id="e517e-115">없음</span><span class="sxs-lookup"><span data-stu-id="e517e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e517e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e517e-116">Child Elements</span></span>  
  
|<span data-ttu-id="e517e-117">요소</span><span class="sxs-lookup"><span data-stu-id="e517e-117">Element</span></span>|<span data-ttu-id="e517e-118">설명</span><span class="sxs-lookup"><span data-stu-id="e517e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e517e-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e517e-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="e517e-120">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="e517e-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e517e-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e517e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e517e-122">요소</span><span class="sxs-lookup"><span data-stu-id="e517e-122">Element</span></span>|<span data-ttu-id="e517e-123">설명</span><span class="sxs-lookup"><span data-stu-id="e517e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e517e-124">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="e517e-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e517e-125">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e517e-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e517e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e517e-126">See Also</span></span>  
 <span data-ttu-id="e517e-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e517e-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e517e-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e517e-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="e517e-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="e517e-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e517e-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="e517e-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
