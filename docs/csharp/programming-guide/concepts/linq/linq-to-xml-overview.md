---
title: "LINQ to XML 개요(C#) | Microsoft 문서"
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
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 05a1eab1470094405f66345515c275edfb26da45
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-overview-c"></a>LINQ to XML 개요(C#)
XML은 다양한 컨텍스트에서 데이터의 형식을 지정하는 방법으로 널리 채택되고 있습니다. 예를 들어, 웹에 있는 구성 파일, Microsoft Office Word 파일 및 데이터베이스에서 XML을 찾을 수 있습니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 XML을 사용한 프로그래밍을 위해 다시 디자인된 최신 방법입니다. LINQ to XML은 DOM(문서 개체 모델)의 메모리 내 문서 수정 기능을 제공하며 .[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 식을 지원합니다. 이러한 쿼리 식은 구문적으로 XPath와 다르지만 유사한 기능을 제공합니다.  
  
## <a name="linq-to-xml-developers"></a>LINQ to XML 개발자  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 다양한 개발자를 대상으로 합니다. 특정 작업을 수행하려는 일반 개발자의 경우 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 SQL과 유사한 쿼리 경험을 제공하므로 XML을 더 쉽게 사용할 수 있습니다. 프로그래머는 약간의 시간만 투자해도 원하는 프로그래밍 언어로 간결하고 강력한 쿼리를 작성하는 방법을 배울 수 있습니다.  
  
 전문 개발자는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하여 생산성을 크게 높일 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 통해 더욱 표현성이 크고 압축적이며 강력한 코드를 더 적게 작성할 수 있습니다. 이와 동시에 여러 데이터 도메인에서 쿼리 식을 사용할 수 있습니다.  
  
## <a name="what-is-linq-to-xml"></a>LINQ to XML이란?  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 LINQ를 사용할 수 있는 메모리 내 XML 프로그래밍 인터페이스로, [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 프로그래밍 언어에서 XML 작업을 수행할 수 있도록 합니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 XML 문서를 메모리로 가져온다는 점에서 DOM(문서 개체 모델)과 같습니다. 문서를 쿼리하고 수정할 수 있으며 문서를 수정한 후 파일에 저장하거나 serialize하고 네트워크를 통해 보낼 수 있습니다. 그러나 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 DOM과 다릅니다. LINQ to XML은 간단하고 작업하기 쉬우며 C#의 언어 기능을 활용하는 새로운 개체 모델을 제공합니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 가장 중요한 이점은 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]와 통합되었다는 점입니다. 이 통합을 통해 메모리 내 XML 문서에 대한 쿼리를 작성하여 요소와 특성의 컬렉션을 검색할 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 쿼리 기능은 기능 면에서(구문 면에서는 아니지만) XPath 및 XQuery와 유사합니다. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]에서는 C#의 통합을 통해 더욱 강력한 형식 지정, 컴파일 시간 검사 및 개선된 디버거 지원 기능을 제공합니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 또 다른 이점은 쿼리 결과를 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XAttribute> 개체 생성자에 대한 매개 변수로 사용할 수 있다는 점입니다. 이러한 이점은 XML 트리를 만드는 강력한 방법의 기반이 됩니다. 개발자는 *함수 생성*이라는 이 방법을 사용하여 XML 트리의 모양을 쉽게 변환할 수 있습니다.  
  
 예를 들어 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348)에 설명된 것과 같은 일반적인 XML 구매 주문이 있을 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하여 다음 쿼리를 실행하면 구매 주문의 모든 품목 요소에 대한 부품 번호 특성 값을 가져올 수 있습니다.  
  
```csharp  
IEnumerable<string> partNos =  
from item in purchaseOrder.Descendants("Item")  
select (string) item.Attribute("PartNumber");  
```  
  
 또 다른 예로, $100보다 큰 값을 가진 품목의 목록을 부품 번호 순서로 정렬하려고 할 수 있습니다. 이 정보를 얻으려면 다음 쿼리를 실행할 수 있습니다.  
  
```csharp  
IEnumerable<XElement> partNos =  
from item in purchaseOrder.Descendants("Item")  
where (int) item.Element("Quantity") *  
    (decimal) item.Element("USPrice") > 100  
orderby (string)item.Element("PartNumber")  
select item;  
```  
  
 이러한 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 기능 외에도 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 향상된 XML 프로그래밍 인터페이스를 제공합니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   파일이나 스트림에서 XML을 로드합니다.  
  
-   파일이나 스트림에서 XML을 serialize합니다.  
  
-   함수 생성을 사용하여 XML을 새로 만듭니다.  
  
-   XPath와 같은 축을 사용하여 XML을 쿼리합니다.  
  
-   <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 및 <xref:System.Xml.Linq.XElement.SetValue%2A>와 같은 메서드를 사용하여 메모리 내 XML 트리를 조작합니다.  
  
-   XSD를 사용하여 XML 트리의 유효성을 검사합니다.  
  
-   이러한 기능을 함께 사용하여 XML 트리의 모양을 변환할 수 있습니다.  
  
## <a name="creating-xml-trees"></a>XML 트리 만들기  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하여 프로그래밍하는 경우의 가장 중요한 이점 중 하나는 XML 트리를 쉽게 만들 수 있다는 점입니다. 예를 들어 작은 XML 트리를 만들려면 다음과 같이 코드를 작성할 수 있습니다.  
  
```csharp  
XElement contacts =  
new XElement("Contacts",  
    new XElement("Contact",  
        new XElement("Name", "Patrick Hines"),  
        new XElement("Phone", "206-555-0144",   
            new XAttribute("Type", "Home")),  
        new XElement("phone", "425-555-0145",  
            new XAttribute("Type", "Work")),  
        new XElement("Address",  
            new XElement("Street1", "123 Main St"),  
            new XElement("City", "Mercer Island"),  
            new XElement("State", "WA"),  
            new XElement("Postal", "68042")  
        )  
    )  
);  
```  
  
 자세한 내용은 [XML 트리 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq>   
 [시작(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
