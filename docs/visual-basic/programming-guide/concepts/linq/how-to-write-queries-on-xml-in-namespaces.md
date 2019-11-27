---
title: '방법: 네임스페이스에서 XML로 쿼리 작성'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 496cf8daf5136e8aafff000312bbd730a5152e9f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344468"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="e8bc0-102">방법: 네임 스페이스에서 XML로 쿼리 작성 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8bc0-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="e8bc0-103">네임스페이스에 있는 XML에 대한 쿼리를 작성하려면 올바른 네임스페이스를 가진 <xref:System.Xml.Linq.XName> 개체를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="e8bc0-104">Visual Basic을 사용하는 경우 가장 일반적인 방법은 전역 네임스페이스를 정의한 다음 전역 네임스페이스를 사용하는 XML 속성과 XML 리터럴을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="e8bc0-105">XML 리터럴의 case 요소가 기본적으로 네임스페이스에 있는 전역 기본 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="e8bc0-106">또는 접두사를 사용하여 전역 네임스페이스를 정의한 다음 필요한 경우 XML 리터럴과 XML 속성에서 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="e8bc0-107">XML의 다른 형태와 마찬가지로 기본적으로 특성은 항상 네임스페이스에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="e8bc0-108">이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스에 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="e8bc0-109">두 번째 예제 집합에서는 접두사가 포함된 네임스페이스에 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8bc0-110">예제</span><span class="sxs-lookup"><span data-stu-id="e8bc0-110">Example</span></span>  
 <span data-ttu-id="e8bc0-111">다음 예제에서는 기본 네임스페이스에 있는 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="e8bc0-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="e8bc0-112">요소의 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e8bc0-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-113">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="e8bc0-114">예제</span><span class="sxs-lookup"><span data-stu-id="e8bc0-114">Example</span></span>  
 <span data-ttu-id="e8bc0-115">그러나 Visual Basic의 경우에는 접두사가 포함된 네임스페이스를 사용하는 XML 트리에 쿼리를 작성하는 방법과 기본 네임스페이스를 사용하는 XML 트리에 쿼리를 작성하는 방법이 상당히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="e8bc0-116">일반적으로 `Imports` 문을 사용하여 접두사가 포함된 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="e8bc0-117">그런 다음 XML 트리를 생성할 때 요소 및 특성 이름에 해당 접두사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="e8bc0-118">또한 XML 속성을 사용하여 XML 트리를 쿼리할 때도 접두사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="e8bc0-119">다음 예제에서는 접두사가 포함된 네임스페이스에 있는 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="e8bc0-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="e8bc0-120">요소의 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e8bc0-121">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bc0-121">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8bc0-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8bc0-122">See also</span></span>

- [<span data-ttu-id="e8bc0-123">네임 스페이스 개요 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8bc0-123">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
