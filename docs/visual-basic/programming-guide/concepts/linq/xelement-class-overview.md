---
title: "XElement 클래스 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 78a72effa021408943b9248546106c6fd655ac0b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="c29fd-102">XElement 클래스 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c29fd-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="c29fd-103"><xref:System.Xml.Linq.XElement>클래스의 기본 클래스 중 하나는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c29fd-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="c29fd-104">XML 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-104">It represents an XML element.</span></span> <span data-ttu-id="c29fd-105">이 클래스를 사용하여 요소를 만들거나, 요소의 내용을 변경하거나, 자식 요소를 추가, 변경 또는 삭제하거나, 특성을 요소에 추가하거나, 요소의 내용을 텍스트 형태로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="c29fd-106">다른 클래스와 상호 운용할 수도 있습니다 <xref:System.Xml?displayProperty=fullName>, 예: <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, 및 <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c29fd-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=fullName>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="c29fd-107">XElement 기능</span><span class="sxs-lookup"><span data-stu-id="c29fd-107">XElement Functionality</span></span>  
 <span data-ttu-id="c29fd-108">이 항목에서는 <xref:System.Xml.Linq.XElement>클래스</xref:System.Xml.Linq.XElement> 에서 제공 하는 기능 설명</span><span class="sxs-lookup"><span data-stu-id="c29fd-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="c29fd-109">XML 트리 생성</span><span class="sxs-lookup"><span data-stu-id="c29fd-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="c29fd-110">다음과 같은 다양한 방법으로 XML 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="c29fd-111">코드에서 XML 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="c29fd-112">자세한 내용은 참조 [XML 트리 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="c29fd-113">같은 다양 한 소스에서에서 XML을 구문 분석할 수는 <xref:System.IO.TextReader>, 텍스트 파일 또는 웹 주소 (URL).</xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="c29fd-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="c29fd-114">자세한 내용은 참조 [XML 구문 분석 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="c29fd-115">사용할 수는 <xref:System.Xml.XmlReader>트리를 채우는.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="c29fd-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="c29fd-116">자세한 내용은 <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c29fd-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="c29fd-117">콘텐츠를 쓸 수 있는 모듈이 있는 경우는 <xref:System.Xml.XmlWriter>를 사용할 수는 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>메서드를 만들어를 작성기는 모듈에 작성기를 전달한 다음에 기록 된 콘텐츠를 사용 하 여는 <xref:System.Xml.XmlWriter>XML 트리를 채우는.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="c29fd-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="c29fd-118">그러나 XML 트리를 만드는 가장 일반적인 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="c29fd-119">XML 트리를 만드는 또 다른 일반적인 방법에는 다음 예제에서와 같이 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리의 결과를 사용하여 XML 트리를 채우는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="c29fd-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="c29fd-121">XML 트리 serialization</span><span class="sxs-lookup"><span data-stu-id="c29fd-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="c29fd-122">XML 트리를 serialize 할 수는 <xref:System.IO.File>, <xref:System.IO.TextWriter>, 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="c29fd-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="c29fd-123">자세한 내용은 참조 [XML 트리를 직렬화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="c29fd-124">축 메서드를 통해 XML 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="c29fd-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="c29fd-125">축 메서드를 사용하여 특성, 자식 요소, 하위 요소 및 상위 요소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]<span data-ttu-id="c29fd-126"> 쿼리는 축 메서드에 대해 작동하며 XML 트리를 탐색하고 처리하는 융통성 있고 강력한 몇 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-126"> queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="c29fd-127">자세한 내용은 참조 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="c29fd-128">XML 트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="c29fd-128">Querying XML Trees</span></span>  
 <span data-ttu-id="c29fd-129">XML 트리에서 데이터를 추출하는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-129">You can write [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="c29fd-130">자세한 내용은 참조 [XML 트리 쿼리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="c29fd-131">XML 트리 수정</span><span class="sxs-lookup"><span data-stu-id="c29fd-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="c29fd-132">내용이나 특성을 변경하는 등의 다양한 방법으로 요소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="c29fd-133">또한 부모에서 요소를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="c29fd-134">자세한 내용은 참조 [XML 트리 수정 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fd-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29fd-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c29fd-135">See Also</span></span>  
 [<span data-ttu-id="c29fd-136">LINQ to XML 프로그래밍 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c29fd-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
