---
title: '방법: 도킹 된 ToolStrip 컨트롤의 Z 순서 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 1ae7e6f63488d2dbb6b408cdf255f111f929298f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722666"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a>방법: 도킹 된 ToolStrip 컨트롤의 Z 순서 정의
도킹을 사용하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 올바르게 배치하려면 폼의 z 순서에 컨트롤을 올바르게 배치해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 z 순서를 지정하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 도킹된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 정렬하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 z 순서는 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip>  
  
 컨트롤이 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 추가된 순서에 따라 결정됩니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 이러한 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 메서드 호출 순서를 반대로 바꾸고 레이아웃에 미치는 영향을 확인합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [ToolStrip 컨트롤](toolstrip-control-windows-forms.md)
