---
title: "방법: 포커스 이벤트를 사용하여 요소의 색 변경"
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
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64b1b788ddebe77704a7d34f31ad82b10da34a5a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>방법: 포커스 이벤트를 사용하여 요소의 색 변경
얻거나를 사용 하 여 포커스를 잃을 때 요소의 색을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트입니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 숨김 파일입니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 두 개의 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.Controls.Button> 개체, 및에 대 한 이벤트 처리기를 연결의 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트를는 <xref:System.Windows.Controls.Button> 개체입니다.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트 처리기입니다.  경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 얻으면은 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 빨강으로 변경 합니다.  경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 잃을 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 다시 흰색으로 변경 합니다.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)
