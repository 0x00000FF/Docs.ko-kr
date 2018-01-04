---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="f5d4b-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="f5d4b-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="f5d4b-103">속성</span><span class="sxs-lookup"><span data-stu-id="f5d4b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5d4b-104">ID</span><span class="sxs-lookup"><span data-stu-id="f5d4b-104">ID</span></span>|<span data-ttu-id="f5d4b-105">1008</span><span class="sxs-lookup"><span data-stu-id="f5d4b-105">1008</span></span>|  
|<span data-ttu-id="f5d4b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f5d4b-106">Keywords</span></span>|<span data-ttu-id="f5d4b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f5d4b-107">WFRuntime</span></span>|  
|<span data-ttu-id="f5d4b-108">수준</span><span class="sxs-lookup"><span data-stu-id="f5d4b-108">Level</span></span>|<span data-ttu-id="f5d4b-109">정보</span><span class="sxs-lookup"><span data-stu-id="f5d4b-109">Information</span></span>|  
|<span data-ttu-id="f5d4b-110">채널</span><span class="sxs-lookup"><span data-stu-id="f5d4b-110">Channel</span></span>|<span data-ttu-id="f5d4b-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f5d4b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5d4b-112">설명</span><span class="sxs-lookup"><span data-stu-id="f5d4b-112">Description</span></span>  
 <span data-ttu-id="f5d4b-113">워크플로 응용 프로그램이 언로드되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5d4b-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5d4b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f5d4b-114">Message</span></span>  
 <span data-ttu-id="f5d4b-115">WorkflowInstance Id: '%1'이(가) 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5d4b-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5d4b-116">설명</span><span class="sxs-lookup"><span data-stu-id="f5d4b-116">Details</span></span>  
  
|<span data-ttu-id="f5d4b-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f5d4b-117">Data Item Name</span></span>|<span data-ttu-id="f5d4b-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f5d4b-118">Data Item Type</span></span>|<span data-ttu-id="f5d4b-119">설명</span><span class="sxs-lookup"><span data-stu-id="f5d4b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5d4b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5d4b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f5d4b-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="f5d4b-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f5d4b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5d4b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f5d4b-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5d4b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
