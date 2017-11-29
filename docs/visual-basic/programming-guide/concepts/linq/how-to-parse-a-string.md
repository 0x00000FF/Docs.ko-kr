---
title: "방법: 문자열 (Visual Basic)을 구문 분석"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a>방법: 문자열 (Visual Basic)을 구문 분석
이 항목에서는 C#에서 XML 트리를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 에 문자열을 구문 분석할 수 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 사용 하 여는 `XElement.Parse` 메서드. 그러나 XML 리터럴을에서 문자열에서 XML을 구문 분석으로 동일한 성능 저하가 발생 하지 않습니다 때문에 다음 코드에 표시 된 대로 XML 리터럴을 사용 하는 더 효율적입니다.  
  
 XML 리터럴을 사용하는 경우 XML을 복사하여 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램에 붙여 넣기만 하면 됩니다.  
  
> [!NOTE]
>  텍스트의 구문을 분석하거나 텍스트 파일에서 XML 문서를 로드하는 방법은 함수 생성보다 효율적이지 않습니다. 코드에서 XML 트리를 초기화하는 경우 텍스트의 구문을 분석하는 경우보다 함수 생성을 사용하는 경우에 프로세서 시간을 적게 사용합니다.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 구문 분석 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
