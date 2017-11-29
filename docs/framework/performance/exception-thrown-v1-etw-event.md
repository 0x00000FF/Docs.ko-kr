---
title: "예외가 throw된 V1 ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dcf3390821c4210ced4c43dab5a94c93802d5f9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="25791-102">예외가 throw된 V1 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="25791-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="25791-103">이 이벤트는 throw된 예외에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="25791-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="25791-104">다음 표에서는 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25791-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="25791-105">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25791-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="25791-106">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="25791-106">Keyword for raising the event</span></span>|<span data-ttu-id="25791-107">수준</span><span class="sxs-lookup"><span data-stu-id="25791-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="25791-108">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="25791-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="25791-109">경고(2)</span><span class="sxs-lookup"><span data-stu-id="25791-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="25791-110">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25791-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="25791-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="25791-111">Event</span></span>|<span data-ttu-id="25791-112">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="25791-112">Event ID</span></span>|<span data-ttu-id="25791-113">발생 시기</span><span class="sxs-lookup"><span data-stu-id="25791-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="25791-114">80</span><span class="sxs-lookup"><span data-stu-id="25791-114">80</span></span>|<span data-ttu-id="25791-115">관리되는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="25791-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="25791-116">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25791-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="25791-117">필드 이름</span><span class="sxs-lookup"><span data-stu-id="25791-117">Field name</span></span>|<span data-ttu-id="25791-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="25791-118">Data type</span></span>|<span data-ttu-id="25791-119">설명</span><span class="sxs-lookup"><span data-stu-id="25791-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="25791-120">예외 형식</span><span class="sxs-lookup"><span data-stu-id="25791-120">Exception Type</span></span>|<span data-ttu-id="25791-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="25791-121">win:UnicodeString</span></span>|<span data-ttu-id="25791-122">예외 형식, 예: `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="25791-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="25791-123">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="25791-123">Exception Message</span></span>|<span data-ttu-id="25791-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="25791-124">win:UnicodeString</span></span>|<span data-ttu-id="25791-125">실제 예외 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="25791-125">Actual exception message.</span></span>|  
|<span data-ttu-id="25791-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="25791-126">EIPCodeThrow</span></span>|<span data-ttu-id="25791-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="25791-127">win:Pointer</span></span>|<span data-ttu-id="25791-128">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25791-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="25791-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="25791-129">ExceptionHR</span></span>|<span data-ttu-id="25791-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="25791-130">win:UInt32</span></span>|<span data-ttu-id="25791-131">예외 [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679)입니다.</span><span class="sxs-lookup"><span data-stu-id="25791-131">Exception [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="25791-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="25791-132">ExceptionFlags</span></span>|<span data-ttu-id="25791-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="25791-133">win:UInt16</span></span>|<span data-ttu-id="25791-134">0x01: HasInnerException(Visual Basic 설명서에서 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="25791-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="25791-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="25791-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="25791-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="25791-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="25791-137">0x08: IsCorruptedStateException(프로세스 상태가 손상됨을 나타냄, MSDN에서 [손상된 상태 예외 처리](http://go.microsoft.com/fwlink/?LinkId=179681) 참조).</span><span class="sxs-lookup"><span data-stu-id="25791-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](http://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="25791-138">0x10: IsCLSCompliant(<xref:System.Exception>에서 파생된 예외는 CLS와 호환됨, 그러지 않으면 CLS와 호환되지 않음).</span><span class="sxs-lookup"><span data-stu-id="25791-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="25791-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="25791-139">ClrInstanceID</span></span>|<span data-ttu-id="25791-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="25791-140">win:UInt16</span></span>|<span data-ttu-id="25791-141">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="25791-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25791-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25791-142">See Also</span></span>  
 [<span data-ttu-id="25791-143">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="25791-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
