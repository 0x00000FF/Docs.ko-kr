---
title: '방법: 컨텍스트 (Visual Basic)를 기반으로 하는 요소를 찾는 쿼리 작성'
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: 0981da1e35f2c0b6023c009d4f62c95a612d8971
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814265"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a>방법: 컨텍스트 (Visual Basic)를 기반으로 하는 요소를 찾는 쿼리 작성
컨텍스트에 따라 요소를 선택하는 쿼리를 작성해야 하는 경우가 있습니다. 이전 또는 다음 형제 요소를 기준으로 필터링하거나, 자식 또는 상위 요소를 기준으로 필터링하려고 할 수 있습니다.  
  
 쿼리를 작성하고 `where` 절에서 쿼리의 결과를 사용하여 이를 수행할 수 있습니다. 먼저 null에 대해 테스트하고 값을 테스트해야 하는 경우에는 `let` 절에서 쿼리를 수행한 다음 `where` 절에서 결과를 사용하는 것이 더 편리합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `p` 요소 바로 이전에 있는 모든 `ul` 요소를 선택합니다.  
  
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
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
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
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
- [기본 쿼리 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
