---
title: '방법: 간격 및 Windows Forms에서 ToolStrip 항목의 맞춤 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 2c9c60a3bfd78b7111b9cdff6a791d70c8e53c82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685065"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="040cc-102">방법: 간격 및 Windows Forms에서 ToolStrip 항목의 맞춤 변경</span><span class="sxs-lookup"><span data-stu-id="040cc-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="040cc-103">합니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤 크기 조정 간격 등의 레이아웃 기능을 완벽 하 게 지원 <xref:System.Windows.Forms.ToolStripItem> 의 서로 상대적인, 컨트롤 배열을 컨트롤에 <xref:System.Windows.Forms.ToolStrip>, 및 간격을 기준으로 컨트롤의는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="040cc-104">때문에 기본값인 합니다 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성은 `true`, 컨트롤의 크기가 자동으로 설정 하지 않으면를 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="040cc-105">ToolStripItem의 크기를 수동으로 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="040cc-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="040cc-106">설정 된 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false` 연결된 된 컨트롤에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="040cc-107">설정 된 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 관련 된 원하는 방식으로 속성 <xref:System.Windows.Forms.ToolStripItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="040cc-108">ToolStripItem의 간격을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="040cc-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="040cc-109">픽셀을 원하는 값을 삽입 합니다 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 연결된 된 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="040cc-110">값을 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 순서로 항목과 인접 항목 사이의 간격을 지정 하는 속성: 왼쪽, 위쪽, 오른쪽 및 아래입니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="040cc-111">오른쪽 ToolStrip에 toolstripitem을 가리키는 맞게</span><span class="sxs-lookup"><span data-stu-id="040cc-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="040cc-112">설정 된 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 연결된 된 컨트롤에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="040cc-113">기본적으로 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 로 설정 된 <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, 컨트롤의 왼쪽에 맞춰집니다는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="040cc-114">ToolStrip에서 ToolStrip 항목을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="040cc-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="040cc-115">설정 된 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성의 값을 <xref:System.Windows.Forms.ToolStripLayoutStyle> 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="040cc-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="040cc-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="040cc-116">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="040cc-117">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="040cc-117">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="040cc-118">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="040cc-118">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="040cc-119">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="040cc-119">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
