---
title: "방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5911d8e36b82aa44a1fdadfa60d422c894b4fc71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용
스크롤 메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ScrollViewer> 요소입니다. 이러한 메서드는 증분 스크롤 콘텐츠의 줄 또는 페이지에 제공 된 <xref:System.Windows.Controls.ScrollViewer>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 한 <xref:System.Windows.Controls.ScrollViewer> 라는 `sv1`, 자식을 호스트 하는 <xref:System.Windows.Controls.TextBlock> 요소입니다. 때문에 <xref:System.Windows.Controls.TextBlock> 부모 보다 큰 <xref:System.Windows.Controls.ScrollViewer>을 스크롤할 수 있도록 스크롤 막대가 표시 합니다. <xref:System.Windows.Controls.Button>다양 한 스크롤 메서드를 나타내는 요소는 별도의 왼쪽에 도킹 되어 <xref:System.Windows.Controls.StackPanel>합니다. 각 <xref:System.Windows.Controls.Button> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 의 스크롤 동작을 제어 하는 관련된 사용자 지정 메서드를 호출 하는 파일 <xref:System.Windows.Controls.ScrollViewer>합니다.  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> 및 <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> 메서드.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
