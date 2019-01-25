---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: e216a91a612c5d4370d5786492426f757f39a262
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658093"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b9f2b-102">방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="b9f2b-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b9f2b-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 열 다시 정렬을 사용하도록 설정하면 사용자가 마우스로 열 머리글을 끌어서 열을 새 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="b9f2b-104"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성 값은 사용자가 열을 다른 위치로 이동할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="b9f2b-105">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="b9f2b-106">또한 참조 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="b9f2b-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="b9f2b-107">프로그래밍 방식으로 열 다시 정렬을 사용하도록 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="b9f2b-108"><xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9f2b-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b9f2b-109">Compiling the Code</span></span>  
 <span data-ttu-id="b9f2b-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f2b-110">This example requires:</span></span>  
  
-   <span data-ttu-id="b9f2b-111">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b9f2b-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="b9f2b-112"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="b9f2b-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f2b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b9f2b-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b9f2b-114">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="b9f2b-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="b9f2b-115">방법: Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="b9f2b-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
