---
title: 이벤트 처리 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 12267e0a70419298bc581421c4f3a220088d205f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956305"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="a44da-102">연습: 이벤트 처리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a44da-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="a44da-103">이벤트를 사용 하는 방법을 보여 주는 두 항목 중 두 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="a44da-104">첫 번째 항목인 [연습: 이벤트](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)선언 및 발생에서는 이벤트를 선언 하 고 발생 시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="a44da-105">이 단원에서는 해당 연습의 폼과 클래스를 사용 하 여 이벤트를 처리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="a44da-106">`Widget` 클래스 예제에서는 기존의 이벤트 처리 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="a44da-107">Visual Basic는 이벤트를 사용 하는 다른 기술을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="a44da-108">연습으로이 예제를 수정 하 여 `AddHandler` 및 `Handles` 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="a44da-109">Widget 클래스의 PercentDone 이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-109">To handle the PercentDone event of the Widget class</span></span>  
  
1. <span data-ttu-id="a44da-110">에 `Form1`다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     <span data-ttu-id="a44da-111">키워드는 변수 `mWidget` 를 사용 하 여 개체의 이벤트를 처리 하도록 지정 합니다. `WithEvents`</span><span class="sxs-lookup"><span data-stu-id="a44da-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="a44da-112">개체를 만들 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="a44da-113">변수는 클래스 수준 이어야 `Form1` 하므로 `WithEvents` 에서 선언 됩니다.`mWidget`</span><span class="sxs-lookup"><span data-stu-id="a44da-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="a44da-114">이는 위치를 지정 하는 클래스의 형식에 관계 없이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="a44da-115">변수 `mblnCancel` 는 `LongTask` 메서드를 취소 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="a44da-116">이벤트를 처리 하는 코드 작성</span><span class="sxs-lookup"><span data-stu-id="a44da-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="a44da-117">를 사용 하 여 `WithEvents`변수를 선언 하는 즉시 변수 이름이 클래스 **코드 편집기**의 왼쪽 드롭다운 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="a44da-118">를 선택 `mWidget`하면 클래스의이벤트가오른쪽드롭다운목록에표시됩니다.`Widget`</span><span class="sxs-lookup"><span data-stu-id="a44da-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="a44da-119">이벤트를 선택 하면 접두사 `mWidget` 와 밑줄을 사용 하 여 해당 이벤트 프로시저가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="a44da-120">`WithEvents` 변수와 연결 된 모든 이벤트 프로시저에는 변수 이름이 접두사로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="a44da-121">이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-121">To handle an event</span></span>  
  
1. <span data-ttu-id="a44da-122">`mWidget` **코드 편집기**의 왼쪽 드롭다운 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="a44da-123">오른쪽 드롭다운 `PercentDone` 목록에서 이벤트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="a44da-124">**코드 편집기** 가 이벤트 프로시저 `mWidget_PercentDone` 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a44da-125">**코드 편집기** 는 새 이벤트 처리기를 삽입 하는 데 유용 하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="a44da-126">이 연습에서는 이벤트 처리기를 코드에 직접 복사 하는 것이 더 직접적입니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3. <span data-ttu-id="a44da-127">다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     <span data-ttu-id="a44da-128">이벤트가 발생할 때마다 이벤트 프로시저는 `Label` 컨트롤에 완료율을 표시 합니다. `PercentDone`</span><span class="sxs-lookup"><span data-stu-id="a44da-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="a44da-129">메서드를 사용 하면 레이블을 다시 그릴 수 있으며 사용자에 게 취소 단추를 클릭할 수 있는 기회가 제공 됩니다. `DoEvents`</span><span class="sxs-lookup"><span data-stu-id="a44da-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="a44da-130">`Button2_Click` 이벤트 처리기에 대 한 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 <span data-ttu-id="a44da-131">을 실행 `LongTask`하는 동안 사용자가 취소 단추를 클릭 하면 이벤트 처리가 발생 하는 것이 `DoEvents` 문에 의해 즉시 실행 됩니다. `Button2_Click`</span><span class="sxs-lookup"><span data-stu-id="a44da-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="a44da-132">클래스 수준 변수 `mblnCancel` 는 `True`로 `True`설정 되 고, 이벤트는 `mWidget_PercentDone` 이를 테스트 하 고 `ByRef Cancel` 인수를로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="a44da-133">WithEvents 변수를 개체에 연결</span><span class="sxs-lookup"><span data-stu-id="a44da-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="a44da-134">`Form1`이제를 설정 하 여 `Widget` 개체의 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="a44da-135">모든 `Widget` 위치를 찾는 것은입니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="a44da-136">디자인 타임에 변수 `WithEvents` 를 선언 하면 개체가 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="a44da-137">변수 `WithEvents` 는 다른 개체 변수와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="a44da-138">개체를 만들고 `WithEvents` 변수를 사용 하 여 개체에 대 한 참조를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="a44da-139">개체를 만들고이 개체에 대 한 참조를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-139">To create an object and assign a reference to it</span></span>  
  
1. <span data-ttu-id="a44da-140">**코드 편집기**의 왼쪽 드롭다운 목록에서 **(Form1 이벤트)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="a44da-141">오른쪽 드롭다운 `Load` 목록에서 이벤트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="a44da-142">**코드 편집기** 가 이벤트 프로시저 `Form1_Load` 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3. <span data-ttu-id="a44da-143">`Form1_Load` 이벤트 프로시저에 대 한 다음 코드를 추가 하 여 `Widget`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 <span data-ttu-id="a44da-144">이 코드가 실행 되 면 Visual Basic `Widget` 개체를 만들고 해당 이벤트를와 `mWidget`연결 된 이벤트 프로시저에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="a44da-145">이 시점부터가 `Widget` `PercentDone` 이벤트를 `mWidget_PercentDone` 발생 시킬 때마다 이벤트 프로시저가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="a44da-146">LongTask 메서드를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-146">To call the LongTask method</span></span>  
  
- <span data-ttu-id="a44da-147">다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 <span data-ttu-id="a44da-148">메서드를 호출 하기 전에 완료율을 표시 하는 레이블이 초기화 되어야 하 고 메서드를 취소 하기 위한 클래스 수준 `Boolean` 플래그가로 `False`설정 되어야 합니다. `LongTask`</span><span class="sxs-lookup"><span data-stu-id="a44da-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="a44da-149">`LongTask`는 작업 기간 12.2 초를 사용 하 여 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="a44da-150">이벤트 `PercentDone` 는 1 초 마다 한 번씩 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="a44da-151">이벤트가 발생할 `mWidget_PercentDone` 때마다 이벤트 프로시저가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="a44da-152">이 `LongTask` `LongTask` `mblnCancel` 완료되`True`면가 정상적으로 종료 되었는지 여부를 확인 하거나가로 설정 되어 있기 때문에 중지 된경우를테스트합니다.`mblnCancel`</span><span class="sxs-lookup"><span data-stu-id="a44da-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="a44da-153">완료율은 이전 경우에만 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="a44da-154">프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-154">To run the program</span></span>  
  
1. <span data-ttu-id="a44da-155">F5 키를 눌러 프로젝트를 실행 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-155">Press F5 to put the project in run mode.</span></span>  
  
2. <span data-ttu-id="a44da-156">**작업 시작** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-156">Click the **Start Task** button.</span></span> <span data-ttu-id="a44da-157">`PercentDone` 이벤트가 발생할 때마다 레이블이 완료 된 작업의 백분율을 사용 하 여 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3. <span data-ttu-id="a44da-158">작업을 중지 하려면 **취소** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="a44da-159">클릭 하면 **취소** 단추의 모양이 즉시 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="a44da-160">이 `Click` 이벤트는 `My.Application.DoEvents` 문에서 이벤트를 처리할 수 있을 때까지 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a44da-161">`My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="a44da-162">예를 들어이 연습에서는 **취소** 단추를 두 번 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="a44da-163">폼에서 이벤트를 직접 처리할 수 있도록 하려면 다중 스레딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="a44da-164">자세한 내용은 [관리 되는 스레딩](../../../../standard/threading/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a44da-164">For more information, see [Managed Threading](../../../../standard/threading/index.md).</span></span>
  
 <span data-ttu-id="a44da-165">F11 키를 사용 하 여 프로그램을 실행 하 고 한 번에 한 줄씩 코드를 단계별로 실행 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="a44da-166">실행 `LongTask`방법을 명확 하 게 확인 한 다음 `PercentDone` 이벤트가 발생 될 때마다 잠시 다시 `Form1` 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="a44da-167">실행이 `Form1`다시 실행 `LongTask` 되는 동안 메서드가 다시 호출 된 경우에는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="a44da-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="a44da-168">최악의 경우 이벤트가 발생 될 때마다가 호출 되 `LongTask` 면 스택 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="a44da-169">새 `mWidget` `Widget` `mWidget`에 대 한 참조를에 할당 하 여 변수가 다른 개체에 대 한 이벤트를 처리할 수 있습니다. `Widget`</span><span class="sxs-lookup"><span data-stu-id="a44da-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="a44da-170">실제로 단추를 클릭할 때마다에서 `Button1_Click` 코드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="a44da-171">다른 위젯의 이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="a44da-171">To handle events for a different widget</span></span>  
  
- <span data-ttu-id="a44da-172">`Button1_Click` 프로시저에 다음 코드 줄을 추가 하 여를 읽는 `mWidget.LongTask(12.2, 0.33)`줄 바로 앞에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 <span data-ttu-id="a44da-173">위의 코드는 단추를 클릭할 `Widget` 때마다 새를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="a44da-174">`LongTask` 메서드가 완료 되는 즉시에 `Widget` 대 한 참조가 해제 되 고 `Widget` 이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="a44da-175">변수 `WithEvents` 는 한 번에 하나의 개체 참조만 포함할 수 있으므로 다른 `Widget` 개체를에 할당 하는 경우 `mWidget`에는 이전 `Widget` 개체의 이벤트가 더 이상 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="a44da-176">가 `mWidget` 이전`Widget`에 대 한 참조를 포함 하는 유일한 개체 변수인 경우 개체가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="a44da-177">여러 `Widget` 개체의 이벤트를 처리 하려면 `AddHandler` 문을 사용 하 여 각 개체의 이벤트를 개별적으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a44da-178">필요한 만큼의 `WithEvents` 변수를 선언할 수 있지만 `WithEvents` 변수 배열은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a44da-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44da-179">참고자료</span><span class="sxs-lookup"><span data-stu-id="a44da-179">See also</span></span>

- [<span data-ttu-id="a44da-180">연습: 이벤트 선언 및 발생</span><span class="sxs-lookup"><span data-stu-id="a44da-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [<span data-ttu-id="a44da-181">이벤트</span><span class="sxs-lookup"><span data-stu-id="a44da-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
