---
title: 스택 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7cba2bd1dd5b83e29c7a6c192a1a7e5e2d33ecc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949151"
---
# <a name="stack-etw-event"></a><span data-ttu-id="8bd58-102">스택 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="8bd58-102">Stack ETW Event</span></span>
<span data-ttu-id="8bd58-103">스택 이벤트는 이벤트가 발생한 후 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="8bd58-104">런타임 공급자가 사용하도록 설정된 경우에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="8bd58-105">다른 런타임 이벤트가 발생할 때마다 이벤트가 발생하기 때문에 빈도가 매우 높은 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="8bd58-106">이러한 이유로 이 이벤트를 사용할 때는 주의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="8bd58-107">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="8bd58-108">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bd58-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="8bd58-109">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="8bd58-109">Keyword for raising the event</span></span>|<span data-ttu-id="8bd58-110">수준</span><span class="sxs-lookup"><span data-stu-id="8bd58-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="8bd58-111">`StackKeyword`(0x40000000)</span><span class="sxs-lookup"><span data-stu-id="8bd58-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="8bd58-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="8bd58-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="8bd58-113">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="8bd58-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="8bd58-114">Event</span></span>|<span data-ttu-id="8bd58-115">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="8bd58-115">Event ID</span></span>|<span data-ttu-id="8bd58-116">발생 시기</span><span class="sxs-lookup"><span data-stu-id="8bd58-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="8bd58-117">82</span><span class="sxs-lookup"><span data-stu-id="8bd58-117">82</span></span>|<span data-ttu-id="8bd58-118">다른 이벤트와 더불어 이벤트 다음에 스택 추적을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="8bd58-119">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="8bd58-120">필드 이름</span><span class="sxs-lookup"><span data-stu-id="8bd58-120">Field name</span></span>|<span data-ttu-id="8bd58-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8bd58-121">Data Type</span></span>|<span data-ttu-id="8bd58-122">설명</span><span class="sxs-lookup"><span data-stu-id="8bd58-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="8bd58-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8bd58-123">ClrInstanceID</span></span>|<span data-ttu-id="8bd58-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="8bd58-124">win:Uint16</span></span>|<span data-ttu-id="8bd58-125">고유한 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="8bd58-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="8bd58-126">Reserved1</span></span>|<span data-ttu-id="8bd58-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="8bd58-127">win:UInt8</span></span>|<span data-ttu-id="8bd58-128">예약됨.</span><span class="sxs-lookup"><span data-stu-id="8bd58-128">Reserved.</span></span>|  
|<span data-ttu-id="8bd58-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="8bd58-129">Reserved2</span></span>|<span data-ttu-id="8bd58-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="8bd58-130">win:UInt8</span></span>|<span data-ttu-id="8bd58-131">예약됨.</span><span class="sxs-lookup"><span data-stu-id="8bd58-131">Reserved.</span></span>|  
|<span data-ttu-id="8bd58-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="8bd58-132">FrameCount</span></span>|<span data-ttu-id="8bd58-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8bd58-133">win:UInt32</span></span>|<span data-ttu-id="8bd58-134">스택 추적의 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="8bd58-135">스택</span><span class="sxs-lookup"><span data-stu-id="8bd58-135">Stack</span></span>|<span data-ttu-id="8bd58-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="8bd58-136">win:Pointer</span></span>|<span data-ttu-id="8bd58-137">명령 포인터의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd58-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bd58-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="8bd58-138">See also</span></span>

- [<span data-ttu-id="8bd58-139">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="8bd58-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
