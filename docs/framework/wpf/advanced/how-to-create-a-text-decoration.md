---
title: '방법: 텍스트 장식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: b85bbaed13d9406f85c62a9a5bc5ca220d90b0b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607948"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="bb718-102">방법: 텍스트 장식 만들기</span><span class="sxs-lookup"><span data-stu-id="bb718-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="bb718-103"><xref:System.Windows.TextDecoration> 개체가 시각적 장식 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="bb718-104">텍스트 장식의 네 가지가: 밑줄, 기준, 취소선 및 윗줄 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="bb718-105">다음 예제에서는 텍스트를 기준으로 텍스트 장식의 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="bb718-106">![텍스트 장식 위치의 다이어그램](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="bb718-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="bb718-107">텍스트 장식 형식의 예제</span><span class="sxs-lookup"><span data-stu-id="bb718-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="bb718-108">텍스트 장식에 텍스트를 추가 하려면 만들기를 <xref:System.Windows.TextDecoration> 개체 및 해당 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="bb718-109">사용 된 <xref:System.Windows.TextDecoration.Location%2A> 밑줄 등 텍스트 장식 나타나는 위치를 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="bb718-110">사용 된 <xref:System.Windows.TextDecoration.Pen%2A> 텍스트 장식 단색 또는 그라데이션 색 등의 모양을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="bb718-111">에 대 한 값을 지정 하지 않으면 경우는 <xref:System.Windows.TextDecoration.Pen%2A> 속성에 장식 텍스트와 동일한 색의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="bb718-112">정의한 후는 <xref:System.Windows.TextDecoration> 개체에 추가 하는 <xref:System.Windows.TextDecorations> 원하는 텍스트 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="bb718-113">다음 예제에서는 파선된 펜 선형 그라데이션 브러시와 스타일이 지정 된 텍스트 장식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="bb718-114">![선형 그라데이션 밑줄로 텍스트 장식](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="bb718-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="bb718-115">선형 그라데이션으로 밑줄 예가 스타일 파선된 펜 및 브러시</span><span class="sxs-lookup"><span data-stu-id="bb718-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="bb718-116"><xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에서 하이퍼링크를 호스트할 수 있는 인라인 수준의 유동 콘텐츠 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="bb718-117">기본적으로 <xref:System.Windows.Documents.Hyperlink> 사용을 <xref:System.Windows.TextDecoration> 밑줄을 표시 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="bb718-118"><xref:System.Windows.TextDecoration> 많을 경우에 특히 개체를 인스턴스화할 때 성능이 저하 될 수 있습니다 <xref:System.Windows.Documents.Hyperlink> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="bb718-119">광범위 하 게 사용 한다면 <xref:System.Windows.Documents.Hyperlink> 와 같은 경우 트리거될 때만 밑줄이 표시 하려는 요소를 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="bb718-120">다음 예제에서는 "My MSN" 링크 밑줄은 동적-만 표시 될 때를 <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="bb718-121">![Textdecoration을 표시 하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="bb718-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="bb718-122">Textdecoration을 사용 하 여 정의 하는 하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="bb718-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="bb718-123">자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb718-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb718-124">예제</span><span class="sxs-lookup"><span data-stu-id="bb718-124">Example</span></span>  
 <span data-ttu-id="bb718-125">다음 코드 예제에서 밑줄 텍스트 장식의 기본 글꼴 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="bb718-126">다음 코드 예제에서 밑줄 텍스트 장식은 펜에 대 한 단색 브러시를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="bb718-127">다음 코드 예제에서 밑줄 텍스트 장식은 파선된 펜에 대 한 선형 그라데이션 브러시를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bb718-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="bb718-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb718-128">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="bb718-129">하이퍼링크에 밑줄이 그어지는지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="bb718-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
