---
title: '방법: 메시지 상자 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: f05190030ed6324917348fa1926abd5385e30f7e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274689"
---
# <a name="how-to-open-a-message-box"></a>방법: 메시지 상자 열기
이 예제에서는 메시지 상자를 여는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 메시지 상자는 사용자에 게 정보를 표시 하기 위한 미리 만들어진된 모달 대화 상자. 정적 호출 하 여 메시지 상자가 열려 <xref:System.Windows.MessageBox.Show%2A> 메서드는 <xref:System.Windows.MessageBox> 클래스입니다. 때 <xref:System.Windows.MessageBox.Show%2A> 는 호출 메시지 문자열 매개 변수를 사용 하 여 전달 됩니다. 여러 오버 로드가 <xref:System.Windows.MessageBox.Show%2A> 메시지 상자는 표시 되는 방식을 구성할 수 있습니다 (참조 <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>참고 항목  
 [MessageBox 샘플](https://go.microsoft.com/fwlink/?LinkID=160023)
