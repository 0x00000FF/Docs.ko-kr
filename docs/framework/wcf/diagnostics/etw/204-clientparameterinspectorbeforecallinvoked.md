---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f896055d958947e54ee77bb812b8d424e6f4f94f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="6d501-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="6d501-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="6d501-103">속성</span><span class="sxs-lookup"><span data-stu-id="6d501-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d501-104">ID</span><span class="sxs-lookup"><span data-stu-id="6d501-104">ID</span></span>|<span data-ttu-id="6d501-105">204</span><span class="sxs-lookup"><span data-stu-id="6d501-105">204</span></span>|  
|<span data-ttu-id="6d501-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="6d501-106">Keywords</span></span>|<span data-ttu-id="6d501-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6d501-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6d501-108">수준</span><span class="sxs-lookup"><span data-stu-id="6d501-108">Level</span></span>|<span data-ttu-id="6d501-109">정보</span><span class="sxs-lookup"><span data-stu-id="6d501-109">Information</span></span>|  
|<span data-ttu-id="6d501-110">채널</span><span class="sxs-lookup"><span data-stu-id="6d501-110">Channel</span></span>|<span data-ttu-id="6d501-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="6d501-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d501-112">설명</span><span class="sxs-lookup"><span data-stu-id="6d501-112">Description</span></span>  
 <span data-ttu-id="6d501-113">이 이벤트는 서비스 모델이 클라이언트 매개 변수 검사자에 대해 `BeforeCall` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6d501-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d501-114">메시지</span><span class="sxs-lookup"><span data-stu-id="6d501-114">Message</span></span>  
 <span data-ttu-id="6d501-115">디스패처가 '%1' 형식의 ClientParameterInspector에 대해 'BeforeCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d501-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d501-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6d501-116">Details</span></span>  
  
|<span data-ttu-id="6d501-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="6d501-117">Data Item Name</span></span>|<span data-ttu-id="6d501-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="6d501-118">Data Item Type</span></span>|<span data-ttu-id="6d501-119">설명</span><span class="sxs-lookup"><span data-stu-id="6d501-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d501-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="6d501-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="6d501-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="6d501-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="6d501-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6d501-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6d501-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6d501-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6d501-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="6d501-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6d501-125">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6d501-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6d501-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d501-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6d501-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d501-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
