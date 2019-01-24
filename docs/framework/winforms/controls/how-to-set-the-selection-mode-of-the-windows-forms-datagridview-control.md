---
title: '방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 65fb7360d45baea4fff20d06316d3955f0064207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539742"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="eabc5-102">방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정</span><span class="sxs-lookup"><span data-stu-id="eabc5-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="eabc5-103">다음 코드 예제에서는 구성 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView> 컨트롤 자동으로 한 행 내에서 아무 곳 이나 클릭 하 여 전체 행을 선택한 다음 이므로 한 번에 하나의 행을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabc5-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eabc5-104">예제</span><span class="sxs-lookup"><span data-stu-id="eabc5-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eabc5-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="eabc5-105">Compiling the Code</span></span>  
 <span data-ttu-id="eabc5-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eabc5-106">This example requires:</span></span>  
  
-   <span data-ttu-id="eabc5-107">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="eabc5-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="eabc5-108"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="eabc5-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabc5-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="eabc5-109">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="eabc5-110">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="eabc5-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="eabc5-111">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="eabc5-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
