---
title: '방법: 선택적 요소로 필터링'
ms.date: 07/20/2015
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
ms.openlocfilehash: 6db377ae30582ef010d5af467e88c52b008483ed
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78267056"
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a><span data-ttu-id="73d39-102">방법: 선택적 요소 필터링(시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="73d39-102">How to: Filter on an Optional Element (Visual Basic)</span></span>
<span data-ttu-id="73d39-103">요소가 XML 문서에 있는지 확실하지 않은 경우에도 해당 요소를 기준으로 필터링하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="73d39-104">특정 요소에 자식 요소가 없는 경우 이 요소를 기준으로 필터링하여 null 참조 예외를 트리거하지 않도록 검색을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="73d39-105">다음 예제에서는 `Child5` 요소에 `Type` 자식 요소가 없지만 쿼리가 여전히 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d39-106">예제</span><span class="sxs-lookup"><span data-stu-id="73d39-106">Example</span></span>  
 <span data-ttu-id="73d39-107">이 예제에서는 <xref:System.Xml.Linq.Extensions.Elements%2A> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```vb  
Dim root As XElement = _
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 <span data-ttu-id="73d39-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-108">This code produces the following output:</span></span>  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="73d39-109">예제</span><span class="sxs-lookup"><span data-stu-id="73d39-109">Example</span></span>  
 <span data-ttu-id="73d39-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="73d39-111">자세한 내용은 [네임스페이스 개요(LINQ에서 XML까지)(시각적 기본)를](namespaces-overview-linq-to-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73d39-111">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="73d39-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73d39-112">This code produces the following output:</span></span>  
  
```console  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="73d39-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73d39-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="73d39-114">기본 쿼리(LINQ에서 XML까지) (시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="73d39-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="73d39-115">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="73d39-115">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="73d39-116">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="73d39-116">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="73d39-117">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="73d39-117">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="73d39-118">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73d39-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="73d39-119">프로젝션 작업(시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="73d39-119">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
