---
title: '방법: 자식 요소의 하위 항목 찾기 (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a958af40-f754-4409-85f9-7746978d4cb3
ms.openlocfilehash: e5f92e645a06a93cee95d439fc858d82ebb6b240
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291677"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="4149e-102">방법: 자식 요소의 하위 항목 찾기 (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4149e-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4149e-103">이 항목에서는 특정 이름을 가진 자식 요소의 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="4149e-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="4149e-105">예제</span><span class="sxs-lookup"><span data-stu-id="4149e-105">Example</span></span>  
 <span data-ttu-id="4149e-106">이 예제에서는 워드 프로세서 문서의 XML 표현에서 텍스트를 추출하는 경우의 문제를 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="4149e-107">먼저 모든 `Paragraph` 요소를 선택한 다음 각 `Text` 요소의 모든 `Paragraph` 하위 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="4149e-108">`Text` 요소의 하위 `Comment` 요소는 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Paragraph>  
            <Text>This is the start of</Text>  
        </Paragraph>  
        <Comment>  
            <Text>This comment is not part of the paragraph text.</Text>  
        </Comment>  
        <Paragraph>  
            <Annotation Emphasis='true'>  
                <Text> a sentence.</Text>  
            </Annotation>  
        </Paragraph>  
        <Paragraph>  
            <Text>This is a second sentence.</Text>  
        </Paragraph>  
    </Root>  
  
' LINQ to XML query  
Dim str1 As String = _  
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _  
    Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
' XPath expression  
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _  
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _  
    .Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
If str1 = str2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(str2)  
```  
  
 <span data-ttu-id="4149e-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4149e-109">This example produces the following output:</span></span>  
  
```console  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="4149e-110">참조</span><span class="sxs-lookup"><span data-stu-id="4149e-110">See also</span></span>

- [<span data-ttu-id="4149e-111">XPath 사용자에 대 한 LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4149e-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
