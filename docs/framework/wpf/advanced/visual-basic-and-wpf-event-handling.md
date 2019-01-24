---
title: Visual Basic 및 WPF 이벤트 처리
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: 8b4601ea4034068ccdb4bfe0744f658586d74ece
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582230"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic 및 WPF 이벤트 처리
Microsoft Visual Basic.NET 언어에 대 한 특히 따르면 언어별 `Handles` 특성을 사용 하 여 이벤트 처리기를 연결 하거나 사용 하지 않고 인스턴스를 사용 하 여 이벤트 처리기를 연결 하는 키워드는 <xref:System.Windows.UIElement.AddHandler%2A> 메서드. 그러나 처리기를 인스턴스에 연결하는 `Handles` 기술에는 몇 가지 제한 사항이 있습니다. 이는 `Handles` 구문이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템의 특정 라우트된 이벤트 기능 중 일부를 지원할 수 없기 때문입니다.  
  
## <a name="using-handles-in-a-wpf-application"></a>WPF 애플리케이션에서 "Handles" 사용  
 `Handles`를 사용하여 인스턴스 및 이벤트에 연결되는 이벤트 처리기는 모두 인스턴스의 partial 클래스 선언 내에 정의되어야 하며, 이는 요소에서 특성 값을 통해 할당되는 이벤트 처리기에 대한 요구 사항이기도 합니다. 만 지정할 수 있습니다 `Handles` 있는 페이지의 요소에 대 한 <xref:System.Windows.FrameworkContentElement.Name%2A> 속성 값 (또는 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 선언). 때문에 이것이 합니다 <xref:System.Windows.FrameworkContentElement.Name%2A> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지 원하는 데 필요한 인스턴스 참조를 만듭니다를 *Instance.Event* 참조 형식에 필요한는 `Handles` 구문. 에 사용할 수 있는 유일한 요소 `Handles` 없이 <xref:System.Windows.FrameworkContentElement.Name%2A> 참조는 partial 클래스를 정의 하는 루트 요소 인스턴스입니다.  
  
 `Handles` 다음에 오는 *Instance.Event* 참조를 쉼표로 구분하여 동일한 처리기를 여러 요소에 할당할 수 있습니다.  
  
 `Handles`를 사용하여 둘 이상의 처리기를 동일한 *Instance.Event* 참조에 할당할 수 있습니다. `Handles` 참조에서 처리기가 지정되는 순서에 중요성을 부여하지 마세요. 동일한 이벤트를 처리하는 처리기는 순서에 관계없이 호출될 수 있다고 가정해야 합니다.  
  
 사용 하 여 추가한 처리기를 제거할 `Handles` 선언에서 호출할 수 있습니다 <xref:System.Windows.UIElement.RemoveHandler%2A>합니다.  
  
 해당 멤버 테이블에서 처리되고 있는 이벤트를 정의하는 인스턴스에 처리기를 연결하는 한 `Handles`를 사용하여 라우트된 이벤트에 대한 처리기를 연결할 수 있습니다. 라우트된 이벤트를 사용 하 여 연결 된 처리기에 대 한 `Handles` 와 연결 된 처리기와 같은 라우팅 규칙을 따릅니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성의 공용 시그니처를 사용 하 여 또는 <xref:System.Windows.UIElement.AddHandler%2A>합니다. 즉, 이벤트가 이미 처리 표시 되 면 (합니다 <xref:System.Windows.RoutedEventArgs.Handled%2A> 이벤트 데이터의 속성은 `True`)로 연결 된 처리기 `Handles` 가 해당 이벤트 인스턴스에 대 한 응답에서 호출 되지 않습니다. 이벤트는 경로에 있는 다른 요소의 인스턴스 처리기에서 처리되거나 경로를 따르는 현재 요소 또는 이전 요소의 클래스 처리에 의해 처리된 것으로 표시할 수 있습니다. 쌍을 이루는 터널/버블 이벤트를 지원하는 입력 이벤트의 경우 터널링 경로에서 이벤트 쌍을 처리된 것으로 표시했을 수 있습니다. 라우트된 이벤트에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하세요.  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>처리기를 추가하는 "Handles"의 제한 사항  
 `Handles`는 연결된 이벤트에 대해 처리기를 참조할 수 없습니다. 해당 연결된 이벤트에 `add` 접근자 메서드를 사용하거나 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 *typename.eventname* 이벤트 특성을 사용해야 합니다. 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하세요.  
  
 라우트된 이벤트의 경우 `Handles`를 사용하면 해당 이벤트가 인스턴스 멤버 테이블에 있는 인스턴스에 대해서만 처리기를 할당할 수 있습니다. 그러나 일반적으로 라우트된 이벤트를 사용하면 부모 요소는 부모 요소의 해당 멤버 테이블에 해당 이벤트가 없는 경우에도 자식 요소의 이벤트에 대한 수신기가 될 수 있습니다. 특성 구문에서는 처리하려는 이벤트를 실제로 정의하는 형식을 한정하는 *typename.membername* 특성 형태를 통해 이를 지정할 수 있습니다. 예를 들어, 부모 `Page` (없이 `Click` 정의 된 이벤트) 형태로 특성 처리기를 할당 하 여 단추 클릭 이벤트를 수신할 수 `Button.Click`입니다. 그러나 `Handles`는 *typename.membername* 형태를 지원하지 않습니다. 이는 충돌하는 *Instance.Event* 형태를 지원해야 하기 때문입니다. 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하세요.  
  
 `Handles`는 처리된 것으로 이미 표시된 이벤트에 대해 호출되는 처리기를 연결할 수 없습니다. 대신, 코드 및 호출 사용 해야 합니다 `handledEventsToo` 오버 로드 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>합니다.  
  
> [!NOTE]
>  사용 하지 마십시오는 `Handles` XAML에서 동일한 이벤트에 대 한 이벤트 처리기를 지정 하는 경우 Visual Basic 코드에서 구문입니다. 이 경우 이벤트 처리기가 두 번 호출됩니다.  
  
## <a name="how-wpf-implements-handles-functionality"></a>WPF에서 "Handles" 기능을 구현하는 방법  
 경우는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지가 컴파일되면 중간 파일 선언 `Friend` `WithEvents` 된 페이지의 모든 요소에 대 한 참조를 <xref:System.Windows.FrameworkContentElement.Name%2A> 속성 집합 (또는 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 선언). 각 명명된 인스턴스는 `Handles`를 통해 처리기에 할당할 수 있는 요소일 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 내에서 [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)]는 페이지의 `Handles` 참조에 사용할 수 있는 요소의 완성을 보여 줄 수 있습니다. 그러나 이렇게 하려면 중간 파일에서 모든 `Friends` 참조를 채울 수 있도록 하나의 컴파일 패스가 필요할 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.UIElement.AddHandler%2A>
- [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)
- [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
