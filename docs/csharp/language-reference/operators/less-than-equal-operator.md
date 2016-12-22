---
title: "&lt;= 연산자(C# 참조) | Microsoft Docs"
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
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= 연산자[C#]"
  - "작거나 같음 연산자(<=)[C#]"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;= 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

모든 숫자 형식과 열거형은 "작거나 같음" 관계 연산자\(`<=`\)를 정의합니다. 이 연산자는 첫째 피연산자가 둘째 피연산자보다 작거나 같으면 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  
  
## 설명  
 사용자 정의 형식으로 `<=` 연산자를 오버로드할 수 있습니다.  자세한 내용은 [연산자](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  `<=` 연산자를 오버로드할 경우에는 [\>\=](../Topic/%3E=%20Operator%20\(C%23%20Reference\).md) 연산자도 오버로드해야 합니다.  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!CODE [csRefOperators#32](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#32)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)