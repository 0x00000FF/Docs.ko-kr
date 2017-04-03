---
title: "XDocument 쿼리와 XElement 쿼리 비교(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a3da563618ad3dbc9797f252ab51588a43ce8e6
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a>XDocument 쿼리와 XElement 쿼리 비교(C#)
<xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>를 통해 문서를 로드할 경우에는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>를 통해 로드할 때와 약간 다르게 쿼리를 작성해야 합니다.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>XDocument.Load와 XElement.Load의 비교  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>를 통해 XML 문서를 <xref:System.Xml.Linq.XElement>에 로드할 경우 XML 트리 루트의 <xref:System.Xml.Linq.XElement>에는 로드된 문서의 루트 요소가 포함됩니다. 그러나 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>를 통해 동일한 XML 문서를 <xref:System.Xml.Linq.XDocument>에 로드할 경우 트리의 루트는 <xref:System.Xml.Linq.XDocument> 노드이며, 로드된 문서의 루트 요소는 <xref:System.Xml.Linq.XDocument>의 허용되는 자식 <xref:System.Xml.Linq.XElement> 노드입니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 축은 루트 노드와 상대적으로 작동합니다.  
  
 첫 번째 예제는 <xref:System.Xml.Linq.XElement.Load%2A>를 사용하여 XML 트리를 로드합니다. 트리 루트의 자식 요소에 대해 쿼리합니다.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 예상대로 이 예제는 다음과 같이 출력됩니다.  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 다음 예제는 XML 트리가 <xref:System.Xml.Linq.XElement> 대신 <xref:System.Xml.Linq.XDocument>에 로드되는 점을 제외하고 위의 예제와 동일합니다.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 동일한 쿼리에서 세 자식 노드 대신 하나의 `Root` 노드를 반환했습니다.  
  
 이를 처리하는 한 가지 방법은 축 메서드에 액세스하기 전에 다음과 같이 <xref:System.Xml.Linq.XDocument.Root%2A> 속성을 사용하는 것입니다.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 이 쿼리는 이제 <xref:System.Xml.Linq.XElement>에서 시작하는 트리에 대한 쿼리와 동일한 방식으로 수행됩니다. 예제의 결과는 다음과 같습니다.  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 쿼리(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
