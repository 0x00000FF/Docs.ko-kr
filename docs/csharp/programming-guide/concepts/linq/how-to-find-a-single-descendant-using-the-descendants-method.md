---
title: '방법: Descendants 메서드를 사용하여 단일 하위 항목 찾기(C#)'
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 29cac5a666f7e9a560c550ad20a5bb68d02ee1ea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253791"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="0de6f-102">방법: Descendants 메서드를 사용하여 단일 하위 항목 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="0de6f-102">How to: Find a Single Descendant Using the Descendants Method (C#)</span></span>
<span data-ttu-id="0de6f-103"><xref:System.Xml.Linq.XContainer.Descendants%2A> 축 메서드를 사용하여 고유하게 명명된 단일 요소를 찾는 코드를 신속하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="0de6f-104">이 기법은 지정된 이름을 가진 특정 하위 요소를 찾으려는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="0de6f-105">원하는 요소를 탐색하는 코드를 작성할 수도 있지만 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용하여 코드를 작성하는 것이 더 빠르고 쉬운 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de6f-106">예</span><span class="sxs-lookup"><span data-stu-id="0de6f-106">Example</span></span>  
 <span data-ttu-id="0de6f-107">이 예제에서는 <xref:System.Linq.Enumerable.First%2A> 표준 쿼리 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="0de6f-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-108">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="0de6f-109">예</span><span class="sxs-lookup"><span data-stu-id="0de6f-109">Example</span></span>  
 <span data-ttu-id="0de6f-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0de6f-111">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0de6f-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="0de6f-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0de6f-112">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
