---
title: 속성 변경 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
ms.openlocfilehash: 2997696a6617bb9c17bb98bba0b352cb27c07896
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351998"
---
# <a name="property-change-events"></a>속성 변경 이벤트
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 속성 값 변경에 대한 응답으로 발생하는 여러 이벤트를 정의합니다. 일반적으로 속성은 종속성 속성입니다. 이벤트 자체는 라우트된 이벤트인 경우도 있고 표준 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트인 경우도 있습니다. 이벤트 정의는 시나리오에 따라 달라집니다. 일부 속성 변경은 요소 트리를 통해 더 적절하게 라우트되지만 다른 속성 변경은 일반적으로 해당 속성이 변경한 개체에만 영향을 미치기 때문입니다.  
  
## <a name="identifying-a-property-change-event"></a>속성 변경 이벤트 식별  
 속성 변경을 보고하는 일부 이벤트는 시그니처 패턴 또는 명명 패턴 덕분에 속성 변경 이벤트로 명시적으로 식별되지 않습니다. 일반적으로 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] 문서의 이벤트 설명은 이벤트가 속성 값 변경에 직접 연결되고 속성과 이벤트 간의 상호 참조를 제공하는지 여부를 나타냅니다.  
  
### <a name="routedpropertychanged-events"></a>RoutedPropertyChanged 이벤트  
 특정 이벤트에서는 속성 변경 이벤트에 명시적으로 사용되는 이벤트 데이터 형식 및 대리자를 사용합니다. 이벤트 데이터 형식은 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, 고 대리자는 <xref:System.Windows.RoutedPropertyChangedEventHandler%601>합니다. 이벤트 데이터와 대리자는 둘 다 처리기를 정의할 때 변경 중인 속성의 실제 형식을 지정하는 데 사용되는 제네릭 형식 매개 변수를 포함합니다. 이벤트 데이터가 두 개의 속성인 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> 및 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, 둘 전달 형식 인수로 이벤트 데이터입니다.  
  
 이름의 "Routed" 부분은 속성 변경 이벤트가 라우트된 이벤트로 등록되었음을 나타냅니다. 속성 변경 이벤트를 라우트하는 방법의 장점은 자식 요소의 속성(컨트롤의 복합 부분) 값이 변경될 경우 최상위 컨트롤이 속성 변경 이벤트를 수신할 수 있다는 점입니다. 예를 들어 통합 하는 컨트롤을 만들 수 있습니다는 <xref:System.Windows.Controls.Primitives.RangeBase> 등의 컨트롤을 <xref:System.Windows.Controls.Slider>입니다. 경우 값은 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 아닌 부모 컨트롤에서 해당 변경을 처리 하려는 슬라이더 부분에 속성이 변경 합니다.  
  
 이전 값과 새 값이 있으므로 이 이벤트 처리기를 속성 값에 대한 유효성 검사기로 사용하려고 할 수 있습니다. 하지만 이 방법은 대부분 속성 변경 이벤트의 디자인 의도가 아닙니다. 일반적으로 코드의 다른 논리 영역에서 값에 대한 작업을 수행할 수 있도록 해당 값이 제공되지만, 실제로 이벤트 처리기 내의 값을 변경하는 것은 좋지 않고 이로 인해 처리기 구현 방식에 따라 의도치 않은 재귀가 발생할 수 있습니다.  
  
 속성이 사용자 지정 종속성 속성을 하거나 작업 하는 경우 파생된 클래스를 사용 하 여 인스턴스화 코드를 정의한, 하는 경우에 기본 제공 하는 속성 변경 내용을 추적 하기 위한 훨씬 더 나은 메커니즘은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템:는 속성 시스템 콜백과 <xref:System.Windows.CoerceValueCallback> 고 <xref:System.Windows.PropertyChangedCallback>입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템을 유효성 검사 및 강제 변환에 사용하는 방법에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](dependency-property-callbacks-and-validation.md) 및 [사용자 지정 종속성 속성](custom-dependency-properties.md)을 참조하세요.  
  
### <a name="dependencypropertychanged-events"></a>DependencyPropertyChanged 이벤트  
 속성 변경된 이벤트 시나리오에 포함 된 형식의 다른 쌍이 <xref:System.Windows.DependencyPropertyChangedEventArgs> 고 <xref:System.Windows.DependencyPropertyChangedEventHandler>입니다. 이러한 속성 변경에 대한 이벤트는 라우트되지 않습니다. 이러한 이벤트는 표준 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트입니다. <xref:System.Windows.DependencyPropertyChangedEventArgs> 보고 형식에서 파생 되지 않은 비정상적인 이벤트 데이터가 <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> 클래스가 아닌 구조체입니다.  
  
 사용 하는 이벤트 <xref:System.Windows.DependencyPropertyChangedEventArgs> 하 고 <xref:System.Windows.DependencyPropertyChangedEventHandler> 보다 약간 더 공통적인 `RoutedPropertyChanged` 이벤트입니다. 이러한 형식을 사용 하는 이벤트의 예로 <xref:System.Windows.UIElement.IsMouseCapturedChanged>합니다.  
  
 와 같은 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> 속성에 대 한 이전 및 새 값을 보고 합니다. 또한 이러한 값으로 수행할 작업에 대해 같은 사항을 고려해야 합니다. 일반적으로 이벤트에 대한 응답으로 sender에서 값을 다시 변경하지 않는 것이 좋습니다.  
  
## <a name="property-triggers"></a>속성 트리거  
 속성 트리거는 속성 변경 이벤트와 밀접한 관계가 있습니다. 속성 트리거는 스타일 또는 템플릿 내에서 만들어지고 이를 통해 속성 트리거에 할당된 속성 값에 따라 조건부 동작을 만들 수 있습니다.  
  
 속성 트리거의 속성은 종속성 속성이어야 합니다. 읽기 전용 종속성 속성일 수 있고 대부분 이러한 속성입니다. 컨트롤이 표시하는 종속성 속성이 최소한 부분적으로 속성 트리거로 디자인된 경우를 나타내는 좋은 지표는 속성 이름이 "Is"로 시작되는 경우입니다. 일반적으로 이렇게 이름이 지정된 속성은 읽기 전용 부울 종속성 속성입니다. 이 종속성 속성에 대한 기본 시나리오는 실시간 UI에 대한 결과를 생성할 수 있는 컨트롤 상태를 보고하므로 속성 트리거의 후보가 됩니다.  
  
 이러한 속성 중 일부에는 전용 속성 변경 이벤트도 있습니다. 예를 들어 속성 <xref:System.Windows.UIElement.IsMouseCaptured%2A> 속성 변경 이벤트에 <xref:System.Windows.UIElement.IsMouseCapturedChanged>입니다. 속성 자체 읽기 전용 값 입력된 시스템에서 조정 되며 입력된 시스템에서 발생 <xref:System.Windows.UIElement.IsMouseCapturedChanged> 각 실시간 변경 합니다.  
  
 실제 속성 변경 이벤트에 비해 속성 변경에 대한 작업을 수행하는 속성 트리거 사용에는 몇 가지 제한 사항이 있습니다.  
  
 속성 트리거는 정확한 일치 논리를 진행합니다. 속성과 함께 트리거가 작업을 수행할 특정 값을 지정합니다. 예: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. 이 제한 사항 때문에 대부분의 속성 트리거는 부울 속성 또는 전용 열거형 값을 사용하는 속성에 사용됩니다. 여기서 가능한 값 범위는 각 경우에 대한 트리거를 정의할 만큼 충분히 관리하기 쉽습니다. 또는 속성 트리거는 항목 개수가 0에 도달하는데 속성 값이 다시 0이 아닌 수로 변경될 때 이를 처리할 트리거가 없는 경우와 같은 특수 값에 대해서만 존재할 수 있습니다. 모든 경우에 대한 트리거 대신에 여기에는 코드 이벤트 처리기가 필요하거나 값이 0이 아닐 때 다시 트리거 상태에서 전환되는 기본 동작이 필요할 수 있습니다.  
  
 속성 트리거 구문은 프로그래밍의 "if" 문과 비슷합니다. 트리거 조건이 true이면 속성 트리거의 “본문”이 “실행”됩니다. 속성 트리거의 “본문”은 코드가 아니라 태”그입니다. 태그 하나를 사용 하도록 제한 됩니다 <xref:System.Windows.Setter> 스타일 또는 템플릿이 적용 되는 개체의 다른 속성을 설정 하는 요소입니다.  
  
 다양 한 가능한 값이 있는 속성 트리거의 "if" 조건을 오프셋을 사용 하 여 동일한 속성 값을 기본값으로 설정 하려면 일반적으로 권장 것을 <xref:System.Windows.Setter>입니다. 이러한 방식으로 <xref:System.Windows.Trigger> 트리거 조건이 true 인 경우 포함 된 setter 우선 순위를 가집니다 하며 <xref:System.Windows.Setter> 포함 되지 않은 <xref:System.Windows.Trigger> 트리거 조건이 false 일 때마다 우선 순위를 가집니다.  
  
 일반적으로 속성 트리거는 같은 요소에서 또 다른 속성 상태에 따라 하나 이상의 모양 속성을 변경해야 하는 시나리오에 적합합니다.  
  
 속성 트리거에 대한 자세한 내용은 [스타일 지정 및 템플릿](../controls/styling-and-templating.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [라우트된 이벤트 개요](routed-events-overview.md)
- [종속성 속성 개요](dependency-properties-overview.md)
