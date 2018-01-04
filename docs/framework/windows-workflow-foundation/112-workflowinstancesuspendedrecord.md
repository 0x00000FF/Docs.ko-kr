---
title: 112 - WorkflowInstanceSuspendedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc825c7c-8c90-48f7-9336-9a978a8246c6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a53d670082a9e8c3c714c9c1ce519b5b9229d15a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="112---workflowinstancesuspendedrecord"></a><span data-ttu-id="c4161-102">112 - WorkflowInstanceSuspendedRecord</span><span class="sxs-lookup"><span data-stu-id="c4161-102">112 - WorkflowInstanceSuspendedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="c4161-103">속성</span><span class="sxs-lookup"><span data-stu-id="c4161-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4161-104">Id</span><span class="sxs-lookup"><span data-stu-id="c4161-104">Id</span></span>|<span data-ttu-id="c4161-105">112</span><span class="sxs-lookup"><span data-stu-id="c4161-105">112</span></span>|  
|<span data-ttu-id="c4161-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c4161-106">Keywords</span></span>|<span data-ttu-id="c4161-107">EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="c4161-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="c4161-108">수준</span><span class="sxs-lookup"><span data-stu-id="c4161-108">Level</span></span>|<span data-ttu-id="c4161-109">정보</span><span class="sxs-lookup"><span data-stu-id="c4161-109">Information</span></span>|  
|<span data-ttu-id="c4161-110">채널</span><span class="sxs-lookup"><span data-stu-id="c4161-110">Channel</span></span>|<span data-ttu-id="c4161-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="c4161-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c4161-112">설명</span><span class="sxs-lookup"><span data-stu-id="c4161-112">Description</span></span>  
 <span data-ttu-id="c4161-113">워크플로 인스턴스가 WorkflowInstanceSuspended Record를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c4161-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c4161-114">Message</span></span>  
 <span data-ttu-id="c4161-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7</span><span class="sxs-lookup"><span data-stu-id="c4161-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7</span></span>  
  
## <a name="details"></a><span data-ttu-id="c4161-116">설명</span><span class="sxs-lookup"><span data-stu-id="c4161-116">Details</span></span>  
  
|<span data-ttu-id="c4161-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c4161-117">Data Item Name</span></span>|<span data-ttu-id="c4161-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c4161-118">Data Item Type</span></span>|<span data-ttu-id="c4161-119">설명</span><span class="sxs-lookup"><span data-stu-id="c4161-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c4161-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c4161-120">InstanceId</span></span>|<span data-ttu-id="c4161-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="c4161-121">xs:GUID</span></span>|<span data-ttu-id="c4161-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="c4161-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="c4161-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="c4161-123">RecordNumber</span></span>|<span data-ttu-id="c4161-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="c4161-124">xs:long</span></span>|<span data-ttu-id="c4161-125">내보낸 레코드의 시퀀스 번호</span><span class="sxs-lookup"><span data-stu-id="c4161-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="c4161-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="c4161-126">EventTime</span></span>|<span data-ttu-id="c4161-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="c4161-127">xs:dateTime</span></span>|<span data-ttu-id="c4161-128">이벤트를 내보낸 시간(UTC)</span><span class="sxs-lookup"><span data-stu-id="c4161-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="c4161-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="c4161-129">ActivityDefinitionId</span></span>|<span data-ttu-id="c4161-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-130">xs:string</span></span>|<span data-ttu-id="c4161-131">워크플로의 루트 활동 이름</span><span class="sxs-lookup"><span data-stu-id="c4161-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="c4161-132">이유</span><span class="sxs-lookup"><span data-stu-id="c4161-132">Reason</span></span>|<span data-ttu-id="c4161-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-133">xs:string</span></span>|<span data-ttu-id="c4161-134">워크플로가 일시 중단된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-134">The reason the workflow was suspended</span></span>|  
|<span data-ttu-id="c4161-135">주석</span><span class="sxs-lookup"><span data-stu-id="c4161-135">Annotations</span></span>|<span data-ttu-id="c4161-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-136">xs:string</span></span>|<span data-ttu-id="c4161-137">이 이벤트에 추가된 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-137">The annotations that were added to this event.</span></span>  <span data-ttu-id="c4161-138">값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "annotationName" type = "> annotationValue\<항목/>\<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-138">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="c4161-139">주석을 지정 하지 않으면 문자열을 포함 하는 경우 \<항목 / >입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="c4161-140">ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="c4161-141">이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="c4161-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="c4161-142">ProfileName</span></span>|<span data-ttu-id="c4161-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-143">xs:string</span></span>|<span data-ttu-id="c4161-144">이 이벤트를 내보낸 이름 또는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="c4161-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="c4161-145">HostReference</span><span class="sxs-lookup"><span data-stu-id="c4161-145">HostReference</span></span>|<span data-ttu-id="c4161-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-146">xs:string</span></span>|<span data-ttu-id="c4161-147">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-147">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="c4161-148">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName' 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'</span><span class="sxs-lookup"><span data-stu-id="c4161-148">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="c4161-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c4161-149">AppDomain</span></span>|<span data-ttu-id="c4161-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4161-150">xs:string</span></span>|<span data-ttu-id="c4161-151">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c4161-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
