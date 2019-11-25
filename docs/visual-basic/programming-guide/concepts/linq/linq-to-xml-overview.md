---
title: LINQ to XML 개요
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: ef3fca844dc98440eb4816110a5a78482cfa4f4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346791"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="56d13-102">LINQ to XML Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56d13-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="56d13-103">XML은 다양한 컨텍스트에서 데이터의 형식을 지정하는 방법으로 널리 채택되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="56d13-104">예를 들어, 웹에 있는 구성 파일, Microsoft Office Word 파일 및 데이터베이스에서 XML을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="56d13-105">은 XML을 사용한 프로그래밍을 위해 다시 디자인된 최신 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-105">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="56d13-106">LINQ to XML은 DOM(문서 개체 모델)의 메모리 내 문서 수정 기능을 제공하며 .[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="56d13-107">이러한 쿼리 식은 구문적으로 XPath와 다르지만 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="56d13-108">LINQ to XML 개발자</span><span class="sxs-lookup"><span data-stu-id="56d13-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="56d13-109">은 다양한 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-109">targets a variety of developers.</span></span> <span data-ttu-id="56d13-110">특정 작업을 수행하려는 일반 개발자의 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 SQL과 유사한 쿼리 경험을 제공하므로 XML을 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="56d13-111">프로그래머는 약간의 시간만 투자해도 원하는 프로그래밍 언어로 간결하고 강력한 쿼리를 작성하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="56d13-112">전문 개발자는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 생산성을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="56d13-113">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 통해 더욱 표현성이 크고 압축적이며 강력한 코드를 더 적게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="56d13-114">이와 동시에 여러 데이터 도메인에서 쿼리 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="56d13-115">LINQ to XML이란?</span><span class="sxs-lookup"><span data-stu-id="56d13-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="56d13-116">는 LINQ를 사용할 수 있는 메모리 내 XML 프로그래밍 인터페이스로, .NET Framework 프로그래밍 언어에서 XML 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="56d13-117">은 XML 문서를 메모리로 가져온다는 점에서 DOM(문서 개체 모델)과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="56d13-118">문서를 쿼리하고 수정할 수 있으며 문서를 수정한 후 파일에 저장하거나 serialize하고 네트워크를 통해 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="56d13-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56d13-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="56d13-120">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 가장 중요한 이점은 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]와 통합되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="56d13-121">이 통합을 통해 메모리 내 XML 문서에 대한 쿼리를 작성하여 요소와 특성의 컬렉션을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="56d13-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 쿼리 기능은 기능 면에서(구문 면에서는 아니지만) XPath 및 XQuery와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="56d13-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span><span class="sxs-lookup"><span data-stu-id="56d13-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="56d13-124">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 또 다른 이점은 쿼리 결과를 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XAttribute> 개체 생성자에 대한 매개 변수로 사용할 수 있다는 점입니다. 이러한 이점은 XML 트리를 만드는 강력한 방법의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="56d13-125">개발자는 *함수 생성*이라는 이 방법을 사용하여 XML 트리의 모양을 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="56d13-126">예를 들어 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)에 설명된 것과 같은 일반적인 XML 구매 주문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="56d13-127">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 다음 쿼리를 실행하면 구매 주문의 모든 품목 요소에 대한 부품 번호 특성 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="56d13-128">또 다른 예로, $100보다 큰 값을 가진 품목의 목록을 부품 번호 순서로 정렬하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="56d13-129">이 정보를 얻으려면 다음 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="56d13-130">이러한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 기능 외에도 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 향상된 XML 프로그래밍 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-130">In addition to these [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="56d13-131">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
- <span data-ttu-id="56d13-132">파일이나 스트림에서 XML을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-132">Load XML from files or streams.</span></span>  
  
- <span data-ttu-id="56d13-133">파일이나 스트림에서 XML을 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-133">Serialize XML to files or streams.</span></span>  
  
- <span data-ttu-id="56d13-134">함수 생성을 사용하여 XML을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-134">Create XML from scratch by using functional construction.</span></span>  
  
- <span data-ttu-id="56d13-135">XPath와 같은 축을 사용하여 XML을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-135">Query XML using XPath-like axes.</span></span>  
  
- <span data-ttu-id="56d13-136"><xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 및 <xref:System.Xml.Linq.XElement.SetValue%2A>와 같은 메서드를 사용하여 메모리 내 XML 트리를 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
- <span data-ttu-id="56d13-137">XSD를 사용하여 XML 트리의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-137">Validate XML trees using XSD.</span></span>  
  
- <span data-ttu-id="56d13-138">이러한 기능을 함께 사용하여 XML 트리의 모양을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="56d13-139">XML 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="56d13-139">Creating XML Trees</span></span>  
 <span data-ttu-id="56d13-140">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 프로그래밍하는 경우의 가장 중요한 이점 중 하나는 XML 트리를 쉽게 만들 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="56d13-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="56d13-141">For example, to create a small XML tree, you can write  code as follows:</span><span class="sxs-lookup"><span data-stu-id="56d13-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="56d13-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span><span class="sxs-lookup"><span data-stu-id="56d13-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="56d13-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="56d13-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d13-144">참조</span><span class="sxs-lookup"><span data-stu-id="56d13-144">See also</span></span>

- <xref:System.Xml.Linq>
- [<span data-ttu-id="56d13-145">시작(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="56d13-145">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [<span data-ttu-id="56d13-146">Visual Basic의 LINQ to XML 개요</span><span class="sxs-lookup"><span data-stu-id="56d13-146">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [<span data-ttu-id="56d13-147">XML</span><span class="sxs-lookup"><span data-stu-id="56d13-147">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
