---
title: "이 &#39;의 첫 번째 문 새 하위 &#39; 명시적으로 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; 때문에 &#39; &lt;constructorname&gt;&#39; 기본 클래스 &#39;&lt; baseclassname&gt;&#39;의 형식이 &#39;&lt; derivedclassname&gt;&#39; 것으로 표시 됩니다: &#39;&lt; errormessage&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords: BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>이 &#39;의 첫 번째 문 새 하위 &#39; 명시적으로 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; 때문에 &#39; &lt;constructorname&gt;&#39; 기본 클래스 &#39;&lt; baseclassname&gt;&#39;의 형식이 &#39;&lt; derivedclassname&gt;&#39; 것으로 표시 됩니다: &#39;&lt; errormessage&gt;&#39;
클래스 생성자는 기본 클래스 생성자를 명시적으로 호출하지 않으며, 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.  
  
 파생 클래스 생성자가 기본 클래스 생성자를 호출하지 않는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 매개 변수가 없는 암시적 기본 클래스 생성자에 대한 암시적 호출을 생성하려고 합니다. 인수 없이 호출될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 은 암시적 호출을 생성할 수 없습니다. 이 경우 필요한 생성자는 <xref:System.ObsoleteAttribute> 특성으로 표시되어 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 호출할 수 없습니다.  
  
 프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다. 이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다. `True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다. `False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 **오류 ID:** BC30920  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.  
  
2.  `MyBase.New()` 또는 `MyClass.New()` 에 대한 호출을 파생 클래스에 `Sub New` 의 첫 번째 문으로 포함합니다.  
  
## <a name="see-also"></a>참고 항목  
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
