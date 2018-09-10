---
title: '&lt;= 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: afbb932c1be010790236bec73a36acf0f01b97f4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270210"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="21cfd-102">&lt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="21cfd-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="21cfd-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 작거나 같을 경우에 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “작거나 같음” 관계 연산자(`<=`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21cfd-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21cfd-104">설명</span><span class="sxs-lookup"><span data-stu-id="21cfd-104">Remarks</span></span>  
 <span data-ttu-id="21cfd-105">사용자 정의 형식은 `<=` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cfd-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="21cfd-106">자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21cfd-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="21cfd-107">`<=` 연산자가 오버로드되면 [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cfd-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="21cfd-108">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21cfd-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21cfd-109">예</span><span class="sxs-lookup"><span data-stu-id="21cfd-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="21cfd-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21cfd-110">See Also</span></span>

- [<span data-ttu-id="21cfd-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="21cfd-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="21cfd-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="21cfd-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="21cfd-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="21cfd-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="21cfd-114">explicit</span><span class="sxs-lookup"><span data-stu-id="21cfd-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
