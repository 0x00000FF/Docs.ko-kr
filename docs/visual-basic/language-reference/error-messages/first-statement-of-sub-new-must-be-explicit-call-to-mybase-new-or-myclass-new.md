---
title: '이 첫 번째 문은 &#39;Sub&#39; 에 대 한 명시적 호출 이어야 합니다 &#39;MyBase.New&#39; 또는 &#39;m y&#39; 때문에 &#39; &lt;constructorname&gt; &#39; 기본 클래스에 &#39; &lt;baseclassname&gt; &#39; 의 &#39; &lt;derivedclassname&gt; &#39; obsolete로 표시 되어: &#39; &lt;errormessage&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 9d07a68fd8d9790178427c512375323f23f46772
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566780"
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>이 첫 번째 문은 &#39;Sub&#39; 에 대 한 명시적 호출 이어야 합니다 &#39;MyBase.New&#39; 또는 &#39;m y&#39; 때문에 &#39; &lt;constructorname&gt; &#39; 기본 클래스에 &#39; &lt;baseclassname&gt; &#39; 의 &#39; &lt;derivedclassname&gt; &#39; obsolete로 표시 되어: &#39; &lt;errormessage&gt;&#39;
클래스 생성자는 기본 클래스 생성자를 명시적으로 호출하지 않으며, 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.  
  
 파생된 클래스 생성자는 기본 클래스 생성자를 호출 하지 않으면 Visual Basic에서는 매개 변수가 없는 기본 클래스 생성자에 대 한 암시적 호출을 생성 하려고 합니다. 인수 없이 호출할 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없습니다 있으면 Visual Basic에서 암시적 호출을 생성할 수 없습니다. 이 경우 필요한 생성자는 기본적으로 <xref:System.ObsoleteAttribute> 특성을 사용 하므로 Visual Basic에서 호출할 수 없습니다.  
  
 프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다. 이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다. `True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다. `False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 **오류 ID:** BC30920  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.  
  
2.  `MyBase.New()` 또는 `MyClass.New()` 에 대한 호출을 파생 클래스에 `Sub New` 의 첫 번째 문으로 포함합니다.  
  
## <a name="see-also"></a>참고자료
- [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)

