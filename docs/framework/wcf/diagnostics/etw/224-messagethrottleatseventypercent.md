---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e7d35407fe22dc913f7122163006035717d60d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="28efd-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="28efd-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="28efd-103">속성</span><span class="sxs-lookup"><span data-stu-id="28efd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28efd-104">ID</span><span class="sxs-lookup"><span data-stu-id="28efd-104">ID</span></span>|<span data-ttu-id="28efd-105">224</span><span class="sxs-lookup"><span data-stu-id="28efd-105">224</span></span>|  
|<span data-ttu-id="28efd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="28efd-106">Keywords</span></span>|<span data-ttu-id="28efd-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="28efd-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="28efd-108">수준</span><span class="sxs-lookup"><span data-stu-id="28efd-108">Level</span></span>|<span data-ttu-id="28efd-109">경고</span><span class="sxs-lookup"><span data-stu-id="28efd-109">Warning</span></span>|  
|<span data-ttu-id="28efd-110">채널</span><span class="sxs-lookup"><span data-stu-id="28efd-110">Channel</span></span>|<span data-ttu-id="28efd-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="28efd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28efd-112">설명</span><span class="sxs-lookup"><span data-stu-id="28efd-112">Description</span></span>  
 <span data-ttu-id="28efd-113">기본 서비스 스로틀 중 하나가 초과되면 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="28efd-114">작업 스파이크가 느려지고 스로틀의 현재 값이 현재 한계의 70%이면 이 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="28efd-115">이 이벤트는 작업이 느려지므로 한 번만 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="28efd-116">예를 들어 현재 값이 70% 표시 지점을 넘나들면(예: 70,69,70,71,70,69) 처음으로 70%가 될 때만 이 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="28efd-117">이 이벤트가 내보내진 후에 현재 값이 스로틀 한계를 다시 초과하면 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28efd-118">메시지</span><span class="sxs-lookup"><span data-stu-id="28efd-118">Message</span></span>  
 <span data-ttu-id="28efd-119">'%2'의 스로틀 제한 '%1'이(가) 70퍼센트입니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28efd-120">설명</span><span class="sxs-lookup"><span data-stu-id="28efd-120">Details</span></span>  
  
|<span data-ttu-id="28efd-121">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="28efd-121">Data Item Name</span></span>|<span data-ttu-id="28efd-122">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="28efd-122">Data Item Type</span></span>|<span data-ttu-id="28efd-123">설명</span><span class="sxs-lookup"><span data-stu-id="28efd-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28efd-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="28efd-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="28efd-125">초과한 스로틀의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="28efd-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` 또는 `MaxConcurrentSessions` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="28efd-127">Limit</span><span class="sxs-lookup"><span data-stu-id="28efd-127">Limit</span></span>|`xs:long`|<span data-ttu-id="28efd-128">현재 구성된 스로틀 한계입니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="28efd-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="28efd-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="28efd-130">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="28efd-131">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="28efd-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="28efd-132">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="28efd-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="28efd-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="28efd-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="28efd-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28efd-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
