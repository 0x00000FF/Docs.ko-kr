---
title: << 연산자 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: e11dbc453934f1aac4a8092cdc6539ec11f0cc21
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663178"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7622c-102">\<\< 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7622c-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="7622c-103">비트 패턴에 산술 왼쪽된 시프트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7622c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7622c-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="7622c-105">요소</span><span class="sxs-lookup"><span data-stu-id="7622c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7622c-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7622c-106">Required.</span></span> <span data-ttu-id="7622c-107">정수 계열 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-107">Integral numeric value.</span></span> <span data-ttu-id="7622c-108">결과 비트 패턴을 이동한입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="7622c-109">데이터 형식이 동일 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="7622c-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7622c-110">Required.</span></span> <span data-ttu-id="7622c-111">정수 계열 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-111">Integral numeric expression.</span></span> <span data-ttu-id="7622c-112">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="7622c-113">데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`를 `Integer`를 `UInteger`를 `Long`, 또는 `ULong`).</span><span class="sxs-lookup"><span data-stu-id="7622c-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="7622c-114">필수.</span><span class="sxs-lookup"><span data-stu-id="7622c-114">Required.</span></span> <span data-ttu-id="7622c-115">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-115">Numeric expression.</span></span> <span data-ttu-id="7622c-116">비트 패턴을 이동할 비트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="7622c-117">데이터 형식 이어야 합니다 `Integer` 변환할 또는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7622c-118">설명</span><span class="sxs-lookup"><span data-stu-id="7622c-118">Remarks</span></span>  
 <span data-ttu-id="7622c-119">산술 shifts 순환있지 않습니다 즉, 결과의 한쪽 끝에서 벗어나 이동한 비트는 반대쪽 다시 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="7622c-120">산술 왼쪽 시프트에서 결과 데이터 형식의 범위를 벗어나는 이동 하는 비트는 무시 되 고 오른쪽 비워진 비트 위치 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="7622c-121">결과 표시할 수 있는 양보다 더 많은 비트가 이동 되는 방지 하려면 Visual Basic의 값을 마스크 `amount` 의 데이터 형식에 해당 하는 크기 마스크가 있는 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="7622c-122">이러한 값의 이진 AND 시프트에 대 한 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="7622c-123">마스크 크기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="7622c-124">데이터 형식 `pattern`</span><span class="sxs-lookup"><span data-stu-id="7622c-124">Data type of `pattern`</span></span>|<span data-ttu-id="7622c-125">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="7622c-125">Size mask (decimal)</span></span>|<span data-ttu-id="7622c-126">크기 마스크 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="7622c-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="7622c-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="7622c-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="7622c-128">7</span><span class="sxs-lookup"><span data-stu-id="7622c-128">7</span></span>|<span data-ttu-id="7622c-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="7622c-129">&H00000007</span></span>|  
|<span data-ttu-id="7622c-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="7622c-130">`Short`, `UShort`</span></span>|<span data-ttu-id="7622c-131">15</span><span class="sxs-lookup"><span data-stu-id="7622c-131">15</span></span>|<span data-ttu-id="7622c-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="7622c-132">&H0000000F</span></span>|  
|<span data-ttu-id="7622c-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="7622c-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="7622c-134">31</span><span class="sxs-lookup"><span data-stu-id="7622c-134">31</span></span>|<span data-ttu-id="7622c-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="7622c-135">&H0000001F</span></span>|  
|<span data-ttu-id="7622c-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="7622c-136">`Long`, `ULong`</span></span>|<span data-ttu-id="7622c-137">63</span><span class="sxs-lookup"><span data-stu-id="7622c-137">63</span></span>|<span data-ttu-id="7622c-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="7622c-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="7622c-139">하는 경우 `amount` 가 0 이면 값 `result` 의 값과 일치 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="7622c-140">경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="7622c-141">산술 shifts 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7622c-142">합니다 `<<` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="7622c-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7622c-143">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="7622c-144">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7622c-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7622c-145">예제</span><span class="sxs-lookup"><span data-stu-id="7622c-145">Example</span></span>  
 <span data-ttu-id="7622c-146">다음 예제에서는 `<<` 연산자 정수 값에 왼쪽 시프트는 산술 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="7622c-147">결과 항상 동일한 데이터 이동 되는 식의 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="7622c-148">이전 예제의 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="7622c-149">`result1` 192 (0000 0000 1100 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="7622c-150">`result2` 3072 (1100 0000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="7622c-151">`result3` -32768 (1000 0000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="7622c-152">`result4` 384 (0000 0001 1000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="7622c-153">`result5` 0 (왼쪽으로 이동된 15 자리)입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="7622c-154">에 대 한 이동량 `result4` 17 같이 계산 됩니다. 1 및 15입니다.</span><span class="sxs-lookup"><span data-stu-id="7622c-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7622c-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="7622c-155">See also</span></span>

- [<span data-ttu-id="7622c-156">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="7622c-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="7622c-157">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="7622c-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="7622c-158"><<= 연산자</span><span class="sxs-lookup"><span data-stu-id="7622c-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="7622c-159">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="7622c-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7622c-160">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="7622c-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7622c-161">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="7622c-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
