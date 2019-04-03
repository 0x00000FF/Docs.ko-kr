---
title: '방법: Visual Basic에서 XML 문서 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 2f32847c1b3a0fdf1892d6b423bb33783b6bdfe3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814590"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>방법: Visual Basic에서 XML 문서 만들기
이 예제에서는 XML 문서 주석 코드를 추가 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>형식 또는 멤버에 대 한 XML 문서를 만들려면  
  
1.  에 **코드 편집기**, 문서를 만들려면 형식 또는 멤버는 위의 줄에 커서를 놓습니다.  
  
2.  형식 `'''` (세 개의 작은따옴표).  
  
     형식 또는 멤버는 XML 구조에 추가 되는 **코드 편집기**합니다.  
  
3.  적절 한 태그 사이 설명 정보를 추가 합니다.  
  
    > [!NOTE]
    >  각 줄으로 시작 해야 XML 문서 블록에 추가 줄을 추가 하는 경우 `'''`합니다.  
  
4.  새 XML 문서 주석이 포함 된 형식 또는 멤버를 사용 하는 추가 코드를 추가 합니다.  
  
     텍스트를 표시 하는 IntelliSense를 \<요약 > 형식 또는 멤버에 대 한 태그입니다.  
  
5.  설명서 주석이 들어 있는 XML 파일을 생성 하는 코드를 컴파일하십시오. 자세한 내용은 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
