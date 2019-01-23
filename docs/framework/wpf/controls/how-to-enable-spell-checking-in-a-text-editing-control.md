---
title: '방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- spellchecking [WPF]
- real-time spellchecking
- TextBox control [WPF], real-time spellchecking
- spelling checker [WPF]
- checking spelling [WPF]
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
ms.openlocfilehash: 7a394be98e86bb34cb8fe37b1c5c166417587394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605632"
---
# <a name="how-to-enable-spell-checking-in-a-text-editing-control"></a>방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용
다음 예제에서 실시간 맞춤법 검사를 사용 하도록 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.TextBox> 를 사용 하 여는 <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> 의 속성을 <xref:System.Windows.Controls.SpellCheck> 클래스.  
  
## <a name="example"></a>예제  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## <a name="see-also"></a>참고자료
- [상황에 맞는 메뉴로 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)
- [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
