---
title: WPF의 전역화
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 9a08fdeaa3517b1483af3f9958ad2db1c64648b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084169"
---
# <a name="globalization-for-wpf"></a><span data-ttu-id="ad22b-102">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="ad22b-102">Globalization for WPF</span></span>
<span data-ttu-id="ad22b-103">이 항목에서는 소개를 작성할 때 알고 있어야 하는 문제 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 글로벌 시장 용 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-103">This topic introduces issues that you should be aware of when writing [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications for the global market.</span></span> <span data-ttu-id="ad22b-104">전역화 프로그래밍 요소에 정의 된 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 에서 `System.Globalization`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-104">The globalization programming elements are defined in [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.</span></span>

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a><span data-ttu-id="ad22b-105">XAML 전역화</span><span class="sxs-lookup"><span data-stu-id="ad22b-105">XAML Globalization</span></span>
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] <span data-ttu-id="ad22b-106">더해서 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 에 정의 된 전역화 지원을 활용 하 고는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-106">is based on [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] and takes advantage of the globalization support defined in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] specification.</span></span> <span data-ttu-id="ad22b-107">다음 섹션에서는 일부 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고려해 야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-107">The following sections describe some [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] features that you should be aware of.</span></span>

<a name="char_reference"></a>
### <a name="character-references"></a><span data-ttu-id="ad22b-108">문자 참조</span><span class="sxs-lookup"><span data-stu-id="ad22b-108">Character References</span></span>
<span data-ttu-id="ad22b-109">문자 참조를 제공 UTF16 코드 단위의 특정 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 나타내는 10 진수 또는 16 진수 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-109">A character reference gives the UTF16 code unit of the particular [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] character it represents, in either decimal or hexadecimal.</span></span> <span data-ttu-id="ad22b-110">다음 예제에서는 'Ϩ' 콥트어 CAPITAL LETTER 가로에 10 진수 문자 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-110">The following example shows a decimal character reference for the COPTIC CAPITAL LETTER HORI, or 'Ϩ':</span></span>

```
&#1000;
```

<span data-ttu-id="ad22b-111">다음 예제에서는 16 진수 문자 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-111">The following example shows a hexadecimal character reference.</span></span> <span data-ttu-id="ad22b-112">가 **x** 16 진수 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-112">Notice that it has an **x** in front of the hexadecimal number.</span></span>

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a><span data-ttu-id="ad22b-113">인코딩</span><span class="sxs-lookup"><span data-stu-id="ad22b-113">Encoding</span></span>
 <span data-ttu-id="ad22b-114">지 원하는 인코딩은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 됩니다 [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] utf-16 및 u t F-8입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-114">The encoding supported by [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16, and UTF-8.</span></span> <span data-ttu-id="ad22b-115">맨 앞에 인코딩 문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 문서.</span><span class="sxs-lookup"><span data-stu-id="ad22b-115">The encoding statement is at the beginning of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] document.</span></span> <span data-ttu-id="ad22b-116">인코딩 특성이 없으며 바이트 순서가 없으면 기본적으로 구문 분석기가 UTF-8로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-116">If no encoding attribute exists and there is no byte-order, the parser defaults to UTF-8.</span></span> <span data-ttu-id="ad22b-117">UTF-8과 UTF-16이 기본 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-117">UTF-8 and UTF-16 are the preferred encodings.</span></span> <span data-ttu-id="ad22b-118">UTF-7은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-118">UTF-7 is not supported.</span></span> <span data-ttu-id="ad22b-119">다음 예제에서 u t F-8 인코딩을 지정 하는 방법에 설명 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-119">The following example demonstrates how to specify a UTF-8 encoding in a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

```
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a><span data-ttu-id="ad22b-120">언어 특성</span><span class="sxs-lookup"><span data-stu-id="ad22b-120">Language Attribute</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ad22b-121">사용 하 여 [xml: lang](../../xaml-services/xml-lang-handling-in-xaml.md) 를 요소의 언어 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-121">uses [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) to represent the language attribute of an element.</span></span>  <span data-ttu-id="ad22b-122">활용 하기 위해 합니다 <xref:System.Globalization.CultureInfo> 클래스의 미리 정의 된 문화권 이름 중 하나일 언어 특성 값을 해야 <xref:System.Globalization.CultureInfo>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-122">To take advantage of the <xref:System.Globalization.CultureInfo> class, the language attribute value needs to be one of the culture names predefined by <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="ad22b-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md)은 요소 트리에서 상속 가능하며(반드시 종속성 속성 상속성때문이 아니라 XML 규칙에 따름), 명시적으로 할당되지 않은 경우 기본값은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) is inheritable in the element tree (by XML rules, not necessarily because of dependency property inheritance) and its default value is an empty string if it is not assigned explicitly.</span></span>

 <span data-ttu-id="ad22b-124">언어를 지정할 때 언어 특성이 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-124">The language attribute is very useful for specifying dialects.</span></span> <span data-ttu-id="ad22b-125">예를 들어, 프랑스, 퀘벡, 벨기에 및 스위스의 프랑스어에는 다른 철자, 어휘 및 발음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-125">For example, French has different spelling, vocabulary, and pronunciation in France, Quebec, Belgium, and Switzerland.</span></span> <span data-ttu-id="ad22b-126">중국어, 일본어 및 한국어에서 코드 포인트 공유할 수도 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], 하지만 표의 문자 모양은 서로 다르고 완전히 다른 글꼴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-126">Also Chinese, Japanese, and Korean share code points in [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], but the ideographic shapes are different and they use totally different fonts.</span></span>

 <span data-ttu-id="ad22b-127">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 하 여 예제를 `fr-CA` 언어 특성 캐나다 프랑스어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-127">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example uses the `fr-CA` language attribute to specify Canadian French.</span></span>

```xml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a><span data-ttu-id="ad22b-128">유니코드(Unicode)</span><span class="sxs-lookup"><span data-stu-id="ad22b-128">Unicode</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ad22b-129">모든 지원 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 서로게이트를 포함 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-129">supports all [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] features including surrogates.</span></span> <span data-ttu-id="ad22b-130">문자 집합에 매핑될 수 있다면 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-130">As long as the character set can be mapped to [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], it is supported.</span></span> <span data-ttu-id="ad22b-131">예를 들어, GB18030에서는 중국어, 일본어 및 한국어(CFK) 확장 A와 B에 매핑되는 일부 문자와 서로게이트 쌍을 소개하므로 완전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-131">For example, GB18030 introduces some characters that are mapped to the Chinese, Japanese, and Korean (CFK) extension A and B and surrogate pairs, therefore it is fully supported.</span></span> <span data-ttu-id="ad22b-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 사용할 수 <xref:System.Globalization.StringInfo> 결합 문자 또는 서로게이트 쌍 인지 파악 하지 않고도 문자열을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can use <xref:System.Globalization.StringInfo> to manipulate strings without understanding whether they have surrogate pairs or combining characters.</span></span>

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a><span data-ttu-id="ad22b-133">XAML로 국가별 사용자 인터페이스 설계</span><span class="sxs-lookup"><span data-stu-id="ad22b-133">Designing an International User Interface with XAML</span></span>
 <span data-ttu-id="ad22b-134">이 섹션에서는 설명 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응용 프로그램을 작성할 때 고려해 야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-134">This section describes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] features that you should consider when writing an application.</span></span>

<a name="intl_text"></a>
### <a name="international-text"></a><span data-ttu-id="ad22b-135">국가별 텍스트</span><span class="sxs-lookup"><span data-stu-id="ad22b-135">International Text</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ad22b-136">모든 Microsoft.NET Framework 지원 쓰기 시스템에 대 한 기본 제공 처리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-136">includes built-in processing for all Microsoft .NET Framework supported writing systems.</span></span>

 <span data-ttu-id="ad22b-137">현재 지원되는 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-137">The following scripts are currently supported:</span></span>

-   <span data-ttu-id="ad22b-138">아랍어</span><span class="sxs-lookup"><span data-stu-id="ad22b-138">Arabic</span></span>

-   <span data-ttu-id="ad22b-139">벵골어</span><span class="sxs-lookup"><span data-stu-id="ad22b-139">Bengali</span></span>

-   <span data-ttu-id="ad22b-140">데바나가리어</span><span class="sxs-lookup"><span data-stu-id="ad22b-140">Devanagari</span></span>

-   <span data-ttu-id="ad22b-141">키릴 자모</span><span class="sxs-lookup"><span data-stu-id="ad22b-141">Cyrillic</span></span>

-   <span data-ttu-id="ad22b-142">그리스어</span><span class="sxs-lookup"><span data-stu-id="ad22b-142">Greek</span></span>

-   <span data-ttu-id="ad22b-143">구자라트어</span><span class="sxs-lookup"><span data-stu-id="ad22b-143">Gujarati</span></span>

-   <span data-ttu-id="ad22b-144">굴묵키어</span><span class="sxs-lookup"><span data-stu-id="ad22b-144">Gurmukhi</span></span>

-   <span data-ttu-id="ad22b-145">히브리어</span><span class="sxs-lookup"><span data-stu-id="ad22b-145">Hebrew</span></span>

-   <span data-ttu-id="ad22b-146">표의 문자 스크립트</span><span class="sxs-lookup"><span data-stu-id="ad22b-146">Ideographic scripts</span></span>

-   <span data-ttu-id="ad22b-147">칸나다어</span><span class="sxs-lookup"><span data-stu-id="ad22b-147">Kannada</span></span>

-   <span data-ttu-id="ad22b-148">라오어</span><span class="sxs-lookup"><span data-stu-id="ad22b-148">Lao</span></span>

-   <span data-ttu-id="ad22b-149">라틴어</span><span class="sxs-lookup"><span data-stu-id="ad22b-149">Latin</span></span>

-   <span data-ttu-id="ad22b-150">말라얄람어</span><span class="sxs-lookup"><span data-stu-id="ad22b-150">Malayalam</span></span>

-   <span data-ttu-id="ad22b-151">몽골어</span><span class="sxs-lookup"><span data-stu-id="ad22b-151">Mongolian</span></span>

-   <span data-ttu-id="ad22b-152">오리야어</span><span class="sxs-lookup"><span data-stu-id="ad22b-152">Odia</span></span>

-   <span data-ttu-id="ad22b-153">시리아어</span><span class="sxs-lookup"><span data-stu-id="ad22b-153">Syriac</span></span>

-   <span data-ttu-id="ad22b-154">타밀어</span><span class="sxs-lookup"><span data-stu-id="ad22b-154">Tamil</span></span>

-   <span data-ttu-id="ad22b-155">텔루구어</span><span class="sxs-lookup"><span data-stu-id="ad22b-155">Telugu</span></span>

-   <span data-ttu-id="ad22b-156">타나 문자</span><span class="sxs-lookup"><span data-stu-id="ad22b-156">Thaana</span></span>

-   <span data-ttu-id="ad22b-157">태국어\*</span><span class="sxs-lookup"><span data-stu-id="ad22b-157">Thai\*</span></span>

-   <span data-ttu-id="ad22b-158">티베트어</span><span class="sxs-lookup"><span data-stu-id="ad22b-158">Tibetan</span></span>

 <span data-ttu-id="ad22b-159">\* 이 릴리스에서는 태국어 텍스트의 표시 및 편집이 지원되며, 단어 구분은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-159">\*In this release the display and editing of Thai text is supported; word breaking is not.</span></span>

 <span data-ttu-id="ad22b-160">현재 지원되지 않는 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-160">The following scripts are not currently supported:</span></span>

-   <span data-ttu-id="ad22b-161">크메르어</span><span class="sxs-lookup"><span data-stu-id="ad22b-161">Khmer</span></span>

-   <span data-ttu-id="ad22b-162">한국어 옛 한글</span><span class="sxs-lookup"><span data-stu-id="ad22b-162">Korean Old Hangul</span></span>

-   <span data-ttu-id="ad22b-163">미얀마어</span><span class="sxs-lookup"><span data-stu-id="ad22b-163">Myanmar</span></span>

-   <span data-ttu-id="ad22b-164">스리랑카어</span><span class="sxs-lookup"><span data-stu-id="ad22b-164">Sinhala</span></span>

 <span data-ttu-id="ad22b-165">모든 쓰기 시스템 엔진 지원 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-165">All the writing system engines support [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts.</span></span> [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="ad22b-166">글꼴 포함 될 수 있습니다는 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 레이아웃 테이블을 더 잘 국가별 글꼴과 최고급 글꼴을 디자인 하는 글꼴 생성기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-166">fonts can include the [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] layout tables that enable font creators to design better international and high-end typographic fonts.</span></span> <span data-ttu-id="ad22b-167">[!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 레이아웃 테이블에 대 한 정보가 문자 모양 대체, 문자 모양 위치 지정, 양쪽 맞춤 및 기준선 위치 지정 텍스트 레이아웃을 개선 하기 위해 텍스트 처리 응용 프로그램을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-167">The [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] font layout tables contain information about glyph substitutions, glyph positioning, justification, and baseline positioning, enabling text-processing applications to improve text layout.</span></span>

 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="ad22b-168">글꼴 큰 문자 모양 처리를 사용 하 여 집합 허용 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 인코딩.</span><span class="sxs-lookup"><span data-stu-id="ad22b-168">fonts allow the handling of large glyph sets using [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] encoding.</span></span> <span data-ttu-id="ad22b-169">이러한 인코딩을 사용하면 글꼴 문자 모양 변형 외에도 광범위한 국가별 지원이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-169">Such encoding enables broad international support as well as for typographic glyph variants.</span></span>

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ad22b-170">텍스트 렌더링으로 구동 되며 [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] 해상도 독립성을 지 원하는 하위 픽셀 기술을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-170">text rendering is powered by [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] sub-pixel technology that supports resolution independence.</span></span> <span data-ttu-id="ad22b-171">이 기능을 통해 가독성이 크게 향상되며, 모든 스크립트에 대해 고품질 잡지 스타일 문서를 지원하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-171">This significantly improves legibility and provides the ability to support high quality magazine style documents for all scripts.</span></span>

<a name="intl_layout"></a>
### <a name="international-layout"></a><span data-ttu-id="ad22b-172">국가별 레이아웃</span><span class="sxs-lookup"><span data-stu-id="ad22b-172">International Layout</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="ad22b-173">에서는 가로, 양방향 및 세로 레이아웃을 지원하는 매우 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-173">provides a very convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="ad22b-174">프레젠테이션 프레임 워크에서는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 레이아웃을 정의 하려면 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-174">In presentation framework the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="ad22b-175">흐름 방향 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-175">The flow direction patterns are:</span></span>

-   <span data-ttu-id="ad22b-176">*LeftToRight* - 라틴어, 동아시아어 등을 위한 가로 레이아웃.</span><span class="sxs-lookup"><span data-stu-id="ad22b-176">*LeftToRight* - horizontal layout for Latin, East Asian and so forth.</span></span>

-   <span data-ttu-id="ad22b-177">*RightToLeft* - 아랍어, 히브리어 등을 위한 양방향.</span><span class="sxs-lookup"><span data-stu-id="ad22b-177">*RightToLeft* - bidirectional for Arabic, Hebrew and so forth.</span></span>

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a><span data-ttu-id="ad22b-178">지역화 가능 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="ad22b-178">Developing Localizable Applications</span></span>
 <span data-ttu-id="ad22b-179">글로벌 사용을 위해 애플리케이션을 작성할 때 애플리케이션을 지역화해야 한다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-179">When you write an application for global consumption you should keep in mind that the application must be localizable.</span></span> <span data-ttu-id="ad22b-180">다음 항목에서는 고려할 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-180">The following topics point out things to consider.</span></span>

<a name="mui"></a>
### <a name="multilingual-user-interface"></a><span data-ttu-id="ad22b-181">다국어 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad22b-181">Multilingual User Interface</span></span>
 <span data-ttu-id="ad22b-182">다국어 사용자 인터페이스 (MUI)는 한 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 전환에 대 한 지원 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 다른 언어에서입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-182">Multilingual User Interfaces (MUI) is a [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] support for switching [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] from one language to another.</span></span> <span data-ttu-id="ad22b-183">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] MUI를 지원 하기 위해 어셈블리 모델을 사용 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-183">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses the assembly model to support MUI.</span></span> <span data-ttu-id="ad22b-184">한 애플리케이션에는 언어 중립 어셈블리 외에도 언어별 위성 리소스 어셈블리도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-184">One application contains language-neutral assemblies as well as language-dependent satellite resource assemblies.</span></span> <span data-ttu-id="ad22b-185">진입점은 기본 어셈블리에서 관리되는 .EXE입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-185">The entry point is a managed .EXE in the main assembly.</span></span>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ad22b-186">리소스 로더는 활용을 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]의 resource manager 리소스 조회 및 대체 (fallback)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-186">resource loader takes advantage of the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]'s resource manager to support resource lookup and fallback.</span></span> <span data-ttu-id="ad22b-187">여러 언어 위성 어셈블리는 동일한 기본 어셈블리와 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-187">Multiple language satellite assemblies work with the same main assembly.</span></span> <span data-ttu-id="ad22b-188">로드 되는 리소스 어셈블리가 종속 된 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> 현재 스레드의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-188">The resource assembly that is loaded depends on the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> of the current thread.</span></span>

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a><span data-ttu-id="ad22b-189">지역화할 수 있는 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad22b-189">Localizable User Interface</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ad22b-190">응용 프로그램 사용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 정의에 해당 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-190">applications use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to define their [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="ad22b-191">를 사용하면 개발자가 속성 및 논리 집합이 포함된 개체의 계층 구조를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-191">allows developers to specify a hierarchy of objects with a set of properties and logic.</span></span> <span data-ttu-id="ad22b-192">주된 용도 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 개발 하는 데 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하지만 응용 프로그램의 계층을 지정 하려면 사용할 수 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-192">The primary use of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is to develop [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications but it can be used to specify a hierarchy of any [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects.</span></span> <span data-ttu-id="ad22b-193">대부분의 개발자가 사용할 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 응용 프로그램을 지정 하려면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] C#과 같은 프로그래밍 언어를 사용 하 여 사용자 상호 작용에 반응 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-193">Most developers use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify their application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and use a programming language such as C# to react to user interaction.</span></span>

 <span data-ttu-id="ad22b-194">리소스의 관점에서을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 언어별 설명 하도록 설계 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 리소스 요소 이며 따라서, 최종 배포 형식은 국가별 언어를 지원 하도록 지역화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-194">From a resource point of view, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file designed to describe a language-dependent [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is a resource element and therefore its final distribution format must be localizable to support international languages.</span></span> <span data-ttu-id="ad22b-195">때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 없습니다 이벤트를 처리할 여러 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램에이 작업을 수행 하는 코드 블록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-195">Because [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cannot handle events many [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications contain blocks of code to do this.</span></span> <span data-ttu-id="ad22b-196">자세한 내용은 [XAML 개요 (WPF)](xaml-overview-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-196">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md).</span></span> <span data-ttu-id="ad22b-197">코드를 제거 하 고 다른 이진 파일로 컴파일할 때를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 XAML의 BAML 양식으로 토큰화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-197">Code is stripped out and compiled into different binaries when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is tokenized into the BAML form of XAML.</span></span> <span data-ttu-id="ad22b-198">XAML 파일의 BAML 양식, 이미지 및 기타 형식의 관리 리소스 개체는 위성 리소스 어셈블리에 포함되어 다른 언어로 지역화되거나, 지역화가 필요하지 않은 경우 기본 어셈블리에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-198">The BAML form of XAML files, images, and other types of managed resource objects are embedded in the satellite resource assembly, which can be localized into other languages, or the main assembly when localization is not required.</span></span>

> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ad22b-199">응용 프로그램 일부를 지원 합니다 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 문자열 테이블, 이미지 등을 비롯 한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-199">applications support all the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)][!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] resources including string tables, images, and so forth.</span></span>

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a><span data-ttu-id="ad22b-200">지역화 가능 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="ad22b-200">Building Localizable Applications</span></span>
 <span data-ttu-id="ad22b-201">지역화에 맞게 의미를 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를 다른 문화권입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-201">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="ad22b-202">확인을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 개발자가 지역화 가능한 리소스를 모두 리소스 어셈블리에 빌드해야 하는 데 필요한 지역화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-202">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="ad22b-203">다른 언어로 지역화 된 리소스 어셈블리 및 코드 숨김에서는 리소스 관리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-203">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="ad22b-204">에 필요한 파일 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 프로젝트 파일 (.proj)입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-204">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="ad22b-205">애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-205">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="ad22b-206">.csprop 파일의 다음 예에서는 이 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-206">The following example from a .csproj file shows how to do this.</span></span>

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 <span data-ttu-id="ad22b-207">응용 프로그램에서 리소스 인스턴스화하는 데는 <xref:System.Resources.ResourceManager> 하 고 사용 하려는 리소스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-207">To use a resource in your application instantiate a <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="ad22b-208">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-208">The following example demonstrates how to do this.</span></span>

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a><span data-ttu-id="ad22b-209">지역화된 애플리케이션에서 ClickOnce 사용</span><span class="sxs-lookup"><span data-stu-id="ad22b-209">Using ClickOnce with Localized Applications</span></span>
 <span data-ttu-id="ad22b-210">ClickOnce는 Visual Studio 2005를 사용 하 여 제공 될 새 Windows Forms 배포 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-210">ClickOnce is a new Windows Forms deployment technology that will ship with Visual Studio 2005.</span></span> <span data-ttu-id="ad22b-211">애플리케이션 설치 및 웹 애플리케이션의 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-211">It enables application installation and upgrading of Web applications.</span></span> <span data-ttu-id="ad22b-212">ClickOnce로 배포된 애플리케이션이 지역화되면 지역화된 문화권에서만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-212">When an application that was deployed with ClickOnce is localized it can only be viewed on the localized culture.</span></span> <span data-ttu-id="ad22b-213">예를 들어 일본어로 지역화 된 응용 프로그램을 배포 하는 경우만 볼 수 있습니다 일본어 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 영어 Windows에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-213">For example, if a deployed application is localized to Japanese it can only be viewed on Japanese [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] not on English Windows.</span></span> <span data-ttu-id="ad22b-214">일본어 사용자가 Windows의 영어 버전에 대 한 일반적인 시나리오 이므로 문제가 초래 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-214">This presents a problem because it is a common scenario for Japanese users to run an English version of Windows.</span></span>

 <span data-ttu-id="ad22b-215">이 문제는 중립 언어 대체 특성을 설정하여 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-215">The solution to this problem is setting the neutral language fallback attribute.</span></span> <span data-ttu-id="ad22b-216">애플리케이션 개발자가 선택적으로 기본 어셈블리에서 리소스를 제거하고 특정 문화권에 해당하는 위성 어셈블리에서 해당 리소스를 찾을 수 있게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-216">An application developer can optionally remove resources from the main assembly and specify that the resources can be found in a satellite assembly corresponding to a specific culture.</span></span> <span data-ttu-id="ad22b-217">이 프로세스 사용을 제어 하는 <xref:System.Resources.NeutralResourcesLanguageAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-217">To control this process use the <xref:System.Resources.NeutralResourcesLanguageAttribute>.</span></span> <span data-ttu-id="ad22b-218">생성자는 <xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스에 사용 하는 두 개의 서명을 <xref:System.Resources.UltimateResourceFallbackLocation> 위치를 지정 하려면 매개 변수 위치는 <xref:System.Resources.ResourceManager> 대체 (fallback) 리소스를 추출 해야: 주 어셈블리 또는 위성 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-218">The constructor of the <xref:System.Resources.NeutralResourcesLanguageAttribute> class has two signatures, one that takes an <xref:System.Resources.UltimateResourceFallbackLocation> parameter to specify the location where the <xref:System.Resources.ResourceManager> should extract the fallback resources: main assembly or satellite assembly.</span></span> <span data-ttu-id="ad22b-219">다음 예제에서는 이 특성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-219">The following example shows how to use the attribute.</span></span> <span data-ttu-id="ad22b-220">Ultimate 대체 (fallback) 위치에 대 한 코드는 다음과 같이 하면 됩니다.는 <xref:System.Resources.ResourceManager> 현재 실행 중인 어셈블리의 디렉터리의 "de" 하위 디렉터리에 있는 리소스를 찾도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22b-220">For the ultimate fallback location, the code causes the <xref:System.Resources.ResourceManager> to look for the resources in the "de" subdirectory of the directory of the currently executing assembly.</span></span>

```
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a><span data-ttu-id="ad22b-221">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad22b-221">See also</span></span>

- [<span data-ttu-id="ad22b-222">WPF 전역화 및 지역화 개요</span><span class="sxs-lookup"><span data-stu-id="ad22b-222">WPF Globalization and Localization Overview</span></span>](wpf-globalization-and-localization-overview.md)
