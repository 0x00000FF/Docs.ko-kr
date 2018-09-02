---
title: '방법: 활동 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: deb1b6ca5c6fc996a015e32dd5e0c7b9bd6530fa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402509"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="70901-102">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="70901-102">How to: Create an Activity</span></span>
<span data-ttu-id="70901-103">활동은 [!INCLUDE[wf1](../../../includes/wf1-md.md)]에서 동작의 핵심 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="70901-104">활동의 실행 논리는 관리 코드에서 구현하거나 다른 활동을 사용하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70901-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="70901-105">이 항목에서는 두 개의 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70901-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="70901-106">첫 번째 활동은 코드를 사용하여 실행 논리를 구현하는 간단한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="70901-107">두 번째 활동의 구현은 다른 활동을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="70901-108">이러한 활동은 자습서의 다음 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-108">These activities are used in following steps in the tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70901-109">이 자습서의 전체 버전을 다운로드 하려면 [Windows Workflow Foundation(wf45 ()-초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-activity-library-project"></a><span data-ttu-id="70901-110">활동 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="70901-110">To create the activity library project</span></span>  
  
1.  <span data-ttu-id="70901-111">오픈 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택한 **새로 만들기**, **프로젝트** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="70901-111">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and choose **New**,  **Project** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="70901-112">확장 합니다 **기타 프로젝트 형식** 에서 노드를 **설치 됨**를 **템플릿** 나열 하 고 선택 **Visual Studio 솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-112">Expand the **Other Project Types** node in the **Installed**, **Templates** list and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="70901-113">선택 **빈 솔루션** 에서 합니다 **Visual Studio 솔루션** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-113">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="70901-114">.NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="70901-115">형식 `WF45GettingStartedTutorial` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-115">Type `WF45GettingStartedTutorial` in the **Name** box and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="70901-116">마우스 오른쪽 단추로 클릭 **WF45GettingStartedTutorial** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-116">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="70901-117">**솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-117">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="70901-118">**설치됨** 노드에서 **Visual C#**, **워크플로** (또는 **Visual Basic**, **워크플로**)를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-118">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span> <span data-ttu-id="70901-119">했는지 **.NET Framework 4.5** 에서 선택한는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 버전 드롭다운 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-119">Ensure that **.NET Framework 4.5** is selected in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version drop-down list.</span></span> <span data-ttu-id="70901-120">선택 **활동 라이브러리** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-120">Select **Activity Library** from the **Workflow** list.</span></span> <span data-ttu-id="70901-121">형식 `NumberGuessWorkflowActivities` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-121">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70901-122">**설치됨** 노드의 **다른 언어** 노드 아래에는 Visual Studio에서 기본 언어로 구성된 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70901-122">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>  
  
6.  <span data-ttu-id="70901-123">마우스 오른쪽 단추로 클릭 **Activity1.xaml** 에 **솔루션 탐색기** 선택한 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-123">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="70901-124">**확인** 을 클릭하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-124">Click **OK** to confirm.</span></span>  
  
### <a name="to-create-the-readint-activity"></a><span data-ttu-id="70901-125">ReadInt 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="70901-125">To create the ReadInt activity</span></span>  
  
1.  <span data-ttu-id="70901-126">선택할 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="70901-126">Choose **Add New Item** from the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="70901-127">에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-127">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="70901-128">선택 **코드 활동** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-128">Select **Code Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="70901-129">형식 `ReadInt` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-129">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="70901-130">기존 `ReadInt` 정의를 다음 정의로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70901-130">Replace the existing `ReadInt` definition with the following definition.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="70901-131">`ReadInt` 활동은 코드 활동 템플릿의 기본값인 <xref:System.Activities.NativeActivity%601> 대신 <xref:System.Activities.CodeActivity>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-131">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="70901-132">활동이 <xref:System.Activities.CodeActivity%601> 인수를 통해 노출되는 단일 결과를 제공하는 경우 <xref:System.Activities.Activity%601.Result%2A>를 사용할 수 있지만 <xref:System.Activities.CodeActivity%601>는 책갈피 사용을 지원하지 않으므로 <xref:System.Activities.NativeActivity%601>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-132"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>  
  
### <a name="to-create-the-prompt-activity"></a><span data-ttu-id="70901-133">Prompt 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="70901-133">To create the Prompt activity</span></span>  
  
1.  <span data-ttu-id="70901-134">Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-134">Press CTRL+SHIFT+B to build the project.</span></span> <span data-ttu-id="70901-135">프로젝트를 빌드하면 이 프로젝트의 `ReadInt` 활동을 사용하여 이 단계의 사용자 지정 활동을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70901-135">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>  
  
2.  <span data-ttu-id="70901-136">선택할 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="70901-136">Choose **Add New Item** from the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="70901-137">에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-137">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="70901-138">선택 **활동** 에서 합니다 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-138">Select **Activity** from the **Workflow** list.</span></span>  
  
4.  <span data-ttu-id="70901-139">형식 `Prompt` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-139">Type `Prompt` into the **Name** box and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="70901-140">두 번 클릭 **Prompt.xaml** 에 **솔루션 탐색기** 아직 표시 되지 않은 경우 디자이너에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-140">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>  
  
6.  <span data-ttu-id="70901-141">클릭 **인수** 표시할 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-141">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>  
  
7.  <span data-ttu-id="70901-142">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-142">Click **Create Argument**.</span></span>  
  
8.  <span data-ttu-id="70901-143">형식 `BookmarkName` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **문자열** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="70901-143">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
9. <span data-ttu-id="70901-144">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-144">Click **Create Argument**.</span></span>  
  
10. <span data-ttu-id="70901-145">형식 `Result` 에 **이름** 새로 추가 된 아래에 있는 상자 `BookmarkName` 인수 **Out** 에서 **방향** 드롭 다운 목록에서 **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="70901-145">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="70901-146">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-146">Click **Create Argument**.</span></span>  
  
12. <span data-ttu-id="70901-147">형식 `Text` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **문자열** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="70901-147">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
     <span data-ttu-id="70901-148">이 세 가지 인수는 다음 단계에서 <xref:System.Activities.Statements.WriteLine> 활동에 추가되는 `ReadInt` 및 `Prompt` 활동의 해당 인수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-148">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>  
  
13. <span data-ttu-id="70901-149">클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-149">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
14. <span data-ttu-id="70901-150">끌어서를 **시퀀스** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 레이블의 **프롬프트** 활동 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-150">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="70901-151">경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="70901-151">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
15. <span data-ttu-id="70901-152">끌어서를 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 레이블의 **시퀀스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>  
  
16. <span data-ttu-id="70901-153">바인딩를 **텍스트** 인수를 **WriteLine** 활동을를 **텍스트** 인수를 **프롬프트** 입력 하 여 작업 `Text` 에 **C# 식 입력** 또는 **VB 식 입력** 상자에 **속성** 창과 누릅니다 탭 키를 두 번입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-153">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the TAB key two times.</span></span> <span data-ttu-id="70901-154">그러면 IntelliSense 목록 멤버 창이 사라지고 속성에서 선택 항목을 이동하여 속성 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-154">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="70901-155">입력 하 여이 속성을 설정할 수도 있습니다 `Text` 에 **C# 식 입력** 또는 **VB 식 입력** 활동 자체는 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-155">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="70901-156">경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="70901-156">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
17. <span data-ttu-id="70901-157">끌어서를 **ReadInt** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동 오도록 합니다 **WriteLine** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="70901-157">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>  
  
18. <span data-ttu-id="70901-158">바인딩를 **BookmarkName** 인수를 **ReadInt** 활동을는 **BookmarkName** 인수의 **프롬프트** 입력하여활동`BookmarkName` 에 **VB 식 입력** 오른쪽의 상자에는 **BookmarkName** 인수에는 **속성 창**, 두 탭 키를 누릅니다 IntelliSense 목록 멤버 창을 닫고 속성을 저장 하려면 시간이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70901-158">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the TAB key two times to close the IntelliSense list members window and save the property.</span></span>  
  
19. <span data-ttu-id="70901-159">바인딩를 **결과** 인수를 **ReadInt** 활동을를 **결과** 인수를 **프롬프트** 입력 하 여 작업 `Result` 에 **VB 식 입력** 의 오른쪽 상자에는 **결과** 인수에는 **속성 창**, 탭 키를 두 번 누릅니다 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-159">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the TAB key two times.</span></span>  
  
20. <span data-ttu-id="70901-160">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-160">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="70901-161">이러한 활동을 사용 하 여 워크플로 만드는 방법에 대 한 지침 자습서에서 다음 단계를 참조 하세요 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70901-161">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70901-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70901-162">See Also</span></span>  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [<span data-ttu-id="70901-163">사용자 지정 활동 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="70901-163">Designing and Implementing Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [<span data-ttu-id="70901-164">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="70901-164">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="70901-165">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="70901-165">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [<span data-ttu-id="70901-166">사용자 지정 작업 디자이너에서 ExpressionTextBox 사용</span><span class="sxs-lookup"><span data-stu-id="70901-166">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
