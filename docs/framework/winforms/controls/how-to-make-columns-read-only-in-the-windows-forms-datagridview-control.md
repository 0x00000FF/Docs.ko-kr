---
title: '방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: a8b5c0f9492941cf0e01e016d9fb097e1df44d2e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731977"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정
일부 데이터는 편집할 수 없습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성 값은 사용자가 해당 열의 셀을 편집할 수 있는지 여부를 결정합니다. 완전히 읽기 전용 컨트롤을 확인 하는 방법에 대 한 정보를 참조 하세요 [방법: 행 추가 및 삭제 금지 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  도 참조 하세요 [방법: 열을 읽기 전용은 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에서](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\))합니다.  
  
### <a name="to-make-a-column-read-only-programmatically"></a>프로그래밍 방식으로 열을 읽기 전용으로 설정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `CompanyName`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
