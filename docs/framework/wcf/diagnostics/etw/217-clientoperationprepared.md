---
title: 217 - ClientOperationPrepared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5062d2c2146dae8b22165cfbea0c6a78241d17b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="10d22-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="10d22-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="10d22-103">속성</span><span class="sxs-lookup"><span data-stu-id="10d22-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10d22-104">ID</span><span class="sxs-lookup"><span data-stu-id="10d22-104">ID</span></span>|<span data-ttu-id="10d22-105">217</span><span class="sxs-lookup"><span data-stu-id="10d22-105">217</span></span>|  
|<span data-ttu-id="10d22-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="10d22-106">Keywords</span></span>|<span data-ttu-id="10d22-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="10d22-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="10d22-108">수준</span><span class="sxs-lookup"><span data-stu-id="10d22-108">Level</span></span>|<span data-ttu-id="10d22-109">정보</span><span class="sxs-lookup"><span data-stu-id="10d22-109">Information</span></span>|  
|<span data-ttu-id="10d22-110">채널</span><span class="sxs-lookup"><span data-stu-id="10d22-110">Channel</span></span>|<span data-ttu-id="10d22-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="10d22-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10d22-112">설명</span><span class="sxs-lookup"><span data-stu-id="10d22-112">Description</span></span>  
 <span data-ttu-id="10d22-113">이 이벤트는 서비스에 작업을 보내기 바로 전에 클라이언트에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10d22-114">메시지</span><span class="sxs-lookup"><span data-stu-id="10d22-114">Message</span></span>  
 <span data-ttu-id="10d22-115">클라이언트가 '%2' 계약과 연결된 '%1' 작업을 실행하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="10d22-116">메시지를 '%3'(으)로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10d22-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="10d22-117">Details</span></span>  
  
|<span data-ttu-id="10d22-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="10d22-118">Data Item Name</span></span>|<span data-ttu-id="10d22-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="10d22-119">Data Item Type</span></span>|<span data-ttu-id="10d22-120">설명</span><span class="sxs-lookup"><span data-stu-id="10d22-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10d22-121">작업</span><span class="sxs-lookup"><span data-stu-id="10d22-121">Action</span></span>|`xs:string`|<span data-ttu-id="10d22-122">보내는 메시지의 SOAP 동작 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="10d22-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="10d22-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="10d22-124">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-124">The name of the contract.</span></span> <span data-ttu-id="10d22-125">예를 들면 ICalculator와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="10d22-126">대상</span><span class="sxs-lookup"><span data-stu-id="10d22-126">Destination</span></span>|`xs:string`|<span data-ttu-id="10d22-127">메시지를 받는 서비스 끝점의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="10d22-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="10d22-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="10d22-129">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="10d22-130">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="10d22-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="10d22-131">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="10d22-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="10d22-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10d22-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="10d22-133">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10d22-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
