---
title: '방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: 9f579720b4f3ff561ecd807e09db8d464abc9001
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664590"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.
때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다. <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성은 컨트롤 아래쪽에 새 레코드에 대한 행이 있는지를 나타내는 반면, <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성은 행을 제거할 수 있는지를 나타냅니다. 다음 코드 예제에서는 이들 속성을 사용하고 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> 속성을 설정하여 컨트롤을 전체적으로 읽기 전용으로 지정합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다. 또한 참조 [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤 디자이너를 사용 하 여](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   
  <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
