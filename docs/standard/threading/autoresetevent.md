---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1785ce223f0dcd4da7ea6ef9fa3a3e897a39dca
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143520"
---
# <a name="autoresetevent"></a><span data-ttu-id="3cb62-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="3cb62-102">AutoResetEvent</span></span>
<span data-ttu-id="3cb62-103"><xref:System.Threading.AutoResetEvent> 클래스는 단일 대기 스레드를 해제한 후 신호를 받을 때 자동으로 다시 설정되는 로컬 대기 핸들 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cb62-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="3cb62-104">이 클래스는 기본 클래스인 <xref:System.Threading.EventWaitHandle>의 특수한 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cb62-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="3cb62-105">자동 재설정 이벤트의 사용 및 기능은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cb62-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="3cb62-106">단일 대기 스레드가 해제된 후 <xref:System.Threading.AutoResetEvent> 개체가 시스템의 신호를 받지 않음으로 자동으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cb62-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="3cb62-107">대기 스레드가 없으면 이벤트 개체의 상태는 신호를 받은 것으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cb62-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="3cb62-108"><xref:System.Threading.AutoResetEvent>는 `bManualReset` 인수에 대해 `false`를 지정하는 Win32 `CreateEvent` 호출에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb62-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="3cb62-109"><xref:System.Threading.AutoResetEvent>를 사용하는 예제는 <xref:System.Threading.Monitor>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cb62-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb62-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cb62-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="3cb62-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="3cb62-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="3cb62-112">스레딩</span><span class="sxs-lookup"><span data-stu-id="3cb62-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="3cb62-113">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="3cb62-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="3cb62-114">대기 핸들</span><span class="sxs-lookup"><span data-stu-id="3cb62-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
