---
title: Visual Basic의 연결 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: 789478cafc4ed7506d34fb4198531d437683075d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583302"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="44695-102">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="44695-102">Concatenation Operators in Visual Basic</span></span>

<span data-ttu-id="44695-103">연결 연산자는 여러 문자열을 단일 문자열로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="44695-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="44695-104">연결 연산자에는 `+` 및 `&`의 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="44695-105">이 두 연산자는 모두 다음 예제에 나와 있는 것처럼 기본적인 연결 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="44695-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

<span data-ttu-id="44695-106">이러한 연산자는 다음 예제에 나와 있는 것처럼 `String` 변수도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="44695-107">두 연결 연산자의 차이점</span><span class="sxs-lookup"><span data-stu-id="44695-107">Differences Between the Two Concatenation Operators</span></span>

<span data-ttu-id="44695-108">[+ 연산자](../../../../visual-basic/language-reference/operators/addition-operator.md) 에는 두 개의 숫자를 더하는 기본 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="44695-109">그러나 숫자 피연산자와 문자열 피연산자를 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="44695-110">`+` 연산자에는 수행할 작업(덧셈, 연결, 컴파일러 오류 생성, 런타임 <xref:System.InvalidCastException> throw)을 결정하는 복잡한 규칙 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="44695-111">[& 연산자](../../../../visual-basic/language-reference/operators/concatenation-operator.md) 는 `String` 피연산자에 대해서만 정의 되며 `Option Strict`의 설정에 관계 없이 항상 `String`에 대 한 피연산자를 확대 합니다.</span><span class="sxs-lookup"><span data-stu-id="44695-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="44695-112">`&` 연산자는 문자열에 대해서만 정의되며 의도하지 않은 변환을 생성할 가능성을 줄이므로 문자열 연결에 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>

## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="44695-113">성능: String 및 StringBuilder</span><span class="sxs-lookup"><span data-stu-id="44695-113">Performance: String and StringBuilder</span></span>

<span data-ttu-id="44695-114">문자열에서 연결, 삭제, 대체 등의 조작을 많이 수행하는 경우 <xref:System.Text.StringBuilder> 네임스페이스에서 <xref:System.Text> 클래스를 사용하면 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="44695-115"><xref:System.Text.StringBuilder> 개체를 만들고 초기화하려면 추가 명령이 필요하며 최종 값을 `String`으로 변환하려면 또 다른 명령이 필요하지만, <xref:System.Text.StringBuilder>가 더 빠르게 실행되기 때문에 전체적인 작업 시간은 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44695-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>

## <a name="see-also"></a><span data-ttu-id="44695-116">참조</span><span class="sxs-lookup"><span data-stu-id="44695-116">See also</span></span>

- [<span data-ttu-id="44695-117">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="44695-117">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="44695-118">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="44695-118">Types of String Manipulation Methods in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [<span data-ttu-id="44695-119">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="44695-119">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="44695-120">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="44695-120">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="44695-121">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="44695-121">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
