---
title: "방법: 특정 특성으로 요소 찾기(XPath-LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66053135dbfdf6f61ff1f09b846acd9d9cfe054f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="a68b1-102">방법: 특정 특성으로 요소 찾기(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a68b1-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a68b1-103">특정 특성을 가진 모든 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b1-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="a68b1-104">특성의 내용에는 관심이 없으며,</span><span class="sxs-lookup"><span data-stu-id="a68b1-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="a68b1-105">대신 특성의 존재에 따라 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b1-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="a68b1-106">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b1-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="a68b1-107">예제</span><span class="sxs-lookup"><span data-stu-id="a68b1-107">Example</span></span>  
 <span data-ttu-id="a68b1-108">다음 코드에서는 `Select` 특성을 가진 요소만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b1-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="a68b1-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b1-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a68b1-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a68b1-110">See Also</span></span>  
 [<span data-ttu-id="a68b1-111">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="a68b1-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
