---
title: '방법: 특정 특성 (XPath 및 LINQ to XML)으로 요소 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 4bb38d2c-bc7c-4196-8909-aaf41fb86b28
ms.openlocfilehash: 17c5e9abf607df7311ff2552b7e9c54cbf30fd59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825341"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="154fa-102">방법: 특정 특성 (XPath 및 LINQ to XML)으로 요소 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="154fa-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="154fa-103">특정 특성을 가진 모든 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="154fa-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="154fa-104">특성의 내용에는 관심이 없으며,</span><span class="sxs-lookup"><span data-stu-id="154fa-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="154fa-105">대신 특성의 존재에 따라 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="154fa-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="154fa-106">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="154fa-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="154fa-107">예제</span><span class="sxs-lookup"><span data-stu-id="154fa-107">Example</span></span>  
 <span data-ttu-id="154fa-108">다음 코드에서는 `Select` 특성을 가진 요소만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="154fa-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```vb  
Dim doc As XElement = _   
    <Root>  
        <Child1>1</Child1>  
        <Child2 Select='true'>2</Child2>  
        <Child3>3</Child3>  
        <Child4 Select='true'>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In doc.Elements() _  
    Where el.@Select <> Nothing _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = DirectCast(doc.XPathEvaluate _  
    ("./*[@Select]"), IEnumerable).Cast(Of XElement)()  
  
If list1.Count() = list2.Count() And _  
    list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="154fa-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="154fa-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a><span data-ttu-id="154fa-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="154fa-110">See also</span></span>

- [<span data-ttu-id="154fa-111">XPath 사용자 (Visual Basic)를 위한 LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="154fa-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
