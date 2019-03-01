---
title: '방법: XML 리터럴 (Visual Basic)를 수정 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 6e11c1ed4cfe4edc1c88dbbff2e9f555b1a028c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974720"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="6bbad-102">방법: XML 리터럴 (Visual Basic)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-102">How to: Modify XML Literals (Visual Basic)</span></span>
<span data-ttu-id="6bbad-103">Visual Basic XML 리터럴 수정 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="6bbad-104">추가 및 요소 및 특성을 삭제할 수도 있고, 새 XML 요소를 사용 하 여 기존 요소를 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="6bbad-105">이 항목에서는 기존 XML 리터럴 수정 하는 방법의 몇 가지 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="6bbad-106">XML 리터럴의 값을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="6bbad-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="6bbad-107">XML 리터럴의 값을 수정 하려면 XML 리터럴 및 설정에 대 한 참조를 가져올는 `Value` 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="6bbad-108">모든 값을 업데이트 하는 다음 코드 예제는 \<가격 > XML 문서의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]  
  
     <span data-ttu-id="6bbad-109">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-109">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6bbad-110">`Value` 속성 컬렉션의 첫 번째 XML 요소를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-110">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="6bbad-111">컬렉션에 동일한 이름을 가진 요소가 둘 이상 있으면 설정 된 `Value` 속성 컬렉션의 첫 번째 요소에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-111">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="6bbad-112">XML 리터럴에서 특성을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6bbad-112">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="6bbad-113">리터럴 xml 특성을 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-113">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="6bbad-114">그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-114">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="6bbad-115">새 추가할 수도 있습니다 <xref:System.Xml.Linq.XAttribute> 개체를 사용 하 여 리터럴 XML <xref:System.Xml.Linq.XContainer.Add%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-115">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="6bbad-116">다음 예제에서는 두 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-116">The following example shows both options.</span></span>  
  
     [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]  
  
     <span data-ttu-id="6bbad-117">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-117">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     <span data-ttu-id="6bbad-118">XML 특성 축 속성에 대 한 자세한 내용은 참조 하세요. [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-118">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="6bbad-119">XML 리터럴에서 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6bbad-119">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="6bbad-120">XML 리터럴 요소에 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-120">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="6bbad-121">추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement> 개체를 사용 하 여 요소의 마지막 하위 요소로 <xref:System.Xml.Linq.XContainer.Add%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-121">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="6bbad-122">새 추가할 수 있습니다 <xref:System.Xml.Linq.XElement> 개체를 사용 하 여 첫 번째 하위 요소로 <xref:System.Xml.Linq.XContainer.AddFirst%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-122">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="6bbad-123">다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 한 하위 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-123">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="6bbad-124">추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement> 개체를 사용 하 여 인접 한 하위 요소 앞의 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-124">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="6bbad-125">새 추가할 수도 있습니다 <xref:System.Xml.Linq.XElement> 개체를 사용 하 여 인접 한 하위 요소 뒤의 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-125">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="6bbad-126">다음 예제에서는 각이 방법을의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-126">The following example shows examples of each of these techniques.</span></span>  
  
     [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]  
  
     <span data-ttu-id="6bbad-127">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-127">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="6bbad-128">XML 리터럴 요소 또는 특성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6bbad-128">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="6bbad-129">XML 리터럴에서 요소 또는 특성을 제거 하 여 요소 또는 특성 및 호출에 대 한 참조를 가져올는 `Remove` 메서드를 다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-129">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]  
  
     <span data-ttu-id="6bbad-130">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book></Catalog>  
    ```  
  
     <span data-ttu-id="6bbad-131">제거할 모든 요소나 특성에서 XML 리터럴의 xml 리터럴에 대 한 참조를 가져오고 호출을 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6bbad-131">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="6bbad-132">XML 리터럴 수정</span><span class="sxs-lookup"><span data-stu-id="6bbad-132">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="6bbad-133">XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-133">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="6bbad-134">만들 수 있습니다 새 <xref:System.Xml.Linq.XElement> 새 이름을 지정 하 고 새 전달 된 개체 <xref:System.Xml.Linq.XElement> 개체를 <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 기존 메서드의 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-134">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="6bbad-135">대체 하는 요소에 유지 해야 하는 하위 요소가 있으면 새 값을 설정 <xref:System.Xml.Linq.XElement> 개체는 <xref:System.Xml.Linq.XContainer.Nodes%2A> 기존 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-135">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="6bbad-136">기존 요소의 내부 XML을 새 요소의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-136">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="6bbad-137">새 요소의 값을 설정할 수이 고, 그렇지는 `Value` 기존 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-137">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="6bbad-138">다음 코드 예제에서는 모든 바꿉니다 \<설명 > 요소는 \<추상 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-138">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="6bbad-139">내용의 \<설명 > 요소는 새 유지 \<추상 > 요소를 사용 하 여를 <xref:System.Xml.Linq.XContainer.Nodes%2A> 의 속성을 \<설명 > <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-139">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]  
  
     <span data-ttu-id="6bbad-140">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbad-140">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6bbad-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="6bbad-141">See also</span></span>
- [<span data-ttu-id="6bbad-142">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="6bbad-142">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="6bbad-143">XML</span><span class="sxs-lookup"><span data-stu-id="6bbad-143">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="6bbad-144">방법: 파일, 문자열 또는 Stream에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="6bbad-144">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="6bbad-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="6bbad-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="6bbad-146">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="6bbad-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
