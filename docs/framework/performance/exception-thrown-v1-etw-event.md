---
title: 예외가 throw된 V1 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07932a12916138dd7cbee2576e4fc747898b8063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610848"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="efee8-102">예외가 throw된 V1 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="efee8-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="efee8-103">이 이벤트는 throw된 예외에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="efee8-104">다음 표에서는 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="efee8-105">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efee8-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="efee8-106">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="efee8-106">Keyword for raising the event</span></span>|<span data-ttu-id="efee8-107">수준</span><span class="sxs-lookup"><span data-stu-id="efee8-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="efee8-108">`ExceptionKeyword`(0x8000)</span><span class="sxs-lookup"><span data-stu-id="efee8-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="efee8-109">경고(2)</span><span class="sxs-lookup"><span data-stu-id="efee8-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="efee8-110">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="efee8-111">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="efee8-111">Event</span></span>|<span data-ttu-id="efee8-112">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="efee8-112">Event ID</span></span>|<span data-ttu-id="efee8-113">발생 시기</span><span class="sxs-lookup"><span data-stu-id="efee8-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="efee8-114">80</span><span class="sxs-lookup"><span data-stu-id="efee8-114">80</span></span>|<span data-ttu-id="efee8-115">관리되는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="efee8-116">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="efee8-117">필드 이름</span><span class="sxs-lookup"><span data-stu-id="efee8-117">Field name</span></span>|<span data-ttu-id="efee8-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="efee8-118">Data type</span></span>|<span data-ttu-id="efee8-119">설명</span><span class="sxs-lookup"><span data-stu-id="efee8-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="efee8-120">예외 형식</span><span class="sxs-lookup"><span data-stu-id="efee8-120">Exception Type</span></span>|<span data-ttu-id="efee8-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="efee8-121">win:UnicodeString</span></span>|<span data-ttu-id="efee8-122">예외 형식, 예: `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="efee8-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="efee8-123">예외 메시지</span><span class="sxs-lookup"><span data-stu-id="efee8-123">Exception Message</span></span>|<span data-ttu-id="efee8-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="efee8-124">win:UnicodeString</span></span>|<span data-ttu-id="efee8-125">실제 예외 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-125">Actual exception message.</span></span>|  
|<span data-ttu-id="efee8-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="efee8-126">EIPCodeThrow</span></span>|<span data-ttu-id="efee8-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="efee8-127">win:Pointer</span></span>|<span data-ttu-id="efee8-128">예외가 발생한 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="efee8-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="efee8-129">ExceptionHR</span></span>|<span data-ttu-id="efee8-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="efee8-130">win:UInt32</span></span>|<span data-ttu-id="efee8-131">예외 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)입니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="efee8-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="efee8-132">ExceptionFlags</span></span>|<span data-ttu-id="efee8-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="efee8-133">win:UInt16</span></span>|<span data-ttu-id="efee8-134">0x01: HasInnerException (참조 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md) Visual Basic 설명서에서).</span><span class="sxs-lookup"><span data-stu-id="efee8-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="efee8-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="efee8-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="efee8-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="efee8-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="efee8-137">0x08: IsCorruptedStateException (프로세스 상태가 손상 되었음을; 참조 [손상 된 상태 예외 처리](https://go.microsoft.com/fwlink/?LinkId=179681) msdn).</span><span class="sxs-lookup"><span data-stu-id="efee8-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="efee8-138">0x10: IsCLSCompliant (에서 파생 되는 예외가 <xref:System.Exception> CLS 규격이 고, 그렇지 않으면는 CLS 규격이 아니므로).</span><span class="sxs-lookup"><span data-stu-id="efee8-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="efee8-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="efee8-139">ClrInstanceID</span></span>|<span data-ttu-id="efee8-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="efee8-140">win:UInt16</span></span>|<span data-ttu-id="efee8-141">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="efee8-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efee8-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="efee8-142">See also</span></span>
- [<span data-ttu-id="efee8-143">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="efee8-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
