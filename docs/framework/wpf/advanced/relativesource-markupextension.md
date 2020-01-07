---
title: RelativeSource MarkupExtension
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 15fdc9d093bb3efb4ea4cef5d4cdfa8474042f12
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559749"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="b23f8-102">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="b23f8-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="b23f8-103">[바인딩 태그 확장](binding-markup-extension.md)내에서 사용 되거나 XAML로 설정 된 <xref:System.Windows.Data.Binding> 요소의 <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성을 설정할 때 사용 되는 <xref:System.Windows.Data.RelativeSource> 바인딩 소스의 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="b23f8-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="b23f8-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="b23f8-105">XAML 특성 사용(Binding 확장 내에 중첩)</span><span class="sxs-lookup"><span data-stu-id="b23f8-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b23f8-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="b23f8-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="b23f8-107">-또는-</span><span class="sxs-lookup"><span data-stu-id="b23f8-107">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="b23f8-108">XAML 값</span><span class="sxs-lookup"><span data-stu-id="b23f8-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="b23f8-109">다음 중 하나:</span><span class="sxs-lookup"><span data-stu-id="b23f8-109">One of the following:</span></span><br /><br /> <span data-ttu-id="b23f8-110">-문자열 토큰 `Self`; <xref:System.Windows.Data.RelativeSourceMode.Self>로 설정 된 <xref:System.Windows.Data.RelativeSource.Mode%2A> 속성으로 만든 <xref:System.Windows.Data.RelativeSource>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="b23f8-111">-문자열 토큰 `TemplatedParent`; <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>로 설정 된 <xref:System.Windows.Data.RelativeSource.Mode%2A> 속성으로 만든 <xref:System.Windows.Data.RelativeSource>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="b23f8-112">-문자열 토큰 `PreviousData`; <xref:System.Windows.Data.RelativeSourceMode.PreviousData>로 설정 된 <xref:System.Windows.Data.RelativeSource.Mode%2A> 속성으로 만든 <xref:System.Windows.Data.RelativeSource>에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="b23f8-113">-`FindAncestor` 모드에 대 한 자세한 내용은 아래를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f8-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="b23f8-114">토큰 문자열 `FindAncestor`입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="b23f8-115">이 토큰을 사용하면 `RelativeSource`가 상위 항목 형식과 상위 수준(선택 사항)을 지정하는 모드로 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="b23f8-116">이것은 <xref:System.Windows.Data.RelativeSource> 속성을 <xref:System.Windows.Data.RelativeSource.Mode%2A>로 설정하여 생성한 <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="b23f8-117">`FindAncestor` 모드에 필수적인 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="b23f8-118"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> 속성을 채우는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="b23f8-119">`FindAncestor` 모드에서는 선택적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="b23f8-120">논리 트리에서 부모 방향 쪽으로 계산되는 상위 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="b23f8-121">주의</span><span class="sxs-lookup"><span data-stu-id="b23f8-121">Remarks</span></span>

<span data-ttu-id="b23f8-122">`{RelativeSource TemplatedParent}` 바인딩 사용은 컨트롤의 UI와 컨트롤의 논리를 구분 하는 더 큰 개념을 해결 하는 주요 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="b23f8-123">이를 통해 템플릿 정의 내에서 템플릿 기반 부모(템플릿이 적용되는 런타임 개체 인스턴스)로 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="b23f8-124">이 경우 [TemplateBinding 태그 확장](templatebinding-markup-extension.md) 은 실제로 다음 바인딩 식에 대 한 축약형입니다. `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="b23f8-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="b23f8-125">`TemplateBinding` 또는 `{RelativeSource TemplatedParent}` 사용법은 모두 템플릿을 정의 하는 XAML 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="b23f8-126">자세한 내용은 [TemplateBinding 태그 확장](templatebinding-markup-extension.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f8-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="b23f8-127">`{RelativeSource FindAncestor}`는 컨트롤이 항상 특정 상위 형식의 시각적 트리에 있을 것으로 예상 되는 경우 컨트롤 템플릿 또는 예측 가능한 자체 포함 UI 컴포지션에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="b23f8-128">예를 들어, 항목 컨트롤의 항목은 `FindAncestor`를 사용하여 항목 컨트롤 부모 상위 항목의 속성에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="b23f8-129">또는 템플릿에 컨트롤 컴퍼지션의 일부인 요소에서 `FindAncestor` 바인딩을 동일한 컴퍼지션 구조에서 상위 요소로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="b23f8-130">XAML 구문 섹션에 표시된 `FindAncestor` 모드에 대한 개체 요소 구문에서 `FindAncestor` 모드의 경우에는 특히 두 번째 개체 요소 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="b23f8-131">`FindAncestor` 모드에는 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="b23f8-132">찾을 상위 항목의 형식에 대 한 [X:Type 태그 확장](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) 참조를 사용 하 여 <xref:System.Windows.Data.RelativeSource.AncestorType%2A>를 특성으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="b23f8-133">바인딩 요청이 실시간으로 처리될 때 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="b23f8-134">`FindAncestor` 모드의 경우 선택적 속성인 <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A>을 사용하면 요소 트리에 같은 형식의 상위 항목이 둘 이상 있을 때 상위 항목을 쉽게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="b23f8-135">`FindAncestor` 모드를 사용하는 방법에 대한 자세한 내용은 <xref:System.Windows.Data.RelativeSource>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b23f8-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="b23f8-136">`{RelativeSource Self}` 인스턴스의 한 속성이 같은 인스턴스의 다른 속성 값에 종속 되어야 하 고 이러한 두 속성 간에 일반 종속성 속성 관계 (예: 강제 변환)가 이미 존재 하는 시나리오에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="b23f8-137">두 속성이 동일 하 게 동일 하 게 (그리고 동일 하 게 형식화 됨) 개체에 존재 하는 경우에도 `Converter` 매개 변수를 `{RelativeSource Self}`있는 바인딩에 적용 하 고 변환기를 사용 하 여 소스와 대상 형식 사이를 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="b23f8-138">`{RelativeSource Self}`에 대 한 다른 시나리오는 <xref:System.Windows.MultiDataTrigger>의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="b23f8-139">예를 들어, 다음 XAML은 <xref:System.Windows.Shapes.Rectangle>에 어떤 값이 입력되더라도 <xref:System.Windows.FrameworkElement.Width%2A>은 항상 사각형이 되도록 <xref:System.Windows.Shapes.Rectangle> 요소를 정의합니다. `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="b23f8-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="b23f8-140">`{RelativeSource PreviousData}`는 바인딩에서 컬렉션을 데이터 원본으로 사용 하는 경우 또는 데이터 템플릿에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="b23f8-141">`{RelativeSource PreviousData}`를 사용 하 여 컬렉션의 인접 데이터 항목 간 관계를 강조 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="b23f8-142">관련된 기술은 데이터 소스에 있는 현재 항목과 이전 항목 사이에 <xref:System.Windows.Data.MultiBinding>을 구축하고 해당 바인딩에서 변환기를 사용하여 두 항목 사이의 차이점과 해당 속성을 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="b23f8-143">다음 예제에서 항목 템플릿의 첫 번째 <xref:System.Windows.Controls.TextBlock>은 현재 번호를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="b23f8-144">두 번째 <xref:System.Windows.Controls.TextBlock> 바인딩은 현재 레코드와 `{RelativeSource PreviousData}`를 사용 하 여 의도적으로 이전 데이터 레코드를 사용 하는 바인딩 이라는 두 가지 <xref:System.Windows.Data.Binding> 구성 요소 명목상를 포함 하는 <xref:System.Windows.Data.MultiBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="b23f8-145">그런 다음, <xref:System.Windows.Data.MultiBinding>의 변환기가 차이를 계산하고 이를 바인딩으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

<span data-ttu-id="b23f8-146">데이터 바인딩에 대 한 개념 설명은 여기에서 다루지 않습니다. [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f8-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="b23f8-147">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서 구현에서이 태그 확장에 대 한 처리는 <xref:System.Windows.Data.RelativeSource> 클래스에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="b23f8-148">`RelativeSource`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="b23f8-149">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b23f8-150">XAML의 모든 태그 확장은 특성 구문에서 `{` 및 `}` 문자를 사용 합니다 .이는 XAML 프로세서가 태그 확장에서 특성을 처리 해야 함을 인식 하는 데 사용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f8-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="b23f8-151">자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f8-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b23f8-152">참조</span><span class="sxs-lookup"><span data-stu-id="b23f8-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="b23f8-153">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="b23f8-153">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="b23f8-154">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="b23f8-154">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="b23f8-155">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="b23f8-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="b23f8-156">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="b23f8-156">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b23f8-157">바인딩 선언 개요</span><span class="sxs-lookup"><span data-stu-id="b23f8-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="b23f8-158">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="b23f8-158">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
