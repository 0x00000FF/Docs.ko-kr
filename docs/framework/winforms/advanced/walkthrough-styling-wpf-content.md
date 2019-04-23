---
title: '연습: WPF 콘텐츠 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 887a157494c2992c1ae5868229c442f31fafb276
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312152"
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="67fc1-102">연습: WPF 콘텐츠 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="67fc1-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="67fc1-103">이 연습에서는 Windows Forms에 호스트되는 WPF(Windows Presentation Foundation) 컨트롤에 스타일을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="67fc1-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="67fc1-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-105">Create the project.</span></span>

-   <span data-ttu-id="67fc1-106">WPF 컨트롤 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-106">Create the WPF control type.</span></span>

-   <span data-ttu-id="67fc1-107">WPF 컨트롤에 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-107">Apply a style to the WPF control.</span></span>

> [!NOTE]
>  <span data-ttu-id="67fc1-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="67fc1-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="67fc1-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67fc1-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="67fc1-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="67fc1-111">Prerequisites</span></span>  
 <span data-ttu-id="67fc1-112">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-112">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="67fc1-113">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="67fc1-113">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="67fc1-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="67fc1-114">Creating the Project</span></span>  
 <span data-ttu-id="67fc1-115">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67fc1-116">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="67fc1-117">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="67fc1-117">To create the project</span></span>  
  
-   <span data-ttu-id="67fc1-118">Visual Basic 또는 Visual C#에서 새 Windows Forms 응용 프로그램 프로젝트를 만들 `StylingWpfContent`합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="67fc1-119">WPF 컨트롤 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="67fc1-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="67fc1-120">프로젝트에 WPF 컨트롤 형식을 추가한 후 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="67fc1-121">WPF 컨트롤 형식을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-121">To create WPF control types</span></span>  
  
1. <span data-ttu-id="67fc1-122">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="67fc1-123">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="67fc1-124">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="67fc1-125">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="67fc1-126">자세한 내용은 [방법: 선택 하 고 디자인 화면에서 요소를 이동](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-126">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="67fc1-127">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`입니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4. <span data-ttu-id="67fc1-128">추가 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 컨트롤을 합니다 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 **취소**합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5. <span data-ttu-id="67fc1-129">두 번째 추가 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6. <span data-ttu-id="67fc1-130">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="67fc1-131">WPF 컨트롤에 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="67fc1-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="67fc1-132">WPF 컨트롤에 다른 스타일을 적용하여 모양과 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="67fc1-133">WPF 컨트롤에 스타일을 적용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-133">To apply a style to a WPF control</span></span>  
  
1. <span data-ttu-id="67fc1-134">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="67fc1-135">에 **도구 상자**를 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 양식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="67fc1-136">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3. <span data-ttu-id="67fc1-137">에 대 한 스마트 태그 패널에서 `elementHost1`, 클릭 **호스팅된 콘텐츠 편집** 드롭 다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="67fc1-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="67fc1-138">`UserControl1`이 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="67fc1-139">XAML 뷰에서 `<UserControl>` 여는 태그 뒤에 다음 XAML을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="67fc1-140">이 XAML은 대비되는 그라데이션 테두리가 있는 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="67fc1-141">컨트롤을 클릭하면 그라데이션이 변경되어 눌린 단추 모양을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="67fc1-142">자세한 내용은 [스타일 지정 및 템플릿](../../wpf/controls/styling-and-templating.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67fc1-142">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1. <span data-ttu-id="67fc1-143">다음 XAML을 취소 단추의 `<Button>` 태그에 삽입하여 이전 단계에서 정의된 `SimpleButton` 스타일을 취소 단추에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="67fc1-144">단추 선언은 다음 XAML과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1. <span data-ttu-id="67fc1-145">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-145">Build the project.</span></span>  
  
2. <span data-ttu-id="67fc1-146">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3. <span data-ttu-id="67fc1-147">단추 컨트롤에 새 스타일이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-147">The new style is applied to the button control.</span></span>  
  
4. <span data-ttu-id="67fc1-148">**디버그** 메뉴에서 **디버깅 시작** 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5. <span data-ttu-id="67fc1-149">확인 및 취소 단추를 클릭하고 차이점을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67fc1-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67fc1-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="67fc1-150">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="67fc1-151">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="67fc1-151">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="67fc1-152">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="67fc1-152">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="67fc1-153">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="67fc1-153">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="67fc1-154">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="67fc1-154">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="67fc1-155">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="67fc1-155">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
