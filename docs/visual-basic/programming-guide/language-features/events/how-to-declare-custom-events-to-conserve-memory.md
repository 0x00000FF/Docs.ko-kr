---
title: '방법: (Visual Basic) 메모리를 절약 하는 사용자 지정 이벤트 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3bd58a09d016d818c4cc88c1d2527e81a95411e6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967128"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="fc30d-102">방법: (Visual Basic) 메모리를 절약 하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="fc30d-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="fc30d-103">이 응용 프로그램의 메모리 사용량을 낮게 유지 하는 중요 한 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="fc30d-104">사용자 지정 이벤트를 처리 하는 이벤트에 대해서만 메모리를 사용 하도록 응용 프로그램을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="fc30d-105">기본적으로 컴파일러는 클래스에서 이벤트를 선언 이벤트 정보를 저장 하는 필드에 대 한 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="fc30d-106">클래스를 사용 하지 않는 이벤트 수 있으면 메모리를 불필요 하 게 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="fc30d-107">Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 메모리 사용량을 신중 하 게 관리 사용자 지정 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc30d-108">예제</span><span class="sxs-lookup"><span data-stu-id="fc30d-108">Example</span></span>  
 <span data-ttu-id="fc30d-109">이 예제에서는 클래스의 인스턴스 하나를 사용 합니다 <xref:System.ComponentModel.EventHandlerList> 에 저장 된 클래스는 `Events` 사용에서 이벤트에 대 한 정보를 저장할 필드.</span><span class="sxs-lookup"><span data-stu-id="fc30d-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="fc30d-110"><xref:System.ComponentModel.EventHandlerList> 클래스는 대리자를 포함 하도록 디자인 된 최적화 된 목록 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="fc30d-111">클래스 사용의 모든 이벤트는 `Events` 각 이벤트를 처리 하는 방법을 추적 하는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc30d-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="fc30d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc30d-112">See also</span></span>
- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="fc30d-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="fc30d-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="fc30d-114">방법: 차단을 방지 하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="fc30d-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
