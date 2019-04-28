---
title: XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: c557230d1ae350d5f542b79a2c210ce5ce3f73fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786817"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="66f9c-102">XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66f9c-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="66f9c-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 <xref:System.Xml?displayProperty=nameWithType> 상호 운용성 기능을 사용할 때 <xref:System.Xml.Linq.XNode.CreateReader%2A>를 사용하여 <xref:System.Xml.XmlReader>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="66f9c-104">만들어진 <xref:System.Xml.XmlReader>에서 읽는 모듈은 XML 트리에서 노드를 읽고 적절하게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="66f9c-105">XSLT 변환 호출</span><span class="sxs-lookup"><span data-stu-id="66f9c-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="66f9c-106">이 메서드를 사용할 수 있는 한 가지 경우는 XSLT 변환을 호출할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="66f9c-107">XML 트리를 만들고 XML 트리에서 <xref:System.Xml.XmlReader>를 만든 다음 새 문서를 만들고 새 문서에 쓸 <xref:System.Xml.XmlWriter>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="66f9c-108">그런 다음 XSLT 변형을 호출하여 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="66f9c-109">변환이 성공적으로 완료된 후 새 XML 트리가 변환의 결과로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
        <xsl:template match='/Parent'>  
            <Root>  
                <C1>  
                    <xsl:value-of select='Child1'/>  
                </C1>  
                <C2>  
                    <xsl:value-of select='Child2'/>  
                </C2>  
            </Root>  
        </xsl:template>  
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="66f9c-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="66f9c-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66f9c-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="66f9c-111">See also</span></span>

- [<span data-ttu-id="66f9c-112">직렬화 XML 트리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66f9c-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
