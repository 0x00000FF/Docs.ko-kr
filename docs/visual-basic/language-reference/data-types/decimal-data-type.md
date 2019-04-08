---
title: Decimal 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 4d530a8c1f85d2f0045184c05df63849047a8204
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834103"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 데이터 형식(Visual Basic)
부호 있는 10의 거듭제곱으로 조정 된 96 비트 (12 바이트) 정수 숫자를 나타내는 128 비트 (16 바이트) 값을 저장 합니다. 배율은 소수점의 오른쪽에 자릿수를 지정합니다. 이 범위는 0에서 28입니다. 가장 큰 가능한 값은 소수 자릿수가 0 (소수 자릿수 없이)를 사용 하 여 + /-79228162514264337593543950335 (7 + /-.9228162514264337593543950335E + 28). 소수 자릿수가 28 + /-7.9228162514264337593543950335 사이, 가장 큰 값은와 0.0000000000000000000000000001 1E-28) (+ + /-0이 아닌 가장 작은 값입니다.  
  
## <a name="remarks"></a>설명  
 `Decimal` 데이터 형식은 숫자에 대 한 최대 유효 자릿수를 제공 합니다. 최대 29 개의 유효 자릿수를 지원 하 고 7.9228 x 10를 초과 하는 값을 나타낼 수 ^28입니다. 와 같은 계산에 특히 적합 한 것 금융는 많은 수의 자릿수 필요 하지만 반올림 오류를 허용할 수 없습니다.  
  
 `Decimal`의 기본값은 0입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **전체 자릿수입니다.** `Decimal` 부동 소수점 데이터 형식이 아닙니다. `Decimal` 구조 부호 비트가 및 자릿수를 소수 부분 값의 부분을 지정 하는 요소와 함께 이진 정수 값을 보유 합니다. 이 인해 `Decimal` 숫자 부동 소수점 형식 보다 메모리에 대 한 보다 정확한 표현 (`Single` 고 `Double`).  
  
-   **성능.** `Decimal` 데이터 형식은 모든 숫자 형식의 가장 느린 작업입니다. 데이터 형식을 선택 하기 전에 성능에 대해 전체 자릿수의 중요성을 평가 해야 합니다.  
  
-   **확대 합니다.** 합니다 `Decimal` 데이터 형식으로 확장 되는지를 `Single` 또는 `Double`합니다. 즉, 변환할 수 있습니다 `Decimal` 발생 하지 않고 이러한 형식 중 하나에 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
-   **뒤에 오는 0입니다.** Visual Basic의 후행 0을 저장 하지 않습니다는 `Decimal` 리터럴. 그러나는 `Decimal` 변수 계산을 통해 얻은 후행 0 문자를 유지 합니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     출력 `MsgBox` 앞의 예제에는 다음과 같습니다.  
  
     d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4  
  
-   **형식 문자입니다.** 리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다. 식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.  
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="range"></a>범위  
 사용 해야 할 수는 `D` 를 큰 값으로 할당 하는 문자를 입력을 `Decimal` 변수 또는 상수입니다. 컴파일러는 리터럴으로 해석 하기 때문에이 요구 사항은 `Long` 않으면 리터럴 형식 문자는 다음 예제와 같이 리터럴, 따릅니다.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 에 대 한 선언을 `bigDec1` 에 할당 된 값에 대 한 범위 내에 포함 하기 때문에 오버플로 생성 하지 않습니다 `Long`합니다. 합니다 `Long` 값을 할당할 수는 `Decimal` 변수입니다.  
  
 에 대 한 선언을 `bigDec2` 에 할당 된 값에 대 한 너무 크기 때문에 오버플로 오류가 `Long`합니다. 숫자 리터럴 처음으로 해석할 수 없는 때문에 `Long`를 할당할 수 없습니다는 `Decimal` 변수입니다.  
  
 에 대 한 `bigDec3`, 리터럴 형식 문자 `D` 리터럴을 해석 하도록 컴파일러에 강제 적용 하 여 문제 해결을 `Decimal` 대신으로 `Long`.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
