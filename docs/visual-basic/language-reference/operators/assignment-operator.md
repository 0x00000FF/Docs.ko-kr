---
title: = 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 5e6d34802f5f82373d0e8176f3b732a327c55d01
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964996"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="daebc-102">= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="daebc-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="daebc-103">변수 또는 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daebc-104">구문</span><span class="sxs-lookup"><span data-stu-id="daebc-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="daebc-105">요소</span><span class="sxs-lookup"><span data-stu-id="daebc-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="daebc-106">모든 쓰기 가능한 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="daebc-107">모든 리터럴, 상수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daebc-108">설명</span><span class="sxs-lookup"><span data-stu-id="daebc-108">Remarks</span></span>  
 <span data-ttu-id="daebc-109">등호의 왼쪽 요소 (`=`) 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="daebc-110">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="daebc-111">`=` 연산자 왼쪽의 속성 값 변수는 오른쪽에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="daebc-112">`=` 연산자 비교 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="daebc-113">자세한 내용은 참조 하세요 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="daebc-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="daebc-114">Overloading</span></span>  
 <span data-ttu-id="daebc-115">`=` 대입 연산자가 아니라 관계 비교 연산자로 연산자를 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="daebc-116">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daebc-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="daebc-117">예제</span><span class="sxs-lookup"><span data-stu-id="daebc-117">Example</span></span>  
 <span data-ttu-id="daebc-118">다음 예제에서는 대입 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="daebc-119">오른쪽 값을 왼쪽에 있는 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daebc-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="daebc-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="daebc-120">See also</span></span>
- [<span data-ttu-id="daebc-121">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="daebc-122">\*= 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="daebc-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="daebc-124">-= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="daebc-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="daebc-125">/ = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="daebc-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="daebc-126">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="daebc-127">^= 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="daebc-128">문(C++)</span><span class="sxs-lookup"><span data-stu-id="daebc-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="daebc-129">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="daebc-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="daebc-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="daebc-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="daebc-131">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="daebc-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
