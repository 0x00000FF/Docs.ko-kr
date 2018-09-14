---
title: '방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: b86724bda83c701ad5c5872ae8d97bb490158e76
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45618992"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정
<xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 개별적으로 또는 응용 프로그램의 모든 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대해 사용자 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 <xref:System.Windows.Forms.MenuStrip> 컨트롤에 사용자 지정 렌더러를 선택적으로 적용하는 방법을 보여 줍니다.  
  
 이 코드 예제를 사용하려면 응용 프로그램을 컴파일 및 실행한 다음 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 사용자 지정 렌더링 범위를 선택합니다. **적용**을 클릭하여 렌더러를 설정합니다.  
  
 사용자 지정 메뉴 항목 렌더링을 보려면를 선택 합니다 <xref:System.Windows.Forms.MenuStrip> 에서 옵션을 <xref:System.Windows.Forms.ComboBox> 컨트롤을 클릭 **적용**, 연 다음를 **파일** 메뉴 항목.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 설정하여 응용 프로그램의 모든 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 사용자 지정 렌더러를 적용합니다.  
  
 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성을 설정하여 개별 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 사용자 지정 렌더러를 적용합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
