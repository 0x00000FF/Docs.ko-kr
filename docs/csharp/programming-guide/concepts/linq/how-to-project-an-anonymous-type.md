---
title: 무명 형식을 프로젝션하는 방법(C#)
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: 7797c8bfb12943af1ce7f975b170bf002aa7d6fc
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345727"
---
# <a name="how-to-project-an-anonymous-type-c"></a><span data-ttu-id="e6e17-102">무명 형식을 프로젝션하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="e6e17-102">How to project an anonymous type (C#)</span></span>
<span data-ttu-id="e6e17-103">새 형식을 잠깐 동안만 사용할 경우에도 필요에 따라 쿼리를 해당 형식으로 프로젝션하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="e6e17-104">프로젝션에서만 사용하기 위해 새 형식을 만드는 것은 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="e6e17-105">이 경우 더 효율적인 방법은 익명 형식을 프로젝션하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="e6e17-106">익명 형식을 사용하면 클래스를 정의한 다음 클래스의 이름을 지정하지 않고도 클래스의 개체를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="e6e17-107">무명 형식은 *튜플*이라는 수학적 개념의 C# 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="e6e17-108">수학 용어인 튜플은 단일(single), 이중(double), 3중(triple), 4중(quadruple), 5중(quintuple), n중(n-tuple)에서 유래되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="e6e17-109">튜플은 각각 특정 형식으로 되어 있는 개체의 유한 시퀀스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="e6e17-110">이를 이름/값 쌍의 목록이라고 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="e6e17-111">예를 들어 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML 문서에 있는 주소의 내용은 다음과 같이 표현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML document could be expressed as follows:</span></span>  
  
```text  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="e6e17-112">익명 형식의 인스턴스를 만드는 경우 n번째 튜플을 만드는 것으로 생각하면 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="e6e17-113">`select` 절에서 튜플을 만드는 쿼리를 작성하면 쿼리에서 튜플의 `IEnumerable`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-113">If you write a query that creates a tuple in the `select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6e17-114">예제</span><span class="sxs-lookup"><span data-stu-id="e6e17-114">Example</span></span>  
 <span data-ttu-id="e6e17-115">이 예제에서 `select` 절은 익명 형식을 프로젝션한 다음</span><span class="sxs-lookup"><span data-stu-id="e6e17-115">In this example, the `select` clause projects an anonymous type.</span></span> <span data-ttu-id="e6e17-116">`var`을 사용하여 `IEnumerable` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-116">The example then uses `var` to create the `IEnumerable` object.</span></span> <span data-ttu-id="e6e17-117">`foreach` 루프에서 반복 변수는 쿼리 식에서 만든 익명 형식의 인스턴스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-117">Within the `foreach` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="e6e17-118">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="e6e17-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 <span data-ttu-id="e6e17-119">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e17-119">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  