---
title: '|= 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: ad8d5c8e65c2768d1dfc4644323e801189a4399c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245339"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="46bd3-102">|= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="46bd3-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="46bd3-103">OR 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="46bd3-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46bd3-104">설명</span><span class="sxs-lookup"><span data-stu-id="46bd3-104">Remarks</span></span>  
 <span data-ttu-id="46bd3-105">다음과 같은 `|=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="46bd3-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="46bd3-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="46bd3-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="46bd3-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="46bd3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="46bd3-108">[&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)는 정수 피연산자에 대한 비트 논리적 OR 연산과 부울 피연산자에 대한 논리적 OR 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="46bd3-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="46bd3-109">`|=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="46bd3-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46bd3-110">예제</span><span class="sxs-lookup"><span data-stu-id="46bd3-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="46bd3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46bd3-111">See Also</span></span>

- [<span data-ttu-id="46bd3-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="46bd3-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="46bd3-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="46bd3-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="46bd3-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="46bd3-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
