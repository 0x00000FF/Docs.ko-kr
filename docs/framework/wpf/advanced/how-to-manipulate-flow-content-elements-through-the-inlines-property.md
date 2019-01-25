---
title: '방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: a2bf11dc3b2e8bc3658edb12edea5bd890a7929e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661271"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="a1e80-102">방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작</span><span class="sxs-lookup"><span data-stu-id="a1e80-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="a1e80-103">이러한 예제는 인라인 유동 콘텐츠 요소에서 수행할 수 있는 보다 일반적인 작업 중 일부를 보여 (및 이러한 요소는 컨테이너와 같은 <xref:System.Windows.Controls.TextBlock>)를 통해 합니다 **인라인** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="a1e80-104">이 속성에서 항목 추가 및 제거 하는 <xref:System.Windows.Documents.InlineCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="a1e80-105">유동 콘텐츠 요소는 **인라인** 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="a1e80-106">이러한 예제를 사용 하 여 발생할 <xref:System.Windows.Documents.Span> 흐름 콘텐츠 요소 이지만 이러한 기술에 적용할 수 있는 모든 요소나 컨트롤을 호스팅하는 <xref:System.Windows.Documents.InlineCollection> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1e80-107">예제</span><span class="sxs-lookup"><span data-stu-id="a1e80-107">Example</span></span>  
 <span data-ttu-id="a1e80-108">다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체를 사용 하 여 다음을 **추가** 두 텍스트를 추가 하는 방법의 콘텐츠 자식으로 실행 되는 <xref:System.Windows.Documents.Span>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="a1e80-109">예제</span><span class="sxs-lookup"><span data-stu-id="a1e80-109">Example</span></span>  
 <span data-ttu-id="a1e80-110">다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소 부분에 삽입 하는 <xref:System.Windows.Documents.Span>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="a1e80-111">예제</span><span class="sxs-lookup"><span data-stu-id="a1e80-111">Example</span></span>  
 <span data-ttu-id="a1e80-112">다음 예제에서는 최상위 개수를 가져옵니다 <xref:System.Windows.Documents.Inline> 에 포함 된 요소는 <xref:System.Windows.Documents.Span>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="a1e80-113">예제</span><span class="sxs-lookup"><span data-stu-id="a1e80-113">Example</span></span>  
 <span data-ttu-id="a1e80-114">다음 예제에서는 마지막 삭제 <xref:System.Windows.Documents.Inline> 요소에는 <xref:System.Windows.Documents.Span>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="a1e80-115">예제</span><span class="sxs-lookup"><span data-stu-id="a1e80-115">Example</span></span>  
 <span data-ttu-id="a1e80-116">다음 예제에서는 모든 콘텐츠를 지웁니다 (<xref:System.Windows.Documents.Inline> 요소)에서 <xref:System.Windows.Documents.Span>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e80-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="a1e80-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1e80-117">See also</span></span>
- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="a1e80-118">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="a1e80-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
- [<span data-ttu-id="a1e80-119">Blocks 속성을 통한 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="a1e80-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="a1e80-120">Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="a1e80-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="a1e80-121">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="a1e80-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
