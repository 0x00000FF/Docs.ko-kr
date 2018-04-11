---
title: Default(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a>Default(Visual Basic)
해당 클래스, 구조체 또는 인터페이스의 기본 속성으로 속성을 식별합니다.  
  
## <a name="remarks"></a>설명  
 클래스, 구조체 또는 인터페이스와 해당 속성 중 하나만 지정할 수는 *기본 속성*로 속성은 하나 이상의 매개 변수를 사용 합니다. 코드는 멤버를 지정 하지 않고 클래스 또는 구조체에 대 한 참조를 만드는 경우 Visual Basic의 기본 속성에 해당 참조를 확인 합니다.  
  
 기본 속성 소스 코드 문자가 약간 저하 될 수 있지만 코드를 읽기 더 어렵게 만들 수 있습니다. 클래스 또는 구조체 이름에 대 한 참조는 시 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 않아야 특정 참조 하는 클래스 또는 구조체를 자체 또는 기본 속성에 액세스 하는지 여부입니다. 컴파일러 오류 또는 미묘한 런타임에 논리 오류가 발생할 수 있습니다.  
  
 항상 사용 하 여 기본 속성 오류의 가능성을 어느 정도 줄일 수 있습니다는 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.  
  
 에서 사용 하는 미리 정의 된 클래스 또는 구조체 코드를 결정 해야 기본 속성이 여부와 그럴 경우 계획 이라면 해당 이름이 무엇 인지 합니다.  
  
 이러한 단점으로 인해 기본 속성을 정의 하지 않는 고려해 야 합니다. 코드의 가독성을 높이기 위해 또한 항상 모든 속성에 명시적으로 참조를 고려 해야, 심지어 기본 속성 키를 누릅니다.  
  
 `Default` 한정자는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [방법: 선언 하 고 Visual Basic의 기본 속성 호출](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
