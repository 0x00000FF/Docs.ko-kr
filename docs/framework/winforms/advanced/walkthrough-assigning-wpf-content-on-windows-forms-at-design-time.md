---
title: '연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 49421fc6c673ffe090e58d733ff0a309464edbb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527746"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="4ed79-102">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당</span><span class="sxs-lookup"><span data-stu-id="4ed79-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="4ed79-103">이 연습에서는 폼에 표시할 WPF(Windows Presentation Foundation) 컨트롤 형식을 선택하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="4ed79-104">프로젝트에 포함된 모든 WPF 컨트롤 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="4ed79-105">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="4ed79-106">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-106">Create the project.</span></span>

-   <span data-ttu-id="4ed79-107">WPF 컨트롤 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-107">Create the WPF control types.</span></span>

-   <span data-ttu-id="4ed79-108">WPF 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="4ed79-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4ed79-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4ed79-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed79-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ed79-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4ed79-112">Prerequisites</span></span>  
 <span data-ttu-id="4ed79-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-113">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="4ed79-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="4ed79-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4ed79-115">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4ed79-115">Creating the Project</span></span>  
 <span data-ttu-id="4ed79-116">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ed79-117">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4ed79-118">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4ed79-118">To create the project</span></span>  
  
-   <span data-ttu-id="4ed79-119">Visual Basic 또는 Visual C#에서 새 Windows Forms 응용 프로그램 프로젝트를 만들 `SelectingWpfContent`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="4ed79-120">WPF 컨트롤 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="4ed79-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="4ed79-121">프로젝트에 WPF 컨트롤 형식을 추가한 후 다양한 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="4ed79-122">WPF 컨트롤 형식을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="4ed79-123">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="4ed79-124">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="4ed79-125">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="4ed79-126">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="4ed79-127">자세한 내용은 [방법: 선택 하 고 디자인 화면에서 요소를 이동](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="4ed79-128">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="4ed79-129">추가 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 합니다 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **Hosted Content**합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="4ed79-130">프로젝트에 두 번째 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="4ed79-131">컨트롤 형식의 기본 이름인 `UserControl2.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="4ed79-132">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="4ed79-133">추가 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 합니다 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **Hosted Content 2**합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="4ed79-134">**참고** 일반적으로 더 복잡 한 WPF 콘텐츠를 호스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="4ed79-135"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="4ed79-136">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="4ed79-137">WPF 컨트롤 선택</span><span class="sxs-lookup"><span data-stu-id="4ed79-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="4ed79-138">이미 콘텐츠를 호스트하고 있는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 다른 WPF 콘텐츠를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="4ed79-139">WPF 컨트롤을 선택하려면</span><span class="sxs-lookup"><span data-stu-id="4ed79-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="4ed79-140">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="4ed79-141">에 **도구 상자**를 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 양식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="4ed79-142">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="4ed79-143">에 대 한 스마트 태그 패널에서 `elementHost1`열고 합니다 **호스팅된 콘텐츠 선택** 드롭 다운 목록.</span><span class="sxs-lookup"><span data-stu-id="4ed79-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="4ed79-144">선택 **UserControl2** 드롭다운 목록 상자에서.</span><span class="sxs-lookup"><span data-stu-id="4ed79-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="4ed79-145">이제 `elementHost1` 컨트롤이 `UserControl2` 형식의 인스턴스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="4ed79-146">에 **속성** 창 있는지 확인 합니다 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이로 설정 되어 **UserControl2**합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="4ed79-147">**도구 상자**를 **WPF 상호 운용성** 그룹에서 끌어는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="4ed79-148">새 컨트롤의 기본 이름은 `elementHost2`입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="4ed79-149">에 대 한 스마트 태그 패널에서 `elementHost2`열고 합니다 **호스팅된 콘텐츠 선택** 드롭 다운 목록.</span><span class="sxs-lookup"><span data-stu-id="4ed79-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="4ed79-150">선택 **UserControl1** 드롭 다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="4ed79-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="4ed79-151">이제 `elementHost2` 컨트롤이 `UserControl1` 형식의 인스턴스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed79-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed79-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ed79-152">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4ed79-153">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="4ed79-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="4ed79-154">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="4ed79-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="4ed79-155">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="4ed79-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
