---
title: '방법: 순차 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 33a4d6f7db140023bc33839fec7d5e28b7f5fe51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547308"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="cd6d6-102">방법: 순차 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="cd6d6-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="cd6d6-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="cd6d6-104">이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.Sequence> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="cd6d6-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd6d6-106">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="cd6d6-107">이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd6d6-108">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="cd6d6-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cd6d6-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="cd6d6-110">마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="cd6d6-111">에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="cd6d6-112">선택 **활동** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="cd6d6-113">형식 `SequentialNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="cd6d6-114">끌어서를 **시퀀스** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블는 워크플로 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="cd6d6-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cd6d6-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="cd6d6-116">두 번 클릭 **SequentialNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="cd6d6-117">클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="cd6d6-118">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="cd6d6-119">형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="cd6d6-120">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="cd6d6-121">형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="cd6d6-122">클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="cd6d6-123">클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="cd6d6-124">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="cd6d6-125">없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 **시퀀스** 선택 하려면 워크플로 디자이너 화면에 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="cd6d6-126">형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="cd6d6-127">클릭 **변수를 만듭니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="cd6d6-128">형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="cd6d6-129">클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="cd6d6-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="cd6d6-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="cd6d6-131">끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="cd6d6-132">형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="cd6d6-133">경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="cd6d6-134">끌어서를 **DoWhile** 활동에서를 **제어 흐름** 섹션의 **도구 상자** 아래에 워크플로에 놓습니다를 **할당** 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3.  <span data-ttu-id="cd6d6-135">에 다음 식을 입력 합니다 **DoWhile** 활동의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="cd6d6-136"><xref:System.Activities.Statements.DoWhile> 활동은 자식 활동을 실행한 다음 해당 <xref:System.Activities.Statements.DoWhile.Condition%2A>을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="cd6d6-137"><xref:System.Activities.Statements.DoWhile.Condition%2A>이 `True`로 확인되면 <xref:System.Activities.Statements.DoWhile>의 활동이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="cd6d6-138">이 예제에서는 사용자의 추측 값을 확인하여 추측이 올바를 때까지 <xref:System.Activities.Statements.DoWhile>이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4.  <span data-ttu-id="cd6d6-139">끌어서를 **프롬프트** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **DoWhile** 활동 이전 단계의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5.  <span data-ttu-id="cd6d6-140">에 **속성 창**, 형식 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자에는 **프롬프트** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="cd6d6-141">형식 `Guess` 에 **결과** 속성 값 상자 및에 다음 식을 입력 합니다 **텍스트** 속성 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="cd6d6-142">경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6.  <span data-ttu-id="cd6d6-143">끌어서는 **할당** 활동에서를 **기본** 부분을 **도구 상자** 놓습니다를 **DoWhile** 활동 뒤에 놓습니다를 **프롬프트** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6d6-144">놓으면를 **할당** 작업, 워크플로 디자이너를 자동으로 추가 하는 방법을 참고를 **시퀀스** 둘 다 포함 하는 작업을 **프롬프트** 활동과 새로 추가 된 **할당** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7.  <span data-ttu-id="cd6d6-145">형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8.  <span data-ttu-id="cd6d6-146">끌어서는 **경우** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동 뒤에 놓습니다는 새로 추가 된 **할당** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="cd6d6-147">에 다음 식을 입력 합니다 **하는 경우** 활동의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="cd6d6-148">다른 **경우** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **다음** 첫번째섹션**경우** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="cd6d6-149">에 새로 추가 된 다음 식을 입력 **하는 경우** 활동의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="cd6d6-150">두 개 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 되도록 하나에 놓을 **다음** 섹션 새로 추가한 **하는 경우** 활동을 하나는 **Else** 섹션.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="cd6d6-151">클릭는 **WriteLine** 활동에는 **다음** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="cd6d6-152">클릭는 **WriteLine** 활동에는 **Else** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="cd6d6-153">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-153">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="cd6d6-154">![완료 된 순차 워크플로](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="cd6d6-154">![Completed Sequential Workflow](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="cd6d6-155">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="cd6d6-155">To build the workflow</span></span>  
  
1.  <span data-ttu-id="cd6d6-156">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="cd6d6-157">워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="cd6d6-158">이미 완료 하는 경우는 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) 이 단계에서 순차 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6d6-158">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6d6-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd6d6-159">See also</span></span>
- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="cd6d6-160">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cd6d6-160">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
- [<span data-ttu-id="cd6d6-161">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="cd6d6-161">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)
- [<span data-ttu-id="cd6d6-162">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="cd6d6-162">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
- [<span data-ttu-id="cd6d6-163">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="cd6d6-163">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)
- [<span data-ttu-id="cd6d6-164">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="cd6d6-164">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
