---
title: '&#39;설정&#39; 속성의 접근자 &#39; &lt;propertyname&gt; &#39; 에 액세스할 수 없습니다'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: a543506b06742f3ee9101edbac962e761ddd531d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606571"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;설정&#39; 속성의 접근자 &#39; &lt;propertyname&gt; &#39; 에 액세스할 수 없습니다
문에서 속성에 대 한 액세스 되지 않은 경우 속성의 값을 저장 하려고 `Set` 프로시저입니다.  
  
 경우는 [Set 문을](../../../visual-basic/language-reference/statements/set-statement.md) 수준 보다 더 제한적인 액세스를 사용 하 여 표시 됩니다 해당 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md), 다음과 같은 경우 속성 값을 설정 하려는 시도가 실패할 수 있습니다.  
  
-   합니다 `Set` 문이 표시 됩니다 [개인](../../../visual-basic/language-reference/modifiers/private.md) 호출 코드에서 클래스 또는 속성이 정의 된 구조체를 벗어나는 것입니다.  
  
-   합니다 `Set` 문이 표시 됩니다 [보호 된](../../../visual-basic/language-reference/modifiers/protected.md) 클래스 또는 속성이 정의 되어 있는 구조에 없는 또는 파생된 클래스에서 호출 하는 코드는 합니다.  
  
-   합니다 `Set` 문이 표시 됩니다 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 고 호출 코드에서 속성이 정의 된 동일한 어셈블리에 없는 합니다.  
  
 **오류 ID:** BC31102  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   속성을 정의 하는 소스 코드 제어에 있는 경우 선언을 살펴보십시오는 `Set` 해당 속성과 동일한 액세스 레벨을 사용 하 여 프로시저입니다.  
  
-   속성을 정의 하는 소스 코드 제어 없는 또는 제한 해야 하는 경우는 `Set` 프로시저 액세스 수준 속성 자체에 쉽게 액세스할 수 있는 코드의 영역으로 속성 값을 설정 하는 문을 이동 하려고 보다는 속성입니다.  
  
## <a name="see-also"></a>참고자료
- [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [방법: 액세스 수준이 혼합된 된 속성 선언](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
