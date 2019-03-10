---
title: '연습: 시각적 상속 설명'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: aa4d18c0e3bbc2613502c7232771c57acc7f0dc8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721452"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="576b3-102">연습: 시각적 상속 설명</span><span class="sxs-lookup"><span data-stu-id="576b3-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="576b3-103">시각적 상속을 통해 기본 폼의 컨트롤을 보고 새 컨트롤을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="576b3-104">이 연습에서는 기본 폼을 만들고 클래스 라이브러리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="576b3-105">이 클래스 라이브러리를 다른 프로젝트로 가져와 기본 폼에서 상속하는 새 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="576b3-106">이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="576b3-107">기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="576b3-108">기본 폼의 파생 클래스가 수정할 수 있는 속성을 가진 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="576b3-109">기본 폼의 상속자가 수정할 수 없는 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="576b3-110">`BaseForm`에서 상속하는 폼을 포함하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="576b3-111">궁극적으로, 이 연습에서는 상속된 폼의 private 컨트롤과 protected 컨트롤 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="576b3-112">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="576b3-113">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="576b3-114">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="576b3-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="576b3-115">일부 컨트롤은 기본 폼에서의 시각적 상속을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="576b3-116">다음 컨트롤은 이 연습에 설명된 시나리오를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  <span data-ttu-id="576b3-117">상속된 폼의 이러한 컨트롤은 사용하는 한정자(`private`, `protected` 또는 `public`)에 관계없이 항상 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="576b3-118">시나리오 단계</span><span class="sxs-lookup"><span data-stu-id="576b3-118">Scenario Steps</span></span>  
 <span data-ttu-id="576b3-119">첫 번째 단계는 기본 폼을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="576b3-120">기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="576b3-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="576b3-121">**파일** 메뉴에서 선택 **새로 만들기**를 차례로 **프로젝트** 여는 **새 프로젝트** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="576b3-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="576b3-122">라는 Windows Forms 응용 프로그램을 만드는 `BaseFormLibrary`합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="576b3-123">표준 Windows Forms 응용 프로그램을 대신 클래스 라이브러리를 만들려는 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **BaseFormLibrary** 프로젝트 노드를 선택한 **속성**.</span><span class="sxs-lookup"><span data-stu-id="576b3-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="576b3-124">프로젝트에 대 한 속성을 변경 합니다 **출력 형식** 에서 **Windows 응용 프로그램** 하 **클래스 라이브러리**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="576b3-125">**파일** 메뉴 선택 **모두 저장** 파일과 프로젝트 기본 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="576b3-126">다음 두 절차에서는 기본 폼에 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="576b3-127">시각적 상속을 보여 주기 위해 단추의 `Modifiers` 속성을 설정하여 단추에 다양한 액세스 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="576b3-128">기본 폼의 상속자가 수정할 수 있는 단추를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="576b3-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="576b3-129">디자이너에서 **Form1**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="576b3-130">에 **모든 Windows Forms** 탭을 **도구 상자**를 두 번 클릭 **단추** 폼에 단추를 추가 하려면.</span><span class="sxs-lookup"><span data-stu-id="576b3-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="576b3-131">마우스를 사용하여 단추를 배치하고 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="576b3-132">속성 창에서 단추의 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="576b3-133">설정 된 **텍스트** 속성을 **Say Hello**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="576b3-134">설정 된 **(이름)** 속성을 **btnProtected**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="576b3-135">설정 된 **한정자** 속성을 **Protected**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-135">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="576b3-136">따라서에서 상속 하는 폼 **Form1** 속성을 수정 하려면 **btnProtected**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="576b3-137">두 번 클릭 합니다 **Say Hello** 에 대 한 이벤트 처리기를 추가 하려면 단추를 **클릭** 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="576b3-138">다음 코드 줄을 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="576b3-139">기본 폼의 상속자가 수정할 수 없는 단추를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="576b3-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="576b3-140">클릭 하 여 디자인 뷰로 전환 합니다 **Form1.vb [디자인], Form1.cs [Design] 또는 Form1.jsl [Design]** 코드 편집기를 초과 하거나 F7 키를 눌러 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="576b3-141">두 번째 단추를 추가하고 해당 속성을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="576b3-142">설정 된 **텍스트** 속성을 **Say Goodbye**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="576b3-143">설정 된 **(이름)** 속성을 **btnPrivate**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="576b3-144">설정 된 **한정자** 속성을 **개인**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="576b3-145">상속 하는 폼에 대 한 없게 **Form1** 속성을 수정 하려면 **btnPrivate**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="576b3-146">두 번 클릭 합니다 **Say Goodbye** 에 대 한 이벤트 처리기를 추가 하려면 단추를 **클릭** 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="576b3-147">다음 코드 줄을 이벤트 프로시저에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="576b3-148">**빌드** 메뉴 선택 **BaseForm 라이브러리 빌드** 클래스 라이브러리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="576b3-149">라이브러리가 빌드되고 나면 방금 만든 폼에서 상속하는 새 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="576b3-150">기본 폼에서 상속하는 폼을 포함하는 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="576b3-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="576b3-151">합니다 **파일** 메뉴에서 선택 **추가** 차례로 **새 프로젝트** 여는 **새 프로젝트 추가** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="576b3-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="576b3-152">라는 Windows Forms 응용 프로그램을 만드는 `InheritanceTest`합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="576b3-153">상속된 폼을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="576b3-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="576b3-154">**솔루션 탐색기**, 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 **추가**를 선택한 후 **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="576b3-155">**새 항목 추가** 대화 상자를 선택 합니다 **Windows Forms** 범주 (범주 목록이 표시) 하는 경우 선택한 후는 **상속 된 폼** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="576b3-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="576b3-156">기본 이름을 그대로 `Form2` 을 클릭 한 다음 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="576b3-157">에 **상속 선택** 대화 상자에서 **Form1** 에서 합니다 **BaseFormLibrary** 프로젝트의 양식에서 상속 하 고 클릭 **확인** .</span><span class="sxs-lookup"><span data-stu-id="576b3-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="576b3-158">양식을 만듭니다.이 **InheritanceTest** 프로젝트에서 양식에서 파생 되는 **BaseFormLibrary**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="576b3-159">상속 된 폼을 엽니다 (**Form2**)을 두 번 클릭 열려 있지 않으면 디자이너에서.</span><span class="sxs-lookup"><span data-stu-id="576b3-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="576b3-160">디자이너에서 상속 된 단추의 있는 기호 (![VisualBasicInheritanceSymbol screenshot](./media/vbinheritanceglyph.gif "vbInheritanceGlyph"))의 위쪽 모퉁이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](./media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="576b3-161">선택 된 **Say Hello** 단추 및 크기 조정 핸들을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="576b3-162">이 단추는 protected이므로 상속자가 이동하고, 크기를 조정하고, 캡션을 변경하고, 기타 수정 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="576b3-163">개인 선택 **Say Goodbye** 단추 및 크기 조정 핸들 없기는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="576b3-164">또한 합니다 **속성** 창에서이 단추의 속성은 수정할 수 없음을 나타내기 위해 회색으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="576b3-165">Visual C# 사용 중인 경우:</span><span class="sxs-lookup"><span data-stu-id="576b3-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="576b3-166">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Form1** 에 **InheritanceTest** 프로젝트를 선택한 다음 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="576b3-167">표시 되는 메시지 상자에서 클릭 **확인** 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="576b3-168">Program.cs 파일을 열고 `Application.Run(new Form1());` 줄을 `Application.Run(new Form2());`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="576b3-169">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 마우스 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="576b3-170">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **InheritanceTest** 프로젝트를 마우스 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="576b3-171">에 **InheritanceTest** 속성 페이지 설정 합니다 **시작 개체** 상속된 된 폼 되도록 (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="576b3-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="576b3-172">F5 키를 눌러 응용 프로그램을 실행하고 상속된 폼의 동작을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="576b3-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="576b3-173">Next Steps</span></span>  
 <span data-ttu-id="576b3-174">사용자 정의 컨트롤의 상속도 거의 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="576b3-175">새 클래스 라이브러리 프로젝트를 열고 사용자 정의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="576b3-176">구성 요소 컨트롤을 배치하고 프로젝트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="576b3-177">다른 새 클래스 라이브러리 프로젝트를 열고 컴파일된 클래스 라이브러리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="576b3-178">또한 상속된 된 컨트롤을 추가 해 보세요 (통해는 **새 항목 추가** 대화 상자) 프로젝트에 사용 하는 **상속 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="576b3-179">사용자 정의 컨트롤을 추가 하 고 변경 합니다 `Inherits` (`:` Visual C#) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="576b3-180">자세한 내용은 [방법: Windows Forms 상속](how-to-inherit-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="576b3-180">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576b3-181">참고자료</span><span class="sxs-lookup"><span data-stu-id="576b3-181">See also</span></span>
- [<span data-ttu-id="576b3-182">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="576b3-182">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="576b3-183">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="576b3-183">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="576b3-184">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="576b3-184">Windows Forms</span></span>](../index.md)
