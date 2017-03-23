---
title: "방법: 위치 (XPath 및 LINQ to XML)에 따라 자식 요소 찾기 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c1ef9db560de02efa20dbe88ff0e73ffd9e7fff
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>방법: 위치 (XPath 및 LINQ to XML)에 따라 자식 요소 찾기 (Visual Basic)
위치에 따라 요소를 찾으려는 경우가 있습니다. 두 번째 요소를 찾으려고 하거나 세 번째 요소부터 다섯 번째 요소까지 찾으려고 할 수도 있습니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 지연 방식으로 이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리를 작성하는 두 가지 방법이 있습니다. 사용할 수는 <xref:System.Linq.Enumerable.Skip%2A>및 <xref:System.Linq.Enumerable.Take%2A>연산자 하거나 사용할 수 있습니다는 <xref:System.Linq.Enumerable.Where%2A>인덱스를 사용 하는 오버 로드.</xref:System.Linq.Enumerable.Where%2A> </xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A> 사용 하는 경우는 <xref:System.Linq.Enumerable.Where%2A>오버 로드는 두 개의 인수를 사용 하는 람다 식을 사용 합니다.</xref:System.Linq.Enumerable.Where%2A> 다음 예제에서는 위치에 따라 선택하는 두 메서드를 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 두 번째 `Test` 요소부터 네 번째 요소까지 찾습니다. 결과는 요소의 컬렉션입니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 테스트 구성 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)합니다.  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
