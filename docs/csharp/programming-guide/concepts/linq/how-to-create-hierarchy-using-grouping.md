---
title: '방법: 그룹화를 사용하여 계층 구조 만들기(C#)'
ms.date: 07/20/2015
ms.assetid: 0213d59e-5f76-438c-9cab-4bf11f7b971d
ms.openlocfilehash: 8fa384ced04a90002f8f721266f163c874d6e0ff
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45649694"
---
# <a name="how-to-create-hierarchy-using-grouping-c"></a><span data-ttu-id="ae718-102">방법: 그룹화를 사용하여 계층 구조 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="ae718-102">How to: Create Hierarchy Using Grouping (C#)</span></span>
<span data-ttu-id="ae718-103">이 예제에서는 데이터를 그룹화한 다음 그룹화에 따라 XML을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae718-103">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae718-104">예</span><span class="sxs-lookup"><span data-stu-id="ae718-104">Example</span></span>  
 <span data-ttu-id="ae718-105">이 예제에서는 먼저 범주를 기준으로 데이터를 그룹화한 다음 XML 계층 구조가 그룹화를 반영하는 XML 파일을 새로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae718-105">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="ae718-106">이 예제에서는 XML 문서 [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae718-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Load("Data.xml");  
var newData =  
    new XElement("Root",  
        from data in doc.Elements("Data")  
        group data by (string)data.Element("Category") into groupedData  
        select new XElement("Group",  
            new XAttribute("ID", groupedData.Key),  
            from g in groupedData  
            select new XElement("Data",  
                g.Element("Quantity"),  
                g.Element("Price")  
            )  
        )  
    );  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="ae718-107">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae718-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Group ID="A">  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>24.50</Price>  
    </Data>  
    <Data>  
      <Quantity>5</Quantity>  
      <Price>4.95</Price>  
    </Data>  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>66.00</Price>  
    </Data>  
    <Data>  
      <Quantity>15</Quantity>  
      <Price>29.00</Price>  
    </Data>  
  </Group>  
  <Group ID="B">  
    <Data>  
      <Quantity>1</Quantity>  
      <Price>89.99</Price>  
    </Data>  
    <Data>  
      <Quantity>10</Quantity>  
      <Price>.99</Price>  
    </Data>  
    <Data>  
      <Quantity>8</Quantity>  
      <Price>6.99</Price>  
    </Data>  
  </Group>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae718-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae718-108">See Also</span></span>

- [<span data-ttu-id="ae718-109">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="ae718-109">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
