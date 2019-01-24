---
title: LINQ to XML 클래스 개요 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
ms.openlocfilehash: 0b95a3f4411e20390962a2eccf28b8cfad4b8e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570124"
---
# <a name="linq-to-xml-classes-overview-visual-basic"></a><span data-ttu-id="fd65e-102">LINQ to XML 클래스 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd65e-102">LINQ to XML Classes Overview (Visual Basic)</span></span>
<span data-ttu-id="fd65e-103">이 항목에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 네임스페이스의 <xref:System.Xml.Linq> 클래스 목록을 제공하며 각 클래스에 대한 간략한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="fd65e-104">LINQ to XML 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="fd65e-105">XAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-105">XAttribute Class</span></span>  
 <span data-ttu-id="fd65e-106"><xref:System.Xml.Linq.XAttribute>는 XML 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="fd65e-107">자세한 내용 및 예제를 참조 하세요 [XAttribute 클래스 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-107">For detailed information and examples, see [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="fd65e-108">XCData 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-108">XCData Class</span></span>  
 <span data-ttu-id="fd65e-109"><xref:System.Xml.Linq.XCData>는 CDATA 텍스트 노드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="fd65e-110">XComment 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-110">XComment Class</span></span>  
 <span data-ttu-id="fd65e-111"><xref:System.Xml.Linq.XComment>는 XML 주석을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="fd65e-112">XContainer 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-112">XContainer Class</span></span>  
 <span data-ttu-id="fd65e-113"><xref:System.Xml.Linq.XContainer>는 자식 노드를 가질 수 있는 모든 노드의 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="fd65e-114">다음 클래스는 <xref:System.Xml.Linq.XContainer> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="fd65e-115">XDeclaration 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-115">XDeclaration Class</span></span>  
 <span data-ttu-id="fd65e-116"><xref:System.Xml.Linq.XDeclaration>은 XML 선언을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="fd65e-117">XML 선언은 XML 버전과 문서의 인코딩을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="fd65e-118">또한 XML 선언은 XML 문서가 독립 실행형인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="fd65e-119">XML 문서가 독립 실행형인 경우 외부 DTD나 내부 하위 집합에서 참조된 외부 매개 변수 엔터티에 외부 태그 선언이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="fd65e-120">XDocument 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-120">XDocument Class</span></span>  
 <span data-ttu-id="fd65e-121"><xref:System.Xml.Linq.XDocument>는 XML 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="fd65e-122">자세한 내용 및 예제를 참조 하세요 [XDocument 클래스 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-122">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="fd65e-123">XDocumentType 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-123">XDocumentType Class</span></span>  
 <span data-ttu-id="fd65e-124"><xref:System.Xml.Linq.XDocumentType>은 XML DTD(문서 종류 정의)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="fd65e-125">XElement 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-125">XElement Class</span></span>  
 <span data-ttu-id="fd65e-126"><xref:System.Xml.Linq.XElement>는 XML 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="fd65e-127">자세한 내용 및 예제를 참조 하세요 [XElement 클래스 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-127">For detailed information and examples, see [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="fd65e-128">XName 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-128">XName Class</span></span>  
 <span data-ttu-id="fd65e-129"><xref:System.Xml.Linq.XName>은 요소(<xref:System.Xml.Linq.XElement>)와 특성(<xref:System.Xml.Linq.XAttribute>)의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="fd65e-130">자세한 내용 및 예제를 참조 하세요 [XDocument 클래스 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-130">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="fd65e-131">은 XML 이름을 가능한 한 간단하게 만들도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-131">is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="fd65e-132">복잡성 때문에 XML 이름은 흔히 XML의 고급 항목으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="fd65e-133">거의 틀림없이 이 복잡성은 개발자가 프로그래밍에서 정기적으로 사용하는 네임스페이스 때문이 아니라 네임스페이스 접두사 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="fd65e-134">네임스페이스 접두사는 XML을 입력하거나 XML을 읽기 쉽게 만드는 데 필요한 키 입력을 줄이는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="fd65e-135">그러나 접두사는 전체 XML 네임스페이스를 사용하기 위한 바로 가기일 뿐인 경우가 많으며 대부분의 경우 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="fd65e-136">에서는 모든 접두사를 해당 XML 네임스페이스로 확인하여 XML 이름을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-136">simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="fd65e-137">접두사가 필요한 경우 <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> 메서드를 통해 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="fd65e-138">필요한 경우 네임스페이스 접두사를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="fd65e-139">경우에 따라 XSLT, XAML 등의 다른 XML 시스템으로 작업하는 경우 네임스페이스 접두사를 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="fd65e-140">예를 들어 XSLT 스타일시트에 포함된 네임스페이스 접두사를 사용하는 XPath 식이 있는 경우 XML 문서가 XPath 식에 사용된 것과 일치하는 네임스페이스 접두사로 serialize되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="fd65e-141">XNamespace 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-141">XNamespace Class</span></span>  
 <span data-ttu-id="fd65e-142"><xref:System.Xml.Linq.XNamespace>는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>의 네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="fd65e-143">네임스페이스는 <xref:System.Xml.Linq.XName>의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="fd65e-144">XNode 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-144">XNode Class</span></span>  
 <span data-ttu-id="fd65e-145"><xref:System.Xml.Linq.XNode>는 XML 트리의 노드를 나타내는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="fd65e-146">다음 클래스는 <xref:System.Xml.Linq.XNode> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="fd65e-147">XNodeDocumentOrderComparer 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="fd65e-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>는 노드의 문서 순서를 비교하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="fd65e-149">XNodeEqualityComparer 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="fd65e-150"><xref:System.Xml.Linq.XNodeEqualityComparer>는 노드의 값이 동일한지 비교하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="fd65e-151">XObject 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-151">XObject Class</span></span>  
 <span data-ttu-id="fd65e-152"><xref:System.Xml.Linq.XObject>는 <xref:System.Xml.Linq.XNode> 및 <xref:System.Xml.Linq.XAttribute>의 추상 기본 클래스이며,</span><span class="sxs-lookup"><span data-stu-id="fd65e-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="fd65e-153">주석과 이벤트 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="fd65e-154">XObjectChange 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-154">XObjectChange Class</span></span>  
 <span data-ttu-id="fd65e-155"><xref:System.Xml.Linq.XObjectChange>는 <xref:System.Xml.Linq.XObject>에 대한 이벤트가 발생할 때 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="fd65e-156">XObjectChangeEventArgs 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="fd65e-157"><xref:System.Xml.Linq.XObjectChangeEventArgs>는 <xref:System.Xml.Linq.XObject.Changing> 및 <xref:System.Xml.Linq.XObject.Changed> 이벤트에 대한 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="fd65e-158">XProcessingInstruction 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="fd65e-159"><xref:System.Xml.Linq.XProcessingInstruction>은 XML 처리 명령을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="fd65e-160">처리 명령은 XML을 처리하는 정보를 애플리케이션에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="fd65e-161">XText 클래스</span><span class="sxs-lookup"><span data-stu-id="fd65e-161">XText Class</span></span>  
 <span data-ttu-id="fd65e-162"><xref:System.Xml.Linq.XText>는 텍스트 노드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="fd65e-163">대부분의 경우 이 클래스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="fd65e-164">이 클래스는 혼합 내용에 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd65e-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd65e-165">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd65e-165">See also</span></span>
- [<span data-ttu-id="fd65e-166">LINQ to XML 프로그래밍 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd65e-166">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
