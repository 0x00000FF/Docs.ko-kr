---
title: 확장 인덱서 속성(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: a02c482db81d9d76752cfe66a292dc57c48b2acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698904"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="eee3e-102">확장 인덱서 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eee3e-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="eee3e-103">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="eee3e-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="eee3e-105">요소</span><span class="sxs-lookup"><span data-stu-id="eee3e-105">Parts</span></span>  
  
|<span data-ttu-id="eee3e-106">용어</span><span class="sxs-lookup"><span data-stu-id="eee3e-106">Term</span></span>|<span data-ttu-id="eee3e-107">정의</span><span class="sxs-lookup"><span data-stu-id="eee3e-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="eee3e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eee3e-108">Required.</span></span> <span data-ttu-id="eee3e-109">쿼리 가능 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-109">A queryable collection.</span></span> <span data-ttu-id="eee3e-110">즉, 구현 하는 컬렉션 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="eee3e-111">(</span><span class="sxs-lookup"><span data-stu-id="eee3e-111">(</span></span>|<span data-ttu-id="eee3e-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eee3e-112">Required.</span></span> <span data-ttu-id="eee3e-113">인덱서 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="eee3e-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eee3e-114">Required.</span></span> <span data-ttu-id="eee3e-115">컬렉션에 있는 요소의 0부터 시작 위치를 지정 하는 정수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="eee3e-116">)</span><span class="sxs-lookup"><span data-stu-id="eee3e-116">)</span></span>|<span data-ttu-id="eee3e-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="eee3e-117">Required.</span></span> <span data-ttu-id="eee3e-118">인덱서 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="eee3e-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="eee3e-119">Return Value</span></span>  
 <span data-ttu-id="eee3e-120">컬렉션에서 지정된 된 위치에서 개체 또는 `Nothing` 인덱스 범위를 벗어난 경우.</span><span class="sxs-lookup"><span data-stu-id="eee3e-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eee3e-121">설명</span><span class="sxs-lookup"><span data-stu-id="eee3e-121">Remarks</span></span>  
 <span data-ttu-id="eee3e-122">컬렉션의 개별 요소에 액세스 하는 확장명 인덱서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="eee3e-123">이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="eee3e-124">XML 자식 및 XML 하위 축 속성의 컬렉션을 반환 합니다. <xref:System.Xml.Linq.XElement> 개체 또는 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="eee3e-125">Visual Basic 컴파일러에 대 한 호출을 확장명 인덱서 속성을 변환 합니다 `ElementAtOrDefault` 메서드.</span><span class="sxs-lookup"><span data-stu-id="eee3e-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="eee3e-126">배열 인덱서 달리 합니다 `ElementAtOrDefault` 메서드가 반환 되는 `Nothing` 인덱스 범위를 벗어난 경우.</span><span class="sxs-lookup"><span data-stu-id="eee3e-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="eee3e-127">이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="eee3e-128">이 인덱서 속성을 구현 하는 컬렉션에 대 한 확장 속성 비슷합니다 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>: 기본 속성 또는 인덱서는 컬렉션에 없는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="eee3e-129">컬렉션의 첫 번째 요소의 값에 액세스 하려면 <xref:System.Xml.Linq.XElement> 나 <xref:System.Xml.Linq.XAttribute> 개체를 XML을 사용할 수 있습니다 `Value` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="eee3e-130">자세한 내용은 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eee3e-131">예제</span><span class="sxs-lookup"><span data-stu-id="eee3e-131">Example</span></span>  
 <span data-ttu-id="eee3e-132">다음 예제에서는 컬렉션의 두 번째 자식 노드에 액세스 하려면 확장명 인덱서를 사용 하는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="eee3e-133">이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용 하 여 해당 컬렉션에 액세스 `phone` 에 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="eee3e-134">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3e-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="eee3e-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="eee3e-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="eee3e-136">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="eee3e-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="eee3e-137">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="eee3e-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="eee3e-138">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="eee3e-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="eee3e-139">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="eee3e-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
