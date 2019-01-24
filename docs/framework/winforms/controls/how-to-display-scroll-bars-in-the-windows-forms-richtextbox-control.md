---
title: '방법: Windows에서 스크롤 막대 표시 Forms RichTextBox 컨트롤'
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 6b6cfb8c21c8f3a48bb85a0591f3390d5b5575b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610398"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>방법: Windows에서 스크롤 막대 표시 Forms RichTextBox 컨트롤
기본적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤 필요에 따라 가로 및 세로 스크롤 막대를 표시 합니다. 에 대 한 가능한 값이 7 개를 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성의는 <xref:System.Windows.Forms.RichTextBox> 아래 표에서 설명 하는 컨트롤입니다.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>RichTextBox 컨트롤에서 스크롤 막대를 표시 하려면  
  
1.  <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `true`으로 설정합니다. 없는 형식의 스크롤 막대를 포함 하 여 가로, 경우에 표시 됩니다는 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성이 `false`합니다.  
  
2.  설정 된 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성의 적절 한 값을는 <xref:System.Windows.Forms.RichTextBoxScrollBars> 열거형입니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both>(기본값)|텍스트 너비 또는 컨트롤의 길이 초과 하는 경우에 가로 또는 세로 스크롤 막대 또는 둘 다를 표시 합니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|스크롤 막대의 표시 되지 않습니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|가로 스크롤 막대의 텍스트 컨트롤의 너비를 초과 하는 경우에 표시 됩니다. (이 발생 합니다 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성으로 설정 되어 있어야 `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|세로 스크롤 막대의 텍스트 컨트롤의 높이 초과 하는 경우에 표시 됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|가로 스크롤 막대 때 표시 된 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`합니다. 텍스트 컨트롤의 너비를 초과 하지 않는 스크롤 막대를 흐리게 표시 됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|항상 세로 스크롤 막대를 표시합니다. 텍스트 컨트롤의 길이 초과 하지 않는 스크롤 막대를 흐리게 표시 됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|항상 세로 스크롤 막대를 표시합니다. 가로 스크롤 막대 때 표시 된 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`합니다. 스크롤 막대 너비 또는 컨트롤의 길이 텍스트 크지 않으면 흐리게 표시 됩니다.|  
  
3.  <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |`false`|컨트롤의 텍스트 줄 바꿈을 도달할 때까지 오른쪽으로 스크롤됩니다 컨트롤의 너비에 맞게 자동으로 조정 되지 됩니다. 위의 가로 스크롤 막대 또는 둘 다 선택한 경우이 값을 사용 합니다.|  
    |`true`(기본값)|컨트롤의 텍스트 컨트롤의 너비에 맞게 자동으로 조정 됩니다. 가로 스크롤 막대가 표시 되지 않습니다. 하나 이상의 단락 표시 위에 세로 스크롤 막대 또는 none을 선택한 경우이 값을 사용 합니다.|  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
