---
title: '방법: 사용자 지정 ToolStripRenderer 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: c6150b23cf8390a31c6b77ae3c56cfb898eded4b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723012"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a>방법: 사용자 지정 ToolStripRenderer 구현
<xref:System.Windows.Forms.ToolStripRenderer>에서 파생된 클래스를 구현하여 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 사용자 지정할 수 있습니다. 이렇게 하면 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 및 <xref:System.Windows.Forms.ToolStripSystemRenderer> 클래스에서 제공하는 모양과 다른 모양을 유연성 있게 만들 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용자 지정 <xref:System.Windows.Forms.ToolStripRenderer> 클래스를 구현하는 방법을 보여 줍니다. 이 예제에서 `GridStrip` 컨트롤은 사용자가 테이블 레이아웃의 타일을 이동하여 이미지를 구성할 수 있게 해주는 슬라이딩 타일 퍼즐을 구현합니다. 사용자 지정 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 표 레이아웃에 정렬합니다. 레이아웃에는 사용자가 끌어서 놓기 작업을 통해 인접한 타일을 밀 수 있는 빈 셀이 하나 포함되어 있습니다. 사용자를 이동할 수 있는 타일이 강조 표시됩니다.  
  
 `GridStripRenderer` 클래스는 `GridStrip` 컨트롤 모양의 세 가지 측면을 사용자 지정합니다.  
  
-   `GridStrip` 테두리  
  
-   <xref:System.Windows.Forms.ToolStripButton> 테두리  
  
-   <xref:System.Windows.Forms.ToolStripButton> 이미지  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip 컨트롤](toolstrip-control-windows-forms.md)
