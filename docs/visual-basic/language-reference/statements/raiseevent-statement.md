---
title: RaiseEvent 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 5d8fd6adf33c992341324e07bcd2ad12986bbdf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783970"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="96453-102">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="96453-102">RaiseEvent Statement</span></span>
<span data-ttu-id="96453-103">클래스, 폼 또는 문서의 모듈 수준에서 선언한 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96453-104">구문</span><span class="sxs-lookup"><span data-stu-id="96453-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="96453-105">요소</span><span class="sxs-lookup"><span data-stu-id="96453-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="96453-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="96453-106">Required.</span></span> <span data-ttu-id="96453-107">트리거할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="96453-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-108">Optional.</span></span> <span data-ttu-id="96453-109">변수, 배열 또는 식의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="96453-110">`argumentlist` 인수를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="96453-111">인수가 없는 경우에 괄호를 생략 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96453-112">설명</span><span class="sxs-lookup"><span data-stu-id="96453-112">Remarks</span></span>  
 <span data-ttu-id="96453-113">필수 `eventname` 은 모듈 내에서 선언 된 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="96453-114">Visual Basic의 변수 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="96453-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="96453-115">이벤트가 발생 하는 모듈 내에서 선언 되지 않은, 경우 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="96453-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="96453-116">다음 코드 조각에는 이벤트 선언 및 이벤트는 이벤트가 발생 하는 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96453-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="96453-117">사용할 수 없습니다 `RaiseEvent` 모듈에서 명시적으로 선언 되지 않은 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="96453-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="96453-118">폼을 모두 상속 하는 예를 들어를 <xref:System.Windows.Forms.Control.Click> 에서 이벤트 <xref:System.Windows.Forms.Form?displayProperty=nameWithType>를 사용 하 여 높일 수 없습니다 `RaiseEvent` 파생된 폼에서.</span><span class="sxs-lookup"><span data-stu-id="96453-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="96453-119">선언 하는 경우는 `Click` 이벤트 폼 자체의 폼 모듈에 숨겨집니다 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="96453-120">양식의 여전히 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Click> 를 호출 하 여 이벤트를 <xref:System.Windows.Forms.Control.OnClick%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="96453-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="96453-121">기본적으로 Visual Basic에서 정의 된 이벤트의 이벤트 처리기는 연결이 설정 된 순서 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="96453-122">이벤트를 가질 수 있으므로 `ByRef` 매개 변수를 나중에 연결 하는 프로세스는 이전 이벤트 처리기에 의해 변경 된 매개 변수를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96453-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="96453-123">이벤트 처리기가 실행 후 이벤트를 발생 시킨 서브루틴에 컨트롤이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96453-124">비공유 이벤트가 선언 되는 클래스의 생성자 내에서 발생 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="96453-125">이러한 이벤트를 런타임 오류 발생 지는 않지만 연결 된 이벤트 처리기에서 포착 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96453-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="96453-126">사용 된 `Shared` 한정자를 생성자에서 이벤트를 발생 하는 경우 공유 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96453-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96453-127">사용자 지정 이벤트를 정의 하 여 이벤트의 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96453-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="96453-128">사용자 지정 이벤트에 대 한 합니다 `RaiseEvent` 문은 호출 이벤트의 `RaiseEvent` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="96453-129">사용자 지정 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 연결 문으로](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96453-130">예제</span><span class="sxs-lookup"><span data-stu-id="96453-130">Example</span></span>  
 <span data-ttu-id="96453-131">다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="96453-132">코드는 다양 한 이벤트 관련 메서드, 속성 및 포함 하 여 문을 보여 줍니다는 `RaiseEvent` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="96453-133">이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="96453-134">이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96453-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="96453-135">클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="96453-136">또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="96453-137">단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="96453-138">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="96453-139">`Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="96453-140">또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="96453-141">이 예제를 사용 하려면 새 Windows 응용 프로그램 프로젝트를 열고 라는 단추를 추가 `Button1` 고 이라는 입력란 `TextBox1` 이라는 기본 폼에 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="96453-142">그런 다음 폼을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기** 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96453-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="96453-143">추가 된 `WithEvents` 의 선언 섹션에 변수를 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96453-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="96453-144">예제</span><span class="sxs-lookup"><span data-stu-id="96453-144">Example</span></span>  
 <span data-ttu-id="96453-145">`Form1`에 대한 코드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="96453-146">같은 존재할 수 있는 모든 중복 프로시저 바꿉니다 `Form_Load`, 또는 `Button_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="96453-147">F5 키를 눌러 앞의 예제를 실행 하 고 레이블이 붙은 단추를 클릭 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="96453-148">첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="96453-149">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96453-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96453-150">`My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="96453-151">폼에 직접 이벤트를 처리할 수 있도록을 따르면 다중 스레딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="96453-152">자세한 내용은 [관리 되는 스레딩](../../../standard/threading/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96453-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96453-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="96453-153">See also</span></span>

- [<span data-ttu-id="96453-154">이벤트</span><span class="sxs-lookup"><span data-stu-id="96453-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="96453-155">Event 문</span><span class="sxs-lookup"><span data-stu-id="96453-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="96453-156">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="96453-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="96453-157">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="96453-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="96453-158">Handles</span><span class="sxs-lookup"><span data-stu-id="96453-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
