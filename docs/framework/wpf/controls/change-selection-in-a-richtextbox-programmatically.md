---
title: 프로그래밍 방식으로 RichTextBox의 선택 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: 1dd6063796c7ed63ddee5e6e2338663db1340fec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664646"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a>프로그래밍 방식으로 RichTextBox의 선택 변경
현재 선택 영역을 프로그래밍 방식으로 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다. 이 옵션을이 선택 사용자의 사용자 인터페이스를 사용 하 여 콘텐츠를 선택한 경우와 동일 합니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 명명 된 코드에 설명 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠를 사용 하 여 제어 합니다.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a>예제  
 사용자가 내부를 클릭할 때 프로그래밍 방식으로 다음 코드는 일부 임의 텍스트 선택의 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a>참고자료
- [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
- [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)
