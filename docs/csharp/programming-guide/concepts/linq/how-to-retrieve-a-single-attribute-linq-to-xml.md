---
title: '방법: 단일 특성 검색(LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 7e7da2b63b9b46a23fcdbcbea6a0f499de32cf19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504998"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="845e5-102">방법: 단일 특성 검색(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="845e5-102">How to: Retrieve a Single Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="845e5-103">이 항목에서는 특성 이름이 제공되는 경우 요소의 단일 특성을 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="845e5-104">이 방법은 특정 특성을 가진 요소를 찾으려는 경우 쿼리 식을 작성하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="845e5-105"><xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement> 메서드는 지정된 이름을 가진 <xref:System.Xml.Linq.XAttribute>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="845e5-106">예</span><span class="sxs-lookup"><span data-stu-id="845e5-106">Example</span></span>  
 <span data-ttu-id="845e5-107">다음 예제에서는 <xref:System.Xml.Linq.XElement.Attribute%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="845e5-108">이 예제에서는 트리에서 이름이 `Phone`인 하위 요소를 모두 찾은 다음 이름이 `type`인 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="845e5-109">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="845e5-110">예</span><span class="sxs-lookup"><span data-stu-id="845e5-110">Example</span></span>  
 <span data-ttu-id="845e5-111">특성의 값을 검색하려면 <xref:System.Xml.Linq.XElement> 개체의 경우와 마찬가지로 특성을 캐스팅하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="845e5-112">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-112">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="845e5-113">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="845e5-114">에서는 <xref:System.Xml.Linq.XAttribute> 클래스를 `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, `GUID?`로 캐스팅할 수 있는 명시적 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-114"> provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string\`, `bool\`, `bool?\`, `int\`, `int?\`, `uint\`, `uint?\`, `long\`, `long?\`, `ulong\`, `ulong?\`, `float\`, `float?\`, `double\`, `double?\`, `decimal\`, `decimal?\`, `DateTime\`, `DateTime?\`, `TimeSpan\`, `TimeSpan?\`, `GUID\`, and `GUID?\`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="845e5-115">예</span><span class="sxs-lookup"><span data-stu-id="845e5-115">Example</span></span>  
 <span data-ttu-id="845e5-116">다음 예제에서는 네임스페이스에 있는 특성에 대한 동일한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="845e5-117">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="845e5-117">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="845e5-118">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="845e5-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="845e5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="845e5-119">See Also</span></span>

- [<span data-ttu-id="845e5-120">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="845e5-120">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
