---
title: "const(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "const_CSharpKeyword"
  - "const"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "const 키워드[C#]"
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# const(C# 참조)
상수 필드 또는 지역 상수를 선언할 때는 `const` 키워드를 사용합니다.  상수 필드 및 지역 상수는 변수가 아니며 수정할 수 없습니다.  상수는 숫자, 부울 값, 문자열 또는 null 참조일 수 있습니다.  언제든지 변경될 수 있는 정보를 나타낼 때는 상수를 만들지 마세요.  예를 들어, 상수 필드를 사용하여 서비스의 가격, 제품 버전 번호 또는 회사의 브랜드 이름을 저장하지 마세요.  이러한 값은 시간이 지남에 따라 변경될 수 있으며, 컴파일러는 상수를 전파하므로 변경 내용을 보기 위해서는 라이브러리를 사용하여 컴파일된 다른 코드를 다시 컴파일해야 합니다.  [readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드도 참조하세요.  예를 들면 다음과 같습니다.  
  
```  
  
      const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## 설명  
 상수 선언 형식은 선언에서 제공하는 멤버의 형식을 지정합니다.  지역 상수 또는 상수 필드의 이니셜라이저는 대상 형식으로 암시적으로 변환될 수 있는 상수 식이어야 합니다.  
  
 상수 식은 컴파일 타임에 완전히 계산될 수 있는 식입니다.  따라서 참조 형식의 상수에 대해 가능한 값은 `string` 및 null 참조뿐입니다.  
  
 상수 선언에서는 다음과 같이 여러 상수를 선언할 수 있습니다.  
  
```  
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 `static` 한정자는 상수 선언에는 허용되지 않습니다.  
  
 상수는 다음과 같이 상수 식에 참여할 수 있습니다.  
  
```  
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  [readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드는 `const` 키워드와 다릅니다.  `const` 필드는 필드 선언에서만 초기화될 수 있습니다.  `readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.  따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.  또한 `const` 필드가 컴파일 타임 상수라고 하더라도 `readonly` 필드는 다음 줄에서와 같이 런타임 상수에 사용될 수 있습니다. `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## 예제  
 [!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## 예제  
 이 예제에서는 상수를 로컬 변수로 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)