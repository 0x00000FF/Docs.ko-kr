---
title: '방법: 간단한 Windows Forms 컨트롤 개발'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 457069cd7ac5af62e08115d84060c9c7fb25beee
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328142"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="6db4c-102">방법: 간단한 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="6db4c-102">How to: Develop a Simple Windows Forms Control</span></span>
<span data-ttu-id="6db4c-103">이 섹션에서는 사용자 지정 Windows Forms 컨트롤을 작성하는 주요 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="6db4c-104">이 연습에서 개발한 간단한 컨트롤의 맞춤을 사용 하면 해당 <xref:System.Windows.Forms.Control.Text%2A> 변경할 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="6db4c-105">이벤트를 발생시키거나 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-105">It does not raise or handle events.</span></span>  
  
### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="6db4c-106">간단한 사용자 지정 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6db4c-106">To create a simple custom control</span></span>  
  
1. <span data-ttu-id="6db4c-107"><xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 파생된 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control {}  
    ```  
  
2. <span data-ttu-id="6db4c-108">속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-108">Define properties.</span></span> <span data-ttu-id="6db4c-109">(필요는 없습니다 속성을 정의 하는 컨트롤에서 여러 속성을 상속 하기 때문에 <xref:System.Windows.Forms.Control> 하지만 대부분의 사용자 지정 컨트롤이 일반적으로 추가 속성을 정의 합니다.) 라는 속성을 정의 하는 다음 코드 조각 `TextAlignment` 하는 `FirstControl` 사용 하 여의 표시 형식을 지정 하는 <xref:System.Windows.Forms.Control.Text%2A> 속성에서 상속 됩니다 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="6db4c-110">속성을 정의하는 방법에 대한 자세한 내용은 [속성 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db4c-110">For more information about defining properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     <span data-ttu-id="6db4c-111">컨트롤의 시각적 표시를 변경 하는 속성을 설정 하면 호출 해야 합니다는 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 컨트롤을 다시 그리도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <xref:System.Windows.Forms.Control.Invalidate%2A> <span data-ttu-id="6db4c-112">기본 클래스에 정의 된 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-112">is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>  
  
3. <span data-ttu-id="6db4c-113">보호 된 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 에서 상속 된 메서드 <xref:System.Windows.Forms.Control> 컨트롤에 렌더링 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="6db4c-114">재정의 하지 않을 경우 <xref:System.Windows.Forms.Control.OnPaint%2A>, 컨트롤이 자신을 그릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="6db4c-115">다음 코드 조각에서 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 표시 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성에서 상속 됩니다 <xref:System.Windows.Forms.Control> 에서 지정 된 맞춤을 사용 하 여는 `alignmentValue` 필드.</span><span class="sxs-lookup"><span data-stu-id="6db4c-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4. <span data-ttu-id="6db4c-116">컨트롤의 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-116">Provide attributes for your control.</span></span> <span data-ttu-id="6db4c-117">특성을 사용하면 시각적 디자이너가 디자인 타임에 컨트롤과 해당 속성 및 이벤트를 적절하게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="6db4c-118">다음 코드 조각은 `TextAlignment` 속성에 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="6db4c-119">Visual Studio와 같은 디자이너는 <xref:System.ComponentModel.CategoryAttribute.Category%2A> (코드 조각에 표시 됨) 특성을 사용 하면 속성을 논리 범주 아래에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="6db4c-120"><xref:System.ComponentModel.DescriptionAttribute.Description%2A> 특성을 사용 하면 설명이 포함 된 문자열의 맨 아래에 표시 되는 **속성** 창 때는 `TextAlignment` 속성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="6db4c-121">특성에 대한 자세한 내용은 [구성 요소에 대한 디자인 타임 특성](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db4c-121">For more information about attributes, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5. <span data-ttu-id="6db4c-122">(선택 사항)컨트롤에 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="6db4c-123">컨트롤과 함께 리소스를 패키징하는 컴파일러 옵션(C#의 경우 `/res`)을 사용하여 컨트롤에 비트맵과 같은 리소스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="6db4c-124">런타임 시 리소스를 검색할 수의 메서드를 사용 하 여 <xref:System.Resources.ResourceManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="6db4c-125">리소스를 만들고 사용하는 방법에 대한 자세한 내용은 [데스크톱 앱의 리소스](../../resources/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db4c-125">For more information about creating and using resources, see the [Resources in Desktop Apps](../../resources/index.md).</span></span>  
  
6. <span data-ttu-id="6db4c-126">컨트롤을 컴파일하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-126">Compile and deploy your control.</span></span> <span data-ttu-id="6db4c-127">`FirstControl,`을 컴파일하고 배포하려면 다음 단계를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>  
  
    1.  <span data-ttu-id="6db4c-128">다음 샘플의 코드를 소스 파일(예: FirstControl.cs 또는 FirstControl.vb)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>  
  
    2.  <span data-ttu-id="6db4c-129">소스 코드를 어셈블리로 컴파일하고 애플리케이션의 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="6db4c-130">이를 수행하려면 소스 파일이 포함된 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>  
  
        ```console  
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```console 
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs  
        ```  
  
         <span data-ttu-id="6db4c-131">`/t:library` 컴파일러 옵션은 사용자가 만드는 어셈블리가 실행 파일이 아니라 라이브러리임을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="6db4c-132">`/out` 옵션은 어셈블리의 경로 및 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="6db4c-133">`/r` 옵션은 코드에 의해 참조되는 어셈블리의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="6db4c-134">이 예제에서는 애플리케이션에서만 사용할 수 있는 전용 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="6db4c-135">따라서 애플리케이션의 디렉터리에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="6db4c-136">배포하기 위한 컨트롤을 패키징하고 배포하는 방법에 대한 자세한 내용은 [배포](../../deployment/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db4c-136">For more information about packaging and deploying a control for distribution, see [Deployment](../../deployment/index.md).</span></span>  
  
 <span data-ttu-id="6db4c-137">다음 샘플은 `FirstControl`의 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="6db4c-138">컨트롤은 네임스페이스 `CustomWinControls`에서 따옴표로 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="6db4c-139">네임스페이스는 관련된 형식의 논리적 그룹화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="6db4c-140">새로운 또는 기존 네임스페이스에서 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="6db4c-141">C#에서 `using` 선언(Visual Basic의 경우 `Imports`)을 사용하면 형식의 정규화된 이름을 사용하지 않고 네임스페이스에서 형식에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="6db4c-142">다음 예제에서는 `using` 선언을 클래스에 액세스 하는 코드를 사용 하면 <xref:System.Windows.Forms.Control> 에서 <xref:System.Windows.Forms?displayProperty=nameWithType> 간단 <xref:System.Windows.Forms.Control> 정규화 된 이름을 사용 하는 대신 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="6db4c-143">양식에서 사용자 지정 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="6db4c-143">Using the Custom Control on a Form</span></span>  
 <span data-ttu-id="6db4c-144">다음 예제에서는 `FirstControl`을 사용하는 간단한 양식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="6db4c-145">`TextAlignment` 속성에 대해 각각 다른 값을 가진 세 개의 `FirstControl` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>  
  
#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="6db4c-146">이 샘플을 컴파일하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6db4c-146">To compile and run this sample</span></span>  
  
1. <span data-ttu-id="6db4c-147">소스 파일(SimpleForm.cs 또는 SimpleForms.vb)에 다음 예제의 코드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
2. <span data-ttu-id="6db4c-148">소스 파일을 포함하는 디렉터리에서 다음 명령을 실행하여 소스 코드를 실행 가능한 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>  
  
    ```console  
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```console 
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     <span data-ttu-id="6db4c-149">CustomWinControls.dll은 클래스를 포함 하는 어셈블리 `FirstControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="6db4c-150">이 어셈블리는 액세스하는 양식의 소스 파일과 동일한 디렉터리에 있어야 합니다(SimpleForm.cs 또는 SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="6db4c-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
3. <span data-ttu-id="6db4c-151">다음 명령을 사용하여 SimpleForm.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6db4c-151">Execute SimpleForm.exe using the following command.</span></span>  
  
    ```console
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="6db4c-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="6db4c-152">See also</span></span>

- [<span data-ttu-id="6db4c-153">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="6db4c-153">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="6db4c-154">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="6db4c-154">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
