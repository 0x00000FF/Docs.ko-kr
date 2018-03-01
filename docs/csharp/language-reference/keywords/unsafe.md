---
title: "unsafe(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fffbe36e39d279b2364b178188381a403c8ff86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-reference"></a>unsafe(C# 참조)
`unsafe` 키워드는 포인터와 관련된 모든 작업에 필요한 안전하지 않은 컨텍스트를 나타냅니다. 자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.  
  
 형식 또는 멤버 선언에서 `unsafe` 한정자를 사용할 수 있습니다. 따라서 형식 또는 멤버의 전체 텍스트 범위가 안전하지 않은 컨텍스트로 간주됩니다. 예를 들어 다음은 `unsafe` 한정자를 사용하여 선언된 메서드입니다.  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 안전하지 않은 컨텍스트의 범위는 매개 변수 목록에서 메서드의 끝까지 확장되므로 매개 변수 목록에 포인터를 사용할 수도 있습니다.  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 안전하지 않은 블록을 통해 이 블록 내에서 안전하지 않은 코드를 사용할 수도 있습니다. 예:  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 안전하지 않은 코드를 컴파일하려면 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션을 지정해야 합니다. 안전하지 않은 코드는 공용 언어 런타임에서 확인할 수 없습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
