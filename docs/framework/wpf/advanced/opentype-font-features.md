---
title: OpenType 글꼴 기능
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 3f1f0698afce6e64711e37ac60d0662d65bbee6b
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016134"
---
# <a name="opentype-font-features"></a><span data-ttu-id="07dd1-102">OpenType 글꼴 기능</span><span class="sxs-lookup"><span data-stu-id="07dd1-102">OpenType Font Features</span></span>

<span data-ttu-id="07dd1-103">이 항목에서는에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]OpenType 글꼴 기술의 주요 기능 중 일부에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-103">This topic provides an overview of some of the key features of OpenType font technology in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a><span data-ttu-id="07dd1-104">OpenType 글꼴 서식</span><span class="sxs-lookup"><span data-stu-id="07dd1-104">OpenType Font Format</span></span>  
 <span data-ttu-id="07dd1-105">OpenType 글꼴 형식은 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 글꼴 형식의 확장으로, 포스트 스크립트 글꼴 데이터에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-105">The OpenType font format is an extension of the [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] font format, adding support for PostScript font data.</span></span> <span data-ttu-id="07dd1-106">OpenType 글꼴 형식은 Microsoft 및 Adobe Corporation에서 공동으로 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-106">The OpenType font format was developed jointly by Microsoft and Adobe Corporation.</span></span> <span data-ttu-id="07dd1-107">Opentype 글꼴 및 opentype 글꼴을 지 원하는 운영 체제 서비스는 글꼴에 윤곽선 또는 CFF (PostScript) 개요가 포함 되어 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 있든 관계 없이 사용자에 게 글꼴을 설치 하 고 사용 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-107">OpenType fonts and the operating system services which support OpenType fonts provide users with a simple way to install and use fonts, whether the fonts contain [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] outlines or CFF (PostScript) outlines.</span></span>  
  
 <span data-ttu-id="07dd1-108">OpenType 글꼴 형식은 다음과 같은 개발자 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-108">The OpenType font format addresses the following developer challenges:</span></span>  
  
- <span data-ttu-id="07dd1-109">광범위한 다중 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="07dd1-109">Broader multi-platform support.</span></span>  
  
- <span data-ttu-id="07dd1-110">국가별 문자 집합에 대한 지원 향상</span><span class="sxs-lookup"><span data-stu-id="07dd1-110">Better support for international character sets.</span></span>  
  
- <span data-ttu-id="07dd1-111">글꼴 데이터 보호 향상</span><span class="sxs-lookup"><span data-stu-id="07dd1-111">Better protection for font data.</span></span>  
  
- <span data-ttu-id="07dd1-112">보다 효율적인 글꼴 배포를 위한 파일 크기 축소</span><span class="sxs-lookup"><span data-stu-id="07dd1-112">Smaller file sizes to make font distribution more efficient.</span></span>  
  
- <span data-ttu-id="07dd1-113">고급 입력 체계 컨트롤을 위한 폭넓은 지원</span><span class="sxs-lookup"><span data-stu-id="07dd1-113">Broader support for advanced typographic control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07dd1-114">Windows SDK에는 응용 프로그램과 함께 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용할 수 있는 샘플 OpenType 글꼴 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-114">The Windows SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="07dd1-115">이 글꼴에서는 이 항목의 나머지 부분에서 보여 주는 대부분의 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-115">These fonts provide most of the features illustrated in the rest of this topic.</span></span> <span data-ttu-id="07dd1-116">자세한 내용은 [샘플 OpenType 글꼴 팩](sample-opentype-font-pack.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07dd1-116">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
 <span data-ttu-id="07dd1-117">OpenType 글꼴 형식에 대 한 자세한 내용은 [Opentype 사양](https://go.microsoft.com/fwlink/?LinkId=96731) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07dd1-117">See the [OpenType Specification](https://go.microsoft.com/fwlink/?LinkId=96731) for details of the OpenType font format.</span></span>  
  
### <a name="advanced-typographic-extensions"></a><span data-ttu-id="07dd1-118">고급 입력 체계 확장</span><span class="sxs-lookup"><span data-stu-id="07dd1-118">Advanced Typographic Extensions</span></span>  
 <span data-ttu-id="07dd1-119">고급 입력 체계 표 (OpenType 레이아웃 테이블)는 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 또는 CFF 윤곽선으로 글꼴의 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-119">The Advanced Typographic tables (OpenType Layout tables) extend the functionality of fonts with either [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] or CFF outlines.</span></span> <span data-ttu-id="07dd1-120">OpenType 레이아웃 글꼴에는 고품질의 국제 입력 체계를 지원 하기 위해 글꼴의 기능을 확장 하는 추가 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-120">OpenType Layout fonts contain additional information that extends the capabilities of the fonts to support high-quality international typography.</span></span> <span data-ttu-id="07dd1-121">대부분의 OpenType 글꼴에 사용할 수 있는 총 OpenType 기능의 하위 집합만 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-121">Most OpenType fonts expose only a subset of the total OpenType features available.</span></span> <span data-ttu-id="07dd1-122">OpenType 글꼴은 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-122">OpenType fonts provide the following features.</span></span>  
  
- <span data-ttu-id="07dd1-123">합자, 위치 형식, 대체 문자 및 기타 글꼴 대체를 지원하는 문자와 문자 모양 간의 다양한 매핑</span><span class="sxs-lookup"><span data-stu-id="07dd1-123">Rich mapping between characters and glyphs that support ligatures, positional forms, alternates, and other font substitutions.</span></span>  
  
- <span data-ttu-id="07dd1-124">2차원 위치 지정 및 문자 모양 첨부 지원</span><span class="sxs-lookup"><span data-stu-id="07dd1-124">Support for two-dimensional positioning and glyph attachment.</span></span>  
  
- <span data-ttu-id="07dd1-125">명시적인 스크립트 및 언어 정보가 글꼴에 포함되어 텍스트 처리 애플리케이션에서 동작을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-125">Explicit script and language information contained in font, so a text-processing application can adjust its behavior accordingly.</span></span>  
  
 <span data-ttu-id="07dd1-126">Opentype 레이아웃 테이블은 OpenType 사양의 ["글꼴 파일 테이블"](https://www.microsoft.com/typography/otspec/otff.htm) 섹션에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-126">The OpenType Layout tables are described in more detail in the ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) section of the OpenType specification.</span></span>  
  
 <span data-ttu-id="07dd1-127">이 개요의 나머지 부분에서는 <xref:System.Windows.Documents.Typography> 개체의 속성에 의해 노출 되는 시각적으로 흥미로운 오픈타입 기능 중 일부의 폭과 유연성을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-127">The remainder of this overview introduces the breadth and flexibility of some of the visually-interesting OpenType features that are exposed by the properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="07dd1-128">이 개체에 대한 자세한 내용은 [입력 체계 클래스](#typography_class)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07dd1-128">For more information on this object, see [Typography Class](#typography_class).</span></span>  
  
<a name="variants"></a>   
## <a name="variants"></a><span data-ttu-id="07dd1-129">변형</span><span class="sxs-lookup"><span data-stu-id="07dd1-129">Variants</span></span>  
 <span data-ttu-id="07dd1-130">변형은 위 첨자 및 아래 첨자와 같은 다양한 입력 체계 스타일을 렌더링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-130">Variants are used to render different typographic styles, such as superscripts and subscripts.</span></span>  
  
### <a name="superscripts-and-subscripts"></a><span data-ttu-id="07dd1-131">위 첨자 및 아래 첨자</span><span class="sxs-lookup"><span data-stu-id="07dd1-131">Superscripts and Subscripts</span></span>  
 <span data-ttu-id="07dd1-132"><xref:System.Windows.Documents.Typography.Variants%2A> 속성을 사용 하면 OpenType 글꼴에 대 한 위 첨자 및 아래 첨자 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-132">The <xref:System.Windows.Documents.Typography.Variants%2A> property allows you to set superscript and subscript values for an OpenType font.</span></span>  
  
 <span data-ttu-id="07dd1-133">다음 텍스트는 Palatino Linotype 글꼴의 위 첨자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-133">The following text displays superscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="07dd1-134">![OpenType 위 첨자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-superscripts.gif "OpenType 위 첨자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-134">![Text using OpenType superscripts](./media/opentype-font-features/opentype-superscripts.gif "Text using OpenType superscripts")</span></span>  
  
 <span data-ttu-id="07dd1-135">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴의 위 첨자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-135">The following markup example shows how to define superscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 <span data-ttu-id="07dd1-136">다음 텍스트는 Palatino Linotype 글꼴의 아래 첨자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-136">The following text displays subscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="07dd1-137">![OpenType 아래 첨자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-subscripts.gif "OpenType 아래 첨자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-137">![Text using OpenType subscripts](./media/opentype-font-features/opentype-subscripts.gif "Text using OpenType subscripts")</span></span>  
  
 <span data-ttu-id="07dd1-138">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴의 아래 첨자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-138">The following markup example shows how to define subscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a><span data-ttu-id="07dd1-139">위 첨자 및 아래 첨자의 장식 사용</span><span class="sxs-lookup"><span data-stu-id="07dd1-139">Decorative Uses of Superscripts and Subscripts</span></span>  
 <span data-ttu-id="07dd1-140">위 첨자와 아래 첨자를 사용하여 대/소문자 혼용 텍스트의 장식 효과를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-140">You can also use superscripts and subscripts to create decorative effects of mixed case text.</span></span> <span data-ttu-id="07dd1-141">다음 텍스트는 Palatino Linotype 글꼴의 위 첨자 및 아래 첨자 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-141">The following text displays superscript and subscript text for the Palatino Linotype font.</span></span> <span data-ttu-id="07dd1-142">대문자는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-142">Note that the capitals are not affected.</span></span>  
  
 <span data-ttu-id="07dd1-143">![OpenType 위 첨자 및 아래 첨자를 사용 하는 텍스트](./media/opentype-font-features/opentype-superscripts-subscripts.gif "OpenType 위 첨자 및 아래 첨자를 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-143">![Text using OpenType superscripts and subscripts](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Text using OpenType superscripts and subscripts")</span></span>  

 <span data-ttu-id="07dd1-144">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 글꼴의 위 첨자 및 아래 첨자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-144">The following markup example shows how to define superscripts and subscripts for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a><span data-ttu-id="07dd1-145">대문자</span><span class="sxs-lookup"><span data-stu-id="07dd1-145">Capitals</span></span>  
 <span data-ttu-id="07dd1-146">대문자는 대문자 스타일의 문자 모양으로 텍스트를 렌더링하는 일련의 입력 체계 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-146">Capitals are a set of typographical forms that render text in capital-styled glyphs.</span></span> <span data-ttu-id="07dd1-147">일반적으로 텍스트를 모두 대문자로 렌더링하면 글자 사이의 간격이 너무 좁아 보이고 글자의 무게와 비율상 너무 무거워 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-147">Typically, when text is rendered as all capitals, the spacing between letters can appear too tight, and the weight and proportion of the letters too heavy.</span></span> <span data-ttu-id="07dd1-148">OpenType 작은 대문자를 포함 하 여, 대문자, 꼬마 대문자, 제목, 및 대문자 간격에 대 한 다양 한 스타일 서식 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-148">OpenType supports a number of styling formats for capitals, including small capitals, petite capitals, titling, and capital spacing.</span></span> <span data-ttu-id="07dd1-149">이러한 스타일 서식을 사용하여 대문자 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-149">These styling formats allow you to control the appearance of capitals.</span></span>  
  
 <span data-ttu-id="07dd1-150">다음 텍스트는 “SmallCaps” 및 “AllSmallCaps”로 스타일이 지정된 문자 앞에 Pescadero 글꼴의 표준 대문자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-150">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="07dd1-151">이 경우 세 단어 모두 동일한 글꼴 크기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-151">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="07dd1-152">![OpenType 대문자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-capitals.gif "OpenType 대문자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-152">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  
  
 <span data-ttu-id="07dd1-153">다음 태그 예제에서는 속성을 사용 하 여 Pescadero 글꼴의 대문자를 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Documents.Typography> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-153">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="07dd1-154">“SmallCaps” 형식을 사용하는 경우 선행 대문자는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-154">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a><span data-ttu-id="07dd1-155">제목 대문자</span><span class="sxs-lookup"><span data-stu-id="07dd1-155">Titling Capitals</span></span>  
 <span data-ttu-id="07dd1-156">제목 대문자는 무게와 비율이 더 가볍고 일반 대문자보다 세련된 느낌을 주도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-156">Titling capitals are lighter in weight and proportion and designed to give a more elegant look than normal capitals.</span></span> <span data-ttu-id="07dd1-157">제목 대문자는 일반적으로 큰 글꼴 크기의 머리글로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-157">Titling capitals are typically used in larger font sizes as headings.</span></span> <span data-ttu-id="07dd1-158">다음 텍스트는 Pescadero 글꼴의 일반 대문자 및 제목 대문자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-158">The following text displays normal and titling capitals for the Pescadero font.</span></span> <span data-ttu-id="07dd1-159">두 번째 줄에 있는 텍스트의 획(stem) 너비가 더 좁은 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-159">Notice the narrower stem widths of the text on the second line.</span></span>  
  
 <span data-ttu-id="07dd1-160">![OpenType 제목 대문자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-titling-capitals.gif "OpenType 제목 대문자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-160">![Text using OpenType titling capitals](./media/opentype-font-features/opentype-titling-capitals.gif "Text using OpenType titling capitals")</span></span>  
  
 <span data-ttu-id="07dd1-161">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pescadero 글꼴의 제목 대문자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-161">The following markup example shows how to define titling capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a><span data-ttu-id="07dd1-162">대문자 간격</span><span class="sxs-lookup"><span data-stu-id="07dd1-162">Capital Spacing</span></span>  
 <span data-ttu-id="07dd1-163">대문자 간격은 텍스트에서 모두 대문자를 사용할 때 더 넓은 간격을 제공할 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-163">Capital spacing is a feature that allows you to provide more spacing when using all capitals in text.</span></span> <span data-ttu-id="07dd1-164">대문자는 대개 소문자와 함께 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-164">Capital letters are typically designed to blend with lowercase letters.</span></span> <span data-ttu-id="07dd1-165">대문자와 소문자 사이에서는 적절해 보이는 간격이 모두 대문자를 사용할 때는 너무 좁게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-165">Spacing that appears attractive between and a capital letter and a lowercase letter may look too tight when all capital letters are used.</span></span> <span data-ttu-id="07dd1-166">다음 텍스트는 Pescadero 글꼴의 일반 간격 및 대문자 간격을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-166">The following text displays normal and capital spacing for the Pescadero font.</span></span>  
  
 <span data-ttu-id="07dd1-167">![OpenType 대문자 간격을 사용 하는 텍스트](./media/opentype-font-features/opentype-capital-spacing.gif "OpenType 대문자 간격을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-167">![Text using OpenType capital spacing](./media/opentype-font-features/opentype-capital-spacing.gif "Text using OpenType capital spacing ")</span></span>  
 
 <span data-ttu-id="07dd1-168">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pescadero 글꼴의 대문자 간격을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-168">The following markup example shows how to define capital spacing for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a><span data-ttu-id="07dd1-169">합자</span><span class="sxs-lookup"><span data-stu-id="07dd1-169">Ligatures</span></span>  
 <span data-ttu-id="07dd1-170">합자는 읽기 쉽거나 보기 좋은 텍스트를 만들기 위해 단일 문자 모양으로 구성된 두 개 이상의 문자 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-170">Ligatures are two or more glyphs that are formed into a single glyph in order to create more readable or attractive text.</span></span> <span data-ttu-id="07dd1-171">OpenType 글꼴은 네 가지 형식의 합자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-171">OpenType fonts support four types of ligatures:</span></span>  
  
- <span data-ttu-id="07dd1-172">**표준 합자**.</span><span class="sxs-lookup"><span data-stu-id="07dd1-172">**Standard ligatures**.</span></span> <span data-ttu-id="07dd1-173">가독성을 향상시키기 위해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-173">Designed to enhance readability.</span></span> <span data-ttu-id="07dd1-174">표준 합자에는 “fi”, “fl” 및 “ff”가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-174">Standard ligatures include "fi", "fl", and "ff".</span></span>  
  
- <span data-ttu-id="07dd1-175">**컨텍스트 합자**.</span><span class="sxs-lookup"><span data-stu-id="07dd1-175">**Contextual ligatures**.</span></span> <span data-ttu-id="07dd1-176">합자를 구성하는 문자 간에 더 나은 결합 동작을 제공하여 가독성을 높이도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-176">Designed to enhance readability by providing better joining behavior between the characters that make up the ligature.</span></span>  
  
- <span data-ttu-id="07dd1-177">**임의 합자**.</span><span class="sxs-lookup"><span data-stu-id="07dd1-177">**Discretionary ligatures**.</span></span> <span data-ttu-id="07dd1-178">장식용으로 디자인되었으며 가독성을 위해 별도로 디자인된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-178">Designed to be ornamental, and not specifically designed for readability.</span></span>  
  
- <span data-ttu-id="07dd1-179">**기록 합자**.</span><span class="sxs-lookup"><span data-stu-id="07dd1-179">**Historical ligatures**.</span></span> <span data-ttu-id="07dd1-180">기록용으로 디자인되었으며 가독성을 위해 별도로 디자인된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-180">Designed to be historical, and not specifically designed for readability.</span></span>  
  
 <span data-ttu-id="07dd1-181">다음 텍스트는 Pericles 글꼴에 대한 표준 합자 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-181">The following text displays standard ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="07dd1-182">![OpenType 표준 합자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-standard-ligatures.gif "OpenType 표준 합자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-182">![Text using OpenType standard ligatures](./media/opentype-font-features/opentype-standard-ligatures.gif "Text using OpenType standard ligatures")</span></span>  
  
 <span data-ttu-id="07dd1-183">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pericles 글꼴에 대 한 표준 합자 문자 모양을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-183">The following markup example shows how to define standard ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 <span data-ttu-id="07dd1-184">다음 텍스트는 Pericles 글꼴의 임의 합자 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-184">The following text displays discretionary ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="07dd1-185">![OpenType 임의 합자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-discretionary-ligatures.gif "OpenType 임의 합자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-185">![Text using OpenType discretionary ligatures](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Text using OpenType discretionary ligatures")</span></span>  
  
 <span data-ttu-id="07dd1-186">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pericles 글꼴에 대 한 임의 합자 문자 모양을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-186">The following markup example shows how to define discretionary ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 <span data-ttu-id="07dd1-187">OpenType 글꼴에 기본적으로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 표준 합자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-187">By default, OpenType fonts in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enable standard ligatures.</span></span> <span data-ttu-id="07dd1-188">예를 들어 Palatino Linotype 글꼴을 사용하면 표준 합자 “fi”, “ff”및 “fl”이 결합된 문자 모양으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-188">For example, if you use the Palatino Linotype font, the standard ligatures "fi", "ff", and "fl" appear as a combined character glyph.</span></span> <span data-ttu-id="07dd1-189">각 표준 합자의 문자 쌍이 서로 붙어 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-189">Notice that the pair of characters for each standard ligature touch each other.</span></span>  
  
 <span data-ttu-id="07dd1-190">![Palatino Linotype와 함께 OpenType 표준 합자를 사용 하는 텍스트](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Palatino Linotype와 함께 OpenType 표준 합자를 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-190">![Text using OpenType standard ligatures with Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Text using OpenType standard ligatures with Palatino Linotype")</span></span>    
   
 <span data-ttu-id="07dd1-191">그러나 표준 합자 기능을 사용하지 않도록 설정하여 “ff”와 같이 표준 합자가 결합된 문자 모양이 아닌 두 개의 별도 문자 모양으로 표시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-191">However, you can disable standard ligature features so that a standard ligature such as "ff" displays as two separate glyphs, rather than as a combined character glyph.</span></span>  
  
 <span data-ttu-id="07dd1-192">![비활성화 된 OpenType 표준 합자를 사용 하 여 텍스트](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "비활성화 된 OpenType 표준 합자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-192">![Text using disabled OpenType standard ligatures](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Text using disabled OpenType standard ligatures")</span></span>  
    
 <span data-ttu-id="07dd1-193">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴에 대 한 표준 합자 문자 모양을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-193">The following markup example shows how to disable standard ligature glyphs for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a><span data-ttu-id="07dd1-194">선단 장식</span><span class="sxs-lookup"><span data-stu-id="07dd1-194">Swashes</span></span>  
 <span data-ttu-id="07dd1-195">선단 장식은 종종 붓글씨와 관련된 정교한 장식을 사용하는 장식용 문자 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-195">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="07dd1-196">다음 텍스트는 Pescadero 글꼴의 표준 및 선단 장식 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-196">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="07dd1-197">![OpenType 표준 및 선단 장식 문자 모양을 사용 하 여 텍스트](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "OpenType 표준 및 선단 장식 문자 모양을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-197">![Text using OpenType standard and swash glyphs](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Text using OpenType standard and swash glyphs")</span></span>  

 <span data-ttu-id="07dd1-198">선단 장식은 종종 이벤트 발표와 같은 짧은 문장에서 장식 요소로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-198">Swashes are often used as decorative elements in short phrases such as event announcements.</span></span> <span data-ttu-id="07dd1-199">다음 텍스트는 선단 장식을 사용하여 이벤트 이름의 대문자를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-199">The following text uses swashes to emphasize the capital letters of the name of the event.</span></span>  
  
 <span data-ttu-id="07dd1-200">![OpenType 선단 장식을 사용 하 여 텍스트](./media/opentype-font-features/opentype-swashes.gif "OpenType 선단 장식을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-200">![Text using OpenType swashes](./media/opentype-font-features/opentype-swashes.gif "Text using OpenType swashes")</span></span>  
  
 <span data-ttu-id="07dd1-201">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 글꼴의 선단 장식을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-201">The following markup example shows how to define swashes for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a><span data-ttu-id="07dd1-202">컨텍스트 선단 장식</span><span class="sxs-lookup"><span data-stu-id="07dd1-202">Contextual Swashes</span></span>  
 <span data-ttu-id="07dd1-203">특정 조합의 선단 장식 문자 모양은 인접 문자에 내림 영자가 겹치는 것과 같이 보기 좋지 않은 모양이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-203">Certain combinations of swash glyphs can cause an unattractive appearance, such as overlapping descenders on adjacent letters.</span></span> <span data-ttu-id="07dd1-204">컨텍스트 선단 장식을 사용하면 더 좋은 모양을 만드는 대체 선단 장식 문자 모양을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-204">Using a contextual swash allows you to use a substitute swash glyph that produces a better appearance.</span></span> <span data-ttu-id="07dd1-205">다음 텍스트는 동일한 단어에 컨텍스트 선단 장식이 적용되기 전후의 모습을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-205">The following text shows the same word before and after a contextual swash is applied.</span></span>  
  
 <span data-ttu-id="07dd1-206">![OpenType 컨텍스트 선단 장식을 사용 하 여 텍스트](./media/opentype-font-features/opentype-contextual-swashes.gif "OpenType 컨텍스트 선단 장식을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-206">![Text using OpenType contextual swashes](./media/opentype-font-features/opentype-contextual-swashes.gif "Text using OpenType contextual swashes")</span></span>  
  
 <span data-ttu-id="07dd1-207">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pescadero 글꼴에 대 한 컨텍스트 선단 장식을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-207">The following markup example shows how to define a contextual swash for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a><span data-ttu-id="07dd1-208">대체 문자</span><span class="sxs-lookup"><span data-stu-id="07dd1-208">Alternates</span></span>  
 <span data-ttu-id="07dd1-209">대체 문자는 표준 문자 모양으로 대체될 수 있는 문자 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-209">Alternates are glyphs that can be substituted for a standard glyph.</span></span> <span data-ttu-id="07dd1-210">다음 예제에서 사용 되는 Pericles 글꼴과 같은 OpenType 글꼴은 텍스트의 다른 모양을 만드는 데 사용할 수 있는 대체 문자 모양을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-210">OpenType fonts, such as the Pericles font used in the following examples, can contain alternate glyphs that you can use to create different appearances for text.</span></span> <span data-ttu-id="07dd1-211">다음 텍스트는 Pericles 글꼴의 표준 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-211">The following text displays standard glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="07dd1-212">![OpenType 표준 문자 모양을 사용 하 여 텍스트](./media/opentype-font-features/opentype-standard-glyphs.gif "OpenType 표준 문자 모양을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-212">![Text using OpenType standard glyphs](./media/opentype-font-features/opentype-standard-glyphs.gif "Text using OpenType standard glyphs")</span></span>  

 <span data-ttu-id="07dd1-213">Pericles OpenType 글꼴 스타일 대체 문자 모양의 표준 집합을 제공 하는 추가 문자 모양이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-213">The Pericles OpenType font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="07dd1-214">다음 텍스트는 스타일 대체 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-214">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="07dd1-215">![OpenType 스타일 대체 문자 모양을 사용 하 여 텍스트](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "OpenType 스타일 대체 문자 모양을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-215">![Text using OpenType stylistic alternate glyphs](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Text using OpenType stylistic alternate glyphs")</span></span>  
  
 <span data-ttu-id="07dd1-216">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Pericles 글꼴에 대 한 스타일 대체 문자 모양을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-216">The following markup example shows how to define stylistic alternate glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 <span data-ttu-id="07dd1-217">다음 텍스트는 Pericles 글꼴에 대한 여러 가지 다른 스타일 대체 문자 모양을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-217">The following text displays several other stylistic alternate glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="07dd1-218">![Pericles 글꼴에 대해 OpenType 스타일 대체 문자 모양을 사용 하는 텍스트](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Pericles 글꼴에 대해 OpenType 스타일 대체 문자 모양을 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-218">![Text using OpenType stylistic alternate glyphs  for the Pericles font](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Text using OpenType stylistic alternate glyphs  for the Pericles font")</span></span>

 <span data-ttu-id="07dd1-219">다음 태그 예제에서는 이러한 다른 스타일 대체 문자 모양을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-219">The following markup example shows how to define these other stylistic alternate glyphs.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a><span data-ttu-id="07dd1-220">임의 컨텍스트 대체 문자</span><span class="sxs-lookup"><span data-stu-id="07dd1-220">Random Contextual Alternates</span></span>  
 <span data-ttu-id="07dd1-221">임의 컨텍스트 대체 문자는 단일 문자에 대해 여러 개의 대체 문자 모양을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-221">Random contextual alternates provide multiple substitute glyphs for a single character.</span></span> <span data-ttu-id="07dd1-222">이 기능은 스크립트 유형의 글꼴로 구현될 때 임의로 선택한 외관상 약간 다른 문자 집합을 사용하여 필기를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-222">When implemented with script-type fonts, this feature can simulate handwriting by using of a set of randomly chosen glyphs with slight differences in appearance.</span></span> <span data-ttu-id="07dd1-223">다음 텍스트는 Lindsey 글꼴에 대한 임의 컨텍스트 대체 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-223">The following text uses random contextual alternates for the Lindsey font.</span></span> <span data-ttu-id="07dd1-224">문자 “a”의 모양이 약간 다른 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-224">Notice that the letter "a" varies slightly in appearance</span></span>  
  
 <span data-ttu-id="07dd1-225">![OpenType 임의 컨텍스트 대체 문자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-random-contextual-alternates.gif "OpenType 임의 컨텍스트 대체 문자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-225">![Text using OpenType random contextual alternates](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Text using OpenType random contextual alternates")</span></span>  
  
 <span data-ttu-id="07dd1-226">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Lindsey 글꼴에 대 한 임의 컨텍스트 대체 항목을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-226">The following markup example shows how to define random contextual alternates for the Lindsey font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a><span data-ttu-id="07dd1-227">기록 형식</span><span class="sxs-lookup"><span data-stu-id="07dd1-227">Historical Forms</span></span>  
 <span data-ttu-id="07dd1-228">기록 형식은 과거에는 일반적이었던 입력 체계 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-228">Historical forms are typographic conventions that were common in the past.</span></span> <span data-ttu-id="07dd1-229">다음 텍스트는 Palatino Linotype 글꼴에 대한 기록 형식 문자 모양을 사용하여 “Boston, Massachusetts” 구문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-229">The following text displays the phrase, "Boston, Massachusetts", using an historical form of glyphs for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="07dd1-230">![OpenType 기록 폼을 사용 하 여 텍스트](./media/opentype-font-features/opentype-historical-forms.gif "OpenType 기록 폼을 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-230">![Text using OpenType historical forms](./media/opentype-font-features/opentype-historical-forms.gif "Text using OpenType historical forms")</span></span>  
   
 <span data-ttu-id="07dd1-231">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴에 대 한 기록 폼을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-231">The following markup example shows how to define historical forms for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a><span data-ttu-id="07dd1-232">숫자 스타일</span><span class="sxs-lookup"><span data-stu-id="07dd1-232">Numerical Styles</span></span>  
 <span data-ttu-id="07dd1-233">OpenType 글꼴은 텍스트의 숫자 값으로 사용할 수 있는 많은 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-233">OpenType fonts support a large number of features that can be used with numerical values in text.</span></span>  
  
### <a name="fractions"></a><span data-ttu-id="07dd1-234">소수</span><span class="sxs-lookup"><span data-stu-id="07dd1-234">Fractions</span></span>  
 <span data-ttu-id="07dd1-235">OpenType 글꼴 분수 슬래시 사용 하거나 위아래로 표현에 대 한 스타일을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-235">OpenType fonts support styles for fractions, including slashed and stacked.</span></span>  
  
 <span data-ttu-id="07dd1-236">다음 텍스트는 Palatino Linotype 글꼴의 분수 스타일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-236">The following text displays fraction styles for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="07dd1-237">![OpenType를 사용 하 여 텍스트 슬래시 및 상하 형 분수](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "OpenType를 사용 하 여 텍스트 슬래시 및 상하 형 분수")</span><span class="sxs-lookup"><span data-stu-id="07dd1-237">![Text using OpenType slashed and stacked fractions](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Text using OpenType slashed and stacked fractions")</span></span>  
   
 <span data-ttu-id="07dd1-238">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴의 분수 스타일을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-238">The following markup example shows how to define fraction styles for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a><span data-ttu-id="07dd1-239">이전 스타일 숫자</span><span class="sxs-lookup"><span data-stu-id="07dd1-239">Old Style Numerals</span></span>  
 <span data-ttu-id="07dd1-240">OpenType 글꼴에는 이전 스타일 숫자 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-240">OpenType fonts support an old style numeral format.</span></span> <span data-ttu-id="07dd1-241">이 형식은 더 이상 표준이 아닌 스타일의 숫자를 표시할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-241">This format is useful for displaying numerals in styles that are no longer standard.</span></span> <span data-ttu-id="07dd1-242">다음 텍스트는 Palatino Linotype 글꼴의 표준 및 이전 스타일 숫자 형식으로 된 18세기 날짜를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-242">The following text displays an 18th century date in standard and old style numeral formats for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="07dd1-243">![OpenType 이전 스타일 숫자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-old-style-numerals.gif "OpenType 이전 스타일 숫자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-243">![Text using OpenType old style numerals](./media/opentype-font-features/opentype-old-style-numerals.gif "Text using OpenType old style numerals")</span></span>  
    
 <span data-ttu-id="07dd1-244">다음 텍스트는 Palatino Linotype 글꼴의 표준 숫자 뒤에 이전 스타일 숫자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-244">The following text displays standard numerals for the Palatino Linotype font, followed by old style numerals.</span></span>  
  
 <span data-ttu-id="07dd1-245">![OpenType 이전 스타일 숫자 집합을 사용 하 여 텍스트](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "OpenType 이전 스타일 숫자 집합을 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-245">![Text using OpenType old style numeral sets](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Text using OpenType old style numeral sets")</span></span>  
  
 <span data-ttu-id="07dd1-246">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Palatino Linotype 글꼴의 이전 스타일 숫자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-246">The following markup example shows how to define old style numerals for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a><span data-ttu-id="07dd1-247">가변 폭 및 테이블 형식 숫자</span><span class="sxs-lookup"><span data-stu-id="07dd1-247">Proportional and Tabular Figures</span></span>  
 <span data-ttu-id="07dd1-248">OpenType 글꼴 숫자를 사용할 때 너비 맞춤을 제어 하는 가변 폭 및 테이블 형식 숫자 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-248">OpenType fonts support a proportional and tabular figure feature to control the alignment of widths when using numerals.</span></span> <span data-ttu-id="07dd1-249">가변 폭 숫자는 각 숫자의 너비를 다르게 처리합니다. 예를 들어 “1”은 “5”보다 너비가 좁습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-249">Proportional figures treat each numeral as having a different width—"1" is narrower than "5".</span></span> <span data-ttu-id="07dd1-250">테이블 형식 숫자는 같은 너비의 숫자로 처리되어 세로로 정렬되므로 금융 형식 정보의 가독성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-250">Tabular figures are treated as equal-width numerals so that they align vertically, which increases the readability of financial type information.</span></span>  
  
 <span data-ttu-id="07dd1-251">다음 텍스트는 Miramonte 글꼴을 사용하여 첫 번째 열에 두 개의 가변 폭 숫자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-251">The following text displays two proportional figures in the first column using the Miramonte font.</span></span> <span data-ttu-id="07dd1-252">숫자 “5”와 “1” 사이의 너비 차이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-252">Note the difference in width between the numerals "5" and "1".</span></span> <span data-ttu-id="07dd1-253">두 번째 열은 테이블 형식 숫자 기능을 사용하여 너비가 조정된 동일한 두 개의 숫자 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-253">The second column shows the same two numeric values with the widths adjusted by using the tabular figure feature.</span></span>  
  
 <span data-ttu-id="07dd1-254">![OpenType 비례 & 테이블 형식 그림을 사용 하는 텍스트](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "OpenType 비례 및 테이블 형식 수치를 사용 하는 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-254">![Text using OpenType proportional & tabular figures](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Text using OpenType proportional and tabular figures")</span></span>  
    
 <span data-ttu-id="07dd1-255">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Miramonte 글꼴에 대해 비례 및 테이블 형식 숫자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-255">The following markup example shows how to define proportional and tabular figures for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a><span data-ttu-id="07dd1-256">슬래시 0</span><span class="sxs-lookup"><span data-stu-id="07dd1-256">Slashed Zero</span></span>  
 <span data-ttu-id="07dd1-257">OpenType 글꼴 지원 슬래시 0 숫자 형식을 "O" 문자와 숫자 "0"의 차이 강조 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="07dd1-257">OpenType fonts support a slashed zero numeral format to emphasize the difference between the letter "O" and the numeral "0".</span></span> <span data-ttu-id="07dd1-258">슬래시 0 숫자는 금융 정보 및 비즈니스 정보의 식별자에 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-258">The slashed zero numeral is often used for identifiers in financial and business information.</span></span>  
  
 <span data-ttu-id="07dd1-259">다음 텍스트는 Miramonte 글꼴을 사용하는 샘플 주문 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-259">The following text displays a sample order identifier using the Miramonte font.</span></span> <span data-ttu-id="07dd1-260">첫 번째 줄에는 표준 숫자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-260">The first line uses standard numerals.</span></span> <span data-ttu-id="07dd1-261">두 번째 줄에서는 대문자 “O” 문자와의 대비를 높이기 위해 슬래시 0 숫자가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-261">The second line used slashed zero numerals to provide better contrast with the uppercase "O" letter.</span></span>  
  
 <span data-ttu-id="07dd1-262">![OpenType를 사용 하 여 텍스트의 슬래시 0 숫자](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "OpenType를 사용 하 여 텍스트의 슬래시 0 숫자")</span><span class="sxs-lookup"><span data-stu-id="07dd1-262">![Text using OpenType slashed zero numerals](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Text using OpenType slashed zero numerals")</span></span>  
    
 <span data-ttu-id="07dd1-263">다음 태그 예제에서는 <xref:System.Windows.Documents.Typography> 개체의 속성을 사용 하 여 Miramonte 글꼴에 대 한 슬래시 0 숫자를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-263">The following markup example shows how to define slashed zero numerals for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a><span data-ttu-id="07dd1-264">입력 체계 클래스</span><span class="sxs-lookup"><span data-stu-id="07dd1-264">Typography Class</span></span>  
 <span data-ttu-id="07dd1-265">개체 <xref:System.Windows.Documents.Typography> 는 OpenType 글꼴이 지 원하는 기능 집합을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-265">The <xref:System.Windows.Documents.Typography> object exposes the set of features that an OpenType font supports.</span></span> <span data-ttu-id="07dd1-266">태그에서의 <xref:System.Windows.Documents.Typography> 속성을 설정 하 여 OpenType 기능을 활용 하는 문서를 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-266">By setting the properties of <xref:System.Windows.Documents.Typography> in markup, you can easily author documents that take advantage of OpenType features.</span></span>  
  
 <span data-ttu-id="07dd1-267">다음 텍스트는 “SmallCaps” 및 “AllSmallCaps”로 스타일이 지정된 문자 앞에 Pescadero 글꼴의 표준 대문자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-267">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="07dd1-268">이 경우 세 단어 모두 동일한 글꼴 크기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-268">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="07dd1-269">![OpenType 대문자를 사용 하 여 텍스트](./media/opentype-font-features/opentype-capitals.gif "OpenType 대문자를 사용 하 여 텍스트")</span><span class="sxs-lookup"><span data-stu-id="07dd1-269">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  
    
 <span data-ttu-id="07dd1-270">다음 태그 예제에서는 속성을 사용 하 여 Pescadero 글꼴의 대문자를 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Documents.Typography> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-270">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="07dd1-271">“SmallCaps” 형식을 사용하는 경우 선행 대문자는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-271">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 <span data-ttu-id="07dd1-272">다음 코드 예제에서는 이전 태그 예제와 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-272">The following code example accomplishes the same task as the previous markup example.</span></span>  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a><span data-ttu-id="07dd1-273">입력 체계 클래스 속성</span><span class="sxs-lookup"><span data-stu-id="07dd1-273">Typography Class Properties</span></span>  
 <span data-ttu-id="07dd1-274">다음 표에서는 <xref:System.Windows.Documents.Typography> 개체의 속성, 값 및 기본 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07dd1-274">The following table lists the properties, values, and default settings of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
|<span data-ttu-id="07dd1-275">속성</span><span class="sxs-lookup"><span data-stu-id="07dd1-275">Property</span></span>|<span data-ttu-id="07dd1-276">값</span><span class="sxs-lookup"><span data-stu-id="07dd1-276">Value(s)</span></span>|<span data-ttu-id="07dd1-277">기본값</span><span class="sxs-lookup"><span data-stu-id="07dd1-277">Default Value</span></span>|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|<span data-ttu-id="07dd1-278">숫자 값-바이트</span><span class="sxs-lookup"><span data-stu-id="07dd1-278">Numeric value - byte</span></span>|<span data-ttu-id="07dd1-279">0</span><span class="sxs-lookup"><span data-stu-id="07dd1-279">0</span></span>|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<span data-ttu-id="07dd1-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span><span class="sxs-lookup"><span data-stu-id="07dd1-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span></span>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|<span data-ttu-id="07dd1-281">숫자 값-바이트</span><span class="sxs-lookup"><span data-stu-id="07dd1-281">Numeric value - byte</span></span>|<span data-ttu-id="07dd1-282">0</span><span class="sxs-lookup"><span data-stu-id="07dd1-282">0</span></span>|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<span data-ttu-id="07dd1-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span><span class="sxs-lookup"><span data-stu-id="07dd1-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span></span>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<span data-ttu-id="07dd1-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span><span class="sxs-lookup"><span data-stu-id="07dd1-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span></span>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<span data-ttu-id="07dd1-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span><span class="sxs-lookup"><span data-stu-id="07dd1-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span></span>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<span data-ttu-id="07dd1-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span><span class="sxs-lookup"><span data-stu-id="07dd1-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span></span>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|<span data-ttu-id="07dd1-287">숫자 값-바이트</span><span class="sxs-lookup"><span data-stu-id="07dd1-287">numeric value – byte</span></span>|<span data-ttu-id="07dd1-288">0</span><span class="sxs-lookup"><span data-stu-id="07dd1-288">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|<span data-ttu-id="07dd1-289">숫자 값-바이트</span><span class="sxs-lookup"><span data-stu-id="07dd1-289">numeric value – byte</span></span>|<span data-ttu-id="07dd1-290">0</span><span class="sxs-lookup"><span data-stu-id="07dd1-290">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<span data-ttu-id="07dd1-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span><span class="sxs-lookup"><span data-stu-id="07dd1-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span></span>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="07dd1-292">참고자료</span><span class="sxs-lookup"><span data-stu-id="07dd1-292">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- [<span data-ttu-id="07dd1-293">OpenType 사양</span><span class="sxs-lookup"><span data-stu-id="07dd1-293">OpenType Specification</span></span>](https://go.microsoft.com/fwlink/?LinkId=96731)
- [<span data-ttu-id="07dd1-294">WPF의 입력 체계</span><span class="sxs-lookup"><span data-stu-id="07dd1-294">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="07dd1-295">샘플 OpenType 글꼴 팩</span><span class="sxs-lookup"><span data-stu-id="07dd1-295">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
- [<span data-ttu-id="07dd1-296">응용 프로그램과 함께 글꼴 패키징</span><span class="sxs-lookup"><span data-stu-id="07dd1-296">Packaging Fonts with Applications</span></span>](packaging-fonts-with-applications.md)
