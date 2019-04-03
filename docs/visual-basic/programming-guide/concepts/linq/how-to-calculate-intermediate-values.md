---
title: '방법: 중간 값 (Visual Basic)를 계산 합니다.'
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: cb619784d487ae12b1fb8bb3adc97acb0f767455
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827044"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="c3d39-102">방법: 중간 값 (Visual Basic)를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="c3d39-103">이 예제에서는 정렬, 필터링 및 선택에 사용할 수 있는 중간 값을 계산하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d39-104">예제</span><span class="sxs-lookup"><span data-stu-id="c3d39-104">Example</span></span>  
 <span data-ttu-id="c3d39-105">다음 예제에서는 `Let` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="c3d39-106">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c3d39-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="c3d39-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="c3d39-108">예제</span><span class="sxs-lookup"><span data-stu-id="c3d39-108">Example</span></span>  
 <span data-ttu-id="c3d39-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c3d39-110">자세한 내용은 [XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="c3d39-111">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스의 숫자 데이터](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c3d39-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c3d39-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d39-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d39-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3d39-113">See also</span></span>

- [<span data-ttu-id="c3d39-114">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3d39-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
