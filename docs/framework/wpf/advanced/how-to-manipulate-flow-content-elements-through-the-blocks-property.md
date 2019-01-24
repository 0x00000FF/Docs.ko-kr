---
title: '방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: ea664409073fc342d5f988f9d2af0df9b6b0af16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521948"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="76f47-102">방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작</span><span class="sxs-lookup"><span data-stu-id="76f47-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="76f47-103">이러한 예제를 보여 줍니다을 통한 유동 콘텐츠 요소에서 수행할 수 있는 보다 일반적인 작업 중 일부는 **블록** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="76f47-104">이 속성에서 항목 추가 및 제거 하는 <xref:System.Windows.Documents.BlockCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="76f47-105">유동 콘텐츠 요소를 **블록** 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="76f47-106">이 예제에서 사용 하 여 오류가 발생 <xref:System.Windows.Documents.Section> 흐름 콘텐츠 요소 하지만 이러한 방법은 유동 콘텐츠 요소 컬렉션을 호스트 하는 모든 요소에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76f47-107">예제</span><span class="sxs-lookup"><span data-stu-id="76f47-107">Example</span></span>  
 <span data-ttu-id="76f47-108">다음 예제에서는 새 <xref:System.Windows.Documents.Section> 를 사용 하 여는 **추가** 새 단락을 추가 하는 방법의 **섹션** 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="76f47-109">예제</span><span class="sxs-lookup"><span data-stu-id="76f47-109">Example</span></span>  
 <span data-ttu-id="76f47-110">다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소 부분에 삽입 하는 <xref:System.Windows.Documents.Section>합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="76f47-111">예제</span><span class="sxs-lookup"><span data-stu-id="76f47-111">Example</span></span>  
 <span data-ttu-id="76f47-112">다음 예제에서는 최상위 개수를 가져옵니다 <xref:System.Windows.Documents.Block> 에 포함 된 요소는 <xref:System.Windows.Documents.Section>합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="76f47-113">예제</span><span class="sxs-lookup"><span data-stu-id="76f47-113">Example</span></span>  
 <span data-ttu-id="76f47-114">다음 예제에서는 마지막 삭제 <xref:System.Windows.Documents.Block> 요소에는 <xref:System.Windows.Documents.Section>합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="76f47-115">예제</span><span class="sxs-lookup"><span data-stu-id="76f47-115">Example</span></span>  
 <span data-ttu-id="76f47-116">다음 예제에서는 모든 콘텐츠를 지웁니다 (<xref:System.Windows.Documents.Block> 요소)에서 <xref:System.Windows.Documents.Section>합니다.</span><span class="sxs-lookup"><span data-stu-id="76f47-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="76f47-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="76f47-117">See also</span></span>
- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="76f47-118">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="76f47-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
- [<span data-ttu-id="76f47-119">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="76f47-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="76f47-120">Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="76f47-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="76f47-121">RowGroups 속성을 통한 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="76f47-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
