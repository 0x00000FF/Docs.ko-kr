---
title: '방법: LINQ (Visual Basic)를 사용 하 여 XML 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 628af13a4cdea41ade943b69e326ec2d9abcbf1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536349"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>방법: LINQ (Visual Basic)를 사용 하 여 XML 변환
[XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md) 쉽게 한 소스에서 XML을 읽고 새 XML 형식으로 변환 합니다. 를 변환 하려면 콘텐츠를 검색 하는 LINQ 쿼리를 활용 하거나 새 XML 형식으로 기존 문서에서 콘텐츠를 변경할 수 있습니다.  
  
 이 항목의 예제 XML 소스 문서에서 콘텐츠를 브라우저에서 볼 수 있도록 HTML로 변환 합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>XML 문서를 변환 합니다.  
  
1.  Visual Studio에서 Visual Basic 프로젝트를 새로 만듭니다는 **콘솔 응용 프로그램** 프로젝트 템플릿.  
  
2.  Visual Basic 코드를 수정 하려면 프로젝트에서 생성 된 Module1.vb 파일을 두 번 클릭 합니다. 다음 코드를 추가 합니다 `Sub Main` 의 `Module1` 모듈입니다. 이 코드는 소스 XML 문서를 만듭니다는 <xref:System.Xml.Linq.XDocument> 개체입니다.  
  
    ```vb  
    Dim catalog =   
      <?xml version="1.0"?>  
        <Catalog>  
          <Book id="bk101">  
            <Author>Garghentini, Davide</Author>  
            <Title>XML Developer's Guide</Title>  
            <Price>44.95</Price>  
            <Description>  
              An in-depth look at creating applications  
              with <technology>XML</technology>. For   
              <audience>beginners</audience> or   
              <audience>advanced</audience> developers.  
            </Description>  
          </Book>  
          <Book id="bk331">  
            <Author>Spencer, Phil</Author>  
            <Title>Developing Applications with Visual Basic .NET</Title>  
            <Price>45.95</Price>  
            <Description>  
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     [방법: 파일, 문자열 또는 Stream에서 XML을 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)합니다.  
  
3.  원본 XML 문서를 만드는 코드 뒤 모든 검색 하려면 다음 코드를 추가 합니다 \<책 > 개체 요소를에서 HTML 문서를 변환 하 고 있습니다. 목록을 \<책 > 요소 컬렉션을 반환 하는 LINQ 쿼리를 사용 하 여 만들어지는 <xref:System.Xml.Linq.XElement> 변환된 된 HTML을 포함 하는 개체입니다. 새 XML 형식으로 원본 문서에서 값을 삽입할 포함된 식에 사용할 수 있습니다.  
  
     결과 HTML 문서를 사용 하 여 파일에 기록 되는 <xref:System.Xml.Linq.XElement.Save%2A> 메서드.  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  후 `Sub Main` 의 `Module1`, 새 메서드 추가 (`Sub`) 변환 하는 \<설명 > 지정 된 HTML 형식으로 노드. 이 메서드는 이전 단계에서 코드에 의해 호출 되며 형식의 유지 하는 데 사용 되는 \<설명 > 요소입니다.  
  
     하위 요소를 대체 하는이 메서드는 \<설명 > HTML 요소입니다. `ReplaceWith` 메서드를 사용 하는 하위 요소의 위치를 유지 합니다. 변환된 된 내용을 합니다 \<설명 > 요소는 HTML 단락에 포함 됩니다 (\<p >) 요소입니다. <xref:System.Xml.Linq.XContainer.Nodes%2A> 속성의 변환된 된 내용을 검색을 사용 하는 \<설명 > 요소입니다. 이렇게 하면 하위 요소는 변환된 된 내용에 포함 되도록 합니다.  
  
     다음 코드를 추가 `Sub Main` 의 `Module1`합니다.  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  변경 내용을 저장합니다.  
  
6.  F5 키를 눌러 코드를 실행 합니다. 문서를 저장 된 결과 다음과 같습니다.  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a>참고자료
- [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [방법: 파일, 문자열 또는 Stream에서 XML 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
