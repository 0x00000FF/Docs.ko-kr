---
title: '방법: 기존 Windows Forms 컨트롤에서 상속'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0571bd6b169b94b1626bffb0d0793bbb22a93ba0
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015861"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="990c0-102">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="990c0-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="990c0-103">기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="990c0-104">기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="990c0-105">예를 들어에서 <xref:System.Windows.Forms.Button>상속 된 컨트롤을 만든 경우 새 컨트롤은 표준 <xref:System.Windows.Forms.Button> 컨트롤과 똑같이 표시 되 고 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="990c0-106">그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="990c0-107">일부 컨트롤에서는 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의 하 여 상속 된 컨트롤의 시각적 모양을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="990c0-108">상속된 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="990c0-108">To create an inherited control</span></span>

1. <span data-ttu-id="990c0-109">Visual Studio에서 새 **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

2. <span data-ttu-id="990c0-110">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-110">From the **Project** menu, choose **Add New Item**.</span></span>

     <span data-ttu-id="990c0-111">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-111">The **Add New Item** dialog box appears.</span></span>

3. <span data-ttu-id="990c0-112">**새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

     <span data-ttu-id="990c0-113">새 사용자 지정 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="990c0-114">다음을 사용 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="990c0-114">If you using:</span></span>

   - <span data-ttu-id="990c0-115">Visual Basic **솔루션 탐색기**맨 위에서 **모든 파일 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="990c0-116">CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
   - <span data-ttu-id="990c0-117">C#코드 편집기에서 CustomControl1.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

6. <span data-ttu-id="990c0-118">에서 <xref:System.Windows.Forms.Control>상속 되는 클래스 선언을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

7. <span data-ttu-id="990c0-119">기본 클래스를 상속하려는 컨트롤로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="990c0-120">예를 들어에서 <xref:System.Windows.Forms.Button>상속 하려는 경우 클래스 선언을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

8. <span data-ttu-id="990c0-121">Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="990c0-122">코드 편집기에서 CustomControl1.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-122">Open CustomControl1.vb in the Code Editor.</span></span>

9. <span data-ttu-id="990c0-123">컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-123">Implement any custom methods or properties that your control will incorporate.</span></span>

10. <span data-ttu-id="990c0-124">컨트롤의 그래픽 모양을 수정 하려면 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="990c0-125">재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 하면 모든 컨트롤의 모양을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="990c0-126">Windows에서 수행 하는 모든 그리기 작업 (예: <xref:System.Windows.Forms.TextBox>)이 있는 컨트롤은 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출 하지 않으므로 사용자 지정 코드를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="990c0-127"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 사용할 수 있는지 확인 하려면 수정 하려는 특정 컨트롤에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="990c0-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="990c0-128">모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](controls-to-use-on-windows-forms.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990c0-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="990c0-129">컨트롤이 멤버 메서드로 <xref:System.Windows.Forms.Control.OnPaint%2A> 나열 되지 않은 경우이 메서드를 재정의 하 여 모양을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="990c0-130">사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990c0-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

11. <span data-ttu-id="990c0-131">컨트롤을 저장하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="990c0-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="990c0-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="990c0-132">See also</span></span>

- [<span data-ttu-id="990c0-133">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="990c0-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="990c0-134">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="990c0-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="990c0-135">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="990c0-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="990c0-136">방법: Windows Forms에 대 한 Author 컨트롤</span><span class="sxs-lookup"><span data-stu-id="990c0-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="990c0-137">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="990c0-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="990c0-138">연습: Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="990c0-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
