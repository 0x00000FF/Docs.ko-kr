---
title: 스타일 지정 및 템플릿
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- triggers [WPF]
- styles [WPF], referencing
- event triggers [WPF]
- styles [WPF], prerequisites
- styles [WPF], declaring
- styles [WPF], overview
- styles [WPF], extending
- styles [WPF], triggers
- styles [WPF], event triggers
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
ms.openlocfilehash: 3fae4993a13b02ad998668f644a80ba7c07196fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132299"
---
# <a name="styling-and-templating"></a>스타일 지정 및 템플릿
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 스타일 지정 및 템플릿 집합 개발자와 디자이너가 시각적으로 멋진 효과를 만들고 해당 제품에 대해 일관 된 모양을 만들려면 허용 하는 기능 (스타일, 템플릿, 트리거 및 스토리 보드)을 참조 하십시오. 개발자 및/또는 디자이너는 애플리케이션에 따라 모양을 광범위하게 사용자 지정할 수 있지만 애플리케이션 내에서 또는 애플리케이션 간에 모양을 유지 관리 및 공유하려면 강력한 스타일 지정 및 템플릿 모델이 필요합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이 모델을 제공 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 지정 모델의 또 다른 기능은 프레젠테이션과 논리의 분리입니다. 즉, 개발자가 C# 또는 Visual Basic을 사용하여 프로그래밍 논리 작업을 수행할 때 동시에 디자이너가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]만 사용하여 애플리케이션 모양 작업을 수행할 수 있습니다.  
  
 이 개요에서는 애플리케이션의 스타일 지정 및 템플릿 측면을 집중적으로 살펴보고 데이터 바인딩 개념은 설명하지 않습니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.  
  
 또한 스타일 및 템플릿을 재사용할 수 있게 해주는 리소스를 이해해야 합니다. 리소스에 대한 자세한 내용은 [XAML 리소스](../advanced/xaml-resources.md)를 참조하세요.

<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>스타일 지정 및 템플릿 샘플  
 이 개요에 사용된 코드 예제는 다음 그림에 표시된 간단한 사진 샘플을 기반으로 합니다.  
  
 ![스타일 지정된 ListView](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 이 간단한 사진 샘플에서는 스타일 지정 및 템플릿을 사용하여 시각적으로 눈에 띄는 사용자 환경을 만듭니다. 이 샘플에는 두 개의 <xref:System.Windows.Controls.TextBlock> 요소 및 <xref:System.Windows.Controls.ListBox> 이미지 목록에 바인딩되는 컨트롤입니다. 전체 샘플을 보려면 [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(스타일 지정 및 템플릿 샘플 소개)을 참조하세요.  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>스타일 기본 사항  
 생각할 수 있습니다는 <xref:System.Windows.Style> 둘 이상의 요소에 속성 값 집합을 적용 하는 편리한 방법으로 합니다. 예를 들어, 다음 사항을 고려 <xref:System.Windows.Controls.TextBlock> 요소와 기본 모양을:  
  
 [!code-xaml[StylingIntroSample_snippet#TextBlocks](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![스타일 샘플 스크린 샷](./media/stylingintro-textblocksbefore.PNG "StylingIntro_TextBlocksBefore")  
  
 와 같은 속성을 설정 하 여 기본 모양을 변경할 수 있습니다 <xref:System.Windows.Controls.Control.FontSize%2A> 하 고 <xref:System.Windows.Controls.Control.FontFamily%2A>, 각 <xref:System.Windows.Controls.TextBlock> 요소에서 직접. 그러나 하려는 경우에 <xref:System.Windows.Controls.TextBlock> 일부 속성을 공유 하는 요소 만들 수 있습니다를 <xref:System.Windows.Style> 에 `Resources` 의 섹션에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 다음과 같이:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb1](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 설정 하는 경우는 <xref:System.Windows.Style.TargetType%2A> 에 스타일의는 <xref:System.Windows.Controls.TextBlock> 형식 스타일을 적용할 모든는 <xref:System.Windows.Controls.TextBlock> 창에서 구성 요소입니다.  
  
 이제는 <xref:System.Windows.Controls.TextBlock> 요소가 다음과 같이 나타납니다.  
  
 ![스타일 샘플 스크린 샷](./media/stylingintro-textblocksbasestyle.PNG "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>스타일 확장  
 두 하려는 경우가 있을 것 <xref:System.Windows.Controls.TextBlock> 와 같은 일부 속성 값을 공유 하는 요소는 <xref:System.Windows.Controls.Control.FontFamily%2A> 가운데에 맞춰진 및 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, 텍스트 "내 사진" 몇 가지 추가 속성을 가질 수도 있지만. 이 작업을 수행하려면 다음과 같이 첫 번째 스타일을 기반으로 새 스타일을 만듭니다.  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 이전 스타일에는 `x:Key`가 제공됨을 알 수 있습니다. 설정한 스타일을 적용 하는 <xref:System.Windows.FrameworkElement.Style%2A> 속성에 <xref:System.Windows.Controls.TextBlock> 에 `x:Key` 값을 다음과 같이:  
  
 [!code-xaml[StylingIntroSnippet#UIText](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 이 <xref:System.Windows.Controls.TextBlock> 스타일 설정 되었습니다를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 의 값 <xref:System.Windows.HorizontalAlignment.Center>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 값 `Comic Sans MS`, <xref:System.Windows.Controls.TextBlock.FontSize%2A> 26의 값 및 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 값으로 설정 합니다 <xref:System.Windows.Media.LinearGradientBrush> 예제와 같이 합니다. 재정의 하는 <xref:System.Windows.Controls.Control.FontSize%2A> 기본 스타일의 값입니다. 둘 이상 있으면 <xref:System.Windows.Setter> 에서 동일한 속성을 설정를 <xref:System.Windows.Style>는 <xref:System.Windows.Setter> 즉 선언 된 마지막 우선 적용 됩니다.  
  
 다음은 무엇을 <xref:System.Windows.Controls.TextBlock> 요소의 모양을:  
  
 ![스타일 지정된 TextBlock](./media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 이 `TitleText` 스타일에 대해 만들어진 스타일을 확장 합니다 <xref:System.Windows.Controls.TextBlock> 형식입니다. `x:Key` 값을 사용하여 `x:Key`가 포함된 스타일을 확장할 수도 있습니다. 예를 들어 제공 하는 예제를 참조 합니다 <xref:System.Windows.Style.BasedOn%2A> 속성입니다.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>TargetType 속성 및 x:Key 특성의 관계  
 첫 번째 예제와 같이 설정 합니다 <xref:System.Windows.Style.TargetType%2A> 속성을 `TextBlock` 스타일을 할당 하지 않고는 `x:Key` 모두에 적용할 스타일을 사용 하면 <xref:System.Windows.Controls.TextBlock> 요소입니다. 이 경우 `x:Key`는 암시적으로 `{x:Type TextBlock}`으로 설정됩니다. 즉, 명시적으로 설정 하는 경우는 `x:Key` 이외의 모든 항목에 값 `{x:Type TextBlock}`의 <xref:System.Windows.Style> 모두에 적용 되지 않습니다 <xref:System.Windows.Controls.TextBlock> 요소 자동으로 합니다. 스타일을 적용 해야 하는 대신 (사용 하 여 합니다 `x:Key` 값)에 <xref:System.Windows.Controls.TextBlock> 요소 명시적으로 합니다. 스타일 리소스 섹션에 있고 설정 하지 않으면 경우는 <xref:System.Windows.Style.TargetType%2A> 속성에서 스타일을 지정 해야 합니다는 `x:Key`합니다.  
  
 에 대 한 기본값을 제공 하는 것 외에도 합니다 `x:Key`, <xref:System.Windows.Style.TargetType%2A> 속성 setter 속성이 적용 되는 형식을 지정 합니다. 지정 하지 않는 경우는 <xref:System.Windows.Style.TargetType%2A>의 속성을 정규화 해야 하 <xref:System.Windows.Setter> 구문을 사용 하 여 클래스 이름으로 개체 `Property="ClassName.Property"`합니다. 예를 들어, 설정 하는 대신 `Property="FontSize"`를 설정 해야 합니다 <xref:System.Windows.Setter.Property%2A> 하 `"TextBlock.FontSize"` 또는 `"Control.FontSize"`.  
  
 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 조합으로 구성됩니다. 한 형식의 모든 컨트롤에 적용되는 스타일을 만들 경우 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 대상으로 하는 스타일을 만들를 <xref:System.Windows.Controls.TextBlock> 입력을 <xref:System.Windows.Window>, 모든 스타일 적용 됩니다 <xref:System.Windows.Controls.TextBlock> 창에서 컨트롤 경우에는 <xref:System.Windows.Controls.TextBlock> 와 같은 다른 컨트롤의 파트는는 <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>스타일 및 리소스  
 파생 된 모든 요소에 스타일을 사용할 수 있습니다 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 스타일을 선언하는 가장 일반적인 방법은 이전 예제와 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 `Resources` 섹션에서 리소스로 선언하는 것입니다. 스타일은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 따라야 합니다. 스타일을 선언하는 위치가 스타일이 적용될 수 있는 위치에 영향을 미칩니다. 예를 들어 스타일을 애플리케이션 정의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 루트 요소에서 선언하면 애플리케이션의 모든 곳에서 스타일을 사용할 수 있습니다. 탐색 애플리케이션을 만들고 스타일을 애플리케이션의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 중 하나에서 선언하면 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에서만 스타일을 사용할 수 있습니다. 리소스 범위 지정 규칙에 대한 자세한 내용은 [XAML 리소스](../advanced/xaml-resources.md)를 참조하세요.  
  
 또한 이 개요의 뒷부분에 있는 [공유 리소스 및 테마](#styling_themes)에서 스타일 및 리소스에 대한 추가 정보를 찾을 수 있습니다.  
  
### <a name="setting-styles-programmatically"></a>프로그래밍 방식으로 스타일 설정  
 요소에 명명된 된 스타일에 프로그래밍 방식으로 할당 하려면 스타일 리소스 컬렉션에서 가져오고 요소에 할당할 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다. 형식의 리소스 컬렉션의 항목에는 <xref:System.Object>합니다. 따라서 검색된 된 스타일을 캐스팅 해야 합니다는 <xref:System.Windows.Style> 에 할당 하기 전에 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다. 예를 들어 정의 된 설정 `TitleText` 에서 스타일을 <xref:System.Windows.Controls.TextBlock> 라는 `textblock1`, 다음을 수행:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 스타일이 적용된 후에는 봉인되고 변경할 수 없습니다. 이미 적용된 스타일을 동적으로 변경하려면 기존 스타일을 대체할 새 스타일을 만들어야 합니다. 자세한 내용은 <xref:System.Windows.Style.IsSealed%2A> 속성을 참조하세요.  
  
 사용자 지정 논리에 따라 적용할 스타일을 선택하는 개체를 만들 수 있습니다. 예를 들어 제공 하는 예제를 참조 합니다 <xref:System.Windows.Controls.StyleSelector> 클래스입니다.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>바인딩, 동적 리소스 및 이벤트 처리기  
 `Setter.Value` 속성을 사용하여 [Binding 태그 확장](../advanced/binding-markup-extension.md) 또는 [DynamicResource 태그 확장](../advanced/dynamicresource-markup-extension.md)을 지정할 수 있습니다. 자세한 내용은 참조에 대 한 제공 된 예제는 <xref:System.Windows.Setter.Value%2A?displayProperty=nameWithType> 속성입니다.  
  
 지금까지 이 개요에서는 setter를 사용하여 속성 값을 설정하는 방법만 설명했습니다. 스타일에서 이벤트 처리기를 지정할 수도 있습니다. 자세한 내용은 <xref:System.Windows.EventSetter>을 참조하세요.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>데이터 템플릿  
 이 샘플 응용 프로그램에는 <xref:System.Windows.Controls.ListBox> 사진 목록에 바인딩된 컨트롤입니다.  
  
 [!code-xaml[StylingIntroSnippet#UIListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 이 <xref:System.Windows.Controls.ListBox> 현재 다음과 같이 보입니다.  
  
 ![템플릿 적용 전의 ListBox](./media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 대부분 컨트롤에는 몇 가지 콘텐츠 형식이 있고 해당 콘텐츠는 보통 바인딩할 데이터에서 나옵니다. 이 샘플에서 데이터는 사진 목록입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 사용을 <xref:System.Windows.DataTemplate> 데이터의 시각적 표현을 정의 합니다. 기본적으로, 새로운 넣은 <xref:System.Windows.DataTemplate> 렌더링된 된 응용 프로그램에 데이터 모양을 결정 합니다.  
  
 샘플 애플리케이션에서 각 사용자 지정 `Photo` 개체에는 이미지의 파일 경로를 지정하는 string 형식의 `Source` 속성이 있습니다. 현재 사진 개체는 파일 경로로 표시됩니다.  
  
 만든 이미지로 표시할 사진에 대 한는 <xref:System.Windows.DataTemplate> 리소스로:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#DataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 <xref:System.Windows.DataTemplate.DataType%2A> 속성은 매우 비슷합니다는 <xref:System.Windows.Style.TargetType%2A> 의 속성을 <xref:System.Windows.Style>. 경우에 <xref:System.Windows.DataTemplate> 지정할 때는 리소스 섹션에는 합니다 <xref:System.Windows.DataTemplate.DataType%2A> 속성을 형식 할당 하 고는 `x:Key`의 <xref:System.Windows.DataTemplate> 해당 형식이 나타날 때마다 적용 됩니다. 할당 하는 옵션을 항상 해야 합니다 <xref:System.Windows.DataTemplate> 사용 하 여는 `x:Key` 로 설정한 후를 `StaticResource` 사용 하는 속성에 대 한 <xref:System.Windows.DataTemplate> 같은 형식을 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성 또는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성.  
  
 기본적으로 <xref:System.Windows.DataTemplate> 위의 예제에서 정의 될 때마다를 `Photo` 개체로 표시 됩니다는 <xref:System.Windows.Controls.Image> 내에서 <xref:System.Windows.Controls.Border>. 이 사용 하 여 <xref:System.Windows.DataTemplate>, 이제 응용 프로그램은 다음과 같습니다.  
  
 ![사진 이미지](./media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 데이터 템플릿 모델은 다른 기능을 제공합니다. 예를 들어, 사용 하 여 다른 컬렉션이 포함 된 컬렉션 데이터를 표시 하는 경우는 <xref:System.Windows.Controls.HeaderedItemsControl> 등의 입력을 <xref:System.Windows.Controls.Menu> 또는 <xref:System.Windows.Controls.TreeView>는 <xref:System.Windows.HierarchicalDataTemplate>합니다. 다른 데이터 템플릿 기능은 합니다 <xref:System.Windows.Controls.DataTemplateSelector>를 선택할 수 있습니다는 <xref:System.Windows.DataTemplate> 에 따라 사용자 지정 논리를 사용 하 합니다. 자세한 내용은 다양한 데이터 템플릿 기능을 자세히 설명하는 [템플릿 개요](../data/data-templating-overview.md)를 참조하세요.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>컨트롤 템플릿  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 컨트롤의 모양을 정의 합니다. 새 정의 하 여 컨트롤의 모양과 구조를 변경할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한 합니다. 대부분의 경우 이 방법을 사용하면 충분하므로 자체 사용자 지정 컨트롤을 작성할 필요가 없습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>트리거  
 트리거는 속성 값이 변경되거나 이벤트가 발생할 때 속성을 설정하거나 애니메이션 등의 작업을 시작합니다. <xref:System.Windows.Style>를 <xref:System.Windows.Controls.ControlTemplate>, 및 <xref:System.Windows.DataTemplate> 모두는 `Triggers` 트리거 집합을 포함할 수 있는 속성입니다. 다양한 형식의 트리거가 있습니다.  
  
### <a name="property-triggers"></a>속성 트리거  
 <xref:System.Windows.Trigger> 집합 속성 값 또는 속성의 값을 기반으로 하는 작업을 시작 하는 속성 트리거 호출 됩니다.  
  
 속성 트리거를 사용 하는 방법을 보여 주기 위해, 할 수 있습니다 각 <xref:System.Windows.Controls.ListBoxItem> 선택 되지 않은 경우 부분적으로 투명 하 게 합니다. 다음 스타일 집합을 <xref:System.Windows.UIElement.Opacity%2A> 의 값을 <xref:System.Windows.Controls.ListBoxItem> 에 `0.5`합니다. 경우는 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 속성은 `true`그러나 합니다 <xref:System.Windows.UIElement.Opacity%2A> 로 설정 된 `1.0`:  
  
 [!code-xaml[StylingIntroSample_snippet#Triggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xaml[StylingIntroSample_snippet#EndTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 이 예에서는 <xref:System.Windows.Trigger> 속성 값을 설정 하는 합니다 <xref:System.Windows.Trigger> 클래스에는 <xref:System.Windows.TriggerBase.EnterActions%2A> 및 <xref:System.Windows.TriggerBase.ExitActions%2A> 작업을 수행 하는 트리거를 사용 하도록 설정 하는 속성입니다.  
  
 있음을 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 의 속성을 <xref:System.Windows.Controls.ListBoxItem> 로 설정 된 `75`합니다. 다음 그림에서 세 번째 항목이 선택된 항목입니다.  
  
 ![스타일 지정된 ListView](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTrigger 및 and Storyboard  
 다른 유형의 트리거를 <xref:System.Windows.EventTrigger>, 일련의 이벤트의 발생을 기반으로 하는 작업을 시작 하는 합니다. 예를 들어, 다음 <xref:System.Windows.EventTrigger> 마우스 포인터가 내부로 들어갈 때 개체가 지정 하는 <xref:System.Windows.Controls.ListBoxItem>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> 속성의 값에 애니메이션 효과 `90` 조치를 `0.2` 두 번째 기간. 마우스가 항목을 떠나면 속성은 `1`초 기간에 걸쳐 원래 값으로 돌아갑니다. 확인 되는 방법을 지정 하는 데 필요한를 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 에 대 한 값을 <xref:System.Windows.ContentElement.MouseLeave> 애니메이션 합니다. 이는 애니메이션은 원래 값을 추적할 수 있기 때문입니다.  
  
 [!code-xaml[StylingIntroSample_snippet#EventTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 자세한 내용은 [스토리보드 개요](../graphics-multimedia/storyboards-overview.md)를 참조하세요.  
  
 다음 그림에서 마우스는 세 번째 항목을 가리키고 있습니다.  
  
 ![스타일 샘플 스크린 샷](./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger 및 MultiDataTrigger  
 외에 <xref:System.Windows.Trigger> 및 <xref:System.Windows.EventTrigger>, 다른 형식의 트리거가 있습니다. <xref:System.Windows.MultiTrigger> 여러 조건에 따라 속성 값을 설정할 수 있습니다. 사용할 <xref:System.Windows.DataTrigger> 고 <xref:System.Windows.MultiDataTrigger> 조건의 속성이 데이터 바인딩된 경우입니다.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>공유 리소스 및 테마  
 일반적인 Windows Presentation Foundation (WPF) 응용 프로그램을 응용 프로그램에 걸쳐 적용 되는 여러 사용자 인터페이스 (UI) 리소스가 있을 수 있습니다. 전체적으로 이 리소스 집합을 애플리케이션에 대한 테마로 간주할 수 있습니다. Windows Presentation Foundation (WPF) 지 패키징 사용자 인터페이스 (UI) 리소스를 테마로 캡슐화 된 리소스 사전을 사용 하 여는 <xref:System.Windows.ResourceDictionary> 클래스입니다.  
  
 Windows Presentation Foundation (WPF) 테마는 요소의 시각적 개체를 사용자 지정에 대 한 스타일 지정 및 Windows Presentation Foundation (WPF)를 노출 하는 템플릿 메커니즘을 사용 하 여 정의 됩니다.  
  
 Windows Presentation Foundation (WPF) 테마 리소스는 포함 된 리소스 사전에 저장 됩니다. 이러한 리소스 사전은 서명된 어셈블리에 포함되어야 하고 같은 어셈블리에 코드 자체로 포함되거나 side-by-side 어셈블리에 포함될 수 있습니다. PresentationFramework.dll, Windows Presentation Foundation (WPF) 컨트롤을 포함 하는 어셈블리의 경우 테마 리소스는 일련의 side-by-side-어셈블리에서.  
  
 테마는 요소의 스타일을 검색할 때 보이는 마지막 위치가 됩니다. 일반적으로 적절한 리소스를 검색할 때 요소 트리에서 위로 이동하면 검색이 시작되고 애플리케이션 리소스 컬렉션을 확인하고 마지막으로 시스템을 쿼리합니다. 이를 통해 애플리케이션 개발자는 테마에 도달하기 전에 트리 또는 애플리케이션 수준에서 개체에 대한 스타일을 다시 정의할 수 있습니다.  
  
 리소스 사전을 여러 애플리케이션에 걸쳐 테마를 재사용할 수 있는 개별 파일로 정의할 수 있습니다. 또한 같은 형식의 리소스를 제공하지만 값이 서로 다른 여러 리소스 사전을 정의하여 전환 가능한 테마를 만들 수 있습니다. 애플리케이션에 스킨을 지정하려면 애플리케이션 수준에서 이러한 스타일이나 다른 리소스를 다시 정의하는 것이 좋습니다.  
  
 스타일 및 템플릿, 여러 응용 프로그램에서 같은 리소스 집합을 공유를 만들 수 있습니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 및 정의 <xref:System.Windows.ResourceDictionary>입니다. 예를 들어 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)의 일부를 보여 주는 다음 그림을 살펴보겠습니다.

![컨트롤 템플릿 예제](./media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 샘플에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 살펴보면 파일에 모두 다음 항목이 포함됨을 알 수 있습니다.  
  
 [!code-xaml[ControlTemplateExamples#MergedDictionaries](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 공유 하는 것 `shared.xaml`를 정의 하는 한 <xref:System.Windows.ResourceDictionary> 동일 하 게 표시 하려면이 샘플의 컨트롤을 활성화 하는 스타일 및 브러시 리소스 집합이 포함 된 합니다.  
  
 자세한 내용은 [병합된 리소스 사전](../advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
 사용자 지정 컨트롤에 대한 테마를 만들 경우 [컨트롤 작성 개요](control-authoring-overview.md)의 외부 컨트롤 라이브러리 섹션을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [WPF의 Pack URI](../app-development/pack-uris-in-wpf.md)
- [방법: ControlTemplate에서 생성된 요소 찾기](how-to-find-controltemplate-generated-elements.md)
- [DataTemplate에서 생성된 요소 찾기](../data/how-to-find-datatemplate-generated-elements.md)
