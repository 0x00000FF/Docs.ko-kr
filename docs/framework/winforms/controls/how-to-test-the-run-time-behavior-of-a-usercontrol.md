---
title: '방법: UserControl의 런타임 동작 테스트'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 06f2320648bd8fee3465ea1672be886293667879
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664421"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="4e08a-102">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="4e08a-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="4e08a-103">개발 하는 경우는 <xref:System.Windows.Forms.UserControl>, 해당 런타임 동작을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="4e08a-104">별도 Windows 기반 응용 프로그램 프로젝트를 만들고 테스트 폼에서 컨트롤을 배치할 수 있지만이 절차를 편리 하 게 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="4e08a-105">빠르고 쉽게 방법을 사용 하는 것은 **UserControl 테스트 컨테이너** Visual Studio에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="4e08a-106">이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e08a-107">로드 테스트 컨테이너에 대 한 프로그램 <xref:System.Windows.Forms.UserControl>를 컨트롤에는 하나 이상의 공용 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e08a-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4e08a-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4e08a-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e08a-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e08a-111">Visual c + + 컨트롤을 사용 하 여 테스트할 수 없습니다는 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="4e08a-112">UserControl의 런타임 동작을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="4e08a-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="4e08a-113">라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 **컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="4e08a-114">자세한 내용은 참조 하세요 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-114">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="4e08a-115">에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.Label> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="4e08a-116">F5 키를 눌러 프로젝트를 빌드 및 실행 하는 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="4e08a-117">테스트 컨테이너에 표시 하 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.</span><span class="sxs-lookup"><span data-stu-id="4e08a-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="4e08a-118">선택는 <xref:System.Windows.Forms.Control.BackColor%2A> 에 표시 되는 속성을 <xref:System.Windows.Forms.PropertyGrid> 컨트롤의 오른쪽에는 **미리 보기** 창.</span><span class="sxs-lookup"><span data-stu-id="4e08a-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="4e08a-119">해당 값을 변경할 `ControlDark`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="4e08a-120">컨트롤 어두운 색으로 변경 되는지 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="4e08a-121">다른 속성 값을 변경 하 고 컨트롤에 대 한 효과 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="4e08a-122">클릭 합니다 **사용자 정의 컨트롤 전체 도킹** 아래 확인란 합니다 **미리 보기** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="4e08a-123">컨트롤의 창에 맞게 크기가 조정 됩니다 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="4e08a-124">테스트 컨테이너 크기를 조정 하 고 컨트롤의 창 크기 조정 되는 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="4e08a-125">테스트 컨테이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="4e08a-126">다른 사용자 정의 컨트롤을 추가 합니다 **컨트롤** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="4e08a-127">자세한 내용은 [방법: 프로젝트에 기존 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-127">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>  
  
8.  <span data-ttu-id="4e08a-128">에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.Button> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="4e08a-129">F5 키를 눌러 프로젝트를 빌드 및 테스트 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="4e08a-130">클릭 합니다 **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox> 두 개의 사용자 정의 컨트롤을 전환 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="4e08a-131">다른 프로젝트에서 사용자 정의 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="4e08a-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="4e08a-132">현재 프로젝트의 테스트 컨테이너에서 다른 프로젝트에서 사용자 정의 컨트롤을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="4e08a-133">다른 프로젝트에서 사용자 정의 컨트롤을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="4e08a-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="4e08a-134">라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 **TestContainerExample2**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="4e08a-135">자세한 내용은 참조 하세요 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-135">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="4e08a-136">에 **Windows Forms 디자이너**를 끌어를 <xref:System.Windows.Forms.RadioButton> 에서 제어를 **도구 상자** 컨트롤의 디자인 화면으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="4e08a-137">F5 키를 눌러 프로젝트를 빌드 및 테스트 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="4e08a-138">테스트 컨테이너에 표시 하 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.</span><span class="sxs-lookup"><span data-stu-id="4e08a-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="4e08a-139">클릭 합니다 **부하** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="4e08a-140">에 **엽니다** 대화 상자에서 **컨트롤**이전 절차에서 만든.dll입니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="4e08a-141">선택 **컨트롤**.dll 및 클릭 합니다 **오픈** 사용자 정의 컨트롤을 로드 하려면 단추를</span><span class="sxs-lookup"><span data-stu-id="4e08a-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="4e08a-142">사용 합니다 **사용자 정의 컨트롤을 선택** <xref:System.Windows.Forms.ComboBox> 에서 두 개의 사용자 정의 컨트롤을 전환 하는 **컨트롤** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="4e08a-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e08a-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e08a-143">See also</span></span>
- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="4e08a-144">방법: 복합 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="4e08a-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)
- [<span data-ttu-id="4e08a-145">연습: Visual Basic에서 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="4e08a-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="4e08a-146">연습: 시각적 개체를 사용 하 여 복합 컨트롤 제작C#</span><span class="sxs-lookup"><span data-stu-id="4e08a-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="4e08a-147">[사용자 정의 컨트롤 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4e08a-147">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
