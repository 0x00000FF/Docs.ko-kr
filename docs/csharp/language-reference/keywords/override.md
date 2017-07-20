---
title: "override(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 44874332454d73da712a228c3eeeb58b0343e7e7
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="override-c-reference"></a>override(C# 참조)
`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `Square` 클래스는 `Area`가 추상 `ShapesClass`에서 상속되기 때문에 `Area`의 재정의된 구현을 제공해야 합니다.  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 `override` 메서드는 기본 클래스에서 상속된 멤버의 새 구현을 제공합니다. `override` 선언에서 재정의된 메서드를 재정의된 기본 메서드라고 합니다. 재정의된 기본 메서드에는 `override` 메서드와 동일한 시그니처가 있어야 합니다. 상속에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.  
  
 비가상 또는 정적 메서드는 재정의할 수 없습니다. 재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override`여야 합니다.  
  
 `override` 선언에서는 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다. `override` 메서드 및 `virtual` 메서드 둘 다에 동일한 [액세스 수준 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)가 있어야 합니다.  
  
 `new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 수정할 수 없습니다.  
  
 재정의 속성 선언은 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 지정해야 하고, 재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.  
  
 `override` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다. `SalesEmployee` 클래스에는 추가 속성 `salesbonus`가 포함되어 있고, 이를 고려하기 위해 `CalculatePay` 메서드를 재정의합니다.  
  
 [!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
