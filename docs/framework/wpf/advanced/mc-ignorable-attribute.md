---
title: mc:Ignorable 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 45b9ee94b35f368a9d0c96381083aa58c9a23f77
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998413"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="b8dd0-102">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="b8dd0-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="b8dd0-103">지정 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 여는 태그 파일에서 발생 하는 네임 스페이스 접두사를 무시할 수 있습니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="b8dd0-104">합니다 `mc:Ignorable` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="b8dd0-105">XAML 특성 사용 (단일 접두사)</span><span class="sxs-lookup"><span data-stu-id="b8dd0-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="b8dd0-106">XAML 특성 사용 (두 개의 접두사)</span><span class="sxs-lookup"><span data-stu-id="b8dd0-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b8dd0-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="b8dd0-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8dd0-108">*ignorablePrefix, ignorablePrefix1 등입니다.*</span><span class="sxs-lookup"><span data-stu-id="b8dd0-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="b8dd0-109">XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b8dd0-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="b8dd0-110">*ignorableUri*</span></span>|<span data-ttu-id="b8dd0-111">XML 1.0 사양에 따라 네임 스페이스를 지정 하는 것에 대 한 모든 유효한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b8dd0-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="b8dd0-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="b8dd0-113">무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8dd0-114">설명</span><span class="sxs-lookup"><span data-stu-id="b8dd0-114">Remarks</span></span>  
 <span data-ttu-id="b8dd0-115">합니다 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스 접두사는 매핑할 때 권장 되는 접두사 규칙 합니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 호환성 네임 스페이스 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="b8dd0-116">요소 또는 특성으로 요소 이름의 접두사 부분 식별 되는 위치 `mc:Ignorable` 하 여 처리 될 때 오류가 발생 하지는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="b8dd0-117">해당 특성을 내부 형식 또는 프로그래밍 구문에 확인할 수 없는, 하는 경우 해당 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="b8dd0-118">그러나 note 무시 되는 요소는 처리 되지 않고 해당 요소의 부작용이 추가로 요소 요구 사항에 대 한 추가 구문 분석 오류를 생성할 여전히 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="b8dd0-119">예를 들어, 특정 요소 콘텐츠 모델을 지정된 된 자식 요소에서 되었으면 하지만 정확히 하나의 자식 요소만 필요할를 `mc:Ignorable` 접두사 및 지정 된 자식 요소를 확인할 수 없는 형식으로 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 수 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="b8dd0-120">`mc:Ignorable` 네임 스페이스 매핑을 식별자 문자열에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="b8dd0-121">`mc:Ignorable` 네임 스페이스 매핑을 지정 하는 어셈블리에 적용 되지 않습니다는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임 스페이스 및 어셈블리 (또는 기본적으로 어셈블리는 현재 실행 파일).</span><span class="sxs-lookup"><span data-stu-id="b8dd0-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="b8dd0-122">구현 하는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서, 프로세서 구현 해야 발생 시 키 지 구문 분석 또는 임의의 요소 또는 특성으로 식별 되는 접두사는 대 한 형식 변환 오류를 처리 `mc:Ignorable`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="b8dd0-123">하지만 프로세서 구현 보조 로드 또는 위의 하나 자식 요소가 예제와 같은 처리에 실패 하는 요소의 되는 예외를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="b8dd0-124">기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 무시 된 요소 내에서 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="b8dd0-125">그러나 추가 특성을 지정할 수 있습니다 [mc: processcontent 특성](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), 다음 사용 가능한 부모 요소에서 무시 된 요소 내의 콘텐츠는 계속된 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="b8dd0-126">예를 들어 구분 기호로, 하나 이상의 공백 문자를 사용 하는 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:Ignorable="ignore1 ignore2"`합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  
  
 <span data-ttu-id="b8dd0-127">합니다 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와의이 영역 내에서 다루지 않는 특성을 정의 하는 네임 스페이스는 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="b8dd0-128">자세한 내용은 [XML 태그 호환성 사양](http://go.microsoft.com/fwlink/?LinkId=73824)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8dd0-128">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dd0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8dd0-129">See Also</span></span>  
 <xref:System.Windows.Markup.XamlReader>  
 [<span data-ttu-id="b8dd0-130">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="b8dd0-130">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [<span data-ttu-id="b8dd0-131">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="b8dd0-131">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="b8dd0-132">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="b8dd0-132">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
