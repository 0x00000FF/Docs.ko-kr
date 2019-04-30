---
title: 속성 표 확장성-WF 샘플
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: f1cb64cb10e8d88359e8f94b57602ab127314cff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004876"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="2ecd8-102">속성 표 확장성</span><span class="sxs-lookup"><span data-stu-id="2ecd8-102">Property grid extensibility</span></span>

<span data-ttu-id="2ecd8-103">개발자는 디자이너 내에서 지정된 활동을 선택할 경우 표시되는 속성 표를 사용자 지정할 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="2ecd8-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="2ecd8-104">이를 통해 다양한 편집 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="2ecd8-105">이 샘플에서는 이러한 작업을 수행하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-105">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="2ecd8-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="2ecd8-106">Demonstrates</span></span>

<span data-ttu-id="2ecd8-107">Workflow Designer 속성 표 확장성</span><span class="sxs-lookup"><span data-stu-id="2ecd8-107">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ecd8-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2ecd8-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2ecd8-110">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ecd8-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="2ecd8-112">토론</span><span class="sxs-lookup"><span data-stu-id="2ecd8-112">Discussion</span></span>

<span data-ttu-id="2ecd8-113">개발자는 속성 표 편집기의 인라인 모양을 사용자 지정하거나 고급 편집 화면용으로 표시되는 대화 상자를 제공하여 속성 표를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="2ecd8-114">이 샘플에 나오는 편집기는 인라인 편집기와 대화 상자 편집기, 이렇게 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="2ecd8-115">인라인 편집기</span><span class="sxs-lookup"><span data-stu-id="2ecd8-115">Inline editor</span></span>

<span data-ttu-id="2ecd8-116">인라인 편집기 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-116">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="2ecd8-117"><xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>에서 파생되는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="2ecd8-118">생성자에는 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> 값은 Windows Presentation Foundation (WPF) 데이터 템플릿을 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="2ecd8-119">이 값은 XAML 템플릿에 바인딩할 수 있지만 이 샘플에서는 코드를 사용하여 데이터 바인딩을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="2ecd8-120">데이터 템플릿에는 속성 표에서 렌더링된 항목의 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>에 대한 데이터 컨텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="2ecd8-121">CustomInlineEditor.cs에 있는 다음 코드에서는 이 컨텍스트가 `Value` 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- <span data-ttu-id="2ecd8-122">활동과 디자이너는 같은 어셈블리에 있기 때문에 활동 디자이너 특성은 SimpleCodeActivity.cs의 다음 예제와 같이 활동 자체의 정적 생성자에서 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="2ecd8-123">대화 상자 편집기</span><span class="sxs-lookup"><span data-stu-id="2ecd8-123">Dialog editor</span></span>

<span data-ttu-id="2ecd8-124">대화 상자 편집기 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-124">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="2ecd8-125"><xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>에서 파생되는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="2ecd8-126"><xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> 데이터 템플릿을 사용하여 생성자에서 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] data template.</span></span> <span data-ttu-id="2ecd8-127">이 값을 XAML로 만들 수 있지만 이 샘플에서는 코드로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-127">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="2ecd8-128">데이터 템플릿에는 속성 표에서 렌더링된 항목의 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>에 대한 데이터 컨텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="2ecd8-129">다음 코드에서는 이 컨텍스트가 `Value` 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="2ecd8-130">FilePickerEditor.cs에 대화 상자를 발생시키는 단추를 제공하도록 <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton>를 포함하는 것도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. <span data-ttu-id="2ecd8-131">대화 상자 표시를 처리하도록 디자이너 형식의 <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-131">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="2ecd8-132">이 샘플에서는 기본 <xref:System.Windows.Forms.FileDialog>가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. <span data-ttu-id="2ecd8-133">활동과 디자이너는 같은 어셈블리에 있기 때문에 활동 디자이너 특성은 SimpleCodeActivity.cs의 다음 예제와 같이 활동 자체의 정적 생성자에서 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2ecd8-134">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2ecd8-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="2ecd8-135">솔루션을 빌드한 다음 Workflow1.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-135">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="2ecd8-136">끌어서를 **SimpleCodeActivity** 디자이너 캔버스로 도구 상자에서.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="2ecd8-137">클릭 합니다 **SimpleCodeActivity** 연 다음 속성 표의 슬라이더 컨트롤에 있는 파일과 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ecd8-138">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2ecd8-139">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2ecd8-140">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ecd8-141">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ecd8-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`