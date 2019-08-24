---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781643"
---
# <a name="222---operationfailed"></a><span data-ttu-id="0ed95-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="0ed95-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="0ed95-103">속성</span><span class="sxs-lookup"><span data-stu-id="0ed95-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ed95-104">ID</span><span class="sxs-lookup"><span data-stu-id="0ed95-104">ID</span></span>|<span data-ttu-id="0ed95-105">222</span><span class="sxs-lookup"><span data-stu-id="0ed95-105">222</span></span>|  
|<span data-ttu-id="0ed95-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0ed95-106">Keywords</span></span>|<span data-ttu-id="0ed95-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0ed95-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0ed95-108">수준</span><span class="sxs-lookup"><span data-stu-id="0ed95-108">Level</span></span>|<span data-ttu-id="0ed95-109">경고</span><span class="sxs-lookup"><span data-stu-id="0ed95-109">Warning</span></span>|  
|<span data-ttu-id="0ed95-110">채널</span><span class="sxs-lookup"><span data-stu-id="0ed95-110">Channel</span></span>|<span data-ttu-id="0ed95-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="0ed95-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ed95-112">설명</span><span class="sxs-lookup"><span data-stu-id="0ed95-112">Description</span></span>  
 <span data-ttu-id="0ed95-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 예외가 발생하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="0ed95-114">`FaultException`에서 파생되는 예외가 발생할 경우에는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ed95-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0ed95-115">Message</span></span>  
 <span data-ttu-id="0ed95-116">OperationInvoker의 호출을 받은 '%1' 메서드에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="0ed95-117">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ed95-118">설명</span><span class="sxs-lookup"><span data-stu-id="0ed95-118">Details</span></span>  
  
|<span data-ttu-id="0ed95-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0ed95-119">Data Item Name</span></span>|<span data-ttu-id="0ed95-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0ed95-120">Data Item Type</span></span>|<span data-ttu-id="0ed95-121">설명</span><span class="sxs-lookup"><span data-stu-id="0ed95-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ed95-122">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="0ed95-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="0ed95-123">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="0ed95-124">기간</span><span class="sxs-lookup"><span data-stu-id="0ed95-124">Duration</span></span>|`xs:long`|<span data-ttu-id="0ed95-125">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="0ed95-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="0ed95-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="0ed95-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0ed95-128">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="0ed95-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0ed95-129">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0ed95-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0ed95-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ed95-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0ed95-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0ed95-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
