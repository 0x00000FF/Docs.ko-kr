---
title: '방법: MDI 자식 양식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 83f94830eec1d82112719a48e8ea98e2503f4542
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124529"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="73f8b-102">방법: MDI 자식 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="73f8b-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="73f8b-103">MDI 자식 폼의 중요 한 요소는 [다중 문서 MDI (인터페이스) 응용 프로그램](multiple-document-interface-mdi-applications.md)같이 이러한 사용자 상호 작용의 중심 이므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="73f8b-104">다음 절차에서는 대부분의 워드프로세싱 응용 프로그램과 비슷하게 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 표시하는 MDI 자식 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="73f8b-105"><xref:System.Windows.Forms> 컨트롤을 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 다른 컨트롤이나 컨트롤 혼합으로 대체하면 다양한 가능성을 가진 MDI 자식 창(및 확장을 통해 MDI 응용 프로그램)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73f8b-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="73f8b-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="73f8b-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73f8b-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="73f8b-109">MDI 자식 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="73f8b-109">To create MDI child forms</span></span>  
  
1.  <span data-ttu-id="73f8b-110">새 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="73f8b-111">**속성 Windows** 폼에 대 한 설정 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`, 및 `WindowsState` 속성을 `Maximized`입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="73f8b-112">그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-112">This designates the form as an MDI container for child windows.</span></span>  
  
2.  <span data-ttu-id="73f8b-113">`Toolbox`에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="73f8b-114">설정 해당 `Text` 속성을 **파일**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-114">Set its `Text` property to **File**.</span></span>  
  
3.  <span data-ttu-id="73f8b-115">옆에 있는 줄임표 (...)를 **항목** 속성과 클릭 **추가** 두 자식 도구 스트립 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="73f8b-116">설정 합니다 `Text` 이러한 항목에 대 한 속성 **새로 만들기** 하 고 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4.  <span data-ttu-id="73f8b-117">**솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**를 선택한 후 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5.  <span data-ttu-id="73f8b-118">에 **새 항목 추가** 대화 상자에서 **Windows 폼** (Visual Basic 또는 Visual C#) 또는 **Windows Forms 응용 프로그램 (.NET)** (에서 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 합니다 에서 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-118">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="73f8b-119">에 **이름을** 상자에서 폼의 이름을 **Form2**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="73f8b-120">클릭 합니다 **열려** 프로젝트에 폼을 추가 하려면 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73f8b-121">이 단계에서 만든 MDI 자식 폼은 표준 Windows Form입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="73f8b-122">따라서 폼의 투명도를 제어할 수 있는 <xref:System.Windows.Forms.Form.Opacity%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="73f8b-123">그러나 <xref:System.Windows.Forms.Form.Opacity%2A> 속성은 최상위 창에 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="73f8b-124">그리기 문제가 발생할 수 있으므로 MDI 자식 폼에는 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="73f8b-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="73f8b-125">이 폼은 MDI 자식 폼에 대한 템플릿이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="73f8b-126">합니다 **Windows Forms 디자이너** 열리는지 **Form2**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6.  <span data-ttu-id="73f8b-127">**도구 상자**를 끌어를 **RichTextBox** 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7.  <span data-ttu-id="73f8b-128">에 **속성** 창에서 합니다 `Anchor` 속성을 **위쪽, 왼쪽** 및 `Dock` 속성을 **채우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="73f8b-129">이렇게 하면 폼의 크기를 조정하는 경우에도 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 MDI 자식 폼의 영역을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8.  <span data-ttu-id="73f8b-130">두 번 클릭 합니다 **새로 만들기** 만들려는 메뉴 항목을 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="73f8b-131">사용자가 클릭할 때 새 MDI 자식 폼을 만들려면 다음과 비슷한 코드를 삽입 합니다 **새로 만들기** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73f8b-132">다음 예제에서는 이벤트 처리기가 `MenuItem2`에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="73f8b-133">주의 응용 프로그램 아키텍처의 세부 사항에 따라 프로그램 **새로 만들기** 메뉴 항목 아닐 `MenuItem2`합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="73f8b-134">[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서 Form1.h의 맨 위에 다음 `#include` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="73f8b-135">맨 위에 있는 드롭다운 목록에서를 **속성** 창에 해당 하는 메뉴 스트립을 선택 합니다 **파일** 설정 하 고 메뉴 스트립을 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성 창에 <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="73f8b-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="73f8b-136">이렇게 하면 합니다 **창을** 활성 자식 창 옆에 있는 확인 표시가 있는 열린 MDI 자식 창의 목록을 유지 관리 하는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="73f8b-137">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-137">Press F5 to run the application.</span></span> <span data-ttu-id="73f8b-138">선택 하 여 **새로 만들기** 에서 **파일** 메뉴에서의 추적 유지 되는 새 MDI 자식 폼을 만들 수 있습니다 합니다 **창** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73f8b-139">MDI 자식 폼이 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)를 포함하고 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)가 있는 MDI 부모 폼 내에서 열린 경우 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성(및 필요에 따라 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성)을 설정했으면 메뉴 항목이 자동으로 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="73f8b-140">두 <xref:System.Windows.Forms.MainMenu> 구성 요소와 자식 폼의 모든 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성을 <xref:System.Windows.Forms.MenuMerge.MergeItems>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="73f8b-141">또한 두 메뉴의 메뉴 항목이 원하는 순서대로 표시되도록 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="73f8b-142">MDI 부모 폼을 닫을 경우 MDI 부모에 대한 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하기 전에 각 MDI 자식 폼에서 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="73f8b-143">MDI 자식의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 취소해도 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하지 않도록 방지되지는 않습니다. 그러나 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 <xref:System.ComponentModel.CancelEventArgs> 인수가 이제 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="73f8b-144"><xref:System.ComponentModel.CancelEventArgs> 인수를 `false`로 설정하여 MDI 부모 및 모든 MDI 자식 폼을 강제로 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73f8b-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f8b-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="73f8b-145">See also</span></span>

- [<span data-ttu-id="73f8b-146">MDI 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="73f8b-146">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="73f8b-147">방법: MDI 부모 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="73f8b-147">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="73f8b-148">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="73f8b-148">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="73f8b-149">방법: 활성 MDI 자식으로 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="73f8b-149">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="73f8b-150">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="73f8b-150">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
