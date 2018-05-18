---
title: '방법: XmlReader에서 트리 조각 만들기(C#)'
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 1a0f56655f2b328be5a6615088ef242061ddbd5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>방법: XmlReader에서 트리 조각 만들기(C#)
이 항목에서는 <xref:System.Xml.XmlReader>에서 XML 트리를 직접 만드는 방법을 보여 줍니다. <xref:System.Xml.Linq.XElement>에서 <xref:System.Xml.XmlReader>를 만들려면 요소 노드에 <xref:System.Xml.XmlReader>를 배치해야 합니다. <xref:System.Xml.XmlReader>는 주석과 처리 명령을 건너뛰지만 <xref:System.Xml.XmlReader>가 텍스트 노드에 배치되면 오류가 throw됩니다. 이러한 오류를 방지하려면 <xref:System.Xml.XmlReader>에서 XML 트리를 만들기 전에 항상 <xref:System.Xml.XmlReader>를 요소에 배치하세요.  
  
## <a name="example"></a>예  
 이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.  
  
 다음 코드에서는 `T:System.Xml.XmlReader` 개체를 만들고 첫 번째 요소 노드를 찾을 때까지 노드를 읽은 다음 <xref:System.Xml.Linq.XElement> 개체를 로드합니다.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 구문 분석(C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
