---
title: '&#39;사용자 지정&#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에 올바르지 않습니다.'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c909973ef1c00cb01179b0e5527dfecd6f41e577
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574783"
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="ac7e1-102">&#39;사용자 지정&#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="ac7e1-103">사용자 지정이 아닌 경우와 달리를 `Custom Event` 선언에 필요는 `As` 절과 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="ac7e1-104">비-사용자 지정 이벤트 수 사용 하 여 정의 `As` 절 및 명시적 대리자 형식 또는 매개 변수를 사용 하 여 목록 바로 이벤트 이름 다음에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="ac7e1-105">**오류 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="ac7e1-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac7e1-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ac7e1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ac7e1-107">사용자 지정 이벤트와 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="ac7e1-108">예를 들어 경우는 `Custom Event` 정의한 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 해당 대리자는 다음 것을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="ac7e1-109">대체 매개 변수 목록을 사용 하 여 사용자 지정 이벤트는 `As` 절 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="ac7e1-110">예를 사용 하 여 계속 `Custom Event` 선언을 다음과 같이 다시 작성할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="ac7e1-111">예제</span><span class="sxs-lookup"><span data-stu-id="ac7e1-111">Example</span></span>  
 <span data-ttu-id="ac7e1-112">이 예제에서는 선언 된 `Custom Event` 필요한 지정 `As` 대리자 형식으로는 절.</span><span class="sxs-lookup"><span data-stu-id="ac7e1-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ac7e1-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac7e1-113">See also</span></span>
- [<span data-ttu-id="ac7e1-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="ac7e1-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="ac7e1-115">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="ac7e1-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ac7e1-116">이벤트</span><span class="sxs-lookup"><span data-stu-id="ac7e1-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
