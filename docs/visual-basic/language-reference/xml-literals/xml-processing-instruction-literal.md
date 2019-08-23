---
title: XML 처리 명령 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: c589d3f4ac6bbb9aa9b2b8f2535888bddbf9c934
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958475"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="23d7a-102">XML 처리 명령 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23d7a-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="23d7a-103"><xref:System.Xml.Linq.XProcessingInstruction> 개체를 나타내는 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="23d7a-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="23d7a-105">요소</span><span class="sxs-lookup"><span data-stu-id="23d7a-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="23d7a-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23d7a-106">Required.</span></span> <span data-ttu-id="23d7a-107">XML 처리 명령 리터럴의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="23d7a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23d7a-108">Required.</span></span> <span data-ttu-id="23d7a-109">처리 명령이 대상으로 하는 응용 프로그램을 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="23d7a-110">"Xml" 또는 "XML"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="23d7a-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-111">Optional.</span></span> <span data-ttu-id="23d7a-112">에서 대상으로 `piName` 하는 응용 프로그램이 XML 문서를 처리 하는 방법을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="23d7a-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23d7a-113">Required.</span></span> <span data-ttu-id="23d7a-114">처리 명령의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23d7a-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="23d7a-115">Return Value</span></span>  
 <span data-ttu-id="23d7a-116"><xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d7a-117">설명</span><span class="sxs-lookup"><span data-stu-id="23d7a-117">Remarks</span></span>  
 <span data-ttu-id="23d7a-118">XML 처리 명령 리터럴은 응용 프로그램이 XML 문서를 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="23d7a-119">응용 프로그램이 XML 문서를 로드할 때 응용 프로그램은 XML 처리 명령을 확인 하 여 문서 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="23d7a-120">응용 프로그램은 및 `piName` `piData`의 의미를 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="23d7a-121">XML 문서 리터럴은 XML 처리 명령의 구문과 비슷한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="23d7a-122">자세한 내용은 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23d7a-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23d7a-123">Xml `piName` 1.0 사양에서는 이러한 식별자를 예약 하기 때문에 요소는 문자열 "xml" 또는 "xml"로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="23d7a-124">XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23d7a-125">XML 리터럴은 줄 연속 문자 없이 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="23d7a-126">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="23d7a-127">Visual Basic 컴파일러는 XML 처리 명령 리터럴을 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자에 대 한 호출로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d7a-128">예제</span><span class="sxs-lookup"><span data-stu-id="23d7a-128">Example</span></span>  
 <span data-ttu-id="23d7a-129">다음 예에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23d7a-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="23d7a-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="23d7a-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="23d7a-131">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="23d7a-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="23d7a-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="23d7a-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="23d7a-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="23d7a-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
