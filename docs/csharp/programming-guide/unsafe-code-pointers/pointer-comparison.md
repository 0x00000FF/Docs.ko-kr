---
title: 포인터 비교(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: fa980c944159c477c333762ffad569332fba9402
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086641"
---
# <a name="pointer-comparison-c-programming-guide"></a>포인터 비교(C# 프로그래밍 가이드)
다음 연산자를 적용하여 임의 형식의 포인터를 비교할 수 있습니다.  
  
 **==   !=   \<   >   \<=   >=**  
  
 비교 연산자는 부호 없는 정수처럼 두 피연산자의 주소를 비교합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>샘플 출력  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [C# 연산자](../../../csharp/language-reference/operators/index.md)  
- [포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [유형](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
