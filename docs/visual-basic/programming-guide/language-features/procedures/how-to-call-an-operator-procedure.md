---
title: "방법: 연산자 프로시저 (Visual Basic)를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2403e7a8270c17a8db5417cd8394fd47c373d493
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>방법: 연산자 프로시저 호출(Visual Basic)
연산자 기호를 사용 하 여 식에서 연산자 프로시저를 호출 합니다. 변환 연산자의 경우 호출 된 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 다른 값의 데이터 형식을 변환 하 합니다.  
  
 연산자 프로시저를 명시적으로 호출 하지 않습니다. 연산자를 사용 또는 `CType` 대입문 이나 일반적으로 연산자를 사용 하면 동일한 방식으로 식에서 함수입니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]연산자 프로시저를 호출 합니다.  
  
 연산자를 정의 하는 클래스 또는 구조체에는 라고도 *오버 로드* 연산자입니다.  
  
### <a name="to-call-an-operator-procedure"></a>연산자 프로시저를 호출 하려면  
  
1.  일반적인 방법으로 식에서 연산자 기호를 사용 합니다.  
  
2.  피연산자의 데이터 형식에 적합 한 연산자를 올바른 순서로 이어야 합니다.  
  
3.  연산자는 예상 대로 식의 값에 기여 합니다.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>변환 연산자 프로시저를 호출 하려면  
  
1.  사용 하 여 `CType` 식 안에 있습니다.  
  
2.  변환에 적합 한 올바른 순서로 피연산자의 데이터 형식 이어야 합니다.  
  
3.  `CType`변환 연산자 프로시저를 호출 하 고 변환 된 값을 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 <xref:System.TimeSpan>구조를 함께 추가 하 고 세 번째 결과 저장 <xref:System.TimeSpan>구조.</xref:System.TimeSpan> </xref:System.TimeSpan> <xref:System.TimeSpan>구조 연산자 프로시저를 여러 표준 연산자를 오버 로드를 정의 합니다.</xref:System.TimeSpan>  
  
 [!code-vb[VbVbcnProcedures #&29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 때문에 <xref:System.TimeSpan>표준 오버 로드 `+` 연산자 앞의 예제 프로시저를 호출 연산자의 값을 계산할 때 `combinedSpan`.</xref:System.TimeSpan>  
  
 변환 연산자 프로시저 호출의 예제를 참조 하십시오. [하는 방법: 클래스는 정의 연산자를 사용 하는 여](./how-to-use-a-class-that-defines-operators.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 프로시저](./operator-procedures.md)   
 [방법: 연산자 정의](./how-to-define-an-operator.md)   
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)   
 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [확대 변환](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
