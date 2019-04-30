---
title: '방법: (Windows Forms) MenuStrip에 옵션 단추 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: e764c7e181870d8faf6157cacc13164977ce2e3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013428"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>방법: (Windows Forms) MenuStrip에 옵션 단추 표시
옵션 단추, 라디오 단추 라고도 하며 한 번에 하나씩만 선택할 수 있다는 점을 제외 하 고 확인란을 선택 하는 것과 비슷합니다. 하지만 기본적 합니다 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스 옵션 단추 동작을 제공 하지 않습니다, 클래스는 메뉴 항목에 대 한 옵션 단추 동작을 구현 하는 사용자 지정할 수 있는 확인란 동작을 제공 하는 것을 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.  
  
 때를 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 메뉴 항목의 속성이 `true`, 사용자는 확인란의 표시를 전환 하려면 항목을 클릭 합니다. <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성 항목의 현재 상태를 나타냅니다. 기본 옵션 단추 동작을 구현 해야 항목을 선택 하면 설정 하는 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 이전에 선택한 항목에 대 한 속성 `false`합니다.  
  
 다음 절차에서는이 구현 하는 방법 및 상속 된 클래스에 추가 된 기능을 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스입니다. 합니다 `ToolStripRadioButtonMenuItem` 클래스와 같은 멤버를 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 선택 동작 및 옵션 단추 모양을 제공 합니다. 또한이 클래스는 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성 하위 메뉴의 옵션을 부모 항목을 선택 하지 않으면 사용 하지 않도록 설정 됩니다.  
  
### <a name="to-implement-option-button-selection-behavior"></a>옵션 단추가 선택 동작을 구현 하려면  
  
1. 초기화 된 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true` 항목을 선택할 수 있도록 합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2. 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 새 항목이 선택 될 때 이전에 선택한 항목의 선택을 취소 하는 방법입니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3. 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 메서드는 이미 선택 된 항목을 클릭 하면 선택한을 지우지 않습니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>옵션 단추 항목의 모양을 수정 하려면  
  
1. 재정의 된 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드를 사용 하 여 기본 확인란 옵션 단추를 사용 하 여 대체를 <xref:System.Windows.Forms.RadioButtonRenderer> 클래스.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2. 재정의 된 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 마우스 상태를 추적 하 고 있는지 확인 하는 메서드를 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드는 올바른 옵션 단추 상태를 그립니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>부모 항목을 선택 하지 않으면 하위 메뉴의 옵션을 사용 하지 않도록 설정  
  
1. 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성 항목을 모두 사용 하 여 부모 항목에 있을 때 사용 되지 않도록를 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 의 값 `true` 및 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 값 `false`합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2. 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 구독할 메서드는 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 부모 항목의 이벤트입니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3. 부모 항목에 대 한 처리기에서 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트를 새 활성된 상태를 사용 하 여 디스플레이 업데이트 하려면 항목을 무효화 합니다.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>예제  
 다음 코드 예에서는 전체 `ToolStripRadioButtonMenuItem` 클래스 및 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스 옵션 단추 동작을 보여 줍니다.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
- [방법: 사용자 지정 ToolStripRenderer 구현](how-to-implement-a-custom-toolstriprenderer.md)
