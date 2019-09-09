---
title: '방법: 복합 필터링으로 쿼리 작성(C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 7759a02c1b9ef0ae0c1af4bfb2600543b21cdf0f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253185"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="f9652-102">방법: 복합 필터링으로 쿼리 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="f9652-102">How to: Write Queries with Complex Filtering (C#)</span></span>
<span data-ttu-id="f9652-103">복잡한 필터를 사용하여 LINQ to XML 쿼리를 작성하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="f9652-104">예를 들어, 특정 이름과 값을 가진 자식 요소가 있는 모든 요소를 찾으려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="f9652-105">이 항목에서는 복잡한 필터링을 사용하여 쿼리를 작성하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9652-106">예</span><span class="sxs-lookup"><span data-stu-id="f9652-106">Example</span></span>  
 <span data-ttu-id="f9652-107">이 예제에서는 `PurchaseOrder` 특성이 "Shipping"과 같고 자식 `Address` 요소가 "NY"와 같은 자식 `Type` 요소가 있는 모든 `State` 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="f9652-108">이 예제에서는 `Where` 절에서 중첩 쿼리를 사용하며, `Any` 연산자는 컬렉션에 요소가 있는 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="f9652-109">메서드 기반 쿼리 구문을 사용하는 방법에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](./query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9652-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="f9652-110">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f9652-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f9652-111">`Any` 연산자에 대한 자세한 내용은 [수량자 작업(C#)](./quantifier-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9652-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="f9652-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-112">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="f9652-113">예</span><span class="sxs-lookup"><span data-stu-id="f9652-113">Example</span></span>  
 <span data-ttu-id="f9652-114">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="f9652-115">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9652-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f9652-116">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 여러 구매 주문](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f9652-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="f9652-117">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9652-117">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9652-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9652-118">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="f9652-119">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="f9652-119">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="f9652-120">수량자 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="f9652-120">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
