---
title: "XML 트리 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e86ba12b-17de-4579-81bb-66322b84cfbe
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c60746a3da6255e4c245febf55151b41186a75b7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-trees-visual-basic"></a><span data-ttu-id="9f8fc-102">XML 트리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="9f8fc-102">Creating XML Trees (Visual Basic)</span></span>
<span data-ttu-id="9f8fc-103">가장 일반적인 XML 작업 중 하나는 XML 트리를 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="9f8fc-104">이 단원에서는 XML 트리를 만드는 몇 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f8fc-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="9f8fc-105">In This Section</span></span>  
  
|<span data-ttu-id="9f8fc-106">항목</span><span class="sxs-lookup"><span data-stu-id="9f8fc-106">Topic</span></span>|<span data-ttu-id="9f8fc-107">설명</span><span class="sxs-lookup"><span data-stu-id="9f8fc-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9f8fc-108">함수 생성 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8fc-108">Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="9f8fc-109">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 함수 생성에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="9f8fc-110">함수 생성을 통해 단일 문으로 XML 트리를 모두 만들거나 일부만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="9f8fc-111">또한 XML 트리를 생성할 때 쿼리를 포함하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="9f8fc-112">Visual Basic의 XML 리터럴 소개</span><span class="sxs-lookup"><span data-stu-id="9f8fc-112">Introduction to XML Literals in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)|<span data-ttu-id="9f8fc-113">XML 리터럴을 사용하여 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 트리를 만드는 방법에 대해 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-113">Provides a quick introduction to creating trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using XML literals.</span></span> <span data-ttu-id="9f8fc-114">이 항목에는 XML 리터럴의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 설명서에 대한 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-114">This topic includes links to the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] documentation of XML literals.</span></span>|  
|[<span data-ttu-id="9f8fc-115">복제와 연결 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8fc-115">Cloning vs. Attaching (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="9f8fc-116">기존 XML 트리의 노드를 추가하는 방법(노드가 복제된 다음 추가됨)과 부모가 없는 노드를 추가하는 방법(노드가 추가되기만 함)의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-116">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="9f8fc-117">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="9f8fc-117">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="9f8fc-118">다양한 소스에서 XML의 구문을 분석하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-118">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="9f8fc-119">맨 위에 계층화 <xref:System.Xml.XmlReader>, XML을 구문 분석 하는 데 사용 됩니다.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9f8fc-119"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="9f8fc-120">방법: XmlWriter (LINQ to XML)와 XML 트리 채우기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8fc-120">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="9f8fc-121"><xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 를 사용 하 여 XML 트리를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-121">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="9f8fc-122">방법: XSD (LINQ to XML)를 사용 하 여 유효성을 검사 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8fc-122">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="9f8fc-123">XSD를 사용하여 XML 트리의 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-123">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="9f8fc-124">XElement 및 XDocument 개체의 올바른 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="9f8fc-124">Valid Content of XElement and XDocument Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects.md)|<span data-ttu-id="9f8fc-125">생성자에 전달될 수 있는 유효한 인수에 대해 설명하고 내용을 요소와 문서에 추가하는 데 사용되는 메서드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8fc-125">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f8fc-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f8fc-126">See Also</span></span>  
 [<span data-ttu-id="9f8fc-127">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f8fc-127">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
