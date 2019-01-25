---
title: '- 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333761"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="56458-102">- 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="56458-102">- operator (C# Reference)</span></span>

<span data-ttu-id="56458-103">`-` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56458-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="56458-104">주의</span><span class="sxs-lookup"><span data-stu-id="56458-104">Remarks</span></span>

<span data-ttu-id="56458-105">단항 `-` 연산자는 모든 숫자 형식에 대해 미리 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="56458-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="56458-106">숫자 형식에 대한 단항 `-` 연산의 결과는 피연산자의 숫자 부정입니다.</span><span class="sxs-lookup"><span data-stu-id="56458-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="56458-107">이항 `-` 연산자는 첫 번째 피연산자에서 두 번째 피연산자를 빼도록 모든 숫자 및 열거형 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56458-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="56458-108">대리자 형식도 대리자 제거를 수행하는 이항 `-` 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56458-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="56458-109">사용자 정의 형식은 단항 `-` 및 이항 `-` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56458-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="56458-110">자세한 내용은 [operator 키워드](../keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56458-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="56458-111">예제</span><span class="sxs-lookup"><span data-stu-id="56458-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="56458-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56458-112">See also</span></span>

- [<span data-ttu-id="56458-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="56458-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56458-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="56458-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56458-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="56458-115">C# operators</span></span>](index.md)