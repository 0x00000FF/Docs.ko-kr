---
title: '방법: 요소 (Visual Basic)를 정렬 합니다.'
ms.date: 07/20/2015
ms.assetid: c2c09279-6c8a-482e-8e71-b1453a815052
ms.openlocfilehash: 868f3eb448393e5c06a37ab68431620638e9dc35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642092"
---
# <a name="how-to-sort-elements-visual-basic"></a><span data-ttu-id="17e94-102">방법: 요소 (Visual Basic)를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-102">How to: Sort Elements (Visual Basic)</span></span>
<span data-ttu-id="17e94-103">이 예제에서는 결과를 정렬하는 쿼리를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e94-104">예제</span><span class="sxs-lookup"><span data-stu-id="17e94-104">Example</span></span>  
 <span data-ttu-id="17e94-105">이 예제에서는 XML 문서 [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim prices As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let price = Convert.ToDecimal(el.<Price>.Value) _  
    Order By (price) _  
    Select price  
For Each el As Decimal In prices  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="17e94-106">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="17e94-107">예제</span><span class="sxs-lookup"><span data-stu-id="17e94-107">Example</span></span>  
 <span data-ttu-id="17e94-108">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="17e94-109">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-109">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="17e94-110">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스의 숫자 데이터](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim prices As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let price = Convert.ToDecimal(el.<Price>.Value) _  
            Order By (price) _  
            Select price  
        For Each el As Decimal In prices  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="17e94-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="17e94-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="17e94-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17e94-112">See Also</span></span>  
 [<span data-ttu-id="17e94-113">데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="17e94-113">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
 [<span data-ttu-id="17e94-114">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17e94-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
