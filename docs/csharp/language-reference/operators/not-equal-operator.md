---
title: '!= 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b69d0b12734e690f0ba0209ccbbc7627ff92fe8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a94ec-102">!= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a94ec-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="a94ec-103">같지 않음 연산자(`!=`)는 피연산자가 같으면 false, 다르면 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="a94ec-104">문자열과 개체를 포함하여 모든 형식에 대해 같지 않음 연산자가 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="a94ec-105">사용자 정의 형식은 `!=` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a94ec-106">설명</span><span class="sxs-lookup"><span data-stu-id="a94ec-106">Remarks</span></span>  
 <span data-ttu-id="a94ec-107">미리 정의된 값 형식의 경우 같지 않음 연산자(`!=`)는 피연산자의 값이 다르면 true, 같으면 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="a94ec-108">`string`를 제외한 참조 형식의 경우 `!=`은 두 피연산자가 서로 다른 개체를 참조하면 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="a94ec-109">`string` 형식의 경우 `!=`은 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="a94ec-110">사용자 정의 값 형식은 `!=` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="a94ec-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a94ec-111">사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `!=`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="a94ec-112">`!=` 연산자가 오버로드되면 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="a94ec-113">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a94ec-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a94ec-114">예제</span><span class="sxs-lookup"><span data-stu-id="a94ec-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a94ec-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a94ec-115">See Also</span></span>  
 [<span data-ttu-id="a94ec-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a94ec-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a94ec-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a94ec-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a94ec-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a94ec-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
