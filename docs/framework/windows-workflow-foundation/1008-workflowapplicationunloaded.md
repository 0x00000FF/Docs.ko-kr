---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925231"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="4cbdb-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="4cbdb-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="4cbdb-103">속성</span><span class="sxs-lookup"><span data-stu-id="4cbdb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cbdb-104">ID</span><span class="sxs-lookup"><span data-stu-id="4cbdb-104">ID</span></span>|<span data-ttu-id="4cbdb-105">1008</span><span class="sxs-lookup"><span data-stu-id="4cbdb-105">1008</span></span>|  
|<span data-ttu-id="4cbdb-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4cbdb-106">Keywords</span></span>|<span data-ttu-id="4cbdb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4cbdb-107">WFRuntime</span></span>|  
|<span data-ttu-id="4cbdb-108">수준</span><span class="sxs-lookup"><span data-stu-id="4cbdb-108">Level</span></span>|<span data-ttu-id="4cbdb-109">정보</span><span class="sxs-lookup"><span data-stu-id="4cbdb-109">Information</span></span>|  
|<span data-ttu-id="4cbdb-110">채널</span><span class="sxs-lookup"><span data-stu-id="4cbdb-110">Channel</span></span>|<span data-ttu-id="4cbdb-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="4cbdb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4cbdb-112">설명</span><span class="sxs-lookup"><span data-stu-id="4cbdb-112">Description</span></span>  
 <span data-ttu-id="4cbdb-113">워크플로 응용 프로그램이 언로드되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdb-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4cbdb-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4cbdb-114">Message</span></span>  
 <span data-ttu-id="4cbdb-115">WorkflowInstance Id: '%1'이(가) 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdb-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4cbdb-116">설명</span><span class="sxs-lookup"><span data-stu-id="4cbdb-116">Details</span></span>  
  
|<span data-ttu-id="4cbdb-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4cbdb-117">Data Item Name</span></span>|<span data-ttu-id="4cbdb-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4cbdb-118">Data Item Type</span></span>|<span data-ttu-id="4cbdb-119">설명</span><span class="sxs-lookup"><span data-stu-id="4cbdb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4cbdb-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4cbdb-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4cbdb-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="4cbdb-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4cbdb-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4cbdb-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4cbdb-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdb-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
