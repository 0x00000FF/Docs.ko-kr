---
title: XML 문서 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 09ab9d0bf3feeea70ddbc094183406a6fd646c1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690516"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="79814-102">XML 문서 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79814-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="79814-103">리터럴 나타내는 <xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79814-104">구문</span><span class="sxs-lookup"><span data-stu-id="79814-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="79814-105">요소</span><span class="sxs-lookup"><span data-stu-id="79814-105">Parts</span></span>  
  
|<span data-ttu-id="79814-106">용어</span><span class="sxs-lookup"><span data-stu-id="79814-106">Term</span></span>|<span data-ttu-id="79814-107">정의</span><span class="sxs-lookup"><span data-stu-id="79814-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="79814-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-108">Optional.</span></span> <span data-ttu-id="79814-109">리터럴 텍스트 문서의 인코딩을 선언 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79814-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="79814-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-110">Optional.</span></span> <span data-ttu-id="79814-111">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-111">Literal text.</span></span> <span data-ttu-id="79814-112">"Yes" 여야 합니다 또는 "no"입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="79814-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-113">Optional.</span></span> <span data-ttu-id="79814-114">XML 처리 명령 및 XML 주석 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="79814-115">다음 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="79814-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="79814-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="79814-117">각 `piComment` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="79814-118">-   [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="79814-119">-   [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="79814-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="79814-120">Required.</span></span> <span data-ttu-id="79814-121">문서의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-121">Root element of the document.</span></span> <span data-ttu-id="79814-122">형식에는 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="79814-123">[XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="79814-124">포함 식 형식의 `<%=` `elementExp` `%>`합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="79814-125">`elementExp` 다음 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="79814-126"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="79814-127">하나를 포함 하는 컬렉션 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 고 <xref:System.Xml.Linq.XComment> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="79814-128">자세한 내용은 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79814-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="79814-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="79814-129">Return Value</span></span>  
 <span data-ttu-id="79814-130"><xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79814-131">설명</span><span class="sxs-lookup"><span data-stu-id="79814-131">Remarks</span></span>  
 <span data-ttu-id="79814-132">XML 문서 리터럴에 리터럴의 시작 XML 선언에 의해 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79814-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="79814-133">각 XML 문서 리터럴에 루트 XML 요소가 하나만 있어야, 있지만 원하는 수의 XML 처리 명령과 XML 주석에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="79814-134">XML 문서 리터럴에 XML 요소에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79814-135">XML 리터럴을 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="79814-136">이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79814-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="79814-137">리터럴 XML 문서에 대 한 호출으로 변환 하는 Visual Basic 컴파일러는 <xref:System.Xml.Linq.XDocument.%23ctor%2A> 고 <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="79814-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79814-138">예제</span><span class="sxs-lookup"><span data-stu-id="79814-138">Example</span></span>  
 <span data-ttu-id="79814-139">다음 예제에서는 XML 선언, 처리 명령, 주석 및 다른 요소를 포함 하는 요소에는 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79814-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="79814-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="79814-140">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="79814-141">XML 처리 명령 리터럴</span><span class="sxs-lookup"><span data-stu-id="79814-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="79814-142">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="79814-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="79814-143">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="79814-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="79814-144">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="79814-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="79814-145">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="79814-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="79814-146">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="79814-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
