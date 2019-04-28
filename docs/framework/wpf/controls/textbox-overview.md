---
title: TextBox 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 577a12a0c04e5e3bfbfecb2c45263b684f0ffc17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791003"
---
# <a name="textbox-overview"></a>TextBox 개요
<xref:System.Windows.Controls.TextBox> 클래스 표시 하거나 서식 없는 텍스트를 편집할 수 있습니다. 일반적인 용도 <xref:System.Windows.Controls.TextBox> 형태로 서식 없는 텍스트를 편집 하는 합니다. 예를 들어, 사용자의 이름, 전화 번호에 대 한 요청 하는 폼 등 사용 <xref:System.Windows.Controls.TextBox> 텍스트 입력 컨트롤입니다. 이 항목에서는 소개 합니다 <xref:System.Windows.Controls.TextBox> 클래스 및 둘 다에서 사용 하는 방법의 예가 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 C#.  

<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox 또는 RichTextBox?  
 둘 다 <xref:System.Windows.Controls.TextBox> 고 <xref:System.Windows.Controls.RichTextBox> 사용자가 텍스트를 입력할 수 있지만 두 개의 서로 다른 시나리오에 사용 됩니다. A <xref:System.Windows.Controls.TextBox> 적은 시스템 리소스를 필요는 <xref:System.Windows.Controls.RichTextBox> 일반 텍스트만 편집 해야 하는 경우 적합 하므로 (즉, 폼에서 사용). <xref:System.Windows.Controls.RichTextBox> 는 것이 좋습니다는 사용자가 서식 있는 텍스트, 이미지, 테이블, 편집할 때나 다른 지원 되는 콘텐츠입니다. 예를 들어 이미지 문서 편집, 문서 또는 서식 지정 해야 하는 블로그, 등을 사용 하 여 훌륭하게 수행할는 <xref:System.Windows.Controls.RichTextBox>합니다. 아래 표에서 기본 기능의 <xref:System.Windows.Controls.TextBox> 고 <xref:System.Windows.Controls.TextBox>입니다.  
  
|컨트롤|실시간 맞춤법 검사|상황에 맞는 메뉴|서식 명령 등 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument> 이미지, 단락, 테이블 등과 같은 콘텐츠입니다.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|예|예|아니요|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|예|예|예([RichTextBox 개요](richtextbox-overview.md) 참조)|예([RichTextBox 개요](richtextbox-overview.md) 참조)|  
  
> [!NOTE]
>  하지만 <xref:System.Windows.Controls.TextBox> 와 같은 명령 서식 지정 관련 편집을 지원 하지 않습니다 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B), 대부분의 기본 명령은 같은 두 컨트롤 모두에서 지원 됩니다 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>합니다. 자세한 내용은 <xref:System.Windows.Documents.EditingCommands>를 참조하세요.  
  
 지 원하는 기능 <xref:System.Windows.Controls.TextBox> 아래 섹션에 나와 있습니다. 에 대 한 자세한 내용은 <xref:System.Windows.Controls.RichTextBox>를 참조 하세요 [RichTextBox 개요](richtextbox-overview.md)합니다.  
  
### <a name="real-time-spellchecking"></a>실시간 맞춤법 검사  
 실시간 맞춤법 검사를 설정할 수 있습니다.는 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>합니다. 맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).  
  
 ![맞춤법 검사 기능이 있는 Textbox](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.  
  
### <a name="context-menu"></a>상황에 맞는 메뉴  
 기본적으로 둘 다 <xref:System.Windows.Controls.TextBox> 고 <xref:System.Windows.Controls.RichTextBox> 가 컨트롤 내에서 단추로 클릭할 때 표시 되는 상황에 맞는 메뉴입니다. 상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 동작을 재정의할 수 있습니다. 자세한 내용은 [TextBox에 사용자 지정 컨텍스트 메뉴 사용](how-to-use-a-custom-context-menu-with-a-textbox.md)을 참조하세요.  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>TextBox 만들기  
 <xref:System.Windows.Controls.TextBox> 여러 줄으로 구성 하거나 높이에서 한 줄 수 있습니다. 한 줄 <xref:System.Windows.Controls.TextBox> 작은 양의 일반 텍스트 (즉, 적합 합니다. 입력하는 데 가장 적합합니다. 다음 예제에는 한 줄을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox>합니다.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 만들 수도 있습니다는 <xref:System.Windows.Controls.TextBox> 를 여러 줄의 텍스트를 입력할 수 있도록 합니다. 예를 들어, 폼 사용자의 경력에 대 한 요청 되 면 하려는 사용을 <xref:System.Windows.Controls.TextBox> 지 원하는 여러 줄의 텍스트입니다. 다음 예제에서는 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 <xref:System.Windows.Controls.TextBox> 여러 줄의 텍스트에 맞게 자동으로 확장 되는 컨트롤입니다.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 설정 합니다 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 `Wrap` 텍스트가 새 때 줄 가장자리를 <xref:System.Windows.Controls.TextBox> 컨트롤에 도달 하면 자동으로 확장 되는 <xref:System.Windows.Controls.TextBox> 필요한 경우 새 줄에 대 한 공간을 포함 하도록 컨트롤.  
  
 설정 합니다 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 `true` RETURN 키를 누르면 자동으로 다시 한 번 확장 삽입할 새 줄을 <xref:System.Windows.Controls.TextBox> 필요한 경우 새 줄에 대 한 공간을 포함 하도록 합니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 특성에 있는 스크롤 막대를 추가 합니다 <xref:System.Windows.Controls.TextBox>되도록 내용의 <xref:System.Windows.Controls.TextBox> 경우 스크롤할 수를 <xref:System.Windows.Controls.TextBox> 포함 하는 창 프레임의 크기 이상으로 확장.  
  
 사용과 관련 된 다양 한 작업에 대 한 자세한 내용은 <xref:System.Windows.Controls.TextBox>를 참조 하세요 [방법 도움말 항목](textbox-how-to-topics.md)합니다.  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 검색할 때마다 이벤트를 사용 해야의 텍스트를 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox> 변경 대신 <xref:System.Windows.UIElement.KeyDown> 예상할 수 있듯이 합니다. 예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [방법 항목](textbox-how-to-topics.md)
- [RichTextBox 개요](richtextbox-overview.md)
