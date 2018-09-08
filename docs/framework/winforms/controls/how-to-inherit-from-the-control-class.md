---
title: '방법: Control 클래스에서 상속'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: 1a0eea1930699ed85fcf0eaf184ba0aabe398d73
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137657"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="8ad8f-102">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="8ad8f-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="8ad8f-103">Windows Form에 사용 하 여 완전 한 사용자 지정 컨트롤을 만들려는 경우에서 상속 해야 하는 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="8ad8f-104">상속 하는 동안는 <xref:System.Windows.Forms.Control> 클래스는 수행한 자세한 계획 및 구현, 광범위 한 옵션을 사용 하 여도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="8ad8f-105">상속할 때 <xref:System.Windows.Forms.Control>, 컨트롤이 작동 되도록 하는 기본적인 기능을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="8ad8f-106">고유한 기능은 <xref:System.Windows.Forms.Control> 클래스 키보드 및 마우스를 통해 사용자 입력 처리, 컨트롤의 크기와 범위를 정의 창 핸들을 제공 및 메시지 처리 및 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="8ad8f-107">이 경우에는 컨트롤의 그래픽 인터페이스의 실제 렌더링인 그리기를 통합하거나 특정 사용자 상호 작용 기능을 통합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="8ad8f-108">사용자 지정 코드를 통해 이러한 모든 사항을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-108">You must provide all of these aspects through custom code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad8f-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8ad8f-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8ad8f-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-custom-control"></a><span data-ttu-id="8ad8f-112">사용자 지정 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8ad8f-112">To create a custom control</span></span>  
  
1.  <span data-ttu-id="8ad8f-113">새 **Windows 응용 프로그램** 또는 **Windows 컨트롤 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-113">Create a new **Windows Application** or **Windows Control Library** project.</span></span>  
  
2.  <span data-ttu-id="8ad8f-114">**프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-114">From the **Project** menu, choose **Add Class**.</span></span>  
  
3.  <span data-ttu-id="8ad8f-115">**새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-115">In the **Add New Item** dialog box, click **Custom Control**.</span></span>  
  
     <span data-ttu-id="8ad8f-116">새 사용자 지정 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="8ad8f-117">F7 키를 눌러 사용자 지정 컨트롤의 **코드 편집기**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-117">Press F7 to open the **Code Editor** for your custom control.</span></span>  
  
5.  <span data-ttu-id="8ad8f-118">찾을 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 호출을 제외 하 고 비어 있는 <xref:System.Windows.Forms.Control.OnPaint%2A> 기본 클래스의 메서드.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-118">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
6.  <span data-ttu-id="8ad8f-119">코드를 수정하여 컨트롤에 원하는 사용자 지정 그리기를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-119">Modify the code to incorporate any custom painting you want for your control.</span></span>  
  
     <span data-ttu-id="8ad8f-120">컨트롤의 그래픽을 렌더링하는 코드를 작성하는 방법에 대한 정보는 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-120">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
7.  <span data-ttu-id="8ad8f-121">컨트롤이 통합하는 사용자 지정 메서드, 속성 또는 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-121">Implement any custom methods, properties, or events that your control will incorporate.</span></span>  
  
8.  <span data-ttu-id="8ad8f-122">컨트롤을 저장하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad8f-122">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad8f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ad8f-123">See Also</span></span>  
 [<span data-ttu-id="8ad8f-124">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="8ad8f-124">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="8ad8f-125">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="8ad8f-125">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="8ad8f-126">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="8ad8f-126">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="8ad8f-127">방법: Windows Forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="8ad8f-127">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="8ad8f-128">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8ad8f-128">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="8ad8f-129">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="8ad8f-129">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
