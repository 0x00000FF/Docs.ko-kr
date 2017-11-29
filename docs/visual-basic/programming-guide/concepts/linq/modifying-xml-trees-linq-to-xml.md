---
title: "XML 트리 수정 (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de66788186f3ffd09560d8eacdebbbaa5edf067c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="be958-102">XML 트리 수정 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be958-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="be958-103">은 XML 트리의 메모리 내 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="be958-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="be958-104">소스에서 XML 트리를 로드하거나 XML 트리의 구문을 분석한 후 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 통해 메모리 내 트리를 수정하고 serialize한 다음 파일에 저장하거나 원격 서버에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be958-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="be958-105">메모리 내 트리를 수정하는 경우 <xref:System.Xml.Linq.XContainer.Add%2A>와 같은 특정 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="be958-106">그러나 함수 생성을 사용하여 다른 모양의 새 트리를 생성하는 다른 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be958-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="be958-107">XML 트리에 수행해야 하는 변경 유형과 트리 크기에 따라 이 방법은 더 강력하고 개발하기 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be958-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="be958-108">이 단원의 첫 번째 항목에서는 이러한 두 방법을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be958-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="be958-109">In This Section</span></span>  
  
|<span data-ttu-id="be958-110">항목</span><span class="sxs-lookup"><span data-stu-id="be958-110">Topic</span></span>|<span data-ttu-id="be958-111">설명</span><span class="sxs-lookup"><span data-stu-id="be958-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="be958-112">메모리 내 XML 트리 수정과 함수 생성 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be958-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="be958-113">메모리 내 XML 트리 수정과 함수 생성을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="be958-114">요소, 특성 및 노드 (Visual Basic)를 XML 트리에 추가</span><span class="sxs-lookup"><span data-stu-id="be958-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="be958-115">요소, 특성 또는 노드를 XML 트리에 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="be958-116">XML 트리에서 요소, 특성 및 노드 수정</span><span class="sxs-lookup"><span data-stu-id="be958-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="be958-117">기존 요소, 특성 또는 노드를 수정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="be958-118">(Visual Basic)는 XML 트리에서 요소, 특성 및 노드 제거</span><span class="sxs-lookup"><span data-stu-id="be958-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="be958-119">XML 트리에서 요소, 특성 또는 노드를 제거하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="be958-120">이름/값 쌍 (Visual Basic) 유지 관리</span><span class="sxs-lookup"><span data-stu-id="be958-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="be958-121">이름/값 쌍으로 가장 잘 유지되는 응용 프로그램 정보(예: 구성 정보 또는 전역 설정)를 유지 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be958-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="be958-122">방법: 전체 XML 트리에 (Visual Basic)에 대 한는 Namespace를 변경</span><span class="sxs-lookup"><span data-stu-id="be958-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="be958-123">XML 트리를 한 네임스페이스에서 다른 네임스페이스로 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be958-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be958-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be958-124">See Also</span></span>  
 [<span data-ttu-id="be958-125">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be958-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
