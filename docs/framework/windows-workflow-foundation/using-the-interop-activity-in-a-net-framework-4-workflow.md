---
title: .NET Framework 4 워크플로에서 Interop 활동 사용
ms.date: 03/30/2017
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
ms.openlocfilehash: 02eeaf5bb7ff484ba5982197fc395e247cd5a87f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528112"
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="80102-102">.NET Framework 4 워크플로에서 Interop 활동 사용</span><span class="sxs-lookup"><span data-stu-id="80102-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="80102-103">[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 또는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 만든 활동은 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 통해 <xref:System.Activities.Statements.Interop> 워크플로에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80102-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="80102-104">이 항목에서는 <xref:System.Activities.Statements.Interop> 활동 사용에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80102-105">합니다 <xref:System.Activities.Statements.Interop> 워크플로 프로젝트에 없는 경우 활동이 workflow designer 도구 상자에 나타나지 않습니다 해당 **대상 프레임 워크** 로 설정 **.NET Framework 4** 이상.</span><span class="sxs-lookup"><span data-stu-id="80102-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="80102-106">.NET Framework 4.5 워크플로에서 Interop 활동 사용</span><span class="sxs-lookup"><span data-stu-id="80102-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="80102-107">이 항목에서는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동을 포함하는 `DiscountCalculator` 활동 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="80102-108">`DiscountCalculator`는 구매량을 기준으로 할인을 계산하며 <xref:System.Workflow.Activities.SequenceActivity>를 포함하는 <xref:System.Workflow.Activities.PolicyActivity>로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80102-109">이 항목에서 만드는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동은 <xref:System.Workflow.Activities.PolicyActivity>를 사용하여 활동 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="80102-110">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 워크플로에서 규칙을 사용하기 위해 사용자 지정 <xref:System.Activities.Statements.Interop> 활동이나 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80102-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="80102-111">규칙을 사용 하는 예는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 사용 하지 않고 워크플로 <xref:System.Activities.Statements.Interop> 활동 참조는 [.NET Framework 4.5의 정책 작업](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="80102-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="80102-112">.NET Framework 3.5 활동 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="80102-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="80102-113">오픈 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택한 **새로 만들기** 차례로 **프로젝트...**</span><span class="sxs-lookup"><span data-stu-id="80102-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="80102-114">**파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="80102-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="80102-115">확장을 **기타 프로젝트 형식** 에서 노드를 **설치 된 템플릿** 창과 선택 **Visual Studio 솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="80102-116">선택 **빈 솔루션** 에서 합니다 **Visual Studio 솔루션** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="80102-117">형식 `PolicyInteropDemo` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="80102-118">마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에 **솔루션 탐색기** 선택한 **추가** 차례로 **새 프로젝트...** .</span><span class="sxs-lookup"><span data-stu-id="80102-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="80102-119">경우는 **솔루션 탐색기** 창이 표시, 선택 되지 않으면 **솔루션 탐색기** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="80102-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="80102-120">에 **설치 된 템플릿** 목록에서 **Visual C#** 차례로 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="80102-121">선택 **.NET Framework 3.5** .NET Framework 버전 드롭다운 목록에서 선택 **Workflow Activity Library** 에서 합니다 **템플릿** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="80102-122">형식 `PolicyActivityLibrary` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="80102-123">마우스 오른쪽 단추로 클릭 **Activity1.cs** 에 **솔루션 탐색기** 선택한 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="80102-124">**확인** 을 클릭하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="80102-125">DiscountCalculator 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="80102-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="80102-126">마우스 오른쪽 단추로 클릭 **PolicyActivityLibrary** 에 **솔루션 탐색기** 선택한 **추가** 차례로 **작업 하는 중...** .</span><span class="sxs-lookup"><span data-stu-id="80102-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="80102-127">선택 **활동 (코드 분리)** 에서 합니다 **Visual C# 항목** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="80102-128">형식 `DiscountCalculator` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="80102-129">마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에 **솔루션 탐색기** 선택한 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="80102-130">`DiscountCalculator` 클래스에 다음 세 가지 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="80102-131">마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에 **솔루션 탐색기** 선택한 **뷰 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="80102-132">끌어서를 **정책** 활동에서는 **Windows Workflow v3.0** 부분을 **도구 상자** 놓습니다를 **DiscountCalculator** 활동 .</span><span class="sxs-lookup"><span data-stu-id="80102-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="80102-133">경우는 **도구 상자** 창이 표시, 선택 되지 않으면 **도구 상자** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="80102-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="80102-134">규칙을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="80102-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="80102-135">새로 추가 된 클릭 **정책** 활동이 아직 선택 하지 않은 경우 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="80102-136">클릭 합니다 **RuleSetReference** 속성에는 **속성** 속성의 오른쪽에 줄임표 (...) 단추를 클릭 하 고 선택한 후에 창입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="80102-137">경우는 **속성** 창이 표시 되지 않으면, 선택 **속성 창** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="80102-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="80102-138">선택 **새로 만들기 클릭...** .</span><span class="sxs-lookup"><span data-stu-id="80102-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="80102-139">클릭 **규칙 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="80102-140">에 다음 식을 입력 합니다 **조건을** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="80102-141">에 다음 식을 입력 합니다 **Thenactions** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="80102-142">클릭 **규칙 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="80102-143">에 다음 식을 입력 합니다 **조건을** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="80102-144">에 다음 식을 입력 합니다 **Thenactions** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="80102-145">클릭 **규칙 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="80102-146">에 다음 식을 입력 합니다 **조건을** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="80102-147">에 다음 식을 입력 합니다 **Thenactions** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="80102-148">에 다음 식을 입력 합니다 **Else 작업** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="80102-149">클릭 **확인** 닫으려면 합니다 **규칙 집합 편집기** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="80102-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="80102-150">새로 만든 했는지 <xref:System.Workflow.Activities.Rules.RuleSet> 에서 선택한는 **이름** 목록 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="80102-151">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="80102-152">다음 코드 예제에서는 이 절차에서 `DiscountCalculator` 활동에 추가한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80102-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="80102-153"><xref:System.Workflow.Activities.PolicyActivity>가 실행되면 이 세 가지 규칙은 `Subtotal` 활동의 `DiscountPercent`, `Total` 및 `DiscountCalculator` 속성 값을 평가하고 수정하여 원하는 할인을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="80102-154">Interop 활동과 함께 DiscountCalculator 활동 사용</span><span class="sxs-lookup"><span data-stu-id="80102-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="80102-155">`DiscountCalculator` 워크플로 내에서 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 사용하려면 <xref:System.Activities.Statements.Interop> 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="80102-156">이 단원에서는 <xref:System.Activities.Statements.Interop> 활동과 함께 `DiscountCalculator` 활동을 사용하는 방법을 보여 주는 두 개의 워크플로를 코드 및 Workflow Designer를 사용하여 각각 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="80102-157">두 워크플로에 동일한 호스트 응용 프로그램을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="80102-158">호스트 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="80102-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="80102-159">마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에 **솔루션 탐색기** 선택한 **추가**를 차례로 **새 프로젝트...** .</span><span class="sxs-lookup"><span data-stu-id="80102-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="80102-160">했는지 **.NET Framework 4.5** 선택한.NET Framework 버전 드롭다운 목록에서 선택한 **워크플로 콘솔 응용 프로그램** 에서 합니다 **Visual C# 항목** 목록.</span><span class="sxs-lookup"><span data-stu-id="80102-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="80102-161">형식 `PolicyInteropHost` 에 **이름** 상자 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="80102-162">마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택한 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="80102-163">에 **대상 프레임 워크** 드롭 다운 목록에서 선택 항목을 변경 **.NET Framework 4 Client Profile** 에 **.NET Framework 4.5**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="80102-164">클릭 **예** 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="80102-165">마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택한 **참조 추가...** .</span><span class="sxs-lookup"><span data-stu-id="80102-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="80102-166">선택 **PolicyActivityLibrary** 에서 합니다 **프로젝트** 탭을 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="80102-167">마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택한 **참조 추가...** .</span><span class="sxs-lookup"><span data-stu-id="80102-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="80102-168">선택 **System.Workflow.Activities**를 **System.Workflow.ComponentModel**를 차례로 **System.Workflow.Runtime** 에서 **.NET**탭을 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="80102-169">마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택한 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="80102-170">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="80102-171">코드에서 Interop 활동 사용</span><span class="sxs-lookup"><span data-stu-id="80102-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="80102-172">이 예제에서는 코드를 사용하여 <xref:System.Activities.Statements.Interop> 활동과 `DiscountCalculator` 활동을 포함하는 워크플로 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="80102-173">이 워크플로는 <xref:System.Activities.WorkflowInvoker>를 사용하여 호출하고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 규칙 평가 결과를 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="80102-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="80102-174">코드에서 Interop 활동을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="80102-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="80102-175">마우스 오른쪽 단추로 클릭 **Program.cs** 에 **솔루션 탐색기** 선택한 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="80102-176">파일 맨 위에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="80102-177">`Main` 메서드의 내용을 제거하고 다음 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="80102-178">`Program` 클래스에 다음 코드를 포함하는 `CalculateDiscountUsingCodeWorkflow`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="80102-179">`Subtotal` 활동의 `DiscountPercent`, `Total` 및 `DiscountCalculator` 속성은 <xref:System.Activities.Statements.Interop> 활동의 인수로 표시되고 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 컬렉션에서 로컬 워크플로 변수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="80102-180">`Subtotal`은 <xref:System.Activities.ArgumentDirection.In> 데이터가 `Subtotal` 활동 안으로 흐르기 때문에 <xref:System.Activities.Statements.Interop> 인수로 추가되고, `DiscountPercent` 및 `Total`은 해당 데이터가 <xref:System.Activities.ArgumentDirection.Out> 활동 밖으로 흐르기 때문에 <xref:System.Activities.Statements.Interop> 인수로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="80102-181">두 <xref:System.Activities.ArgumentDirection.Out> 인수는 `DiscountPercentOut` 인수임을 나타내기 위해 `TotalOut` 및 <xref:System.Activities.ArgumentDirection.Out>이라는 이름으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="80102-182">`DiscountCalculator` 형식은 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityType%2A>으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="80102-183">Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="80102-184">`Subtotal` 값에 다양한 값을 대체하여 `DiscountCalculator` 활동에서 제공하는 다양한 할인 수준을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="80102-185">Workflow Designer에서 Interop 활동 사용</span><span class="sxs-lookup"><span data-stu-id="80102-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="80102-186">이 예제에서는 Workflow Designer를 사용하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="80102-187">이 워크플로는 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 할인을 표시하는 대신에 워크플로가 완료될 때 호스트 응용 프로그램이 할인 정보를 검색하여 표시한다는 점을 제외하고 이전 예제와 동일한 기능을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="80102-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="80102-188">또한 로컬 워크플로 변수를 사용하여 데이터를 포함하는 대신에 Workflow Designer에서 인수가 만들어지고 워크플로가 호출될 때 호스트에서 값이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="80102-189">워크플로 디자이너에서 만든 워크플로를 사용하여 PolicyActivity를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="80102-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="80102-190">마우스 오른쪽 단추로 클릭 **Workflow1.xaml** 에 **솔루션 탐색기** 선택한 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="80102-191">**확인** 을 클릭하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="80102-192">마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택한 **추가**, **새 항목...** .</span><span class="sxs-lookup"><span data-stu-id="80102-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="80102-193">확장 된 **Visual C# 항목** 노드와 선택 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="80102-194">선택 **활동** 에서 합니다 **Visual C# 항목** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="80102-195">형식 `DiscountWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="80102-196">클릭 합니다 **인수** 표시할 워크플로 디자이너의 왼쪽 아래 단추를 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="80102-197">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="80102-198">형식 `Subtotal` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭다운 목록에서 선택 **Double** 합니다 에서**인수 형식** 드롭다운 목록에서 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80102-199">하는 경우 **이중** 에 없는 경우 합니다 **인수 형식** 드롭 다운 목록에서 **형식 찾아보기...** , 형식 `System.Double` 에 **형식 이름** 상자를 선택한 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="80102-200">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="80102-201">형식 `DiscountPercent` 에 **이름** 상자에서 **Out** 에서 합니다 **방향** 드롭다운 목록에서 선택 **Double** 합니다 에서**인수 형식** 드롭다운 목록에서 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="80102-202">클릭 **인수를 만드는**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="80102-203">형식 `Total` 에 **이름** 상자에서 **Out** 에서 합니다 **방향** 드롭다운 목록에서 선택 **Double** 합니다 에서**인수 형식** 드롭다운 목록에서 enter 키를 눌러 인수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="80102-204">클릭 합니다 **인수** 닫습니다 워크플로 디자이너의 왼쪽 아래 단추를 **인수** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="80102-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="80102-205">끌어서를 **시퀀스** 활동에서를 **제어 흐름** 섹션의 **도구 상자** 워크플로 디자이너 화면에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="80102-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="80102-206">끌어서를 **Interop** 활동에서는 **마이그레이션** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동.</span><span class="sxs-lookup"><span data-stu-id="80102-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="80102-207">클릭 합니다 **Interop** 활동에는 **찾아보려면 클릭...**</span><span class="sxs-lookup"><span data-stu-id="80102-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="80102-208">레이블을 입력 합니다 **DiscountCalculator** 에 **유형 이름** 상자를 선택한 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80102-209"><xref:System.Activities.Statements.Interop> 활동이 워크플로에 추가되고 `DiscountCalculator` 형식이 해당 <xref:System.Activities.Statements.Interop.ActivityType%2A>으로 지정되면 <xref:System.Activities.Statements.Interop> 활동은 <xref:System.Activities.ArgumentDirection.In> 활동의 세 가지 공용 속성을 나타내는 <xref:System.Activities.ArgumentDirection.Out> 인수 세 개와 `DiscountCalculator` 인수 세 개를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="80102-210"><xref:System.Activities.ArgumentDirection.In> 인수는 세 가지 공용 속성 및 세 가지 동일한 이름을 가질 <xref:System.Activities.ArgumentDirection.Out> 인수에 사용 하 여 동일한 이름을 가진 **Out** 속성 이름에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="80102-211">다음 단계에서는 이전 단계에서 만든 워크플로 인수가 <xref:System.Activities.Statements.Interop> 활동의 인수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="80102-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="80102-212">형식 `DiscountPercent` 에 **VB 식 입력** 오른쪽의 상자에는 **DiscountPercentOut** 속성과 TAB 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="80102-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="80102-213">형식 `Subtotal` 에 **VB 식 입력** 오른쪽의 상자에는 **Subtotal** 속성과 TAB 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="80102-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="80102-214">형식 `Total` 에 **VB 식 입력** 오른쪽의 상자에는 **TotalOut** 속성과 TAB 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="80102-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="80102-215">마우스 오른쪽 단추로 클릭 **Program.cs** 에 **솔루션 탐색기** 선택한 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="80102-216">파일 맨 위에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="80102-217">`CalculateDiscountInCode` 메서드에서 `Main` 메서드에 대한 호출을 주석으로 처리하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80102-218">이전 절차를 따르지 않은 경우 기본 `Main` 코드가 있으면 `Main`의 내용을 다음 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="80102-219">`Program` 클래스에 다음 코드를 포함하는 `CalculateDiscountUsingDesignerWorkflow`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="80102-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="80102-220">Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="80102-221">다른 `Subtotal` 금액을 지정하려면 다음 코드에서 `SubtotalValue`의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="80102-222">규칙 기능 개요</span><span class="sxs-lookup"><span data-stu-id="80102-222">Rules Features Overview</span></span>  
 <span data-ttu-id="80102-223">[!INCLUDE[wf1](../../../includes/wf1-md.md)] 규칙 엔진은 전방 연결을 지원하면서 우선 순위 기반 방식의 규칙 처리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="80102-224">단일 항목 또는 컬렉션의 항목에 대해 규칙을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80102-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="80102-225">규칙에 대한 간략한 설명과 특정 규칙의 기능에 대한 자세한 내용은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80102-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="80102-226">규칙 기능</span><span class="sxs-lookup"><span data-stu-id="80102-226">Rules Feature</span></span>|<span data-ttu-id="80102-227">설명서</span><span class="sxs-lookup"><span data-stu-id="80102-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="80102-228">규칙 개요</span><span class="sxs-lookup"><span data-stu-id="80102-228">Rules Overview</span></span>|[<span data-ttu-id="80102-229">Windows Workflow Foundation 규칙 엔진 소개</span><span class="sxs-lookup"><span data-stu-id="80102-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](https://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="80102-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="80102-230">RuleSet</span></span>|<span data-ttu-id="80102-231">[워크플로에서 Ruleset 사용](https://go.microsoft.com/fwlink/?LinkId=178516) 및 <xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="80102-231">[Using RuleSets in Workflows](https://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="80102-232">규칙 확인</span><span class="sxs-lookup"><span data-stu-id="80102-232">Evaluation of Rules</span></span>|[<span data-ttu-id="80102-233">Ruleset의 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="80102-233">Rules Evaluation in RuleSets</span></span>](https://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="80102-234">규칙 연결</span><span class="sxs-lookup"><span data-stu-id="80102-234">Rules Chaining</span></span>|<span data-ttu-id="80102-235">[전방 연결 제어](https://go.microsoft.com/fwlink/?LinkId=178518) 고 [규칙의 전방 연결](https://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="80102-235">[Forward Chaining Control](https://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](https://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="80102-236">규칙에서 컬렉션 처리</span><span class="sxs-lookup"><span data-stu-id="80102-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="80102-237">규칙에서 컬렉션 처리</span><span class="sxs-lookup"><span data-stu-id="80102-237">Processing Collections in Rules</span></span>](https://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="80102-238">PolicyActivity 사용</span><span class="sxs-lookup"><span data-stu-id="80102-238">Using the PolicyActivity</span></span>|<span data-ttu-id="80102-239">[PolicyActivity 활동](https://go.microsoft.com/fwlink/?LinkId=178521) 및 <xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="80102-239">[Using the PolicyActivity Activity](https://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="80102-240">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서 만든 워크플로는 선언적 활동 조건 및 [!INCLUDE[wf1](../../../includes/wf1-md.md)], <xref:System.Workflow.Activities.ConditionedActivityGroup> 등의 조건부 활동과 같은 <xref:System.Workflow.Activities.ReplicatorActivity>에서 제공하는 모든 규칙 기능을 사용하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="80102-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="80102-241">필요할 경우 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 및 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 만든 워크플로에 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80102-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="80102-242">자세한 내용은 [마이그레이션 지침](../../../docs/framework/windows-workflow-foundation/migration-guidance.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80102-242">For more information, see [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
