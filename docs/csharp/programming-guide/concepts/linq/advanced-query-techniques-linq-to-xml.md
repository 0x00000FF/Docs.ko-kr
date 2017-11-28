---
title: "고급 쿼리 기술(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 028d978e-215b-4d50-ba70-adce0659386d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5898813d5773f13fa2c969b065e5ab1412726e9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-query-techniques-linq-to-xml-c"></a><span data-ttu-id="967f6-102">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-102">Advanced Query Techniques (LINQ to XML) (C#)</span></span>
<span data-ttu-id="967f6-103">이 단원에서는 고급 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리 기법의 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="967f6-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="967f6-104">In This Section</span></span>  
  
|<span data-ttu-id="967f6-105">항목</span><span class="sxs-lookup"><span data-stu-id="967f6-105">Topic</span></span>|<span data-ttu-id="967f6-106">설명</span><span class="sxs-lookup"><span data-stu-id="967f6-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="967f6-107">방법: 두 컬렉션 조인(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-107">How to: Join Two Collections (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="967f6-108">`Join` 절을 사용하여 XML 데이터의 관계를 이용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="967f6-109">방법: 그룹화를 사용하여 계층 구조 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-109">How to: Create Hierarchy Using Grouping (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="967f6-110">데이터를 그룹화한 다음 그룹화에 따라 XML을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="967f6-111">방법: XPath를 사용하여 LINQ to XML 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-111">How to: Query LINQ to XML Using XPath (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="967f6-112">XPath 쿼리를 기반으로 컬렉션을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="967f6-113">방법: LINQ to XML 축 메서드 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-113">How to: Write a LINQ to XML Axis Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="967f6-114">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 축 메서드를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="967f6-115">방법: 텍스트를 XML로 변환 스트리밍 수행(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-115">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transformations-of-text-to-xml.md)|<span data-ttu-id="967f6-116">작은 메모리 사용 공간을 유지하면서 매우 큰 텍스트 파일을 XML로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-116">Shows how to transform very large text files into XML while maintaining a small memory footprint.</span></span>|  
|[<span data-ttu-id="967f6-117">방법: 트리의 모든 노드 나열(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-117">How to: List All Nodes in a Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="967f6-118">XML 트리의 모든 노드를 나열하는 유틸리티 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-118">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="967f6-119">이 메서드는 XML 트리를 수정하는 디버깅 코드에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-119">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="967f6-120">방법: Office Open XML 문서에서 단락 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-120">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="967f6-121">Office Open XML 문서를 열고 XElement 개체 컬렉션의 단락, 단락의 텍스트 및 단락의 스타일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-121">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="967f6-122">방법: Office Open XML 문서 수정(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-122">How to: Modify an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="967f6-123">Office Open XML 문서를 열고, 수정하고, 저장하는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-123">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="967f6-124">방법: 파일 시스템에서 XML 트리 채우기(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-124">How to: Populate an XML Tree from the File System (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="967f6-125">파일 시스템에서 XML 트리를 만드는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="967f6-125">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="967f6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="967f6-126">See Also</span></span>  
 [<span data-ttu-id="967f6-127">XML 트리 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="967f6-127">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
