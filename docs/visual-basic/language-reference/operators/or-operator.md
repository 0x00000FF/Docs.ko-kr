---
title: Or 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835299"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="59f9f-102">Or 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59f9f-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="59f9f-103">두 논리합 연산을 수행 `Boolean` 식이나 두 숫자 식의 비트 논리합 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="59f9f-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="59f9f-105">요소</span><span class="sxs-lookup"><span data-stu-id="59f9f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="59f9f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="59f9f-106">Required.</span></span> <span data-ttu-id="59f9f-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="59f9f-108">에 대 한 `Boolean` 반면 `result` 가 2의 포함 논리합 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="59f9f-109">비트 연산의 경우 `result` 두 숫자 비트 패턴의 포함 비트 논리합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="59f9f-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="59f9f-110">Required.</span></span> <span data-ttu-id="59f9f-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="59f9f-112">필수.</span><span class="sxs-lookup"><span data-stu-id="59f9f-112">Required.</span></span> <span data-ttu-id="59f9f-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59f9f-114">설명</span><span class="sxs-lookup"><span data-stu-id="59f9f-114">Remarks</span></span>  
 <span data-ttu-id="59f9f-115">에 대 한 `Boolean` 반면 `result` 됩니다 `False` 두 경우에 `expression1` 및 `expression2` 평가 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="59f9f-116">다음 표에서 설명 하는 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="59f9f-117">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="59f9f-117">If `expression1` is</span></span>|<span data-ttu-id="59f9f-118">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="59f9f-118">And `expression2` is</span></span>|<span data-ttu-id="59f9f-119">변수의 `result` 는</span><span class="sxs-lookup"><span data-stu-id="59f9f-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="59f9f-120">에 `Boolean` 비교는 `Or` 연산자 프로시저 호출을 포함할 수 있는 두 식을 계산 하 고 항상 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="59f9f-121">합니다 [OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md) 수행 *단락 (short-circuiting)*, 즉 `expression1` 됩니다 `True`, 다음 `expression2` 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="59f9f-122">비트 연산의 경우 합니다 `Or` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="59f9f-123">경우에 비트 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="59f9f-123">If bit in `expression1` is</span></span>|<span data-ttu-id="59f9f-124">비트 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="59f9f-124">And bit in `expression2` is</span></span>|<span data-ttu-id="59f9f-125">비트 `result` 됩니다</span><span class="sxs-lookup"><span data-stu-id="59f9f-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="59f9f-126">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-126">1</span></span>|<span data-ttu-id="59f9f-127">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-127">1</span></span>|<span data-ttu-id="59f9f-128">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-128">1</span></span>|  
|<span data-ttu-id="59f9f-129">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-129">1</span></span>|<span data-ttu-id="59f9f-130">0</span><span class="sxs-lookup"><span data-stu-id="59f9f-130">0</span></span>|<span data-ttu-id="59f9f-131">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-131">1</span></span>|  
|<span data-ttu-id="59f9f-132">0</span><span class="sxs-lookup"><span data-stu-id="59f9f-132">0</span></span>|<span data-ttu-id="59f9f-133">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-133">1</span></span>|<span data-ttu-id="59f9f-134">1</span><span class="sxs-lookup"><span data-stu-id="59f9f-134">1</span></span>|  
|<span data-ttu-id="59f9f-135">0</span><span class="sxs-lookup"><span data-stu-id="59f9f-135">0</span></span>|<span data-ttu-id="59f9f-136">0</span><span class="sxs-lookup"><span data-stu-id="59f9f-136">0</span></span>|<span data-ttu-id="59f9f-137">0</span><span class="sxs-lookup"><span data-stu-id="59f9f-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="59f9f-138">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="59f9f-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="59f9f-139">Data Types</span></span>  
 <span data-ttu-id="59f9f-140">피연산자 하나 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (– 1 `True` 0에 대 한 `False`) 비트 연산을 수행 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="59f9f-141">에 `Boolean` 반면 데이터 형식의 결과 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="59f9f-142">결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식에서 비트 비교 `expression1` 고 `expression2`입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="59f9f-143">"관계 및 비트 비교" 표를 참조 하세요 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="59f9f-144">오버로딩</span><span class="sxs-lookup"><span data-stu-id="59f9f-144">Overloading</span></span>  
 <span data-ttu-id="59f9f-145">합니다 `Or` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="59f9f-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="59f9f-146">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="59f9f-147">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59f9f-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59f9f-148">예제</span><span class="sxs-lookup"><span data-stu-id="59f9f-148">Example</span></span>  
 <span data-ttu-id="59f9f-149">다음 예제에서는 `Or` 두 식에 포함 논리합 연산을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="59f9f-150">결과 `Boolean` 나타내는 두 식 중 하나 인지 `True`.</span><span class="sxs-lookup"><span data-stu-id="59f9f-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="59f9f-151">앞의 예제 결과 생성 `True`, `True`, 및 `False`, 각각.</span><span class="sxs-lookup"><span data-stu-id="59f9f-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59f9f-152">예제</span><span class="sxs-lookup"><span data-stu-id="59f9f-152">Example</span></span>  
 <span data-ttu-id="59f9f-153">다음 예제에서는 `Or` 연산자에서 두 숫자 식의 개별 비트를 포함 논리합 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="59f9f-154">피연산자의 해당 비트 중 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="59f9f-155">앞의 예제는 각각 10, 14 및 14의 결과 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="59f9f-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f9f-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="59f9f-156">See also</span></span>

- [<span data-ttu-id="59f9f-157">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59f9f-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="59f9f-158">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="59f9f-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="59f9f-159">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="59f9f-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="59f9f-160">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="59f9f-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="59f9f-161">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="59f9f-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
