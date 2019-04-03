---
title: '방법: 특정 요소 이름 (Visual Basic)를 사용 하 여 하위 항목 찾기'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: c7dadec961420988a7f4cc1d6be72d7cdba5c047
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816840"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="e3e2b-102">방법: 특정 요소 이름 (Visual Basic)를 사용 하 여 하위 항목 찾기</span><span class="sxs-lookup"><span data-stu-id="e3e2b-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="e3e2b-103">특정 이름을 가진 모든 하위 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="e3e2b-104">모든 하위 요소를 반복하는 코드를 작성할 수 있지만 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3e2b-105">예제</span><span class="sxs-lookup"><span data-stu-id="e3e2b-105">Example</span></span>  
 <span data-ttu-id="e3e2b-106">다음 예제에서는 요소 이름에 따라 하위 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="e3e2b-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="e3e2b-108">예제</span><span class="sxs-lookup"><span data-stu-id="e3e2b-108">Example</span></span>  
 <span data-ttu-id="e3e2b-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e3e2b-110">자세한 내용은 [XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e3e2b-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e2b-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3e2b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3e2b-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [<span data-ttu-id="e3e2b-113">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3e2b-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
