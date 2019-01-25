---
title: '&lt;type1&gt;&#39;&lt;typename&gt; &#39; 를 구현 해야 합니다 &#39; &lt;methodname&gt; &#39; 인터페이스 &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642444"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39; 를 구현 해야 합니다 &#39; &lt;methodname&gt; &#39; 인터페이스 &#39; &lt;interfacename&gt;&#39;
클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.  
  
 **오류 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  동일한 이름 및 서명을 인터페이스에 정의 된 대로 사용 하 여 프로시저를 선언 합니다. 포함 해야 적어도 `End Function` 또는 `End Sub` 문입니다.  
  
2.  추가 `Implements` 의 끝에 절을 `Function` 또는 `Sub` 문입니다. 예를 들어:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>참고자료
- [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)
- [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
