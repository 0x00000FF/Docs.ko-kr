---
title: '방법: 새 형식 프로젝션(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: a2486d88af537fb4aa8f34243a5a739d25ee5be1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353331"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="abd3c-102">방법: 새 형식 프로젝션 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abd3c-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="abd3c-103">이 단원의 다른 예제에서는 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>의 `string` 및 <xref:System.Collections.Generic.IEnumerable%601>의 `int`로 결과를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="abd3c-104">이러한 결과 형식이 일반적이지만 모든 시나리오에 적합하지는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="abd3c-105">대부분의 경우 다른 형식의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하는 쿼리를 작성하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abd3c-106">예제</span><span class="sxs-lookup"><span data-stu-id="abd3c-106">Example</span></span>  
 <span data-ttu-id="abd3c-107">이 예제에서는 `Select` 절에서 개체를 인스턴스화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="abd3c-108">이 코드에서는 먼저 생성자를 사용하여 새 클래스를 정의한 다음 식이 새 클래스의 새 인스턴스이도록 `Select` 문을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="abd3c-109">이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="abd3c-110">이 예제에서는 [방법: 단일 자식 요소 검색 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)항목에 소개 된 `M:System.Xml.Linq.XElement.Element` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="abd3c-111">또한, 캐스트를 사용하여 `M:System.Xml.Linq.XElement.Element` 메서드에서 반환하는 요소의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="abd3c-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="abd3c-112">This example produces the following output:</span></span>  
  
```console  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="abd3c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abd3c-113">See also</span></span>

- [<span data-ttu-id="abd3c-114">프로젝션 및 변환 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abd3c-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
