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
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-visual-basic"></a>방법: 특정 특성 (XPath 및 LINQ to XML)으로 요소 찾기 (Visual Basic)
특정 특성을 가진 모든 요소를 찾으려는 경우가 있습니다. 특성의 내용에는 관심이 없으며, 대신 특성의 존재에 따라 선택하려고 합니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `./*[@Select]`  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Select` 특성을 가진 요소만 선택합니다.  
  
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
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a>참고자료

- [XPath 사용자 (Visual Basic)를 위한 LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
