---
title: '| 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2018
ms.locfileid: "46706150"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2cc6d-102">| 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2cc6d-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="2cc6d-103">이항 `|` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6d-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="2cc6d-104">정수 형식의 경우 `|` 연산자는 해당 피연산자의 비트 OR 연산자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6d-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="2cc6d-105">`bool` 피연산자의 경우 `|` 연산자는 해당 피연산자의 논리적 OR 연산을 계산합니다. 즉, 피연산자가 둘 다 `false`일 경우에만 결과가 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6d-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc6d-106">설명</span><span class="sxs-lookup"><span data-stu-id="2cc6d-106">Remarks</span></span>  
 <span data-ttu-id="2cc6d-107">이진 `|` 연산자는 [기존 OR 연산자](conditional-or-operator.md) `||`와 달리 첫 번째 연산자의 값에 상관없이 두 피연산자를 모두 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6d-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="2cc6d-108">사용자 정의 형식은 `|` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2cc6d-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cc6d-109">예</span><span class="sxs-lookup"><span data-stu-id="2cc6d-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2cc6d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cc6d-110">See Also</span></span>

- [<span data-ttu-id="2cc6d-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="2cc6d-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2cc6d-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2cc6d-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2cc6d-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="2cc6d-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
