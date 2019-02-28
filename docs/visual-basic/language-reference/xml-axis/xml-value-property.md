---
title: XML Value 속성(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 7cf1dbb1d9dafa9c690b4043da5a6f36469e8d7a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965347"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="e8cc6-102">XML Value 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8cc6-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="e8cc6-103">컬렉션의 첫 번째 요소의 값에 대 한 액세스를 제공 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8cc6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8cc6-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="e8cc6-105">요소</span><span class="sxs-lookup"><span data-stu-id="e8cc6-105">Parts</span></span>  
  
|<span data-ttu-id="e8cc6-106">용어</span><span class="sxs-lookup"><span data-stu-id="e8cc6-106">Term</span></span>|<span data-ttu-id="e8cc6-107">정의</span><span class="sxs-lookup"><span data-stu-id="e8cc6-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="e8cc6-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-108">Required.</span></span> <span data-ttu-id="e8cc6-109"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="e8cc6-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e8cc6-110">Return Value</span></span>  
 <span data-ttu-id="e8cc6-111">A `String` 컬렉션의 첫 번째 요소의 값이 포함 된 또는 `Nothing` 컬렉션이 비어 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8cc6-112">설명</span><span class="sxs-lookup"><span data-stu-id="e8cc6-112">Remarks</span></span>  
 <span data-ttu-id="e8cc6-113">합니다 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용 하면 컬렉션의 첫 번째 요소의 값에 액세스 하려면 쉽게 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e8cc6-114">이 속성은 먼저 컬렉션 개체를 하나 이상 포함 되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="e8cc6-115">이 속성을 반환 하는 경우 컬렉션은 비어, `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="e8cc6-116">이 속성의 값을 반환 하는 고, 그렇지는 <xref:System.Xml.Linq.XElement.Value%2A> 속성 컬렉션의 첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8cc6-117">사용 하 여 XML 특성의 값에 액세스할 때의 '\@' 식별자 특성 값으로 반환 됩니다는 `String` 명시적으로 지정할 필요가 없습니다를 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="e8cc6-118">컬렉션의 다른 요소에 액세스 하려면 XML 확장명 인덱서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="e8cc6-119">자세한 내용은 [확장명 인덱서 속성](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="e8cc6-120">상속</span><span class="sxs-lookup"><span data-stu-id="e8cc6-120">Inheritance</span></span>  
 <span data-ttu-id="e8cc6-121">대부분의 사용자를 구현 하지 않아도 됩니다 <xref:System.Collections.Generic.IEnumerable%601>, 및이 섹션을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="e8cc6-122">합니다 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 구현 하는 형식에 대 한 확장 속성은 `IEnumerable(Of XElement)`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="e8cc6-123">이 확장 속성의 바인딩 확장 메서드 바인딩 비슷합니다: 속성에 확장 속성을 통해 우선 순위를이 형식 인터페이스 중 하나를 구현 하 이름이 "Value" 속성을 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="e8cc6-124">즉,이 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 구현 하는 클래스의 새 속성을 정의 하 여 재정의할 수 있습니다 `IEnumerable(Of XElement)`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8cc6-125">예제</span><span class="sxs-lookup"><span data-stu-id="e8cc6-125">Example</span></span>  
 <span data-ttu-id="e8cc6-126">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Xml.Linq.XElement.Value%2A> 컬렉션의 첫 번째 노드에 액세스 하는 속성 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e8cc6-127">이 예제에서는 자식 축 속성을 사용 하 여 라는 모든 자식 노드의 컬렉션을 가져옵니다 `phone` 에 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="e8cc6-128">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="e8cc6-129">예제</span><span class="sxs-lookup"><span data-stu-id="e8cc6-129">Example</span></span>  
 <span data-ttu-id="e8cc6-130">다음 예제에는 컬렉션에서 XML 특성의 값을 가져오는 방법을 보여 줍니다 <xref:System.Xml.Linq.XAttribute> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="e8cc6-131">이 예제에서는 값을 표시할 특성 축 속성을 사용 합니다 `type` 특성의 모든는 `phone` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="e8cc6-132">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cc6-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="e8cc6-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8cc6-133">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="e8cc6-134">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="e8cc6-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="e8cc6-135">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="e8cc6-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e8cc6-136">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="e8cc6-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="e8cc6-137">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="e8cc6-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="e8cc6-138">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="e8cc6-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="e8cc6-139">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="e8cc6-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="e8cc6-140">XML Attribute 축 속성</span><span class="sxs-lookup"><span data-stu-id="e8cc6-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
