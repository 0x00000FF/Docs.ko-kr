---
title: "-= 연산자(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "-=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-= 연산자(빼기 할당)[C#]"
  - "빼기 할당 연산자(-=)[C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# -= 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

빼기 할당 연산자입니다.  
  
## 설명  
 다음과 같이 `-=` 대입 연산자를 사용하는 식은  
  
```  
x -= y  
```  
  
 동일한 함수는  
  
```  
x = x - y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [\- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)의 의미는 `x` 및 `y`의 형식에 따라 달라집니다\(숫자 피연산자의 빼기, 대리자 피연산자의 대리자 제거 등\).  
  
 `-=` 연산자는 직접 오버로드될 수 없지만, 사용자 정의 형식으로 [\- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
 또한 \-\= 연산자는 이벤트를 구독 취소하기 위해 C\#에서 사용됩니다.  자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하십시오.  
  
## 예제  
 [!CODE [csRefOperators#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#6)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)