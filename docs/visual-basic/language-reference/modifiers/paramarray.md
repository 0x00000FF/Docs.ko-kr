---
title: ParamArray(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816665"
---
# <a name="paramarray-visual-basic"></a>ParamArray(Visual Basic)
프로시저 매개 변수가 지정 된 형식의 요소 선택적 배열 임을 지정 합니다. `ParamArray` 매개 변수 목록의 마지막 매개 변수 에서만 사용할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `ParamArray` 프로시저에 임의 개수의 인수를 전달할 수 있습니다. A `ParamArray` 매개 변수는 항상 사용 하 여 선언 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.  
  
 하나 이상의 인수를 제공할 수 있습니다는 `ParamArray` 적절 한 데이터의 배열을 전달 하 여 매개 변수를 쉼표로 구분 된 목록을 입력 값 또는 아무 것도 전혀 합니다. 자세한 내용은의 "ParamArray 호출"를 참조 하세요 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.  
  
> [!IMPORTANT]
>  무한정 커질 수 있는 배열을 사용 하 여 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다. 호출 코드에서 매개 변수 배열에 동의 하는 경우 해당 길이 테스트 하 고 응용 프로그램에 비해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.  
  
 `ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고자료

- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
