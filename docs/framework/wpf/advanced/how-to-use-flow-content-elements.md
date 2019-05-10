---
title: '방법: 유동 콘텐츠 요소 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: f61116c0bf52ac726238d9e21c2422cedbb4716f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663322"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="84991-102">방법: 유동 콘텐츠 요소 사용</span><span class="sxs-lookup"><span data-stu-id="84991-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="84991-103">다음 예제에서는 다양한 유동 콘텐츠 요소 및 연결된 특성에 대한 선언적 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84991-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="84991-104">여기서 설명하는 요소와 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84991-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="84991-105"><xref:System.Windows.Documents.Bold> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="84991-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> 특성</span><span class="sxs-lookup"><span data-stu-id="84991-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="84991-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> 특성</span><span class="sxs-lookup"><span data-stu-id="84991-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="84991-108"><xref:System.Windows.Documents.Italic> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="84991-109"><xref:System.Windows.Documents.LineBreak> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="84991-110"><xref:System.Windows.Documents.List> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="84991-111"><xref:System.Windows.Documents.ListItem> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="84991-112"><xref:System.Windows.Documents.Paragraph> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="84991-113"><xref:System.Windows.Documents.Run> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="84991-114"><xref:System.Windows.Documents.Section> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="84991-115"><xref:System.Windows.Documents.Span> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="84991-116"><xref:System.Windows.Documents.Typography.Variants%2A> 특성 (위 첨자 및 아래 첨자)</span><span class="sxs-lookup"><span data-stu-id="84991-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="84991-117"><xref:System.Windows.Documents.Underline> 요소</span><span class="sxs-lookup"><span data-stu-id="84991-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="84991-118">예제</span><span class="sxs-lookup"><span data-stu-id="84991-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
