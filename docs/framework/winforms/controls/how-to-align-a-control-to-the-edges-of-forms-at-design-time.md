---
title: '방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 513029c1bd5cc4af52fcee97f7fab961729e613c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389057"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="5bf0d-102">방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="5bf0d-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>
<span data-ttu-id="5bf0d-103">설정 하 여 폼의 가장자리에 맞춰서 컨트롤을 정렬할 수 있게 된 <xref:System.Windows.Forms.Control.Dock%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A>.</span></span> <span data-ttu-id="5bf0d-104">이 속성은 양식에서 컨트롤의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="5bf0d-105"><xref:System.Windows.Forms.Control.Dock%2A> 속성은 다음 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="5bf0d-106">설정</span><span class="sxs-lookup"><span data-stu-id="5bf0d-106">Setting</span></span>|<span data-ttu-id="5bf0d-107">컨트롤에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="5bf0d-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="5bf0d-108">양식의 아래쪽에 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="5bf0d-109">양식의 나머지 공간을 모두 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="5bf0d-110">양식의 왼쪽에 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="5bf0d-111">지정 된 위치에 표시를 도킹 하지 않고 해당 <xref:System.Windows.Forms.Control.Location%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="5bf0d-112">컨트롤을 양식의 오른쪽에 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="5bf0d-113">양식의 위쪽에 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="5bf0d-114">또한 코드에서 이러한 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-114">These values can also be set in code.</span></span> <span data-ttu-id="5bf0d-115">자세한 내용은 [방법: 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-115">For more information, see [How to: Align a Control to the Edges of Forms](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bf0d-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5bf0d-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5bf0d-118">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="5bf0d-119">디자인 타임에 컨트롤에 대 한 Dock 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5bf0d-119">To set the Dock property for your control at design time</span></span>  
  
1.  <span data-ttu-id="5bf0d-120">Windows Forms 디자이너에서 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-120">In the Windows Forms Designer, select your control.</span></span>  
  
2.  <span data-ttu-id="5bf0d-121">에 **속성** 창에서 클릭 드롭다운 목록 상자 옆에는 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-121">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="5bf0d-122">여섯 개의 사용 가능한 그래픽 인터페이스 <xref:System.Windows.Forms.Control.Dock%2A> 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-122">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>  
  
3.  <span data-ttu-id="5bf0d-123">적절 한 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-123">Choose the appropriate setting.</span></span>  
  
4.  <span data-ttu-id="5bf0d-124">설정에서 지정한 방식으로 컨트롤을 도킹 이제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-124">Your control will now dock in the manner specified by the setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf0d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bf0d-125">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5bf0d-126">방법: 컨트롤을 폼의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="5bf0d-126">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 [<span data-ttu-id="5bf0d-127">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5bf0d-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="5bf0d-128">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="5bf0d-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [<span data-ttu-id="5bf0d-129">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5bf0d-129">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="5bf0d-130">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5bf0d-130">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="5bf0d-131">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5bf0d-131">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="5bf0d-132">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5bf0d-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="5bf0d-133">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="5bf0d-133">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
