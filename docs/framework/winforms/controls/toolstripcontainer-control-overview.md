---
title: ToolStripContainer 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: 59afb9de3a97545407fe96f5ded60faee9d9f725
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536343"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="31257-102">ToolStripContainer 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="31257-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="31257-103">A <xref:System.Windows.Forms.ToolStripContainer> 왼쪽, 오른쪽, 위쪽 및 아래쪽 면 배치 및 래프팅 할 패널이 있습니다 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="31257-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="31257-104">왼쪽 또는 오른쪽 <xref:System.Windows.Forms.ToolStripContainer>에 여러 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 배치하면 컨트롤이 세로로 쌓입니다.</span><span class="sxs-lookup"><span data-stu-id="31257-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="31257-105">위쪽 또는 아래쪽 <xref:System.Windows.Forms.ToolStripContainer>에 배치하면 가로로 쌓입니다.</span><span class="sxs-lookup"><span data-stu-id="31257-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="31257-106"><xref:System.Windows.Forms.ToolStripContainer>의 가운데 <xref:System.Windows.Forms.ToolStripContentPanel>을 사용하여 기존 컨트롤을 폼에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31257-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="31257-107">임의 또는 모든 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤은 디자인 타임에 직접 선택할 수 있고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31257-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="31257-108">각 패널은 <xref:System.Windows.Forms.ToolStripContainer> 는 확장 및 축소 가능 하 고 포함 된 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31257-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="31257-109">중요 한 ToolStripContainer 멤버</span><span class="sxs-lookup"><span data-stu-id="31257-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="31257-110">이름</span><span class="sxs-lookup"><span data-stu-id="31257-110">Name</span></span>|<span data-ttu-id="31257-111">설명</span><span class="sxs-lookup"><span data-stu-id="31257-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="31257-112">아래쪽 패널 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="31257-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="31257-113">나타내는 값을 가져오거나 여부의 아래쪽 패널에서 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31257-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="31257-114">왼쪽된 패널을 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="31257-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="31257-115">나타내는 값을 가져오거나 여부의 왼쪽된 창에서 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31257-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="31257-116">오른쪽 패널 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="31257-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="31257-117">나타내는 값을 가져오거나 여부의 오른쪽 패널에서 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31257-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="31257-118">위쪽 패널 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="31257-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="31257-119">나타내는 값을 가져오거나 여부의 위쪽 패널은 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31257-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31257-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31257-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
