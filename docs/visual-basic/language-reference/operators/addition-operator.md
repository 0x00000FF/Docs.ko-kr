---
title: + 연산자 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 91806c204c313956b292eb9c9be078991f733b4e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47231482"
---
# <a name="-operator-visual-basic"></a>+ 연산자(Visual Basic)
두 숫자를 추가 하거나 숫자 식의 양수 값을 반환 합니다. 두 문자열 식을 연결할도 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`expression1`|필수. 모든 숫자 또는 문자열 식입니다.|  
|`expression2`|필수 하지 않는 경우는 `+` 연산자가 음수 값을 계산 합니다. 모든 숫자 또는 문자열 식입니다.|  
  
## <a name="result"></a>결과  
 하는 경우 `expression1` 고 `expression2` 가 모두 숫자인 경우 결과 산술 합계입니다.  
  
 경우 `expression2` 가 없는 합니다 `+` 연산자가는 *단항* id 연산자 식의 변경 되지 않은 값에 대 한 합니다. 이러한 관점에서 작업의 부호를 유지 이루어져 `expression1`이므로 결과 음수 경우 `expression1` 음수입니다.  
  
 하는 경우 `expression1` 및 `expression2` 은 모두 문자열 결과 해당 값의 연결입니다.  
  
 하는 경우 `expression1` 및 `expression2` 은 혼합 형식의 수행 하는 동작에 따라 달라 집니다 해당 형식, 내용 및 설정을 합니다 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다. 자세한 내용은 "설명 합니다."에 있는 표를 참조 하세요.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식, 부동 소수점 및 부호 없는 형식을 포함 하 고 `Decimal`, 및 `String`.  
  
## <a name="remarks"></a>설명  
 일반적으로 `+` 는 산술 더하기를 수행 하 고 두 식이 모두 문자열을가 하는 경우에 연결 합니다.  
  
 두 식 모두 경우는 `Object`, Visual Basic 같은 작업을 수행 합니다.  
  
|식의 데이터 형식|컴파일러에서 작업|  
|---|---|  
|두 식이 모두 숫자 데이터 형식 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`를 `UInteger`, `Long`를 `ULong`, `Decimal`를 `Single`, 또는 `Double`)|추가 합니다. 결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식 `expression1` 고 `expression2`입니다. "정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.|  
|형식의 두 식이 모두 `String`|연결 합니다.|  
|하나의 식이 숫자 데이터 형식이 고 다른 하나는 문자열|하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.<br /><br /> 경우 `Option Strict` 은 `Off`, 암시적으로 변환 합니다 `String` 에 `Double` 추가 합니다.<br /><br /> 경우는 `String` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.|  
|하나의 식이 숫자 데이터 형식이 고 다른 하나는 [Nothing](../../../visual-basic/language-reference/nothing.md)|추가 사용 하 여 `Nothing` 0으로 반환 합니다.|  
|하나의 식 문자열로, 이며 다른 하나는 `Nothing`|연결을 사용 하 여 `Nothing` 값으로 ""입니다.|  
  
 하나의 식이 `Object` Visual Basic 식 같은 작업을 수행 합니다.  
  
|식의 데이터 형식|컴파일러에서 작업|  
|---|---|  
|`Object` 식이 숫자 값 및 다른 하나는 숫자 데이터 형식|하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.<br /><br /> 하는 경우 `Option Strict` 는 `Off`를 추가 합니다.|  
|`Object` 식이 숫자 값 이며 다른 유형의 `String`|하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.<br /><br /> 경우 `Option Strict` 은 `Off`, 암시적으로 변환 합니다 `String` 에 `Double` 추가 합니다.<br /><br /> 경우는 `String` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.|  
|`Object` 식이 문자열 및 숫자 데이터 형식이 다른|하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.<br /><br /> 경우 `Option Strict` 됩니다 `Off`, 다음 문자열을 암시적으로 변환 `Object` 에 `Double` 추가 합니다.<br /><br /> 경우 문자열 `Object` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.|  
|`Object` 식이 문자열 고 다른 하나는 형식 `String`|하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다.<br /><br /> 경우 `Option Strict` 됩니다 `Off`, 암시적으로 변환 `Object` 에 `String` 과 연결 합니다.|  
  
 두 식이 모두 `Object` 식, Visual Basic 같은 작업을 수행 합니다 (`Option Strict Off` 만).  
  
|식의 데이터 형식|컴파일러에서 작업|  
|---|---|  
|둘 다 `Object` 숫자 값을 포함 하는 식|추가 합니다.|  
|둘 다 `Object` 식이란 형식 `String`|연결 합니다.|  
|하나의 `Object` 식에는 숫자 값을 보유 하 고 다른 식이 문자열|문자열을 암시적으로 변환할 `Object` 에 `Double` 추가 합니다.<br /><br /> 경우 문자열 `Object` 숫자 값으로 변환할 수 없습니다. 다음 throw는 <xref:System.InvalidCastException> 예외입니다.|  
  
 경우 `Object` 식이 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 <xref:System.DBNull>의 `+` 연산자도 처리는 `String` 값을 사용 하 여 ""입니다.  
  
> [!NOTE]
>  사용 하는 경우는 `+` 연산자, 더하기 또는 문자열 연결 발생할 지 여부를 확인 하려면 못할 수 있습니다. 사용 된 `&` 모호성을 제거 하 고 자동 문서화 코드를 제공 하도록 연결에 대 한 연산자입니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `+` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `+` 덧셈 연산자입니다. 피연산자가 두 숫자를 Visual Basic 산술 연산 결과 계산 합니다. 산술 연산 결과 두 피연산자의 합계를 나타냅니다.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 사용할 수도 있습니다는 `+` 문자열 연결 연산자. 피연산자가 두 문자열을 Visual Basic에 연결 합니다. 연결 결과 두 피연산자의 내용을 다른 구성 된 단일 문자열을 나타냅니다.  
  
 결과의 설정에 따라 혼합 형식의 피연산자 인 경우는 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다. 다음 예제에서는 결과 보여 줍니다. 때 `Option Strict` 는 `On`합니다.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 다음 예제에서는 결과 보여 줍니다. 때 `Option Strict` 는 `Off`합니다.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 모호성을 제거 하려면 사용 해야 합니다 `&` 연산자 대신 `+` 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
