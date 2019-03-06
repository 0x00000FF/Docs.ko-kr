---
title: '성능 최적화: 개체 동작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 5548292480f07fa192985800931f9d0262f2b791
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352687"
---
# <a name="optimizing-performance-object-behavior"></a>성능 최적화: 개체 동작
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체의 기본 동작을 이해하면 기능과 성능 간의 균형을 적절하게 조정할 수 있습니다.  
  

  
<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>개체에 대한 이벤트 처리기를 제거하지 않으면 개체가 활성 상태로 유지될 수 있음  
 개체가 해당 이벤트에 전달하는 대리자는 사실상 해당 개체에 대한 참조입니다. 따라서 이벤트 처리기는 예상보다 오래 개체의 활성 상태를 유지할 수 있습니다. 개체의 이벤트를 수신하도록 등록된 개체를 정리하려면 개체를 해제하기 전에 먼저 대리자를 제거해야 합니다. 불필요한 개체를 활성 상태로 유지하면 애플리케이션의 메모리 사용이 늘어납니다. 이러한 현상은 특히 개체가 논리적 트리 또는 시각적 트리의 루트인 경우 특히 그렇습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 소스와 수신기 간의 개체 수명 관계를 추적하기 어려운 경우에 유용할 수 있는 이벤트에 대한 약한 이벤트 수신기 패턴이 도입되었습니다. 일부 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트에서 이 패턴을 사용하기도 합니다. 사용자 지정 이벤트를 사용하여 개체를 구현하는 경우 이 패턴이 유용할 수 있습니다. 자세한 내용은 [약한 이벤트 패턴](weak-event-patterns.md)을 참조하세요.  
  
 지정된 프로세스의 메모리 사용에 대한 정보를 제공할 수 있는 CLR 프로파일러 및 작업 집합 뷰어 등 여러 가지 도구가 있습니다. CLR 프로파일러에는 할당된 형식에 대한 히스토그램, 할당 및 호출 그래프, 다양한 세대의 가비지 수집을 보여 주는 시간 표시 막대, 이러한 수집 이후의 관리되는 힙에 대한 결과 상태, 메서드당 할당 및 어셈블리 로드를 보여 주는 호출 트리 등 할당 프로필에 대한 매우 유용한 여러 뷰가 포함되어 있습니다. 자세한 내용은 [.NET Framework 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=117435)를 참조하세요.  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>종속성 속성 및 개체  
 일반적으로 종속성 속성에 액세스 하는 <xref:System.Windows.DependencyObject> 에 액세스 하는 보다 느리지 않습니다는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성입니다. 속성 값을 설정하는 데 약간의 성능 오버헤드가 있지만 값을 가져오는 경우 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성에서 값을 가져올 때와 속도가 비슷합니다. 이러한 약간의 성능 오버헤드가 발생하지만 종속성 속성이 데이터 바인딩, 애니메이션, 상속 및 스타일 지정과 같은 강력한 기능을 지원합니다. 자세한 내용은 [종속성 속성 개요](dependency-properties-overview.md)를 참조하세요.  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty 최적화  
 애플리케이션에서 종속성 속성을 정의할 때는 매우 신중해야 합니다. 경우에 <xref:System.Windows.DependencyProperty> 영향만 다른 메타 데이터 옵션이 아닌 형식 메타 데이터 옵션을 같은 렌더링 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, 해당 메타 데이터를 재정의 하 여으로 표시 해야 합니다. 속성 메타데이터 재정의 또는 가져오기에 대한 자세한 내용은 [종속성 속성 메타데이터](dependency-property-metadata.md)를 참조하세요.  
  
 모든 속성 변경이 실제로 측정, 정렬 및 렌더링에 영향을 미치는 것이 아니라면 속성 변경 처리기가 측정, 정렬 및 렌더링 단계를 수동으로 무효화하도록 하는 것이 더 효율적일 수 있습니다. 예를 들어 값이 설정된 한계보다 클 경우에만 배경을 다시 렌더링하도록 결정한 경우 속성 변경 처리기는 값이 설정된 한계를 초과하는 경우에만 렌더링을 무효화합니다.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>DependencyProperty를 상속 가능하게 만드는 경우 성능에 미치는 영향  
 기본적으로 등록된 종속성 속성은 상속되지 않습니다. 그러나 어떤 속성이든 명시적으로 상속 가능하게 만들 수 있습니다. 이는 유용한 기능이지만 속성을 상속 가능한 속성으로 변환하면 속성 무효화를 위한 시간이 길어져서 성능에 영향을 미칩니다.  
  
### <a name="use-registerclasshandler-carefully"></a>RegisterClassHandler의 신중한 사용  
 호출 하는 동안 <xref:System.Windows.EventManager.RegisterClassHandler%2A> 에서 인스턴스 상태를 저장 하는 것이 성능 문제를 일으킬 수 있는 모든 인스턴스에 처리기가 호출 하 고 알아야 할 중요 한 합니다. 만 사용 하 여 <xref:System.Windows.EventManager.RegisterClassHandler%2A> 응용 프로그램에서 인스턴스 상태를 저장 하는 경우에 필요 합니다.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>등록 시 DependencyProperty에 대한 기본값 설정  
 만들 때를 <xref:System.Windows.DependencyProperty> 기본 값을 입력 해야 하는, 매개 변수로 전달 된 기본 메타 데이터를 사용 하 여 값을 설정 합니다 <xref:System.Windows.DependencyProperty.Register%2A> 메서드의 <xref:System.Windows.DependencyProperty>. 생성자 또는 요소의 각 인스턴스에 속성 값을 설정하는 기술보다 이 기술을 사용합니다.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>레지스터를 사용하여 PropertyMetadata 값 설정  
 만들 때를 <xref:System.Windows.DependencyProperty>, 설정의 옵션이 있습니다 합니다 <xref:System.Windows.PropertyMetadata> 중 하나를 사용 하 여는 <xref:System.Windows.DependencyProperty.Register%2A> 또는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드. 개체를 호출 하기 위한 정적 생성자를 가질 수 있지만 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>,이 최적의 솔루션이 아니며 성능이 영향을 받습니다. 최상의 성능을 위해 설정 된 <xref:System.Windows.PropertyMetadata> 호출 하는 동안 <xref:System.Windows.DependencyProperty.Register%2A>합니다.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Freezable 개체  
 <xref:System.Windows.Freezable> 는 특별 한 유형의 두 가지 상태에 있는 개체: 않음과 고정 합니다. 가능할 때마다 개체를 고정하면 애플리케이션 성능이 향상되며 해당 작업 집합을 줄일 수 있습니다. 자세한 내용은 [Freezable 개체 개요](freezable-objects-overview.md)를 참조하세요.  
  
 각 <xref:System.Windows.Freezable> 에 <xref:System.Windows.Freezable.Changed> 변경 될 때마다 발생 하는 이벤트입니다. 그러나 변경 알림은 애플리케이션 성능을 저하시킵니다.  
  
 다음 예제에서는 각 <xref:System.Windows.Shapes.Rectangle> 에서는 동일한 <xref:System.Windows.Media.Brush> 개체:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 대 한 이벤트 처리기를 제공 합니다 <xref:System.Windows.Media.SolidColorBrush> 개체의 <xref:System.Windows.Freezable.Changed> 무효화 하기 위해 이벤트를 <xref:System.Windows.Shapes.Rectangle> 개체의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성입니다. 때마다이 경우에 <xref:System.Windows.Media.SolidColorBrush> 실행에 해당 <xref:System.Windows.Freezable.Changed> 각각에 대 한 콜백 함수를 호출 하는 데 필요한 이벤트 <xref:System.Windows.Shapes.Rectangle>-이러한 콜백 함수 호출의 누적 적용 성능이 크게 저하. 또한 이 시점에서 처리기를 추가 및 제거하면 애플리케이션에서 이 작업을 위해 전체 목록을 통과해야 하므로 성능에 상당한 영향을 미칩니다. 응용 프로그램 시나리오는 변경 되지 않습니다 경우는 <xref:System.Windows.Media.SolidColorBrush>, 유지 관리 비용을 지불 하면 <xref:System.Windows.Freezable.Changed> 이벤트 처리기 불필요 하 게 합니다.  
  
 고정 된 <xref:System.Windows.Freezable> 이상 마다 리소스 변경 알림 유지 관리를 확장 해야 하므로 성능을 향상 시킬 수 없습니다. 아래 표에 간단한 크기를 보여 줍니다 <xref:System.Windows.Media.SolidColorBrush> 때 해당 <xref:System.Windows.Freezable.IsFrozen%2A> 속성이 `true`있지 않은 경우에 비해, 합니다. 이 가정에 브러시 하나를 적용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 10 속성 <xref:System.Windows.Shapes.Rectangle> 개체입니다.  
  
|**상태**|**Size**|  
|---------------|--------------|  
|고정 <xref:System.Windows.Media.SolidColorBrush>|212바이트|  
|고정 되지 않은 <xref:System.Windows.Media.SolidColorBrush>|972바이트|  
  
 다음 코드 샘플에서는 이러한 개념을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>고정되지 않은 Freezable에 대한 처리기를 변경하면 개체가 활성 상태로 유지될 수 있음  
 개체에 전달 하는 대리자를 <xref:System.Windows.Freezable> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트는 사실상 해당 개체에 대 한 참조입니다. 따라서 <xref:System.Windows.Freezable.Changed> 이벤트 처리기 수 유지 개체 예상 보다 더 이상. 수신 대기 하도록 등록 된 개체의 정리를 수행할 때를 <xref:System.Windows.Freezable> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트 반드시 개체를 해제 하기 전에 해당 대리자를 제거 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 또한 후크 <xref:System.Windows.Freezable.Changed> 이벤트 내부적으로 합니다. 예를 들어, 모든 종속성 속성 걸릴 <xref:System.Windows.Freezable> 값에서 수신 대기 하는 대로 <xref:System.Windows.Freezable.Changed> 이벤트 자동으로 합니다. 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용 하는 속성을 <xref:System.Windows.Media.Brush>,이 개념을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 할당할 `myBrush` 를 `myRectangle.Fill`다시 가리키는 대리자는 <xref:System.Windows.Shapes.Rectangle> 에 추가할 개체를 <xref:System.Windows.Media.SolidColorBrush> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트. 이는 다음 코드에서 실제로 `myRect`를 가비지 수집에 적합하게 만들지 않음을 의미합니다.  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 이 예에서 `myBrush` 하 게 유지 하면서 `myRectangle` 활성 발생 하면을 다시 호출 합니다 해당 <xref:System.Windows.Freezable.Changed> 이벤트입니다. 할당 하는 것 `myBrush` 에 <xref:System.Windows.Shapes.Shape.Fill%2A> 새 속성 <xref:System.Windows.Shapes.Rectangle> 다른 이벤트 처리기를 추가 하기만 하면 `myBrush`합니다.  
  
 제거 하려면 이러한 유형의 개체를 정리 하는 방법이 권장된 됩니다는 <xref:System.Windows.Media.Brush> 에서 <xref:System.Windows.Shapes.Shape.Fill%2A> 가 제거 하는 속성을 <xref:System.Windows.Freezable.Changed> 이벤트 처리기.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>사용자 인터페이스 가상화  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서는 다음의 변형은 <xref:System.Windows.Controls.StackPanel> 자동으로 "가상화" 데이터 바인딩된 자식 콘텐츠는 요소입니다. 여기서 가상화라는 단어는 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 개체의 하위 집합이 생성되는 기술을 가리킵니다. 특정 시점에 화면에 표시되는 것보다 많은 개수의 UI 요소를 생성하는 것은 메모리 및 프로세서 측면에서 비효율적입니다. <xref:System.Windows.Controls.VirtualizingStackPanel> (에서 제공 하는 기능을 통해 <xref:System.Windows.Controls.VirtualizingPanel>) 표시 되는 항목을 계산 하 고 작동 합니다 <xref:System.Windows.Controls.ItemContainerGenerator> 에서 <xref:System.Windows.Controls.ItemsControl> (같은 <xref:System.Windows.Controls.ListBox> 또는 <xref:System.Windows.Controls.ListView>)만 표시 되는 항목에 대 한 요소를 만드는 합니다.  
  
 성능을 최적화하기 위해 이러한 항목에 대한 시각적 개체는 화면에 보이는 경우에만 생성되거나 활성 상태를 유지합니다. 컨트롤의 가시 영역에 더 이상 존재하지 않는 시각적 개체는 제거될 수 있습니다. 이는 데이터 개체가 로컬 컬렉션에 전혀 존재하지 않고 필요에 따라 스트리밍되는 데이터 가상화와 혼동해서는 안 됩니다.  
  
 아래 표에서 경과 된 시간을 추가 하 고 5000 렌더링 <xref:System.Windows.Controls.TextBlock> 요소를 사용 하는 <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.VirtualizingStackPanel>합니다. 측정값이이 시나리오에서는 텍스트 문자열을 연결 사이의 시간을 나타내는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 <xref:System.Windows.Controls.ItemsControl> 패널 요소가 텍스트 문자열을 표시 하는 경우에 개체.  
  
|**호스트 패널**|**렌더링 시간(ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>참고자료
- [WPF 응용 프로그램 성능 최적화](optimizing-wpf-application-performance.md)
- [애플리케이션 성능 계획](planning-for-application-performance.md)
- [하드웨어 이용](optimizing-performance-taking-advantage-of-hardware.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [2차원 그래픽 및 이미징](optimizing-performance-2d-graphics-and-imaging.md)
- [응용 프로그램 리소스](optimizing-performance-application-resources.md)
- [텍스트](optimizing-performance-text.md)
- [데이터 바인딩](optimizing-performance-data-binding.md)
- [기타 성능 권장 사항](optimizing-performance-other-recommendations.md)
