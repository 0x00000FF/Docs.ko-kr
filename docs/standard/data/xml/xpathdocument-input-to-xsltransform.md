---
title: XslTransform에 대한 XPathDocument 입력
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c7c8f6739fc5132af2c8cf1af2c111d51565db0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923296"
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="f73c1-102">XslTransform에 대한 XPathDocument 입력</span><span class="sxs-lookup"><span data-stu-id="f73c1-102">XPathDocument Input to XslTransform</span></span>
<span data-ttu-id="f73c1-103"><xref:System.Xml.XPath.XPathDocument>는 <xref:System.Xml.Xsl.XslTransform>을 사용하여 문서를 처리하기 위한 읽기 전용 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="f73c1-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="f73c1-104">이 캐시는 XML DOM(문서 개체 모델)과 구조상 유사하지만 <xref:System.Xml.XPath.XPathNavigator>의 XPath 최적화 함수를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 처리와 XPath(XML Path Language) 데이터 모델에 대해 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f73c1-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f73c1-105"><xref:System.Xml.Xsl.XslTransform> 클래스는 .NET Framework 2.0에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f73c1-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="f73c1-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f73c1-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="f73c1-107">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f73c1-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="f73c1-108">다음 코드 샘플에서는 변환에 대한 입력으로 <xref:System.Xml.XPath.XPathDocument>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f73c1-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f73c1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f73c1-109">See also</span></span>

- [<span data-ttu-id="f73c1-110">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="f73c1-110">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
