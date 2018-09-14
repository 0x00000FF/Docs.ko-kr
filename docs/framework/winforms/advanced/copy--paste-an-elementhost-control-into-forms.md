---
title: '연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778476"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="5edf7-102">연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="5edf7-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="5edf7-103">이 연습에서는 Windows Forms 간에 WPF(Windows Presentation Foundation) 컨트롤을 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="5edf7-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5edf7-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-105">Create the project.</span></span>  
  
-   <span data-ttu-id="5edf7-106">WPF 컨트롤을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5edf7-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5edf7-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5edf7-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5edf7-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5edf7-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="5edf7-110">Prerequisites</span></span>  
 <span data-ttu-id="5edf7-111">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="5edf7-112">.</span><span class="sxs-lookup"><span data-stu-id="5edf7-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5edf7-113">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="5edf7-113">Creating the Project</span></span>  
 <span data-ttu-id="5edf7-114">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5edf7-115">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="5edf7-116">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5edf7-116">To create the project</span></span>  
  
-   <span data-ttu-id="5edf7-117">Visual Basic 또는 Visual C#에서 새 Windows Forms 응용 프로그램 프로젝트를 만들 `CopyElementHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="5edf7-118">WPF 컨트롤 복사</span><span class="sxs-lookup"><span data-stu-id="5edf7-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="5edf7-119">프로젝트에 WPF 컨트롤을 추가한 후 프로젝트의 다른 폼에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="5edf7-120">WPF 컨트롤을 복사하려면</span><span class="sxs-lookup"><span data-stu-id="5edf7-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="5edf7-121">새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="5edf7-122">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="5edf7-123">자세한 내용은 [연습: 만드는 새 WPF 콘텐츠 디자인 타임에 Windows Forms에서](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="5edf7-124">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="5edf7-125">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="5edf7-126">합니다 **도구 상자**의 인스턴스를 끌어 `UserControl1` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="5edf7-127">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="5edf7-128">`elementHost1`을 선택하고 Ctrl+C를 눌러 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="5edf7-129">새 Windows Form을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="5edf7-130">폼 형식의 기본 이름인 `Form2`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="5edf7-131">Windows Forms 디자이너에서 `Form2`를 열고 Ctrl+V를 눌러 `elementHost1`의 복사본을 폼에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="5edf7-132">`Form2` 클래스의 전용 필드이므로 복사된 컨트롤의 이름도 `elementHost1`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="5edf7-133">`Form1` 클래스에서 `elementHost1`과 이름 충돌이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5edf7-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edf7-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5edf7-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="5edf7-135">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5edf7-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="5edf7-136">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="5edf7-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="5edf7-137">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="5edf7-137">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
