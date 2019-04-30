---
title: '방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 107ec75257907b934412d9ee333b00d5df05a99c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011436"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정
<xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트를 하나 또는 둘 다 처리하여 <xref:System.Windows.Forms.DataGridView> 행의 모양을 제어할 수 있습니다. 이들 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 나머지 부분을 그리게 하는 동안 원하는 부분만 그릴 수 있도록 디자인됩니다. 예를 들어 사용자 지정 배경을 그리려면 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트를 처리하고 개별 셀이 자체 전경 콘텐츠를 그리도록 할 수 있습니다. 또는 셀이 자신을 그리고 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 이벤트에 대한 처리기에서 사용자 지정 전경 콘텐츠를 추가하도록 할 수 있습니다. 셀 그리기를 사용하지 않도록 설정하고 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 이벤트 처리에서 직접 모든 부분을 그릴 수 있습니다.  
  
 다음 코드 예제에서는 여러 열에 걸쳐 있는 그라데이션 선택 배경 및 일부 사용자 지정 전경 콘텐츠를 제공하려고 두 이벤트 모두에 대한 처리기를 구현합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)
- [DataGridView 컨트롤 아키텍처](datagridview-control-architecture-windows-forms.md)
