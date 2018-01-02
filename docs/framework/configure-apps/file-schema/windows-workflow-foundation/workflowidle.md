---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2440f322ea7dbd3a6d6f9d56878273c49b26bfa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="3f05f-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="3f05f-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="3f05f-103">유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="3f05f-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3f05f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f05f-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3f05f-105">\<behaviors></span></span>  
<span data-ttu-id="3f05f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3f05f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3f05f-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3f05f-107">\<behavior></span></span>  
<span data-ttu-id="3f05f-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="3f05f-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f05f-109">구문</span><span class="sxs-lookup"><span data-stu-id="3f05f-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f05f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3f05f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3f05f-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f05f-112">특성</span><span class="sxs-lookup"><span data-stu-id="3f05f-112">Attributes</span></span>  
  
|<span data-ttu-id="3f05f-113">특성</span><span class="sxs-lookup"><span data-stu-id="3f05f-113">Attribute</span></span>|<span data-ttu-id="3f05f-114">설명</span><span class="sxs-lookup"><span data-stu-id="3f05f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f05f-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="3f05f-115">timeToPersist</span></span>|<span data-ttu-id="3f05f-116">워크플로가 유휴 상태가 되 고 유지 하는 시간 사이의 기간을 지정 하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="3f05f-117">기본값은 TimeSpan.MaxValue 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="3f05f-118">워크플로 인스턴스가 유휴 상태가 되면 기간이 경과되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="3f05f-119">이 특성은 가능한 한 오랫동안 메모리에 인스턴스를 그대로 유지 하면서 워크플로 인스턴스를 적극적으로 유지 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="3f05f-120">이 특성은 해당 값이 유효한만 보다 작은 **timeToUnload** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="3f05f-121">이보다 크면 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="3f05f-122">이 특성에 지정 된 값 되기 전에 경과 하는 경우는 **timeToUnload** 특성, 지 속성 워크플로가 언로드되기 전에 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="3f05f-123">이것은 워크플로가 유지될 때까지 언로드 작업이 지연될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="3f05f-124">지속성 계층은 일시적인 오류가 발생할 경우 재시도를 처리하고 복구할 수 없는 오류가 발생하는 경우에만 예외를 throw하는 역할을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="3f05f-125">따라서 유지 중에 throw되는 예외는 심각한 예외로 간주되며 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="3f05f-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="3f05f-126">timeToUnload</span></span>|<span data-ttu-id="3f05f-127">워크플로가 유휴 상태가 되고 언로드되는 시간 간의 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="3f05f-128">기본값은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="3f05f-129">워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="3f05f-130">이 특성은 워크플로 인스턴스가 유지 되 고 후 즉시 언로드됩니다 0으로 설정 하는 경우 워크플로가 유휴 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="3f05f-131">언로드 작업이 해제 timespan.maxvalue 효과적으로이 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="3f05f-132">즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f05f-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f05f-133">Child Elements</span></span>  
 <span data-ttu-id="3f05f-134">없음</span><span class="sxs-lookup"><span data-stu-id="3f05f-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f05f-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f05f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="3f05f-136">요소</span><span class="sxs-lookup"><span data-stu-id="3f05f-136">Element</span></span>|<span data-ttu-id="3f05f-137">설명</span><span class="sxs-lookup"><span data-stu-id="3f05f-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f05f-138">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3f05f-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3f05f-139">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f05f-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f05f-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f05f-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
