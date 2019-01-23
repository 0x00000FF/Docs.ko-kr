---
title: RemoveHandler 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 27cdd2753507c6fc4d5c5041607e2ccb425b81b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560622"
---
# <a name="removehandler-statement"></a><span data-ttu-id="fbff8-102">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="fbff8-102">RemoveHandler Statement</span></span>
<span data-ttu-id="fbff8-103">이벤트와 이벤트 처리기 간의 연결을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbff8-104">구문</span><span class="sxs-lookup"><span data-stu-id="fbff8-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="fbff8-105">요소</span><span class="sxs-lookup"><span data-stu-id="fbff8-105">Parts</span></span>  
  
|<span data-ttu-id="fbff8-106">용어</span><span class="sxs-lookup"><span data-stu-id="fbff8-106">Term</span></span>|<span data-ttu-id="fbff8-107">정의</span><span class="sxs-lookup"><span data-stu-id="fbff8-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="fbff8-108">처리 중인 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="fbff8-109">현재 이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbff8-110">설명</span><span class="sxs-lookup"><span data-stu-id="fbff8-110">Remarks</span></span>  
 <span data-ttu-id="fbff8-111">합니다 `AddHandler` 및 `RemoveHandler` 문을 시작 하 고 언제 든 지 프로그램 실행 중 특정 이벤트에 대 한 이벤트 처리를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbff8-112">사용자 지정 이벤트에 대 한 합니다 `RemoveHandler` 문은 호출 이벤트의 `RemoveHandler` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="fbff8-113">사용자 지정 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 연결 문으로](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbff8-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbff8-114">예제</span><span class="sxs-lookup"><span data-stu-id="fbff8-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fbff8-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fbff8-115">See also</span></span>
- [<span data-ttu-id="fbff8-116">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="fbff8-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="fbff8-117">Handles</span><span class="sxs-lookup"><span data-stu-id="fbff8-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="fbff8-118">Event 문</span><span class="sxs-lookup"><span data-stu-id="fbff8-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="fbff8-119">이벤트</span><span class="sxs-lookup"><span data-stu-id="fbff8-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
