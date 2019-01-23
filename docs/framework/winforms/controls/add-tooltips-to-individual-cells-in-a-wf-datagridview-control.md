---
title: '방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: baa6f79f2e0d454412992d9c951734a3437a96cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517645"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="50eef-102">방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가</span><span class="sxs-lookup"><span data-stu-id="50eef-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="50eef-103">기본적으로 도구 설명의 값을 표시 하 되 <xref:System.Windows.Forms.DataGridView> 너무 작아서 전체 내용을 표시할 수 없는 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="50eef-104">그러나에 개별 셀에 대 한 도구 설명 텍스트 값을 설정 하려면이 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="50eef-105">셀에 대 한 추가 정보를 표시 하거나 셀 내용에 대 한 대체 설명을 사용자에 게 제공할 수에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="50eef-106">예를 들어 상태 아이콘을 표시 하는 행에 있는 경우 도구 설명을 사용 하 여 텍스트 설명을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="50eef-107">셀 수준 도구 설명의 표시를 설정 하 여 비활성화할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="50eef-108">셀 도구 설명을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="50eef-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="50eef-109"><xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50eef-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="50eef-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="50eef-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-111">This example requires:</span></span>  
  
-   <span data-ttu-id="50eef-112">A <xref:System.Windows.Forms.DataGridView> 라는 컨트롤 `dataGridView1` 라는 열이 포함 된 `Rating` 네 개의 별표를 통해 하나의 문자열 값을 표시 ("\*") 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="50eef-113"><xref:System.Windows.Forms.DataGridView.CellFormatting> 컨트롤의 예제와 같이 이벤트 처리기 메서드를 사용 하 여 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="50eef-114"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="50eef-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="50eef-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="50eef-115">Robust Programming</span></span>  
 <span data-ttu-id="50eef-116">바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 외부 데이터 원본에 대 한 제어 또는 가상 모드 구현 하 여 사용자 고유의 데이터 소스를 제공 하 고, 성능 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="50eef-117">많은 양의 데이터를 작업할 때 성능 저하를 방지, 처리 합니다 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 설정이 아닌 이벤트는 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 여러 셀의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="50eef-118">처리할 때이 이벤트는 셀의 값을 가져올 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 이벤트를 발생 시키는 속성과 값을 반환 합니다 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> 속성으로 지정한 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="50eef-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50eef-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="50eef-119">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="50eef-120">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="50eef-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
