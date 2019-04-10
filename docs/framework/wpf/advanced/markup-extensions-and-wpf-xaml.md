---
title: 태그 확장명 및 WPF XAML
ms.date: 03/30/2017
helpviewer_keywords:
- brace character [WPF]
- Binding markup extensions [WPF]
- RelativeSource markup extensions [WPF]
- XAML [WPF], markup extensions
- markup extensions [WPF]
- nesting extension syntax [WPF]
- curly brace characters ({})
- TemplateBinding markup extensions [WPF]
- StaticResource markup extensions [WPF]
- literal curly brace characters ({})
- characters [WPF], curly brace
- DynamicResource markup extensions [WPF]
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
ms.openlocfilehash: 46539f0cfdcc478e2f5e4cd7aecf16ac059e6332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148099"
---
# <a name="markup-extensions-and-wpf-xaml"></a>태그 확장명 및 WPF XAML
이 항목에서는 XAML 태그 확장의 구문 규칙, 용도, 기반이 되는 클래스 개체 모델 등을 비롯한 개념에 대해 소개합니다. 태그 확장은 XAML 언어의 일반적 기능이며 XAML 서비스에 대한 .NET 구현의 일반적 기능입니다. 이 항목에서는 WPF XAML에서 사용할 태그 확장에 대해 자세히 설명합니다.  

<a name="XAML_Processors_and_Markup_Extensions"></a>   
## <a name="xaml-processors-and-markup-extensions"></a>XAML 프로세서 및 태그 확장  
 일반적으로 XAML 파서는 특성 값을 기본 형식으로 변환 가능한 리터럴 문자열로 해석하거나 특정 방법에 따라 개체로 변환할 수 있습니다. 이러한 방법 중 하나는 형식 변환기를 참조하는 것이며, 이에 대한 설명은 [TypeConverter 및 XAML](typeconverters-and-xaml.md) 항목에 나와 있습니다. 하지만 이와 다른 동작이 필요한 경우도 있습니다. 예를 들어 특성 값 때문에 개체 그래프에 새 개체가 나타나지 않도록 XAML 프로세서에 지시할 수 있습니다. 이 경우 해당 특성은 개체 그래프의 다른 부분에 있는 이미 생성된 개체 또는 정적 개체에 대한 참조를 만드는 개체 그래프가 나타나게 해야 합니다. 또 다른 시나리오로 기본값이 아닌 인수를 개체 생성자에 제공하는 구문을 사용하도록 XAML 프로세서에 지시할 수도 있습니다. 이러한 시나리오 유형의 경우 태그 확장을 통해 해결책을 찾을 수 있습니다.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## <a name="basic-markup-extension-syntax"></a>기본 태그 확장 구문  
 태그 확장은 특성에서 사용되는 속성, 속성 요소에서 사용되는 속성 또는 두 속성 모두의 값을 제공하도록 구현할 수 있습니다.  
  
 특성 값을 제공하는 데 사용되는 경우 XAML 프로세서는 구문에서 여는 중괄호와 닫는 중괄호({ 및 })를 통해 태그 확장 시퀀스를 구분합니다. 태그 확장 형식은 여는 중괄호 바로 다음에 오는 문자열 토큰으로 식별됩니다.  
  
 속성 요소 구문에 사용되는 경우 태그 확장은 속성 요소 값을 제공하는 데 사용되는 다른 요소와 시각적으로 동일합니다. 즉, 태그 확장 클래스를 요소로 참조하는 XAML 요소 선언을 꺾쇠 괄호(<>)로 묶습니다.  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## <a name="xaml-defined-markup-extensions"></a>XAML 정의 태그 확장명  
 XAML의 WPF 구현과 관련되지 않고 대신 XAML의 내장 형식 또는 기능 구현에서 언어로 사용되는 몇 가지 태그 확장도 있습니다. 이러한 태그 확장은 System.Xaml 어셈블리에 일반적인 .NET Framework XAML 서비스의 일부로 구현되어 있으며, XAML 언어 XAML 네임스페이스 내에 있습니다. 일반적인 태그 사용법에서 볼 수 있는 것처럼 이러한 태그 확장은 대개 사용법에서 `x:` 접두사로 식별됩니다. <xref:System.Windows.Markup.MarkupExtension> XAML 판독기 및 WPF XAML에서 비롯 한 XAML 작성기에서 지원 되도록 하기 위해 모든 태그 확장 사용 해야 하는 패턴을 제공 하는 기본 클래스 (System.Xaml에 정의).  
  
-   `x:Type` 제공 된 <xref:System.Type> 명명 된 형식에 대 한 개체입니다. 이 기능은 스타일 및 템플릿에서 가장 많이 사용됩니다. 자세한 내용은 [x:Type 태그 확장](../../xaml-services/x-type-markup-extension.md)을 참조하세요.  
  
-   `x:Static` 정적 값을 생성합니다. 값은 직접적으로 대상 속성 값의 형식이 아니라 해당 형식으로 계산될 수 있는 값-형식 코드 엔터티에서 생성됩니다. 자세한 내용은 [x:Static 태그 확장](../../xaml-services/x-static-markup-extension.md)을 참조하세요.  
  
-   `x:Null` 지정 `null` 속성에 대 한 값으로 특성 또는 속성 요소 값에 사용할 수 있습니다. 자세한 내용은 [x:Null 태그 확장](../../xaml-services/x-null-markup-extension.md)을 참조하세요.  
  
-   `x:Array` 컨트롤 모델은 의도적으로 사용 되지 및 WPF 기본 요소에서 제공 하는 컬렉션 지원이 있는 경우 XAML 구문에서 일반적인 배열 만들기에 대 한 지원을 제공 합니다. 자세한 내용은 [x:Array 태그 확장](../../xaml-services/x-array-markup-extension.md)을 참조하세요.  
  
> [!NOTE]
>  `x:` 접두사는 XAML 파일 또는 프로덕션의 루트 요소에서 XAML 언어 내장 형식의 일반적인 XAML 네임스페이스 매핑에 사용됩니다. WPF 응용 프로그램에 대 한 Visual Studio 템플릿을 사용 하 여 XAML 파일을 시작 하는 예를 들어 `x:` 매핑. 사용자 고유의 XAML 네임스페이스 매핑에서 다른 접두사 토큰을 선택할 수 있지만 이 설명서에서는 특정 프레임워크와 관련되지 않은 WPF 기본 네임스페이스나 다른 XAML 네임스페이스와 달리 XAML 언어의 XAML 네임스페이스에서 정의된 부분인 해당 엔터티를 식별하는 방법으로 기본 `x:` 매핑을 가정합니다.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## <a name="wpf-specific-markup-extensions"></a>WPF 관련 태그 확장  
 WPF 프로그래밍에서 사용되는 가장 일반적인 태그 확장은 리소스 참조(`StaticResource` 및 `DynamicResource`)를 지원하는 태그 확장과 데이터 바인딩(`Binding`)을 지원하는 태그 확장입니다.  
  
-   `StaticResource` 이미 정의 된 리소스의 값을 대체 하 여 속성 값을 제공 합니다. `StaticResource` 평가는 궁극적으로 XAML 로드 시간에 수행되고 런타임에는 개체 그래프에 액세스하지 못합니다. 자세한 내용은 [StaticResource 태그 확장](staticresource-markup-extension.md)을 참조하세요.  
  
-   `DynamicResource` 해당 값이 리소스에 대 한 런타임 참조가 되도록 지연 하 여 속성에 대 한 값을 제공 합니다. 동적 리소스 참조는 리소스가 액세스될 때마다 새로 조회하도록 하고 런타임에 개체 그래프에 액세스합니다. 이 액세스를 얻기 위해 WPF 속성 시스템의 종속성 속성 및 계산된 식에 의해 `DynamicResource` 개념이 지원됩니다. 따라서 종속성 속성 대상에는 `DynamicResource`만 사용할 수 있습니다. 자세한 내용은 [DynamicResource 태그 확장](dynamicresource-markup-extension.md)을 참조하세요.  
  
-   `Binding` 데이터 바인딩된 속성의 경우 런타임에 부모 개체에 적용 되는 데이터 컨텍스트를 사용 하 여 값을 제공 합니다. 이 태그 확장은 데이터 바인딩을 지정하는 인라인 구문을 사용하기 때문에 비교적 복잡합니다. 자세한 내용은 [Binding 태그 확장](binding-markup-extension.md)을 참조하세요.  
  
-   `RelativeSource` 에 대 한 소스 정보를 제공 된 <xref:System.Windows.Data.Binding> 런타임 개체 트리에서 가능한 여러 관계를 탐색할 수 있는 합니다. 즉, 주변 개체 트리에 대한 완전한 지식 없이 코드에 생성되거나 다용도 템플릿에 생성되는 바인딩에 대한 특수한 소스를 제공합니다. 자세한 내용은 [RelativeSource 태그 확장](relativesource-markupextension.md)을 참조하세요.  
  
-   `TemplateBinding` 컨트롤 템플릿에서를 템플릿을 사용 하는 클래스의 개체-모델 정의 속성에서 제공 하는 템플릿 기반 속성 값을 사용할 수 있습니다. 즉, 템플릿 정의 내의 속성은 템플릿이 적용된 후의 컨텍스트에만 액세스할 수 있습니다. 자세한 내용은 [TemplateBinding 태그 확장](templatebinding-markup-extension.md)을 참조하세요. `TemplateBinding`의 실질적인 사용 방법에 대한 자세한 내용은 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
-   `ColorConvertedBitmap` 비교적 고급 이미징 시나리오를 지원합니다. 자세한 내용은 [ColorConvertedBitmap 태그 확장](colorconvertedbitmap-markup-extension.md)을 참조하세요.  
  
-   `ComponentResourceKey` 및 `ThemeDictionary` 리소스 및 사용자 지정 컨트롤을 사용 하 여 패키지 된 테마에 대해 특히 리소스 조회를 지원 합니다. 자세한 내용은 [ComponentResourceKey 태그 확장](componentresourcekey-markup-extension.md), [ThemeDictionary 태그 확장](themedictionary-markup-extension.md) 또는 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.  
  
<a name="StarExtension"></a>   
## <a name="extension-classes"></a>*Extension 클래스  
 일반 XAML 언어와 WPF 관련 태그 확장에 대 한 각 태그 확장의 동작을 통해 XAML 프로세서로 식별 되는 `*Extension` 에서 파생 된 클래스 <xref:System.Windows.Markup.MarkupExtension>의 구현을 제공 하 고는 <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A> 메서드입니다. 각 확장에서 이 메서드는 태그 확장이 평가될 때 반환되는 개체를 제공합니다. 반환되는 개체는 대개 태그 확장에 전달된 다양한 문자열 토큰을 기반으로 평가됩니다.  
  
 예를 들어 합니다 <xref:System.Windows.StaticResourceExtension> 클래스는 실제 리소스 조회의 표면적인 구현을 제공 되도록 해당 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> 구현을 해당 특정 구현 하는 데 사용 되는 문자열의 입력을 사용 하 여 요청 되는 개체를 반환 합니다. 리소스를 조회 해당 `x:Key`합니다. 기존 태그 확장을 사용할 때에는 이러한 구현 세부 사항이 중요하지 않습니다.  
  
 일부 태그 확장에는 문자열 토큰 인수가 사용되지 않습니다. 이는 태그 확장이 정적 값 또는 일정한 값을 반환하기 때문이거나, 반환해야 하는 값의 컨텍스트가 `serviceProvider` 매개 변수로 전달된 서비스 중 하나를 통해 사용 가능하기 때문입니다.  
  
 `*Extension` 이름 지정 패턴은 편의성과 일관성을 고려한 것입니다. XAML 프로세서가 해당 클래스를 태그 확장에 대한 지원으로 식별하는 데 필요한 것은 아닙니다. 코드 베이스 System.Xaml이 포함 하 고.NET Framework XAML 서비스 구현을 사용 한다면 모든는 XAML 태그 확장에서 파생 하는 것으로 인식 하는 데 필요한 <xref:System.Windows.Markup.MarkupExtension> 고 생성 구문을 지원 합니다. WPF 따르지 않는 태그 확장 사용 클래스를 정의 합니다 `*Extension` 명명 패턴을 예를 들어 <xref:System.Windows.Data.Binding>합니다. 이와 같은 일반적인 이유는 클래스 지원 시나리오가 순수한 태그 확장 지원의 범위를 벗어나기 때문입니다. 경우 <xref:System.Windows.Data.Binding>, 클래스는 XAML과 관련이 있는 시나리오에 대 한 개체의 메서드 및 속성에 대 한 런타임 액세스를 지원 하 합니다.  
  
### <a name="extension-class-interpretation-of-initialization-text"></a>초기화 텍스트의 확장 클래스 해석  
 XAML 프로세서는 중괄호 안에서 태그 확장 이름 다음에 나오는 문자열 토큰을 다음 방법 중 하나로 해석합니다.  
  
-   쉼표는 항상 개별 토큰의 분리 기호나 구분 기호를 나타냅니다.  
  
-   구분된 개별 토큰에 등호가 포함되지 않은 경우 각 토큰은 생성자 인수로 처리됩니다. 각 생성자 매개 변수는 해당 시그니처에 필요한 형식과 순서로 지정되어야 합니다.  
  
    > [!NOTE]
    >  XAML 프로세서는 여러 쌍 중 인수 수가 일치하는 생성자를 호출해야 합니다. 따라서 사용자 지정 태그 확장을 구현 하는 경우 제공 하지 않습니다 여러 생성자 인수 수가 동일한. 매개 변수 수가 동일한 태그 확장 생성자 경로가 둘 이상 있을 때의 XAML 프로세서 동작은 정의되어 있지 않지만, 태그 확장 형식 정의에 이 상황이 있는 경우 XAML 프로세서에서 사용에 대한 예외를 throw할 수 있다고 예상해야 합니다.  
  
-   구분된 개별 토큰에 등호가 있으면 XAML 프로세서는 먼저 태그 확장의 기본 생성자를 호출합니다. 그런 다음 각 이름=값 쌍이 태그 확장에 존재하는 속성 이름과 해당 속성에 할당할 값으로 해석됩니다.  
  
-   태그 확장에서 생성자 동작과 속성 설정 동작이 동일한 경우에는 어떤 동작을 사용해도 관계가 없습니다. 설정 가능한 속성이 둘 이상 있는 태그 확장에서는 *property*`=`*value* 쌍을 사용하는 것이 보다 일반적입니다. 그 이유는 태그의 의도를 더욱 명확하게 지정할 수 있고, property=value 쌍을 지정할 경우 속성 순서가 중요하지 않으므로 실수로 생성자 매개 변수 순서가 바뀌는 일을 방지할 수 있기 때문입니다. 또한 태그 확장이 설정 가능한 속성을 모두 설정하는 생성자 매개 변수를 제공한다는 보장이 없습니다. 예를 들어 <xref:System.Windows.Data.Binding> 에서 확장을 통해 설정할 수 있는 많은 속성을 사용 하 여는 태그 확장 *속성*`=`*값* 폼 있지만 <xref:System.Windows.Data.Binding> 두 지원 생성자: 기본 생성자와 초기 경로 설정 하는 것입니다.  
  
-   리터럴 쉼표는 이스케이프 없이 태그 확장에 전달할 수 없습니다.  
  
<a name="EscapeSequences"></a>   
## <a name="escape-sequences-and-markup-extensions"></a>이스케이프 시퀀스 및 태그 확장  
 XAML 프로세서의 특성 처리에서는 중괄호를 태그 확장 시퀀스의 표시기로 사용합니다. 또한 필요한 경우에는 리터럴 중괄호 다음에 비어 있는 중괄호 쌍을 사용하여 이스케이프 시퀀스를 입력함으로써 리터럴 중괄호 문자 특성 값을 생성할 수 있습니다. 참조 [ {} 이스케이프 시퀀스-태그 확장](../../xaml-services/escape-sequence-markup-extension.md)합니다.  
  
<a name="Nesting"></a>   
## <a name="nesting-markup-extensions-in-xaml-usage"></a>XAML에서 중첩 태그 확장 사용법  
 여러 태그 확장을 중첩할 수 있으며 각 태그 확장은 가장 깊은 수준부터 평가됩니다. 예를 들어 다음 사용법을 가정해 봅니다.  
  
```  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
```  
  
 이 사용법에서 `x:Static` 문이 먼저 평가되고 문자열이 반환됩니다. 그런 다음 해당 문자열은 `DynamicResource`의 인수로 사용됩니다.  
  
## <a name="markup-extensions-and-property-element-syntax"></a>태그 확장 및 속성 요소 구문  
 속성 요소 값을 채우는 개체 요소로 사용된 경우에는 태그 확장 클래스를 XAML에서 사용할 수 있는 일반적인 형식 기반 개체 요소와 시각적으로 구분할 수 없습니다. 이 경우 일반적인 개체 요소와 태그 확장 간의 실질적인 차이는 태그 확장이 형식화된 값으로 계산되거나 식으로 지연된다는 점입니다. 따라서 다른 프로그래밍 모델에서 런타임에 바인딩되는 속성이 처리되는 방식과 마찬가지로 태그 확장의 속성 값에서 발생할 수 있는 형식 오류에 대한 메커니즘이 달라집니다. 일반적인 개체 요소는 XAML이 구문 분석될 때 해당 요소가 설정하고 있는 대상 속성을 기준으로 형식 일치 여부가 평가됩니다.  
  
 속성 요소를 채우는 개체 요소 구문에 사용되는 대부분의 태그 확장에는 콘텐츠나 추가 속성 요소 구문이 없습니다. 따라서 개체 요소 태그를 닫고 자식 요소를 제공하지 않을 수 있습니다. XAML 프로세서에서 개체 요소를 발견할 때마다 해당 클래스의 생성자가 호출되어 구문 분석된 요소에서 생성되는 개체를 인스턴스화합니다. 태그 확장 클래스의 경우에도 마찬가지입니다. 개체 요소 구문에서 태그 확장을 사용할 수 있으려면 기본 생성자를 제공해야 합니다. 일부 기존 태그 확장에는 효율적인 초기화를 위해 지정해야 하는 필수 속성 값이 적어도 하나는 있습니다. 이런 경우 해당 속성 값은 대개 개체 요소에 속성 특성으로 지정됩니다. 에 [XAML Namespace (x:) 언어 기능](../../xaml-services/xaml-namespace-x-language-features.md) 하 고 [WPF XAML 확장](wpf-xaml-extensions.md) 참조 페이지에는 태그 확장에 필요한 속성 (및 필수 속성의 이름) 표시 됩니다. 또한 참조 페이지에는 특정 태그 확장에서 개체 요소 구문이나 특성 구문을 사용할 수 없는지 여부도 나와 있습니다. 예를 들어 [x:Array 태그 확장](../../xaml-services/x-array-markup-extension.md)의 경우에는 배열의 내용을 태그에서 콘텐츠로 지정해야 하기 때문에 특성 구문을 사용할 수 없습니다. 배열 내용은 일반 개체로 처리되므로 특성에 대한 기본 형식 변환기를 사용할 수 없습니다. [x:Array 태그 확장](../../xaml-services/x-array-markup-extension.md)에는 `type` 매개 변수도 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [XAML 개요(WPF)](xaml-overview-wpf.md)
- [XAML 네임스페이스(x:) 언어 기능](../../xaml-services/xaml-namespace-x-language-features.md)
- [WPF XAML 확장](wpf-xaml-extensions.md)
- [StaticResource 태그 확장](staticresource-markup-extension.md)
- [Binding 태그 확장](binding-markup-extension.md)
- [DynamicResource 태그 확장](dynamicresource-markup-extension.md)
- [x:Type 태그 확장](../../xaml-services/x-type-markup-extension.md)
