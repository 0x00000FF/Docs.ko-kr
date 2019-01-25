---
title: '방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 80a0c6534e15a7a9f30976c739bade2043e96734
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733105"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤
조정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 내의 콘텐츠를 <xref:System.Windows.Controls.StackPanel> 요소 및 조정 하는 방법을 합니다 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 자식 콘텐츠입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 <xref:System.Windows.Controls.ListBox> 요소에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 각 <xref:System.Windows.Controls.ListBox> 의 가능한 값을 나타냅니다는 <xref:System.Windows.Controls.StackPanel.Orientation%2A>를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 의 속성을 <xref:System.Windows.Controls.StackPanel>입니다. 사용자 중 하나에서 값을 선택 하는 경우는 <xref:System.Windows.Controls.ListBox> 요소에 연결된 된 속성의 합니다 <xref:System.Windows.Controls.StackPanel> 및 해당 자식 <xref:System.Windows.Controls.Button> 요소 변경 합니다.  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 다음 코드 숨김 파일을 연관 된 이벤트에는 변경 내용을 정의 합니다 <xref:System.Windows.Controls.ListBox> 선택 항목이 변경 됨. <xref:System.Windows.Controls.StackPanel> 으로 식별 되는 <xref:System.Windows.FrameworkElement.Name%2A> `sp1`합니다.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
