---
title: '방법: 파일, 문자열 또는 Stream (Visual Basic)에서 XML 로드'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: b660900c1ac29e40eeed36b1e07326dfbcf69ec8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492743"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="b582a-102">방법: 파일, 문자열 또는 Stream (Visual Basic)에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="b582a-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="b582a-103">만들 수 있습니다 [XML 리터럴을](../../../../visual-basic/language-reference/xml-literals/index.md) 몇 가지 메서드를 사용 하 여 파일, 문자열 또는 스트림에 같은 외부 원본에서 콘텐츠를 사용 하 여 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="b582a-104">이러한 메서드는 다음 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="b582a-105">파일에서 XML을 로드 하지</span><span class="sxs-lookup"><span data-stu-id="b582a-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="b582a-106">와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 사용 하 여 파일에서 개체를 `Load` 메서드.</span><span class="sxs-lookup"><span data-stu-id="b582a-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="b582a-107">이 메서드는 입력으로 파일 경로, 텍스트 스트림 또는 XML 스트림을 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="b582a-108">다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 채우는 방법은 <xref:System.Xml.Linq.XDocument> 텍스트 파일에서 XML 사용 하 여 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="b582a-109">문자열에서 XML을 로드 하지</span><span class="sxs-lookup"><span data-stu-id="b582a-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="b582a-110">와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체를 문자열에서 사용할 수는 `Parse` 메서드.</span><span class="sxs-lookup"><span data-stu-id="b582a-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="b582a-111">다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> 메서드를는 <xref:System.Xml.Linq.XDocument> 문자열에서 XML 사용 하 여 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="b582a-112">스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="b582a-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="b582a-113">와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 사용할 수는 스트림에서 개체를 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b582a-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b582a-114">다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 채우는 방법은 <xref:System.Xml.Linq.XDocument> XML 스트림에서 XML 사용 하 여 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b582a-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b582a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b582a-115">See also</span></span>
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b582a-116">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="b582a-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b582a-117">XML</span><span class="sxs-lookup"><span data-stu-id="b582a-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="b582a-118">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="b582a-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
