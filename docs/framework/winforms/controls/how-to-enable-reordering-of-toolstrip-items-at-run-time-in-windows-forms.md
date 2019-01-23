---
title: '방법: 런타임에 Windows Forms에서 ToolStrip 항목 다시 정렬 활성화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 0b3662a700d897607780e8d5032c498faff97753
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577021"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="981c8-102">방법: 런타임에 Windows Forms에서 ToolStrip 항목 다시 정렬 활성화</span><span class="sxs-lookup"><span data-stu-id="981c8-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="981c8-103">다시 정렬 하려면 사용자가 수행할 수 있습니다 <xref:System.Windows.Forms.ToolStripItem> 컨트롤을 <xref:System.Windows.Forms.ToolStrip>입니다.</span><span class="sxs-lookup"><span data-stu-id="981c8-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="981c8-104">런타임 시 toolstripitem을 가리키는 재배열을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="981c8-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="981c8-105"><xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="981c8-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="981c8-106">기본적으로 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="981c8-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="981c8-107">런타임 시 사용자를 누르고 ALT 키와 마우스 왼쪽된 단추 끌어서를 <xref:System.Windows.Forms.ToolStripItem> 에서 다른 위치로 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="981c8-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="981c8-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="981c8-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="981c8-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="981c8-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="981c8-110">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="981c8-110">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="981c8-111">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="981c8-111">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
