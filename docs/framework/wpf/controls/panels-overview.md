---
title: Panel 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: f8fd3237d71bc1960678565192c7ef9ddcb2c366
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44265106"
---
# <a name="panels-overview"></a>Panel 개요
<xref:System.Windows.Controls.Panel> 요소는 요소의 렌더링을 제어 하는 구성 요소, 해당 크기와 차원, 위치, 자식 콘텐츠의 정렬 합니다. 합니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 다양 한 미리 정의 된 <xref:System.Windows.Controls.Panel> 사용자 지정을 작성할 수 있을 뿐만 아니라 요소 <xref:System.Windows.Controls.Panel> 요소입니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
-   [Panel 클래스](#Panels_view_from_10000_feet)  
  
-   [패널 요소의 공통 멤버](#Panels_declared_members)  
  
-   [파생 패널 요소](#Panels_derived_elements)  
  
-   [사용자 인터페이스 패널](#Panels_main_UI_elements)  
  
-   [중첩 Panel 요소](#Panels_nested_panel_elements)  
  
-   [사용자 지정 Panel 요소](#Panels_custom_panel_elements)  
  
-   [지역화/세계화 지원](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Panel 클래스  
 <xref:System.Windows.Controls.Panel> 지 원하는 레이아웃을 제공 하는 모든 요소에 대 한 기본 클래스인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다. 파생 <xref:System.Windows.Controls.Panel> 요소를 배치 하 고 요소를 정렬할 사용 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 많은 복잡한 레이아웃을 가능하게 하는 파생 패널 구현의 포괄적인 집합이 포함됩니다. 이러한 파생 클래스는 대부분의 표준 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오를 가능하게 하는 속성 및 메서드를 표시합니다. 요구 사항에 맞는 자식 정렬 동작을 재정의 하 여 새 레이아웃을 만들 수 있습니다를 찾을 수 없는 개발자는 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 고 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드. 사용자 지정 레이아웃 동작에 대한 자세한 내용은 [사용자 지정 Panel 요소](#Panels_custom_panel_elements)를 참조하세요.  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>패널의 공통 멤버  
 모든 <xref:System.Windows.Controls.Panel> 요소 크기 조정 및 위치 지정 속성으로 정의 된 기본 지원 <xref:System.Windows.FrameworkElement>등 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>를 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, 및 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>합니다. 위치 지정 정의한 속성에 대 한 자세한 <xref:System.Windows.FrameworkElement>를 참조 하세요 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)합니다.  
  
 <xref:System.Windows.Controls.Panel> 매우 중요 이해 하 고 레이아웃을 사용 하 여 추가 속성을 노출 합니다. 합니다 <xref:System.Windows.Controls.Panel.Background%2A> 속성은 포함 하는 파생된 패널 요소의 경계 사이 있는 영역을 채우는 데 사용 되는 <xref:System.Windows.Media.Brush>합니다. <xref:System.Windows.Controls.Panel.Children%2A> 요소의 자식 컬렉션을 나타냅니다는 <xref:System.Windows.Controls.Panel> 이루어집니다. <xref:System.Windows.Controls.Panel.InternalChildren%2A> 내용을 나타내는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 및 데이터 바인딩에 의해 생성 된 멤버입니다. 구성 둘 다를 <xref:System.Windows.Controls.UIElementCollection> 부모 내에서 호스트 되는 자식 요소의 <xref:System.Windows.Controls.Panel>합니다.  
  
 패널도 노출 된 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> 연결 된 속성에서 파생 된 계층된 순서를 달성 하기 위해 사용할 수 있는 <xref:System.Windows.Controls.Panel>합니다. 패널의 멤버인 <xref:System.Windows.Controls.Panel.Children%2A> 수집과 더 높은 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> 앞에 낮은 값이 표시 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> 값입니다. 와 같은 패널에 특히 유용 이것이 <xref:System.Windows.Controls.Canvas> 고 <xref:System.Windows.Controls.Grid> 자식이 동일한 좌표 공간을 공유할 수 있는 합니다.  
  
 <xref:System.Windows.Controls.Panel> 또한 정의 <xref:System.Windows.Controls.Panel.OnRender%2A> 의 기본 표시 동작을 재정의 하려면 사용할 수 있는 메서드를 <xref:System.Windows.Controls.Panel>합니다.  
  
#### <a name="attached-properties"></a>연결된 속성  
 파생 패널 요소는 연결된 속성을 광범위하게 사용합니다. 연결된 속성은 기존 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성 "래퍼"가 없는 종속성 속성의 특수 형식입니다. 연결된 속성에는 다음 여러 예제에서 확인할 수 있는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 특수 구문이 있습니다.  
  
 연결된 속성의 한 가지 목적은 자식 요소가 부모 요소를 통해 실제로 정의되는 속성의 고유 값을 저장하도록 하는 것입니다. 이 기능을 제공하는 응용 프로그램에서는 자식 요소가 자신이 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 표시되는 방식을 부모에게 알립니다. 이 기능은 응용 프로그램 레이아웃에 매우 유용합니다. 자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하세요.  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>파생 패널 요소  
 여러 개체에서 파생 <xref:System.Windows.Controls.Panel>, 했는데 루트 레이아웃 공급자로 사용을 위한는 하지 않습니다. 6 개의 정의 된 창 클래스 (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>를 <xref:System.Windows.Controls.VirtualizingStackPanel>, 및 <xref:System.Windows.Controls.WrapPanel>)는 응용 프로그램을 만들기 위해 특별히 설계 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
 각 패널 요소는 다음 테이블에 나와 있는 자체 특수 기능을 캡슐화합니다.  
  
|요소 이름|UI 패널 여부|설명|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|예|명시적으로 좌표를 기준으로 자식 요소를 배치할 수 있는 영역을 정의 하는 <xref:System.Windows.Controls.Canvas> 영역입니다.|  
|<xref:System.Windows.Controls.DockPanel>|예|자식 요소를 서로 맞춰 가로 또는 세로로 정렬할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.Grid>|예|열 및 행으로 구성되는 유연한 그리드 영역을 정의합니다. 자식 요소를 <xref:System.Windows.Controls.Grid> 정확 하 게 사용 하 여 배치 될 수 있습니다는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성입니다.|  
|<xref:System.Windows.Controls.StackPanel>|예|가로 또는 세로 방향으로 한 줄로 자식 요소를 정렬합니다.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|아니요|탭 단추의 레이아웃을 처리 하는 <xref:System.Windows.Controls.TabControl>합니다.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|아니요|내에서 콘텐츠를 정렬 한 <xref:System.Windows.Controls.ToolBar> 제어 합니다.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|아니요|<xref:System.Windows.Controls.Primitives.UniformGrid> 셀 크기가 모두 같은 그리드에서 자식을 정렬 하는 데 사용 됩니다.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|아니요|자식 컬렉션을 "가상화"할 수 있는 패널의 기본 클래스를 제공합니다.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|예|가로 또는 세로 방향으로 한 줄로 콘텐츠를 정렬하고 가상화합니다.|  
|<xref:System.Windows.Controls.WrapPanel>|예|<xref:System.Windows.Controls.WrapPanel> 에서 자식 요소의 위치 왼쪽에서 오른쪽으로 포함 하는 상자의 가장자리에 다음 줄으로 콘텐츠를 분리 합니다. 위쪽에서에서 아래쪽으로 또는 오른쪽에서 왼쪽으로 값에 따라 순차적으로 발생 정렬 된 <xref:System.Windows.Controls.WrapPanel.Orientation%2A> 속성입니다.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>사용자 인터페이스 패널  
 6 가지 panel 클래스에서 사용할 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지원 하도록 최적화 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>를 <xref:System.Windows.Controls.Grid>를 <xref:System.Windows.Controls.StackPanel>를 <xref:System.Windows.Controls.VirtualizingStackPanel>, 및 <xref:System.Windows.Controls.WrapPanel>합니다. 이러한 패널 요소는 쉽게 사용할 수 있고, 유연하고, 대부분 응용 프로그램용으로 충분히 확장 가능합니다.  
  
 각 파생 <xref:System.Windows.Controls.Panel> 요소 크기 조정 제약을 다르게 처리 합니다. 이해 하는 방법을 <xref:System.Windows.Controls.Panel> 가로 또는 세로 방향으로 핸들 제약 조건은 예측 가능성이 더욱 뛰어난 레이아웃을 만들 수 있습니다.  
  
|**패널 이름**|**x 차원**|**y 차원**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|콘텐츠로 제한됨|콘텐츠로 제한됨|  
|<xref:System.Windows.Controls.DockPanel>|제한됨|제한됨|  
|<xref:System.Windows.Controls.StackPanel> (세로 방향)|제한됨|콘텐츠로 제한됨|  
|<xref:System.Windows.Controls.StackPanel> (가로 방향)|콘텐츠로 제한됨|제한됨|  
|<xref:System.Windows.Controls.Grid>|제한됨|경우에서를 제외 하 고 제약 조건이 있는 <xref:System.Windows.GridUnitType.Auto> 행 및 열에 적용|  
|<xref:System.Windows.Controls.WrapPanel>|콘텐츠로 제한됨|콘텐츠로 제한됨|  
  
 이러한 각 요소에 대한 자세한 설명과 사용법 예제는 아래 내용을 참조하세요.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 <xref:System.Windows.Controls.Canvas> 절대에 따라 콘텐츠를 배치할 수 있도록 요소 *x-* 하 고 *y-* 좌표입니다. 요소를 고유한 위치에 그릴 수 있고, 여러 요소가 같은 좌표를 사용하는 경우에는 요소가 태그에 표시되는 순서에 따라 요소를 그리는 순서가 결정됩니다.  
  
 <xref:System.Windows.Controls.Canvas> 가장 유연한 레이아웃 지원을 제공 <xref:System.Windows.Controls.Panel>합니다. 높이 및 너비 속성은 캔버스의 영역을 정의 하는 데 사용 되 고 내부 요소에는 부모 영역을 기준으로 절대 좌표가 할당 됩니다 <xref:System.Windows.Controls.Canvas>합니다. 4 개의 연결 된 속성을 <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>를 정밀 하 게 제어 내에서 개체 배치를 <xref:System.Windows.Controls.Canvas>를 배치 하 고 화면에 정확 하 게 요소를 정렬 하기 때문에 개발자.  
  
#### <a name="cliptobounds-within-a-canvas"></a>캔버스 내의 ClipToBounds  
 <xref:System.Windows.Controls.Canvas> 자체 정의 된 외부에 있는 좌표에도 화면의 다른 위치에 있는 자식 요소를 배치할 수 있습니다 <xref:System.Windows.FrameworkElement.Height%2A> 고 <xref:System.Windows.FrameworkElement.Width%2A>입니다. 또한 <xref:System.Windows.Controls.Canvas> 자식의 크기에 따라 영향을 받지 않습니다. 결과적으로, 부모의 경계 사각형 외부에 다른 요소는 자식 요소 수는 <xref:System.Windows.Controls.Canvas>합니다. 기본 동작을 <xref:System.Windows.Controls.Canvas> 자식이 부모 범위 밖에 그릴 수 있도록 허용 하는 것 <xref:System.Windows.Controls.Canvas>입니다. 이 동작은 바람직하지 않을 경우 합니다 <xref:System.Windows.UIElement.ClipToBounds%2A> 속성 설정할 수 있습니다 `true`합니다. 이 인해 <xref:System.Windows.Controls.Canvas> 자체 크기에 맞춰 잘라 내기에 있습니다. <xref:System.Windows.Controls.Canvas> 자식에 해당 범위 밖으로 그릴 수 있도록 전용 레이아웃 요소가입니다.  
  
 [너비 속성 비교 샘플](https://go.microsoft.com/fwlink/?LinkID=160050)에서 동작을 그래픽 방식으로 설명합니다.  
  
#### <a name="defining-and-using-a-canvas"></a>Canvas 정의 및 사용  
 A <xref:System.Windows.Controls.Canvas> 사용 하 여 인스턴스화할 수 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다. 다음 예제에 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.Canvas> 에 콘텐츠를 절대적으로 배치 합니다. 이 코드는 세 개의 100픽셀 사각형을 생성합니다. 첫 번째 사각형은 빨간색이고 왼쪽 위(*x, y*) 위치는 (0, 0)으로 지정됩니다. 두 번째 사각형은 녹색이고 왼쪽 위 위치는 (100, 100)으로, 첫 번째 사각형의 오른쪽 바로 아래입니다. 세 번째 사각형은 파란색이고 왼쪽 위 위치는 (50, 50)이므로 첫 번째 사각형의 오른쪽 아래 사분면과 두 번째 사각형의 왼쪽 위 사분면을 포함합니다. 세 번째 사각형이 마지막으로 배치되므로 다른 두 개의 사각형 위에 있는 것처럼 보입니다. 즉, 겹치는 부분은 세 번째 상자의 색으로 표시됩니다.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 Canvas 요소](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 합니다 <xref:System.Windows.Controls.DockPanel> 요소를 사용 하는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 컨테이너의 가장자리를 따라 콘텐츠를 배치 하도록 자식 콘텐츠 요소에 설정 된 대로 연결 된 속성입니다. 때 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 로 설정 된 <xref:System.Windows.Controls.Dock.Top> 또는 <xref:System.Windows.Controls.Dock.Bottom>, 자식 요소 위나 아래 서로 다른 위치에 배치 합니다. 때 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 로 설정 된 <xref:System.Windows.Controls.Dock.Left> 또는 <xref:System.Windows.Controls.Dock.Right>, 자식 요소를 왼쪽 또는 오른쪽에 서로 다른 위치에 배치 합니다. 합니다 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 의 자식으로 추가 된 최종 요소의 위치를 결정 하는 속성을 <xref:System.Windows.Controls.DockPanel>입니다.  
  
 사용할 수 있습니다 <xref:System.Windows.Controls.DockPanel> 단추 집합과 같은 관련된 컨트롤 그룹의 위치입니다. [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)]에 있는 UI처럼 "이동된" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만드는 데 사용할 수 있습니다.  
  
#### <a name="sizing-to-content"></a>콘텐츠에 맞게 크기 조정  
 하는 경우 해당 <xref:System.Windows.FrameworkElement.Height%2A> 하 고 <xref:System.Windows.FrameworkElement.Width%2A> 속성이 지정 되지 않은 <xref:System.Windows.Controls.DockPanel> 콘텐츠에 맞게 크기입니다. 자식 요소의 크기를 수용하도록 크기가 증가 또는 감소할 수 있습니다. 그러나 이러한 속성에 지정 된 시점과 공간이 더 이상 다음 지정 된 자식 요소에 대해 <xref:System.Windows.Controls.DockPanel> 자식 요소나 후속 자식 요소를 표시 하지 않습니다 하 고 후속 자식 요소를 측정 하지 않습니다.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 기본적으로 마지막 자식은 <xref:System.Windows.Controls.DockPanel> 요소를 "채웁니다"의 남은 공간을 할당 합니다. 이 동작을 원하지 않는 경우 설정 합니다 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 속성을 `false`입니다.  
  
#### <a name="defining-and-using-a-dockpanel"></a>DockPanel 정의 및 사용  
 다음 예제에서는 다음을 사용 하 여 공간 분할 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.DockPanel>합니다. 다섯 <xref:System.Windows.Controls.Border> 요소가 부모의 자식으로 추가 됩니다 <xref:System.Windows.Controls.DockPanel>합니다. 다른 위치 지정 속성을 사용 하 여 각각을 <xref:System.Windows.Controls.DockPanel> 공간을 분할 합니다. 마지막 요소가 나머지 할당되지 않은 공간을 “채웁니다”.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 DockPanel 시나리오](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>표  
 <xref:System.Windows.Controls.Grid> 요소는 절대 위치 및 표 형식 데이터 컨트롤의 기능을 병합 합니다. <xref:System.Windows.Controls.Grid> 쉽게 위치와 스타일 요소에 있습니다. <xref:System.Windows.Controls.Grid> 유연한 행 및 열 그룹화를 정의할 수 있으며 여러 사이의 크기 조정 정보를 공유 하는 메커니즘을 제공 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
#### <a name="how-is-grid-different-from-table"></a>Grid는 Table과 어떻게 다를까요?  
 <xref:System.Windows.Documents.Table> 및 <xref:System.Windows.Controls.Grid> 일부 공통 기능을 공유 하지만 각각은 다양 한 시나리오에 가장 적합 합니다. A <xref:System.Windows.Documents.Table> 유동 콘텐츠 내에서 사용 하도록 설계 되었습니다 (참조 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md) 유동 콘텐츠에 대 한 자세한 내용은). 그리드는 폼 내부에서 사용하는 것이 적합합니다(기본적으로 유동 콘텐츠 외부의 모든 위치). 내를 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> 지원 유동 콘텐츠 동작 하는 동안 콘텐츠 선택, 페이지 매김 및 열 흐름 변경 등을 <xref:System.Windows.Controls.Grid> 하지 않습니다. A <xref:System.Windows.Controls.Grid> 반면에 가장 적합 외부를 <xref:System.Windows.Documents.FlowDocument> 비롯 한 여러 가지 이유로 <xref:System.Windows.Controls.Grid> 행 및 열 인덱스를 기준으로 요소를 추가 <xref:System.Windows.Documents.Table> 하지 않습니다. <xref:System.Windows.Controls.Grid> 요소를 사용 하면 계층의 자식 콘텐츠를 단일 "셀입니다." 내에 있는 둘 이상의 요소 허용 <xref:System.Windows.Documents.Table> 레이어를 지원 하지 않습니다. 자식 요소는 <xref:System.Windows.Controls.Grid> 해당 "셀" 경계 영역을 기준으로 절대적으로 배치 될 수 있습니다. <xref:System.Windows.Documents.Table> 이 기능을 지원 하지 않습니다. 마지막으로 한 <xref:System.Windows.Controls.Grid> 는 보다 간단은 <xref:System.Windows.Documents.Table>합니다.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>열 및 행의 크기 조정 동작  
 내에 정의 된 행과 열을 <xref:System.Windows.Controls.Grid> 활용할 수 있습니다 <xref:System.Windows.GridUnitType.Star> 나머지 공간을 비례적으로 배포 하기 위해 크기 조정 합니다. 때 <xref:System.Windows.GridUnitType.Star> 높이 또는 너비 행 이나 열 또는 행에는 나머지 사용 가능 공간에 대 한 가중치를 받는 열으로 선택 됩니다. 이 달리 <xref:System.Windows.GridUnitType.Auto>에 공간 열 또는 행 내의 콘텐츠 크기에 따라 균등 하 게 배포 됩니다. 이 값은 `*` 또는 `2*`([!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용할 경우)로 표현됩니다. 첫 번째 경우에 행 또는 열에는 사용 가능한 공간의 1배가 할당되고, 두 번째 경우에는 2배가 할당됩니다. 이 기술을 사용 하 여 공간을 비례적으로 배포를 결합 하 여를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 하 고 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 값 `Stretch` 화면 공간의 비율로 레이아웃 공간을 분할할 수 있습니다. <xref:System.Windows.Controls.Grid> 이 방식으로 공간을 배분할 수 있는 유일한 레이아웃 패널 이며  
  
#### <a name="defining-and-using-a-grid"></a>그리드 정의 및 사용  
 다음 예제에서는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] [시작] 메뉴에 제공되는 [실행] 대화 상자에 있는 UI와 같이 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 빌드하는 방법을 보여 줍니다.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 Grid 요소](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 <xref:System.Windows.Controls.StackPanel> 지정 된 방향으로 요소를 "누적" 할 수 있습니다. 기본 누적 방향은 세로 방향입니다. <xref:System.Windows.Controls.StackPanel.Orientation%2A> 콘텐츠 흐름을 제어 하려면 속성을 사용할 수 있습니다.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel 및 DockPanel  
 하지만 <xref:System.Windows.Controls.DockPanel> 수 또한 "스택" 자식 요소인 <xref:System.Windows.Controls.DockPanel> 및 <xref:System.Windows.Controls.StackPanel> 몇 가지 사용 시나리오에서 유사한 결과 생성 하지 않습니다. 자식 요소의 순서는 크기에 영향을 줄 수는 예를 들어, 한 <xref:System.Windows.Controls.DockPanel> 되지 않습니다는 <xref:System.Windows.Controls.StackPanel>합니다. 왜냐하면 <xref:System.Windows.Controls.StackPanel> 에서 쌓는 방향으로 측정 <xref:System.Double.PositiveInfinity>반면 <xref:System.Windows.Controls.DockPanel> 사용 가능한 크기를 측정 합니다.  
  
 다음 예제에서는 이 키의 차이를 보여 줍니다.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 이 그림에서 렌더링 동작의 차이를 확인할 수 있습니다.  
  
 ![스크린샷: StackPanel 및 DockPanel 스크린샷](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>StackPanel 정의 및 사용  
 다음 예제에 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.StackPanel> 세로로 배치 된 단추 집합을 만들려고 합니다. 가로 위치 지정을 설정 합니다 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성을 <xref:System.Windows.Controls.Orientation.Horizontal>입니다.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 StackPanel 요소](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서는 다음의 변형은 <xref:System.Windows.Controls.StackPanel> 자동으로 "가상화" 데이터 바인딩된 자식 콘텐츠는 요소입니다. 여기서 가상화라는 단어는 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 요소의 하위 집합이 생성되는 기술을 가리킵니다. 특정 시점에 화면에 표시되는 것보다 많은 개수의 UI 요소를 생성하는 것은 메모리 및 프로세서 측면에서 비효율적입니다. <xref:System.Windows.Controls.VirtualizingStackPanel> (에서 제공 하는 기능을 통해 <xref:System.Windows.Controls.VirtualizingPanel>) 표시 되는 항목을 계산 하 고 작동 합니다 <xref:System.Windows.Controls.ItemContainerGenerator> 에서 <xref:System.Windows.Controls.ItemsControl> (같은 <xref:System.Windows.Controls.ListBox> 또는 <xref:System.Windows.Controls.ListView>)만 표시 되는 항목에 대 한 요소를 만드는 합니다.  
  
 합니다 <xref:System.Windows.Controls.VirtualizingStackPanel> 요소와 같은 컨트롤에 대 한 호스트 항목으로 자동으로 설정 됩니다는 <xref:System.Windows.Controls.ListBox>합니다. 호스팅 데이터 바인딩된 컬렉션에 콘텐츠는 자동으로 가상화 범위 내에서 콘텐츠를으로 <xref:System.Windows.Controls.ScrollViewer>합니다. 이렇게 하면 많은 자식 항목을 호스트할 때 성능이 향상됩니다.  
  
 다음 태그를 사용 하는 방법에 설명 된 <xref:System.Windows.Controls.VirtualizingStackPanel> 을 항목 호스트로 합니다. 합니다 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> 연결 된 속성으로 설정 되어 있어야 `true` 가상화를 수행 하려면 (기본값).  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> 자식 요소의 위치를 왼쪽에서 오른쪽, 해당 부모 컨테이너의 가장자리에 도달 하면 다음 줄으로 콘텐츠를 순차적으로 배치에서 하는 데 사용 됩니다. 콘텐츠는 가로 또는 세로 방향으로 설정할 수 있습니다. <xref:System.Windows.Controls.WrapPanel> 간단한 유동 유용 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오입니다. 또한 모든 자식 요소에 균일한 크기를 적용하는 데 사용될 수 있습니다.  
  
 다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.WrapPanel> 표시할 <xref:System.Windows.Controls.Button> 해당 컨테이너의 가장자리에 도달할 때 줄 바꿈 하는 컨트롤입니다.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 WrapPanel 요소](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>중첩 Panel 요소  
 <xref:System.Windows.Controls.Panel> 복잡 한 레이아웃을 생성 하기 위해 요소를 서로 중첩할 수 있습니다. 이 하나 있는 경우에 매우 유용 입증할 수 있습니다 <xref:System.Windows.Controls.Panel> 부분에 대 한 적합을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 있지만 다른 일부의 요구를 충족 하지 않을 수 있습니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
 응용 프로그램에서 지원할 수 있는 중첩 횟수에는 실제로 제한이 없지만, 일반적으로 원하는 레이아웃에 실제로 필요한 패널만 사용하도록 응용 프로그램을 제한하는 것이 가장 좋습니다. 대부분의 경우에 <xref:System.Windows.Controls.Grid> 요소는 레이아웃 컨테이너로 서의 유연성 때문에 중첩된 패널 대신 사용할 수 있습니다. 이 요소를 통해 불필요한 요소를 트리에서 제거하여 응용 프로그램 성능을 향상할 수 있습니다.  
  
 다음 예제에서는 만드는 방법을 보여 줍니다.는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 는 중첩 된 <xref:System.Windows.Controls.Panel> 특정 레이아웃을 얻기 위해 요소입니다. 이 특정 예제의 <xref:System.Windows.Controls.DockPanel> 요소를 제공 하는 데 사용 됩니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 구조체와 중첩 <xref:System.Windows.Controls.StackPanel> 요소를 <xref:System.Windows.Controls.Grid>, 및 <xref:System.Windows.Controls.Canvas> 정확 하 게 부모 내의 자식 요소를 배치 하는 데 사용 됩니다 <xref:System.Windows.Controls.DockPanel>합니다.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![중첩된 패널의 이점을 활용하는 UI](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>사용자 지정 Panel 요소  
 하는 동안 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 유연한 레이아웃 컨트롤을 사용자 지정 레이아웃 동작을 재정의 하 여 얻을 수도 있습니다 배열을 제공 합니다 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 고 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드. 사용자 지정 크기 조정 및 위치 지정을 수행하려면 이러한 재정의 메서드 내에 새로운 위치 지정 동작을 정의합니다.  
  
 마찬가지로, 사용자 지정 레이아웃 동작에 따라 파생 클래스 (같은 <xref:System.Windows.Controls.Canvas> 또는 <xref:System.Windows.Controls.Grid>)를 재정의 하 여 정의할 수 있습니다 해당 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 고 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드.  
  
 다음 태그에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.Panel> 요소입니다. 이 새 <xref:System.Windows.Controls.Panel>로 정의 되 `PlotPanel`, 하드 코드를 사용 하 여 자식 요소의 위치를 지원 *x-* 하 고 *y*좌표입니다. 이 예제는 <xref:System.Windows.Shapes.Rectangle> 요소 (표시 되지 않음)는 플롯 지점 50에 배치 됩니다 (*x*), 자에서 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 더 복잡한 사용자 지정 패널 구현을 보려면 [Create a Custom Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979)(사용자 지정 콘텐츠 줄 바꿈 패널 샘플 만들기)을 참조하세요.  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>지역화/세계화 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 지역화 가능한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 만들기에 유용한 다양한 기능을 지원합니다.  
  
 모든 패널 요소는 기본적으로 지원 합니다 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 동적으로 사용자의 로캘이나 언어 설정을 기반으로 하는 콘텐츠의 흐름에 사용할 수 있는 속성입니다. 자세한 내용은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 참조하세요.  
  
 합니다 <xref:System.Windows.Window.SizeToContent%2A> 응용 프로그램 개발자는 메커니즘을 제공 하는 속성의 요구를 예상 하 지역화 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 사용 하는 <xref:System.Windows.SizeToContent.WidthAndHeight> 부모가이 속성의 값 <xref:System.Windows.Window> 항상 콘텐츠에 맞게 동적으로 크기를 조정 하 고 인위적인 높이 또는 너비 제한으로 제한 되지 않습니다.  
  
 <xref:System.Windows.Controls.DockPanel>를 <xref:System.Windows.Controls.Grid>, 및 <xref:System.Windows.Controls.StackPanel> 에 대 한 모든 적절 한 선택은 지역화할 수 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. <xref:System.Windows.Controls.Canvas> 하지만 적합 하지 않습니다, 위치에 배치 하므로 콘텐츠 물론 지역화 하기가 어렵습니다.  
  
 지역화 가능한 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]가 포함된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 만드는 방법에 대한 자세한 내용은 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [WPF 레이아웃 갤러리 샘플](https://go.microsoft.com/fwlink/?LinkID=160054)  
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)  
 [WPF Controls Gallery Sample](https://go.microsoft.com/fwlink/?LinkID=160053)(WPF 컨트롤 갤러리 샘플)  
 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [사용자 지정 콘텐츠 줄 바꿈 패널 샘플 만들기](https://go.microsoft.com/fwlink/?LinkID=159979)  
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
