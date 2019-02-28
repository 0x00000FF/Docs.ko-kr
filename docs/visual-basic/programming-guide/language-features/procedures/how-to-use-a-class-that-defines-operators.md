---
title: '방법: 연산자 (Visual Basic)를 정의 하는 클래스를 사용 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 358e81904f48ad844351a20a448b615a0fef8f89
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972519"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>방법: 연산자 (Visual Basic)를 정의 하는 클래스를 사용 합니다.
클래스 또는 고유한 연산자를 정의 하는 구조를 사용 하는 경우에 Visual Basic에서 이러한 연산자를 액세스할 수 있습니다.  
  
 클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 SQL 구조에 액세스 <xref:System.Data.SqlTypes.SqlString>, 변환 연산자를 정의 하는 ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) SQL 문자열 및 Visual Basic 문자열 간에 양방향으로. 사용 하 여 `CType(` *SQL 문자열 식*, `String)` Visual Basic 문자열로 SQL 문자열을 변환 하 고 `CType(` *Visual Basic 문자열 식을*, <xref:System.Data.SqlTypes.SqlString> `)` 반대 방향으로 변환 합니다.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString> 구조 정의 변환 연산자 ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md))에서 `String` 에 <xref:System.Data.SqlTypes.SqlString> 에서 다른 <xref:System.Data.SqlTypes.SqlString> 에 `String`입니다. 할당 하는 문을 `title` 하 `jobTitle` 첫 번째 연산자의 사용 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출에서는 두 번째입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다. 클래스 또는 구조체에 정의 된 모든 연산자 오버 로드에 사용할 수는 가정 하지 마십시오. 사용 가능한 연산자 목록을 참조 하세요 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
 적절 한 포함 `Imports` 소스 파일의 시작 부분에는 SQL 문자열에 대 한 문 (이 경우 <xref:System.Data.SqlTypes>).  
  
 프로젝트에는 System.Data 및 System.XML에 대 한 참조가 있어야 합니다.  
  
## <a name="see-also"></a>참고자료
- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 변환 연산자를 정의 합니다.](./how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [확장](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [방법: 구조 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
