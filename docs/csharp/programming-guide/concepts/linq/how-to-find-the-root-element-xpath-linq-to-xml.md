---
title: '방법: 루트 요소 찾기(XPath 및 LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: a0197a34f2e9d1b42a71d3c8cb1a4281ba495c4f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2018
ms.locfileid: "46710991"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="6aac8-102">방법: 루트 요소 찾기(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="6aac8-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="6aac8-103">이 항목에서는 XPath와 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 루트 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6aac8-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="6aac8-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6aac8-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="6aac8-105">예</span><span class="sxs-lookup"><span data-stu-id="6aac8-105">Example</span></span>  
 <span data-ttu-id="6aac8-106">이 예제에서는 루트 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6aac8-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="6aac8-107">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aac8-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="6aac8-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6aac8-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="6aac8-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6aac8-109">See Also</span></span>

- [<span data-ttu-id="6aac8-110">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="6aac8-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
