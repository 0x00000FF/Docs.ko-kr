---
title: '* 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: e723667b6397fe758ae2f33babe27c0e41887aab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641176"
---
# <a name="-operator-visual-basic"></a>* 연산자(Visual Basic)
두 숫자를 곱합니다.  
  
## <a name="syntax"></a>구문  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`number1`|필수 요소. 임의의 숫자 식입니다.|  
|`number2`|필수. 임의의 숫자 식입니다.|  
  
## <a name="result"></a>결과  
 결과 곱한 `number1` 고 `number2`입니다.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식, 부동 소수점 및 부호 없는 형식을 포함 하 고 `Decimal`입니다.  
  
## <a name="remarks"></a>설명  
 데이터 형식의 결과 피연산자의 형식에 따라 달라 집니다. 다음 표에서 결과의 데이터 형식을 결정 하는 것입니다.  
  
|피연산자 데이터 형식|결과 데이터 형식|  
|---|---|  
|두 식이 모두 정수 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)를 [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md)를 [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md)를 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)를 [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)하십시오 [긴](../../../visual-basic/language-reference/data-types/long-data-type.md)하십시오 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|데이터 형식에 대 한 적절 한 숫자 데이터 형식 `number1` 고 `number2`입니다. "정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.|  
|두 식이 모두 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|두 식이 모두 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|두 식 중 하나가 부동 소수점 데이터 형식 (`Single` 또는 [이중](../../../visual-basic/language-reference/data-types/double-data-type.md)) 중 하나만 `Single` (참고 `Decimal` 부동 소수점 데이터 형식이 아닌)|`Double`|  
  
 식을 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md)를 0으로 처리 됩니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `*` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `*` 두 숫자를 곱하기 연산자입니다. 결과 두 피연산자의 제품입니다.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a>참고자료
- [*= 연산자](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
