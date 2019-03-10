---
title: '방법: Windows Forms의 ToolStrip 오버플로 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 53f610a728925d454a8833a49e705818f027aec5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707276"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="318f1-102">방법: Windows Forms의 ToolStrip 오버플로 관리</span><span class="sxs-lookup"><span data-stu-id="318f1-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="318f1-103">경우에 있는 모든 항목이 <xref:System.Windows.Forms.ToolStrip> 제어 할당된 된 공간에 맞지 않는에서 오버플로 기능을 사용할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStrip> 특정의 오버플로 동작을 결정 하 고 <xref:System.Windows.Forms.ToolStripItem>s.</span><span class="sxs-lookup"><span data-stu-id="318f1-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="318f1-104">추가 하는 경우 <xref:System.Windows.Forms.ToolStripItem>에 할당 된 것 보다 더 많은 공간이 필요는 <xref:System.Windows.Forms.ToolStrip> 폼의 현재 크기를 지정를 <xref:System.Windows.Forms.ToolStripOverflowButton> 에 자동으로 표시 되는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="318f1-105"><xref:System.Windows.Forms.ToolStripOverflowButton> 나타납니다 오버플로 드롭다운 메뉴에 오버플로가 활성화 된 항목 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="318f1-106">이렇게 하면 사용자 지정 하 고 우선 순위를 지정할 수 있습니다 하는 방법에 <xref:System.Windows.Forms.ToolStrip> 항목 다양 한 폼 크기에 맞게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="318f1-107">사용 하 여 오버플로 나뉩니다 때에 해당 항목의 모양을 변경할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 하 고 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="318f1-108">더 디자인 타임 또는 런타임에 폼을 확대 하는 경우 <xref:System.Windows.Forms.ToolStripItem>주에 s를 표시할 수 있습니다 <xref:System.Windows.Forms.ToolStrip> 고 <xref:System.Windows.Forms.ToolStripOverflowButton> 폼의 크기를 줄일 때까지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="318f1-109">ToolStrip 컨트롤에는 오버플로 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="318f1-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="318f1-110">있는지 확인 합니다 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 속성으로 설정 되지 않은 `false` 에 대 한는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="318f1-111">기본값은 `True`입니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-111">The default is `True`.</span></span>

     <span data-ttu-id="318f1-112">때 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 는 `True` (기본값)를 <xref:System.Windows.Forms.ToolStripItem> 드롭 다운 오버플로 메뉴로 보낼 때 내용의 <xref:System.Windows.Forms.ToolStripItem> 가로 너비를 초과 <xref:System.Windows.Forms.ToolStrip> 높이의 세로 <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="318f1-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="318f1-113">특정 toolstripitem을 가리키는의 오버플로 동작을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="318f1-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="318f1-114">설정 합니다 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 의 속성은 <xref:System.Windows.Forms.ToolStripItem> 를 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="318f1-115">가능성은 `Always`하십시오 `Never`, 및 `AsNeeded`합니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="318f1-116">기본값은 `AsNeeded`입니다.</span><span class="sxs-lookup"><span data-stu-id="318f1-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="318f1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="318f1-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="318f1-118">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="318f1-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="318f1-119">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="318f1-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="318f1-120">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="318f1-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
