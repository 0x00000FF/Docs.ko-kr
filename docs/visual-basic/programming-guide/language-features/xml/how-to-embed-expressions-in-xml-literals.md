---
title: '방법: (Visual Basic) XML 리터럴에 식 포함'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: fba33bc177641f3fc9f67b1a82919a44d28a11cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681784"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="9e5e3-102">방법: (Visual Basic) XML 리터럴에 식 포함</span><span class="sxs-lookup"><span data-stu-id="9e5e3-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="9e5e3-103">XML 리터럴의 XML 문서, 조각 또는 런타임에 생성 하는 콘텐츠를 포함 하는 요소를 만들려면 포함 된 식으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="9e5e3-104">다음 예제에서는 포함 된 식을 사용 하 여 런타임에 콘텐츠 요소, 특성 및 요소 이름이 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="9e5e3-105">포함 식 구문은 `<%=` `exp` `%>`에 동일한 구문을 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="9e5e3-106">자세한 내용은 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="9e5e3-107">사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api를 만드는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="9e5e3-108">자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9e5e3-109">절차</span><span class="sxs-lookup"><span data-stu-id="9e5e3-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="9e5e3-110">요소 내용으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5e3-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="9e5e3-111">다음 예제에서는에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `contactName` 열기 및 닫기 이름 요소 간의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="9e5e3-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="9e5e3-113">특성 값으로 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5e3-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="9e5e3-114">다음 예제에서는에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다 합니다 `phoneType` 값으로 변수를 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="9e5e3-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="9e5e3-116">요소 이름에 대 한 텍스트를 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5e3-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="9e5e3-117">다음 예제에서는에 포함 된 텍스트를 삽입 하는 방법을 보여 줍니다는 `elementName` 요소의 이름으로 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="9e5e3-118">이 기술을 사용 하 여 요소를 만들 때를 닫아야 하는 \</ > 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="9e5e3-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5e3-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9e5e3-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e5e3-120">See also</span></span>
- [<span data-ttu-id="9e5e3-121">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="9e5e3-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="9e5e3-122">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="9e5e3-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="9e5e3-123">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="9e5e3-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="9e5e3-124">XML</span><span class="sxs-lookup"><span data-stu-id="9e5e3-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
