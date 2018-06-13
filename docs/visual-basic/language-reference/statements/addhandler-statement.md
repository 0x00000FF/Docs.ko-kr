---
title: AddHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603654"
---
# <a name="addhandler-statement"></a><span data-ttu-id="759f9-102">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="759f9-102">AddHandler Statement</span></span>
<span data-ttu-id="759f9-103">이벤트 처리기에서 런타임에 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="759f9-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="759f9-105">요소</span><span class="sxs-lookup"><span data-stu-id="759f9-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="759f9-106">처리할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="759f9-107">이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="759f9-108">설명</span><span class="sxs-lookup"><span data-stu-id="759f9-108">Remarks</span></span>  
 <span data-ttu-id="759f9-109">`AddHandler` 및 `RemoveHandler` 문을 사용 하면 시작 하 고 프로그램 실행 중 언제 든 지 이벤트 처리를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="759f9-110">시그니처는 `eventhandler` 이벤트의 서명이 일치 해야 `event`합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="759f9-111">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="759f9-112">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="759f9-113">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="759f9-114">자세한 내용은 참조 [처리](../../../visual-basic/language-reference/statements/handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="759f9-115">사용자 지정 이벤트에는 `AddHandler` 문은 이벤트의 호출 `AddHandler` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="759f9-116">사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="759f9-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="759f9-117">예제</span><span class="sxs-lookup"><span data-stu-id="759f9-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="759f9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="759f9-118">See Also</span></span>  
 [<span data-ttu-id="759f9-119">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="759f9-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="759f9-120">Handles</span><span class="sxs-lookup"><span data-stu-id="759f9-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="759f9-121">Event 문</span><span class="sxs-lookup"><span data-stu-id="759f9-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="759f9-122">이벤트</span><span class="sxs-lookup"><span data-stu-id="759f9-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
