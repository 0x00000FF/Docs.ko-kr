---
title: '작업: LINQ to XML을 사용하여 사전 작업(C#)'
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: afe4fafb9963b4fc429f441349f8190c9a1e5bac
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43739895"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a>작업: LINQ to XML을 사용하여 사전 작업(C#)
다양한 데이터 구조를 XML로 변환하고 XML을 다시 다른 데이터 구조로 변환하는 것이 편리한 경우가 많습니다. 이 항목에서는 <xref:System.Collections.Generic.Dictionary%602>를 XML로 변환하고 다시 그 반대로 변환하여 이 일반적인 방법을 구체적으로 구현하는 것을 보여 줍니다.  
  
## <a name="example"></a>예  
 이 예제에서는 쿼리가 새 <xref:System.Xml.Linq.XElement> 개체를 프로젝션하고 생성된 컬렉션이 루트 <xref:System.Xml.Linq.XElement> 개체의 생성자에 인수로 전달되는 함수 구문의 형태를 사용합니다.  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>예  
 다음 코드에서는 XML에서 사전을 만듭니다.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a>참고 항목

- [프로젝션 및 변환(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
