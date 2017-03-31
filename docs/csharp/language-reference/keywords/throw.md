---
title: "throw(C# 참조) | Microsoft 문서"
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 095a86f5ab2ce50f5931643161a44b5759583e4e
ms.lasthandoff: 03/13/2017

---
# <a name="throw-c-reference"></a>throw(C# 참조)
프로그램 실행 중 예외 발생 신호를 보냅니다.  
  
## <a name="remarks"></a>주의

`throw`의 구문은 다음과 같습니다.

```csharp
throw [e]
```
여기서 `e`는 <xref:System.Exception?displayProperty=fullName>에서 파생된 클래스의 인스턴스입니다. 다음 예제에서는 `throw` 문을 사용하여 `GetNumber`라는 메서드에 전달된 인수가 내부 배열의 유효한 인덱스에 해당하지 않는 경우 @System.IndexOutOfRangeException을 throw합니다.

[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

그러면 메서드 호출자가 `try-catch` 또는 `try-catch-finally` 블록을 사용하여 throw된 예외를 처리합니다. 다음 예제에서는 `GetNumber` 메서드에 의해 throw된 예외를 처리합니다.

[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>예외 다시 throw

`catch` 블록에서 `throw`를 사용하여 `catch` 블록에서 처리된 예외를 다시 throw할 수도 있습니다.  이 경우 `throw`는 예외 피연산자를 사용하지 않습니다. 이는 메서드가 호출자의 인수를 다른 일부 라이브러리 메서드에 전달하고 라이브러리 메서드가 호출자에게 전달되어야 하는 예외를 throw하는 경우에 가장 유용합니다. 예를 들어 다음 예제에서는 초기화되지 않은 문자열의 첫 번째 문자를 검색하려고 할 때 throw되는 @System.NullReferenceException을 다시 throw합니다. 

[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> `catch` 블록의 `throw e` 구문을 사용하여 호출자에게 전달하는 새 예외를 인스턴스화할 수도 있습니다. 이 경우 @System.Exception.Stacktrace 속성에서 제공되는 원래 예외의 스택 추적이 유지되지 않습니다.
 
## <a name="the-throw-expression"></a>`throw` 식

C# 7부터 `throw`를 문뿐만 아니라 식으로 사용할 수 있습니다. 이렇게 하면 이전에 지원되지 않은 상황에서 예외를 throw할 수 있습니다. 여기에는 다음이 포함됩니다.

- [조건 연산자](../operators/conditional-operator.md). 다음 예제에서는 `throw` 식을 사용하여 메서드에 빈 문자열 배열이 전달된 경우 @System.ArgumentException을 throw합니다. C# 7 이전에는 이 논리가 `if`/`else` 문에 표시되어야 합니다.

   [!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [Null 병합 연산자](../operators/null-conditional-operator.md). 다음 예제에서는 `throw` 식에 Null 병합 연산자를 사용하여 `Name` 속성에 할당된 문자열이 `null`인 경우 예외를 throw합니다.
 
   [!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- 식 본문 [람다](../../lambda-expressions.md) 또는 메서드. 다음 예제에서는 @System.DateTime 값으로 변환이 지원되지 않기 때문에 @System.InvalidCastException을 throw하는 식 본문 메서드를 보여 줍니다.
 
   [!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [C++의 try, catch 및 throw 문](../../../csharp/language-reference/keywords/try-catch.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [예외 처리 문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [방법: 명시적으로 예외 Throw](https://msdn.microsoft.com/library/xhcbs8fz)
