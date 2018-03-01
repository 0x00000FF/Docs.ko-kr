---
title: "&gt;= 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020c2bd8756899908681ab72cac7aa2a203c6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="9567c-102">&gt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9567c-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="9567c-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 크거나 같을 경우에 `true`를 반환하고, 그렇지 않으면 `false`를 반환하는 “크거나 같음" 관계 연산자(`>=`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9567c-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9567c-104">설명</span><span class="sxs-lookup"><span data-stu-id="9567c-104">Remarks</span></span>  
 <span data-ttu-id="9567c-105">사용자 정의 형식은 `>=` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9567c-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="9567c-106">자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9567c-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="9567c-107">`>=` 연산자가 오버로드되면 [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9567c-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="9567c-108">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9567c-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9567c-109">예제</span><span class="sxs-lookup"><span data-stu-id="9567c-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9567c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9567c-110">See Also</span></span>  
 [<span data-ttu-id="9567c-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9567c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9567c-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9567c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9567c-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="9567c-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
