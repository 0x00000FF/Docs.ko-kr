---
title: '방법: (XPath 및 LINQ to XML) 부모의 특성 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ded20c173063492d260aee5ba55f3c4c585bd961
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828656"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="1975f-102">방법: (XPath 및 LINQ to XML) 부모의 특성 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1975f-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="1975f-103">이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1975f-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="1975f-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1975f-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="1975f-105">예제</span><span class="sxs-lookup"><span data-stu-id="1975f-105">Example</span></span>  
 <span data-ttu-id="1975f-106">이 예제에서는 먼저 `Author` 요소를 찾은 다음</span><span class="sxs-lookup"><span data-stu-id="1975f-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="1975f-107">부모 요소의 `id` 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1975f-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="1975f-108">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1975f-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="1975f-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1975f-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="1975f-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="1975f-110">See also</span></span>

- [<span data-ttu-id="1975f-111">XPath 사용자 (Visual Basic)를 위한 LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1975f-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
