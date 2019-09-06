---
title: '연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4fd1f1dc0c2c0ad9ae2009ed592e48b8eeaa2783
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373681"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="367f3-102">연습: 표준 형식의 컬렉션 Serialize</span><span class="sxs-lookup"><span data-stu-id="367f3-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="367f3-103">사용자 지정 컨트롤은 컬렉션을 속성으로 노출 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="367f3-104">이 연습에서는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 클래스를 사용 하 여 디자인 타임에 컬렉션이 serialize 되는 방법을 제어 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="367f3-105">컬렉션 속성에 값을 적용 하면 속성이 serialize 됩니다. <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content></span><span class="sxs-lookup"><span data-stu-id="367f3-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="367f3-106">이 항목의 코드를 단일 목록으로 복사하려면 [방법: DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))를 사용 하 여 표준 형식의 컬렉션을 Serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="367f3-107">전제 조건</span><span class="sxs-lookup"><span data-stu-id="367f3-107">Prerequisites</span></span>

<span data-ttu-id="367f3-108">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="367f3-109">Serializable 컬렉션을 사용 하 여 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="367f3-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="367f3-110">첫 번째 단계는 serialize 할 수 있는 컬렉션을 속성으로 포함 하는 컨트롤을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="367f3-111">**속성** 창에서 액세스할 수 있는 **컬렉션 편집기**를 사용 하 여이 컬렉션의 콘텐츠를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="367f3-112">Visual Studio에서 Windows 컨트롤 라이브러리 프로젝트를 만들고 이름을 **SerializationDemoControlLib**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="367f3-113">이름을 `UserControl1` 로`SerializationDemoControl`바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="367f3-114">자세한 내용은 [코드 기호 이름 바꾸기 리팩터링](/visualstudio/ide/reference/rename)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="367f3-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="367f3-115">**속성** 창에서 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 속성의 값을 **10**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="367f3-116">에 컨트롤 <xref:System.Windows.Forms.TextBox> 을 추가 합니다.`SerializationDemoControl`</span><span class="sxs-lookup"><span data-stu-id="367f3-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="367f3-117"><xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="367f3-118">**속성** 창에서 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="367f3-119">속성</span><span class="sxs-lookup"><span data-stu-id="367f3-119">Property</span></span>|<span data-ttu-id="367f3-120">다음으로 변경</span><span class="sxs-lookup"><span data-stu-id="367f3-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="367f3-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="367f3-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="367f3-122">**결합**</span><span class="sxs-lookup"><span data-stu-id="367f3-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="367f3-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="367f3-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="367f3-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="367f3-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="367f3-125">**코드 편집기**에서 이름이 `stringsValue` `SerializationDemoControl`인 문자열 배열 필드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="367f3-126">에서 속성 `Strings` 을 정의 합니다. `SerializationDemoControl`</span><span class="sxs-lookup"><span data-stu-id="367f3-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="367f3-127"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값은 컬렉션의 serialization을 활성화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="367f3-128">**F5** 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="367f3-129"><xref:System.Windows.Forms.PropertyGrid> **UserControl 테스트 컨테이너**의에서 **Strings** 속성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="367f3-130">**Strings** 속성을 선택한 다음 줄임표 (![Visual Studio](./media/visual-studio-ellipsis-button.png)속성 창의 줄임표 단추 (...)) 단추를 선택 하 여 **문자열 컬렉션 편집기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="367f3-131">**문자열 컬렉션 편집기**에 여러 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="367f3-132">각 문자열의 끝에서 **enter** 키를 눌러 각 문자열을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="367f3-133">문자열 입력을 마치면 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="367f3-134">입력 한 문자열이의에 표시 <xref:System.Windows.Forms.TextBox> `SerializationDemoControl`됩니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="367f3-135">컬렉션 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="367f3-135">Serialize a collection property</span></span>

<span data-ttu-id="367f3-136">컨트롤의 serialization 동작을 테스트 하려면 폼에 추가 하 고 **컬렉션 편집기**를 사용 하 여 컬렉션의 내용을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="367f3-137">**Windows Forms 디자이너** 에서 코드를 내보내는 특수 한 디자이너 파일을 살펴보면 serialize 된 컬렉션 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="367f3-138">Windows 응용 프로그램 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="367f3-139">프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="367f3-140">**도구 상자**에서 **SerializationDemoControlLib Components**라는 탭을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="367f3-141">이 탭에서을 찾을 `SerializationDemoControl`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="367f3-142">자세한 내용은 [연습: 도구 상자에 사용자 지정 구성 요소](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="367f3-143">폼에 `SerializationDemoControl` 를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="367f3-144">속성 창 `Strings` 에서 속성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="367f3-145">속성을 클릭 한 다음, Visual Studio](./media/visual-studio-ellipsis-button.png)의![속성 창에 있는 줄임표 단추 (...) 단추를 클릭 하 여 **문자열 컬렉션 편집기**를 엽니다. `Strings`</span><span class="sxs-lookup"><span data-stu-id="367f3-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="367f3-146">**문자열 컬렉션 편집기**에 여러 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="367f3-147">각 문자열의 끝에서 **enter** 키를 눌러 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="367f3-148">문자열 입력을 마치면 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="367f3-149">입력 한 문자열이의에 표시 <xref:System.Windows.Forms.TextBox> `SerializationDemoControl`됩니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="367f3-150">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="367f3-151">**Form1** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-151">Open the **Form1** node.</span></span> <span data-ttu-id="367f3-152">아래에는 **Form1.Designer.cs 또는** 라는 파일이 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="367f3-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="367f3-153">이 파일은 **Windows Forms 디자이너** 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 내보내는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="367f3-154">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="367f3-155">**Windows Form 디자이너에서 생성 한 코드** 라는 영역을 열고 **serializationDemoControl1**레이블이 지정 된 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="367f3-156">이 레이블 아래에는 컨트롤의 serialize 된 상태를 나타내는 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="367f3-157">5 단계에서 입력 한 문자열은 `Strings` 속성에 대 한 할당에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="367f3-158">및 Visual Basic의 C# 다음 코드 예제에서는 "red", "주황색" 및 "노란색" 문자열을 입력 했을 때 표시 되는 것과 유사한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="367f3-159">**코드 편집기**에서 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> `Strings` 속성의 값을로 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="367f3-160">솔루션을 다시 빌드하고 3 단계와 4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="367f3-161">이 경우 **Windows Forms 디자이너** 는 `Strings` 속성에 대 한 할당을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="367f3-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="367f3-162">Next steps</span></span>

<span data-ttu-id="367f3-163">표준 형식의 컬렉션을 serialize 하는 방법을 알고 있으면 사용자 지정 컨트롤을 디자인 타임 환경에 더 많이 통합 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="367f3-164">다음 항목에서는 사용자 지정 컨트롤의 디자인 타임 통합을 향상 시키는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="367f3-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="367f3-165">[디자인 타임 아키텍처](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="367f3-165">[Design-Time Architecture](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="367f3-166">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="367f3-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="367f3-167">[디자이너 직렬화 개요](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="367f3-167">[Designer Serialization Overview](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="367f3-168">연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="367f3-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="367f3-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="367f3-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="367f3-170">연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자 자동 채우기</span><span class="sxs-lookup"><span data-stu-id="367f3-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
