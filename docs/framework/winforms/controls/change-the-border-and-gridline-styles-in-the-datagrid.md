---
title: '방법: Windows Forms DataGridView 컨트롤에서 테두리 및 눈금선 스타일 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: d24adb98c339f911d6bea0312bce4d4b4f198a61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224996"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 테두리 및 눈금선 스타일 변경
사용 하 여는 <xref:System.Windows.Forms.DataGridView> 컨트롤, 컨트롤의 테두리 및 사용자 환경을 개선 하는 눈금선의 모양을 사용자 지정할 수 있습니다. 모눈선 색과 컨트롤 내에 있는 셀의 테두리 스타일 외에도 컨트롤의 테두리 스타일을 수정할 수 있습니다. 또한 일반 셀, 행 머리글 셀 및 열 머리글 셀에 대 한 다른 셀 테두리 스타일을 적용할 수 있습니다.  
  
> [!NOTE]
>  눈금선 색만 사용 됩니다는 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, 및 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> 의 값을 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 열거형 및 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> 값은 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 열거형. 이러한 열거형의 다른 값을 사용 하 여 운영 체제에서 지정 된 색입니다. 비주얼 스타일이 Windows XP 및 Windows Server 2003 제품군을 통해 사용 되는 경우에 또한 합니다 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를는 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성 값이 사용 되지 않습니다.  
  
### <a name="to-change-the-gridline-color-programmatically"></a>프로그래밍 방식으로 눈금선 색을 변경 하려면  
  
-   <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>프로그래밍 방식으로 전체 DataGridView 컨트롤의 테두리 스타일을 변경 하려면  
  
-   <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 속성을 <xref:System.Windows.Forms.BorderStyle> 열거형 값 중 하나로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>DataGridView 셀의 테두리 스타일을 프로그래밍 방식으로 변경 하려면  
  
-   <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>및 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
