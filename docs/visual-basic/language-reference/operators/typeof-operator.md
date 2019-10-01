---
title: TypeOf 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: c6028f524a16b836310f0c8d564205244515cdc9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701291"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="67480-102">TypeOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67480-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="67480-103">식의 결과에 대 한 런타임 형식이 지정 된 형식과 호환 되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67480-103">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="67480-104">구문</span><span class="sxs-lookup"><span data-stu-id="67480-104">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="67480-105">요소</span><span class="sxs-lookup"><span data-stu-id="67480-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="67480-106">반환됨.</span><span class="sxs-lookup"><span data-stu-id="67480-106">Returned.</span></span> <span data-ttu-id="67480-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67480-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="67480-108">필수.</span><span class="sxs-lookup"><span data-stu-id="67480-108">Required.</span></span> <span data-ttu-id="67480-109">참조 형식으로 계산되는 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="67480-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="67480-110">필수.</span><span class="sxs-lookup"><span data-stu-id="67480-110">Required.</span></span> <span data-ttu-id="67480-111">모든 데이터 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="67480-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67480-112">설명</span><span class="sxs-lookup"><span data-stu-id="67480-112">Remarks</span></span>  
 <span data-ttu-id="67480-113">`TypeOf` 연산자는 `objectexpression`의 런타임 형식이 `typename`과 호환되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="67480-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="67480-114">호환성은 `typename`의 형식 범주에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="67480-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="67480-115">다음 표에서 호환성이 결정되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67480-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="67480-116">`typename`의 형식 범주</span><span class="sxs-lookup"><span data-stu-id="67480-116">Type category of `typename`</span></span>|<span data-ttu-id="67480-117">호환성 조건</span><span class="sxs-lookup"><span data-stu-id="67480-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="67480-118">클래스</span><span class="sxs-lookup"><span data-stu-id="67480-118">Class</span></span>|<span data-ttu-id="67480-119">`objectexpression`이 `typename` 형식이거나 `typename`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="67480-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="67480-120">구조</span><span class="sxs-lookup"><span data-stu-id="67480-120">Structure</span></span>|<span data-ttu-id="67480-121">`objectexpression`이 `typename` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="67480-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="67480-122">인터페이스</span><span class="sxs-lookup"><span data-stu-id="67480-122">Interface</span></span>|<span data-ttu-id="67480-123">`objectexpression`이 `typename`을 구현하거나 `typename`을 구현하는 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="67480-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="67480-124">`objectexpression`의 런타임 형식이 호환성 조건을 충족하면 `result`가 `True`이고,</span><span class="sxs-lookup"><span data-stu-id="67480-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="67480-125">그렇지 않으면 `result`가 `False`입니다.</span><span class="sxs-lookup"><span data-stu-id="67480-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="67480-126">`objectexpression`이 null이면 `TypeOf`...`Is`는 `False`를 반환하고 ...`IsNot`은 `True`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67480-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="67480-127">`TypeOf`는 항상 `Is` 키워드와 함께 사용되어 `TypeOf`...`Is` 식을 생성하거나 `IsNot` 키워드와 함께 사용되어 `TypeOf`...`IsNot` 식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="67480-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67480-128">예제</span><span class="sxs-lookup"><span data-stu-id="67480-128">Example</span></span>  
 <span data-ttu-id="67480-129">다음 예제에서는 `TypeOf`...`Is` 식을 사용하여 데이터 형식이 다양한 두 개체 참조 변수의 형식 호환성을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="67480-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="67480-130">`refInteger` 변수에 `Integer`의 런타임 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67480-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="67480-131">이 변수는 `Integer`와 호환되지만 `Double`과는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67480-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="67480-132">`refForm` 변수에 <xref:System.Windows.Forms.Form>의 런타임 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67480-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="67480-133">이 변수는 해당 형식이기 때문에 <xref:System.Windows.Forms.Form>과 호환되고, <xref:System.Windows.Forms.Form>이 <xref:System.Windows.Forms.Control>에서 상속되기 때문에 <xref:System.Windows.Forms.Control>과 호환되며, <xref:System.Windows.Forms.Form>이 <xref:System.ComponentModel.IComponent>를 구현하는 <xref:System.ComponentModel.Component>에서 상속되기 때문에 <xref:System.ComponentModel.IComponent>와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="67480-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="67480-134">그러나 `refForm`은 <xref:System.Windows.Forms.Label>과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67480-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67480-135">참조</span><span class="sxs-lookup"><span data-stu-id="67480-135">See also</span></span>

- [<span data-ttu-id="67480-136">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="67480-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="67480-137">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="67480-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="67480-138">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="67480-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="67480-139">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="67480-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="67480-140">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="67480-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="67480-141">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="67480-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
