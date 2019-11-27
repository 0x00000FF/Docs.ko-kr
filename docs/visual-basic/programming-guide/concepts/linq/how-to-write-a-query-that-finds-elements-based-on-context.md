---
title: '방법: 컨텍스트에 따라 요소를 찾는 쿼리 작성'
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: d25c6d47eee2ae092c84c3db3c08c3e21e7d98d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346212"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="d9adb-102">방법: 컨텍스트에 따라 요소를 찾는 쿼리 작성 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9adb-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="d9adb-103">컨텍스트에 따라 요소를 선택하는 쿼리를 작성해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="d9adb-104">이전 또는 다음 형제 요소를 기준으로 필터링하거나,</span><span class="sxs-lookup"><span data-stu-id="d9adb-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="d9adb-105">자식 또는 상위 요소를 기준으로 필터링하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="d9adb-106">쿼리를 작성하고 `where` 절에서 쿼리의 결과를 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="d9adb-107">먼저 null에 대해 테스트하고 값을 테스트해야 하는 경우에는 `let` 절에서 쿼리를 수행한 다음 `where` 절에서 결과를 사용하는 것이 더 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9adb-108">예제</span><span class="sxs-lookup"><span data-stu-id="d9adb-108">Example</span></span>  
 <span data-ttu-id="d9adb-109">다음 예제에서는 `p` 요소 바로 이전에 있는 모든 `ul` 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
```  
  
 <span data-ttu-id="d9adb-110">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-110">This code produces the following output:</span></span>  
  
```console  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="d9adb-111">예제</span><span class="sxs-lookup"><span data-stu-id="d9adb-111">Example</span></span>  
 <span data-ttu-id="d9adb-112">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d9adb-113">자세한 내용은 [네임 스페이스 개요 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9adb-113">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d9adb-114">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9adb-114">This code produces the following output:</span></span>  
  
```console  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9adb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9adb-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
- [<span data-ttu-id="d9adb-116">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9adb-116">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
