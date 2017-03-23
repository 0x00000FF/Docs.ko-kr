---
title: "액세스 가능성 수준(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "액세스 한정자[C#], 액세스 수준"
  - "액세스 수준"
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 액세스 가능성 수준(C# 참조)
액세스 한정자\([public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 [private](../../../csharp/language-reference/keywords/private.md)\)를 사용하여 다음의 선언된 액세스 가능성 수준 중 하나를 멤버에 지정할 수 있습니다.  
  
|선언된 액세스 가능성|의미|  
|-----------------|--------|  
|`public`|액세스가 제한되지 않습니다.|  
|`protected`|포함하는 클래스 또는 여기에서 파생된 형식으로 액세스가 제한됩니다.|  
|`internal`|액세스가 현재 어셈블리로 제한됩니다.|  
|`protected` `internal`|현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 액세스가 제한됩니다.|  
|`private`|액세스가 포함하는 형식으로 제한됩니다.|  
  
 `protected` `internal` 조합을 사용할 때를 제외하고는 멤버 또는 형식 하나에 액세스 한정자를 한 개만 지정할 수 있습니다.  
  
 네임스페이스에는 액세스 한정자를 사용할 수 없습니다.  따라서 네임스페이스에는 액세스 제한이 없습니다.  
  
 멤버 선언이 발생하는 컨텍스트에 따라 특정한 선언된 액세스 가능성만 허용됩니다.  멤버 선언에 액세스 한정자를 지정하지 않은 경우에는 기본 액세스 가능성이 사용됩니다.  
  
 다른 형식에 중첩되지 않은 최상위 형식에는 `internal` 또는 `public` 액세스 가능성만 지정할 수 있습니다.  이 형식에 대한 기본 액세스 가능성은 `internal`입니다.  
  
 다른 형식의 멤버인 중첩 형식에는 다음 표에 표시된 것과 같은 선언된 액세스 가능성을 지정할 수 있습니다.  
  
|다음 형식의 멤버|기본 멤버 액세스 가능성|멤버에 대해 허용되는 선언된 액세스 가능성|  
|---------------|-------------------|-----------------------------|  
|`enum`|`public`|없음|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected` `internal`|  
|`interface`|`public`|없음|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 중첩 형식의 액세스 가능성은 [액세스 가능 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)에 따라 달라지는데, 이 액세스 가능 도메인은 멤버의 선언된 액세스 가능성 및 직접 포함하는 형식의 액세스 가능 도메인에 의해 결정됩니다.  그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [액세스 가능성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)