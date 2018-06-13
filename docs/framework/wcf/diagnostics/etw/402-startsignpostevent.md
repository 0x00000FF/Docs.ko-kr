---
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: 6dfb3b187f58de2c9573c2d2f6d579e3557c3de8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33466602"
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="cfd08-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="cfd08-102">402 - StartSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="cfd08-103">속성</span><span class="sxs-lookup"><span data-stu-id="cfd08-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfd08-104">ID</span><span class="sxs-lookup"><span data-stu-id="cfd08-104">ID</span></span>|<span data-ttu-id="cfd08-105">402</span><span class="sxs-lookup"><span data-stu-id="cfd08-105">402</span></span>|  
|<span data-ttu-id="cfd08-106">키워드</span><span class="sxs-lookup"><span data-stu-id="cfd08-106">Keywords</span></span>|<span data-ttu-id="cfd08-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="cfd08-107">Troubleshooting</span></span>|  
|<span data-ttu-id="cfd08-108">수준</span><span class="sxs-lookup"><span data-stu-id="cfd08-108">Level</span></span>|<span data-ttu-id="cfd08-109">정보</span><span class="sxs-lookup"><span data-stu-id="cfd08-109">Information</span></span>|  
|<span data-ttu-id="cfd08-110">채널</span><span class="sxs-lookup"><span data-stu-id="cfd08-110">Channel</span></span>|<span data-ttu-id="cfd08-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="cfd08-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfd08-112">설명</span><span class="sxs-lookup"><span data-stu-id="cfd08-112">Description</span></span>  
 <span data-ttu-id="cfd08-113">이 이벤트는 종단 간 동작의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd08-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="cfd08-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd08-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfd08-115">메시지</span><span class="sxs-lookup"><span data-stu-id="cfd08-115">Message</span></span>  
 <span data-ttu-id="cfd08-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="cfd08-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfd08-117">설명</span><span class="sxs-lookup"><span data-stu-id="cfd08-117">Details</span></span>  
  
|<span data-ttu-id="cfd08-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="cfd08-118">Data Item Name</span></span>|<span data-ttu-id="cfd08-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="cfd08-119">Data Item Type</span></span>|<span data-ttu-id="cfd08-120">설명</span><span class="sxs-lookup"><span data-stu-id="cfd08-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfd08-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="cfd08-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="cfd08-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfd08-122">The name of the activity.</span></span>|  
|<span data-ttu-id="cfd08-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cfd08-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cfd08-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cfd08-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
