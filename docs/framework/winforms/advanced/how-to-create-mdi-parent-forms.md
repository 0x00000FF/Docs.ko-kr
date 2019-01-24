---
title: '방법: MDI 부모 폼 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 1cc3d813b77ddf8220242f4a1dfc7fe39f9cb520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512569"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="64383-102">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="64383-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="64383-103">이 항목에서는 <xref:System.Windows.Forms.MainMenu> 컨트롤로 대체된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="64383-104"><xref:System.Windows.Forms.MainMenu> 컨트롤은 이전 버전과의 호환성을 유지하고 원하는 경우 이후에 사용할 수 있도록 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="64383-105">사용 하 여 부모 폼을 MDI 만들기에 대 한 자세한를 <xref:System.Windows.Forms.MenuStrip>를 참조 하세요 [방법: MenuStrip이 포함 된 MDI 창 목록 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="64383-106">MDI(다중 문서 인터페이스) 부모 폼은 MDI(다중 문서 인터페이스) 애플리케이션의 기반이 되는 요소로,</span><span class="sxs-lookup"><span data-stu-id="64383-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="64383-107">사용자가 MDI 애플리케이션과 상호 작용하는 하위 창인 MDI 자식 창을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="64383-108">MDI 부모 폼은 Windows Forms 디자이너에서 그리고 프로그래밍 방식으로 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="64383-109">디자인 타임에 MDI 부모 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="64383-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="64383-110">Windows 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64383-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="64383-111">에 **속성** 창에서 설정 합니다 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="64383-112">그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64383-113">**속성** 창에서 속성을 설정하는 중에 원하는 경우 `WindowState` 속성을 **Maximized**(최대화)로 설정할 수도 있습니다. 부모 양식을 최대화하면 MDI 자식 창을 가장 쉽게 조작할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="64383-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="64383-114">또한 MDI 부모 폼에는 <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> 속성을 사용하여 설정하는 배경색이 아니라 Windows 시스템 제어판에 설정된 시스템 색이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="64383-115">**도구 상자**에서 **MenuStrip** 컨트롤을 양식으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="64383-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="64383-116">**텍스트** 속성을 **새로 만들기(&N)** 및 **닫기(&C)** 라는 하위 항목이 있는 **파일(&F)** 로 설정하여 최상위 메뉴 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64383-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="64383-117">**창(&W)** 이라는 최상위 메뉴 항목도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64383-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="64383-118">런타임에 첫 번째 메뉴가 작성되고 메뉴 항목은 숨겨지며 두 번째 메뉴는 열려 있는 MDI 자식 창을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="64383-119">이제 MDI 부모 창이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="64383-120">**F5** 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-120">Press **F5** to run the application.</span></span> <span data-ttu-id="64383-121">MDI 부모 폼 내에서 작동 하는 MDI 자식 창을 만드는 방법에 대 한 내용은 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64383-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="64383-122">See also</span></span>
- [<span data-ttu-id="64383-123">MDI(다중 문서 인터페이스) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="64383-123">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="64383-124">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="64383-124">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="64383-125">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="64383-125">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="64383-126">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="64383-126">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="64383-127">방법: MDI 자식 폼 정렬</span><span class="sxs-lookup"><span data-stu-id="64383-127">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
