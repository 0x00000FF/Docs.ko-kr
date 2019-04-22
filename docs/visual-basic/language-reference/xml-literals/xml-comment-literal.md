---
title: XML 주석 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 149bbac6d301a9c2f166d05698e3780171126cb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827278"
---
# <a name="xml-comment-literal-visual-basic"></a>XML 주석 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XComment> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`<!--`|필수 요소. XML 주석의 시작을 나타냅니다.|  
|`content`|필수 요소. XML 주석에 표시할 텍스트입니다. 일련을의 두 개의 하이픈 (-) 또는 닫는 태그에 인접 한 하이픈으로 끝날 수 없습니다.|  
|`-->`|필수 요소. XML 주석의 끝을 나타냅니다.|  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XComment> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML 주석 리터럴 문서 콘텐츠가 없습니다. 문서에 대 한 정보가 있습니다. XML 주석 섹션을 순서 "-->"로 끝납니다. 이 다음 사항을 의미 합니다.  
  
-   포함된 식 구분 기호는 유효한 XML 주석 콘텐츠 때문에 XML 주석 리터럴에 포함된 식을 사용할 수 없습니다.  
  
-   XML 주석 섹션 중첩 될 수 없으므로 있으므로 `content` "-->" 값을 포함할 수 없습니다.  
  
 XML 주석 리터럴에 변수에 할당할 수 있습니다 또는 XML 요소 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴을 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다. 이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 Visual Basic 컴파일러는 XML 주석 리터럴에 호출으로 변환 된 <xref:System.Xml.Linq.XComment.%23ctor%2A> 생성자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 "This is a comment" 텍스트가 포함 된 XML 주석을 만듭니다.  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XComment>
- [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
