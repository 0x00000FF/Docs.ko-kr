---
title: '방법: Windows Forms에 컨트롤 고정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 8de22ae6667446620867f3c15aac3c4af65582bf
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253632"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="f10db-102">방법: Windows Forms에 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="f10db-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="f10db-103">Windows 응용 프로그램의 사용자 인터페이스 (UI)를 디자인할 때 수행 하지 않도록 이동 하거나 다른 속성을 설정 하는 경우 크기를 조정할 수 있도록 올바르게 배치 되 면 컨트롤을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="f10db-104">또한 잠금 및 폼에 한 번에 여러 컨트롤을 사용 하 여 양식을 하는 데 도움이 되는 모든 컨트롤을 잠금 해제 하거나 개별 컨트롤을 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="f10db-105">하려는 양식의 모든 컨트롤을 배치 했으면, 잘못 된 이동을 방지 하기 위해 모든에서 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f10db-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f10db-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f10db-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f10db-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="f10db-109">컨트롤을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="f10db-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="f10db-110">에 **속성** 창 클릭 합니다 **잠금** 속성을 선택 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="f10db-111">(이름을 두 번의 속성 설정을 전환 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f10db-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="f10db-112">또는 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 선택 **잠금 컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f10db-113">컨트롤을 잠그면 디자인 화면에서 새 크기 또는 위치를 끌어 올 하 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="f10db-114">그러나 변경할 수 있습니다 크기를 이용 하 여 컨트롤의 위치를 **속성** 창 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="f10db-115">양식의 모든 컨트롤을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="f10db-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="f10db-116">**형식** 메뉴 선택 **잠금 컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f10db-117">이 명령은 폼 컨트롤 이므로 폼의 크기를 뿐만 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="f10db-118">모두 잠금 해제 하려면 잠긴 폼의 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f10db-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="f10db-119">**형식** 메뉴 선택 **잠금 컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="f10db-120">양식에서 이전에 잠긴된 모든 컨트롤은 이제 잠금 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="f10db-121">잠긴된 컨트롤을 개별적으로 잠금을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="f10db-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="f10db-122">에 **속성** 창 클릭 합니다 **잠금** 속성을 선택 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f10db-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="f10db-123">(이름을 두 번의 속성 설정을 전환 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f10db-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10db-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f10db-124">See Also</span></span>  
 [<span data-ttu-id="f10db-125">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f10db-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="f10db-126">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f10db-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="f10db-127">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="f10db-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="f10db-128">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f10db-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="f10db-129">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f10db-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
