---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGridView control [Windows Forms], manipulating columns
- columns [Windows Forms], manipulating
- data grids [Windows Forms], manipulating columns
ms.assetid: d8cfe6b3-bbab-4182-bec2-0517d9f1eaf6
ms.openlocfilehash: a2c2ae94fb769b6b2455d309db9dbc2231138ea0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496809"
---
# <a name="how-to-manipulate-columns-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열 조작

다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 열을 조작하는 다양한 방법을 보여 줍니다.

## <a name="example"></a>예제

[!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewColumnDemo.cpp#100)]
[!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewColumnDemo.cs#100)]
[!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewcolumndemo.vb#100)]

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조

Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewBand>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
