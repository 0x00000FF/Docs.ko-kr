---
title: 302 - UserDefinedWarningOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1913f4b75a9adf63513abe5799d908b6ea1d8182
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="d3ad5-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="d3ad5-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="d3ad5-103">속성</span><span class="sxs-lookup"><span data-stu-id="d3ad5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3ad5-104">ID</span><span class="sxs-lookup"><span data-stu-id="d3ad5-104">ID</span></span>|<span data-ttu-id="d3ad5-105">302</span><span class="sxs-lookup"><span data-stu-id="d3ad5-105">302</span></span>|  
|<span data-ttu-id="d3ad5-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="d3ad5-106">Keywords</span></span>|<span data-ttu-id="d3ad5-107">문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="d3ad5-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="d3ad5-108">수준</span><span class="sxs-lookup"><span data-stu-id="d3ad5-108">Level</span></span>|<span data-ttu-id="d3ad5-109">경고</span><span class="sxs-lookup"><span data-stu-id="d3ad5-109">Warning</span></span>|  
|<span data-ttu-id="d3ad5-110">채널</span><span class="sxs-lookup"><span data-stu-id="d3ad5-110">Channel</span></span>|<span data-ttu-id="d3ad5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d3ad5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d3ad5-112">설명</span><span class="sxs-lookup"><span data-stu-id="d3ad5-112">Description</span></span>  
 <span data-ttu-id="d3ad5-113">이 이벤트는 사용자 코드에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-113">This event is emitted from user code.</span></span> <span data-ttu-id="d3ad5-114">개발자는 자신의 서비스에서 사용자 정의 경고 이벤트가 발생할 때 이 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="d3ad5-115">이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="d3ad5-116">이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d3ad5-117">메시지</span><span class="sxs-lookup"><span data-stu-id="d3ad5-117">Message</span></span>  
 <span data-ttu-id="d3ad5-118">이름:'%1', 참조:'%2', 페이로드:%3</span><span class="sxs-lookup"><span data-stu-id="d3ad5-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="d3ad5-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d3ad5-119">Details</span></span>  
  
|<span data-ttu-id="d3ad5-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d3ad5-120">Data Item Name</span></span>|<span data-ttu-id="d3ad5-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d3ad5-121">Data Item Type</span></span>|<span data-ttu-id="d3ad5-122">설명</span><span class="sxs-lookup"><span data-stu-id="d3ad5-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d3ad5-123">이름</span><span class="sxs-lookup"><span data-stu-id="d3ad5-123">Name</span></span>|`xs:string`|<span data-ttu-id="d3ad5-124">이벤트의 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="d3ad5-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="d3ad5-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="d3ad5-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d3ad5-127">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d3ad5-128">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d3ad5-129">Payload</span><span class="sxs-lookup"><span data-stu-id="d3ad5-129">Payload</span></span>|`xs:string`|<span data-ttu-id="d3ad5-130">이벤트의 사용자 정의 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-130">The user-defined payload of the event.</span></span>|
