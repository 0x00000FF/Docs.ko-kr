---
title: 사용자 정의 데이터 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814200"
---
# <a name="user-defined-data-type"></a>사용자 정의 데이터 형식
사용자가 정의한 형식으로 데이터를 저장 합니다. `Structure` 문은 형식을 정의 합니다.  
  
 이전 버전의 Visual Basic 사용자 정의 형식 (UDT)를 지원합니다. 현재 버전에는 UDT를 확장 한 *구조*합니다. 구조체는 하나 이상의 연결 *멤버* 다양 한 데이터 형식입니다. Visual Basic는 해당 멤버를 개별적으로 액세스할 수도 있습니다 하지만 단일 단위로 구조를 처리 합니다.  
  
## <a name="remarks"></a>설명  
 정의 하 고 다양 한 데이터 형식을 단일 단위로 결합 해야 할 때 또는 none는 기본 데이터 형식 요구에 부응 하기 때 구조 데이터 형식을 사용 합니다.  
  
 구조 데이터 형식의 기본 값 각 해당 멤버의 기본 값의 조합으로 구성 됩니다.  
  
## <a name="declaration-format"></a>선언 형식  
 구조체 선언 시작 합니다 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md) 종료는 `End Structure` 문. `Structure` 문은 구조체가 정의 하는 데이터 형식 식별자는 구조체의 이름을 제공 합니다. 코드의 다른 부분 변수, 매개 변수 및 함수 반환 값이이 구조체의 데이터 형식으로 선언 하려면이 식별자를 사용할 수 있습니다.  
  
 사이의 선언 합니다 `Structure` 및 `End Structure` 문을 구조체의 멤버를 정의 합니다.  
  
## <a name="member-access-levels"></a>멤버 액세스 수준  
 사용 하 여 모든 멤버를 선언 해야 합니다는 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) 또는 같은 액세스 수준을 지정 하는 문 [공용](../../../visual-basic/language-reference/modifiers/public.md)에 [Friend](../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../visual-basic/language-reference/modifiers/private.md). 사용 하는 경우는 `Dim` 문, 공용 액세스 수준 기본값입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **메모리 사용량** 모든 복합 데이터 형식에서와 마찬가지로 해당 멤버의 일반 저장소 할당량을 함께 추가 하 여 구조체의 총 메모리 소비량을 안전 하 게 계산할 수 없습니다. 또한 가정할 수 없습니다는 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일 합니다. 구조체의 저장소 레이아웃을 제어 해야 하는 경우 적용할 수 있습니다 합니다 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 `Structure` 문입니다.  
  
-   **Interop 고려 사항입니다.** .NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는, 예를 들어 자동화 개체나 COM 개체를 다른 환경에서 사용자 정의 형식을 Visual Basic을 사용 하 여 호환 되지 않음을 명심 형식을 구성 합니다.  
  
-   **확대 합니다.** 자동 변환이 없는 구조체 데이터 형식에서입니다. 사용 하 여 구조체에서 변환 연산자를 정의할 수 있습니다 합니다 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), 고 되도록 각 변환 연산자를 선언할 수 있습니다 `Widening` 또는 `Narrowing`합니다.  
  
-   **형식 문자입니다.** 구조 데이터 형식 식별자 형식 문자가 없거나 리터럴 형식 문자에 있습니다.  
  
-   **Framework 형식입니다.** .NET Framework에는 해당 형식이 없습니다. .NET Framework 클래스에서 상속 하는 모든 구조 <xref:System.ValueType?displayProperty=nameWithType>에 있지만에 해당 하는 개별 구조가 없습니다 <xref:System.ValueType?displayProperty=nameWithType>합니다.  
  
## <a name="example"></a>예제  
 다음 패러다임 구조체 선언의 개요를 보여 줍니다.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)
- [확장](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
