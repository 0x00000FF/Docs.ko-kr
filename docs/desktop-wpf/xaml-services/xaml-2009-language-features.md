---
title: XAML 2009 언어 기능
ms.date: 03/30/2017
helpviewer_keywords:
- XAML 2009 [XAML Services]
- XAML [XAML Services], XAML 2009
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
ms.openlocfilehash: e58e6757b88958bf8a3547c8a272c2e6298dcecb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432841"
---
# <a name="xaml-2009-language-features"></a><span data-ttu-id="41936-102">XAML 2009 언어 기능</span><span class="sxs-lookup"><span data-stu-id="41936-102">XAML 2009 Language Features</span></span>
<span data-ttu-id="41936-103">XAML 2009는 기존 XAML 언어 사양을 확장하는 새 XAML 언어 기능의 약식 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="41936-103">XAML 2009 is the shorthand term for new XAML language features that extend the existing XAML language specification.</span></span> <span data-ttu-id="41936-104">XAML 2009에서는 여러 가지 새로운 지시문과 구문이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-104">XAML 2009 introduces several new directives and constructs.</span></span> <span data-ttu-id="41936-105">여기에는 [x:인수 지시문이 포함됩니다.](xarguments-directive.md) [x:FactoryMethod 지시문;](xfactorymethod-directive.md) [x:참조 마크업 확장;](xreference-markup-extension.md) [x:TypeArguments 지시문;](xtypearguments-directive.md) 및 공통 언어 프리미티브에 대한 기본 `x:Char`제공 형식(예: ).</span><span class="sxs-lookup"><span data-stu-id="41936-105">These include the [x:Arguments Directive](xarguments-directive.md); the [x:FactoryMethod Directive](xfactorymethod-directive.md); the [x:Reference Markup Extension](xreference-markup-extension.md); the [x:TypeArguments Directive](xtypearguments-directive.md); and built-in types for common language primitives (for example `x:Char`).</span></span>

## <a name="xaml-2009-support-in-wpf-and-visual-studio"></a><span data-ttu-id="41936-106">WPF 및 Visual Studio의 XAML 2009 지원</span><span class="sxs-lookup"><span data-stu-id="41936-106">XAML 2009 Support in WPF and Visual Studio</span></span>

<span data-ttu-id="41936-107">WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-107">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="41936-108">태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-108">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>

<span data-ttu-id="41936-109">WPF에서 느슨한 XAML을 로드하는 기존 기술은 태그 컴파일된 XAML보다 제한적인 CLR 형식 및 형식 시스템에 대해 가능한 보안 및 액세스 제한이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-109">Note that existing techniques for loading loose XAML in WPF also have possible security and access restrictions to CLR types and the type system that are more restrictive than for markup-compiled XAML.</span></span> <span data-ttu-id="41936-110">자세한 내용은 [보안(WPF)](../../framework/wpf/security-wpf.md) 또는 [WPF 보안 전략 - 플랫폼 보안](../../framework/wpf/wpf-security-strategy-platform-security.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41936-110">For more information, see [Security (WPF)](../../framework/wpf/security-wpf.md) or [WPF Security Strategy - Platform Security](../../framework/wpf/wpf-security-strategy-platform-security.md).</span></span>

<span data-ttu-id="41936-111">XAML 2009에서는 이전 XAML 2006 구문을 수정하거나 기본 태그 폼을 수정하는 추가 기능도 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-111">XAML 2009 also introduces additional features that either modify the previous XAML 2006 constructs or that modify the basic markup forms.</span></span>

### <a name="xkey-as-an-object-element"></a><span data-ttu-id="41936-112">개체 요소인 x:Key</span><span class="sxs-lookup"><span data-stu-id="41936-112">x:Key as an Object Element</span></span>

<span data-ttu-id="41936-113">XAML 2009에서는 `x:Key` 를 개체(개체 요소 값을 가진 속성 요소)로 지원할 수 있습니다. 그러나 XAML 2006에서는 `x:Key` 를 특성으로만 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-113">XAML 2009 can support `x:Key` as an object (a property element that has object element value); however, XAML 2006 only supported `x:Key` as an attribute.</span></span> <span data-ttu-id="41936-114">[x:Key Directive](xkey-directive.md)의 “XAML 2009” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41936-114">See the "XAML 2009" section of [x:Key Directive](xkey-directive.md).</span></span>

### <a name="xmlns-on-property-elements"></a><span data-ttu-id="41936-115">속성 요소에 대한 xmlns</span><span class="sxs-lookup"><span data-stu-id="41936-115">xmlns on Property Elements</span></span>

<span data-ttu-id="41936-116">XAML 2009에서는 속성 요소에 대한 XAML 네임스페이스(xmlns) 정의를 지원할 수 있습니다. 그러나 XAML 2006에서는 개체 요소에 대한 xmlns 정의만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41936-116">XAML 2009 can support XAML namespace (xmlns) definitions on property elements; however, XAML 2006 only supports xmlns definitions on object elements.</span></span>

### <a name="event-attributes"></a><span data-ttu-id="41936-117">이벤트 특성</span><span class="sxs-lookup"><span data-stu-id="41936-117">Event Attributes</span></span>

<span data-ttu-id="41936-118">이벤트에서 지원하는 특성에 대해 XAML 2006에서는 태그 컴파일이 필요하다고 가정하고 이벤트를 태그 컴파일에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="41936-118">For attributes that are backed by events, XAML 2006 presumes that markup compilation is involved and submits the events to markup compilation.</span></span> <span data-ttu-id="41936-119">XAML 2009에서는 XAML의 런타임 구문 분석 및 로드 시까지 이벤트 연결을 지연하는, 태그 확장과 유사한 태그 폼을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41936-119">XAML 2009 supports a markup form that resembles a markup extension, which defers the event wiring until run-time parsing and loading of the XAML.</span></span> <span data-ttu-id="41936-120">그러나 WPF UI에 대한 XAML 시나리오 및 WPF 애플리케이션에서는 일반적으로 이 기능을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41936-120">However, WPF applications and XAML scenarios for WPF UI generally do not use this capability.</span></span> <span data-ttu-id="41936-121">WPF 및 XAML 2006 구현에서는 대부분의 이벤트 특성 처리에 대해 <xref:System.Windows.UIElement> 수준에서 정의된 라우트된 이벤트에 대한 이벤트 처리기 연결 및 해당 태그 컴파일러 단계의 조합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41936-121">WPF and its XAML 2006 implementation uses the combination of event handler wiring for routed events defined at the <xref:System.Windows.UIElement> level and its markup compiler step for much of its event attribute processing.</span></span> <span data-ttu-id="41936-122">또한 태그 컴파일러는 빌드 작업에서 태그 컴파일러가 사용됨을 선언하는 XAML에 있는 모든 이벤트 특성을 전처리합니다.</span><span class="sxs-lookup"><span data-stu-id="41936-122">The markup compiler also preprocesses any event attributes found in XAML where the build actions declare that the markup compiler is used.</span></span>

## <a name="see-also"></a><span data-ttu-id="41936-123">참조</span><span class="sxs-lookup"><span data-stu-id="41936-123">See also</span></span>

- [<span data-ttu-id="41936-124">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="41936-124">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
