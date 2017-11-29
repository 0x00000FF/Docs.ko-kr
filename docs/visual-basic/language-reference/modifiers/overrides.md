---
title: Overrides(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1bee6a6235b87a7e20f087a73bef76e0fc7bf124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overrides-visual-basic"></a>Overrides(Visual Basic)
속성 또는 프로시저가 기본 클래스에서 상속된 이름이 같은 속성 또는 프로시저를 재정의하도록 지정합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 속성 또는 프로시저 선언문에서만 `Overrides`를 사용할 수 있습니다.  
  
-   **결합 된 한정자입니다.** 동일한 선언에서 `Shadows` 또는 `Shared`와 함께 `Overrides`를 지정할 수 없습니다. 재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.  
  
-   **일치 하는 서명 합니다.** 이 선언의 서명은 정확히 일치 해야는 *서명* 속성 또는 프로시저를 재정의 합니다. 즉, 매개 변수 목록에 동일한 데이터 형식의 매개 변수가 동일한 개수 및 순서로 포함되어야 합니다.  
  
     서명 외에도 재정의 선언이 다음과 정확히 일치해야 합니다.  
  
    -   액세스 수준  
  
    -   반환 형식(있는 경우)  
  
-   **제네릭 서명입니다.** 제네릭 프로시저의 경우 서명에 형식 매개 변수 개수가 포함됩니다. 따라서 해당 측면에서도 재정의 선언이 기본 클래스 버전과 일치해야 합니다.  
  
-   **추가 일치.** 기본 클래스 버전과의 서명 일치 외에도 이 선언은 다음 측면에서 기본 클래스 버전과 일치해야 합니다.  
  
    -   액세스 수준 한정자 (예: [공용](../../../visual-basic/language-reference/modifiers/public.md))  
  
    -   각 매개 변수의 전달 메커니즘 ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))  
  
    -   제네릭 프로시저의 각 형식 매개 변수에 대한 제약 조건 목록  
  
-   **숨기기와 재정의 합니다.** 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 참조 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.  
  
 `Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.  
  
 `Overrides` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)
