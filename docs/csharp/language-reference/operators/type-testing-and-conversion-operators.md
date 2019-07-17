---
title: 형식 테스트 및 변환 연산자 - C# 참조
description: 식 결과의 형식을 검사하고, 필요한 경우 다른 형식으로 변환하는 데 사용할 수 있는 C# 연산자에 대해 알아봅니다.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: a9e5139e6d650aa6935bff934ca25502fdc14775
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744078"
---
# <a name="type-testing-and-conversion-operators-c-reference"></a><span data-ttu-id="107eb-103">형식 테스트 및 변환 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="107eb-103">Type-testing and conversion operators (C# reference)</span></span>

<span data-ttu-id="107eb-104">다음 연산자를 사용하여 형식 검사 또는 형식 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-104">You can use the following operators to perform type checking or type conversion:</span></span>

- <span data-ttu-id="107eb-105">[is 연산자](#is-operator): 식의 런타임 형식이 지정된 형식과 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-105">[is operator](#is-operator): to check if the runtime type of an expression is compatible with a given type</span></span>
- <span data-ttu-id="107eb-106">[as 연산자](#as-operator): 런타임 형식이 지정된 형식과 호환되는 경우 식을 해당 형식으로 명시적으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-106">[as operator](#as-operator): to explicitly convert an expression to a given type if its runtime type is compatible with that type</span></span>
- <span data-ttu-id="107eb-107">[캐스트 연산자 ()](#cast-operator-): 명시적 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-107">[cast operator ()](#cast-operator-): to perform an explicit conversion</span></span>
- <span data-ttu-id="107eb-108">[typeof 연산자](#typeof-operator): 형식의 <xref:System.Type?displayProperty=nameWithType> 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-108">[typeof operator](#typeof-operator): to obtain the <xref:System.Type?displayProperty=nameWithType> instance for a type</span></span>

## <a name="is-operator"></a><span data-ttu-id="107eb-109">is 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-109">is operator</span></span>

<span data-ttu-id="107eb-110">`is` 연산자는 식 결과의 런타임 형식이 지정된 형식과 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-110">The `is` operator checks if the runtime type of an expression result is compatible with a given type.</span></span> <span data-ttu-id="107eb-111">C# 7.0부터, `is` 연산자는 식 결과에 패턴이 있는지도 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-111">Starting with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span>

<span data-ttu-id="107eb-112">형식 테스트 `is` 연산자가 포함된 식의 양식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-112">The expression with the type-testing `is` operator has the following form</span></span>

```csharp
E is T
```

<span data-ttu-id="107eb-113">여기서 `E`는 값을 반환하는 식이고, `T`는 형식 또는 형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-113">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter.</span></span> <span data-ttu-id="107eb-114">`E`은 무명 메서드 또는 람다 식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-114">`E` cannot be an anonymous method or a lambda expression.</span></span>

<span data-ttu-id="107eb-115">`E is T` 식은 `E`의 결과가 null이 아니고 참조 변환, boxing 변환 또는 unboxing 변환을 통해 `T` 형식으로 변환될 수 있는 경우 `true`를 반환하고, 변환될 수 없으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-115">The `E is T` expression returns `true` if the result of `E` is non-null and can be converted to type `T` by a reference conversion, a boxing conversion, or an unboxing conversion; otherwise, it returns `false`.</span></span> <span data-ttu-id="107eb-116">`is` 연산자는 사용자 정의 변환을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-116">The `is` operator doesn't consider user-defined conversions.</span></span>

<span data-ttu-id="107eb-117">다음 예제에서는 식 결과의 런타임 형식이 지정된 형식에서 파생되는 경우, 즉 형식 간에 참조 변환이 있는 경우 `is` 연산자가 `true`를 반환하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-117">The following example demonstrates that the `is` operator returns `true` if the runtime type of an expression result derives from a given type, that is, there exists a reference conversion between types:</span></span>

[!code-csharp[is with reference conversion](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

<span data-ttu-id="107eb-118">다음 예제에서는 `is` 연산자가 boxing 및 unboxing 변환은 고려하지만 숫자 변환을 고려하지 않는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-118">The next example shows that the `is` operator takes into account boxing and unboxing conversions but doesn't consider numeric conversions:</span></span>

[!code-csharp-interactive[is with int](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithInt)]

<span data-ttu-id="107eb-119">C# 변환에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [변환](~/_csharplang/spec/conversions.md) 장을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-119">For information about C# conversions, see the [Conversions](~/_csharplang/spec/conversions.md) chapter of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

### <a name="type-testing-with-pattern-matching"></a><span data-ttu-id="107eb-120">패턴 일치를 사용한 형식 테스트</span><span class="sxs-lookup"><span data-stu-id="107eb-120">Type testing with pattern matching</span></span>

<span data-ttu-id="107eb-121">C# 7.0부터, `is` 연산자는 식 결과에 패턴이 있는지도 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-121">Starting with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span> <span data-ttu-id="107eb-122">특히, 다음 형태의 양식 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-122">In particular, it supports the type pattern in the following form:</span></span>

```csharp
E is T v
```

<span data-ttu-id="107eb-123">여기서 `E`는 값을 반환하는 식이고, `T`는 형식 또는 형식 매개 변수의 이름이며, `v`는 `T` 형식의 새 로컬 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-123">where `E` is an expression that returns a value, `T` is the name of a type or a type parameter, and `v` is a new local variable of type `T`.</span></span> <span data-ttu-id="107eb-124">`E`의 결과가 null이 아니고 참조, boxing 또는 unboxing 변환을 통해 `T`로 변환될 수 있는 경우 `E is T v` 식이 `true`를 반환하고 `E` 결과의 변환된 값이 `v` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-124">If the result of `E` is non-null and can be converted to `T` by a reference, boxing, or unboxing conversion, the `E is T v` expression returns `true` and the converted value of the result of `E` is assigned to variable `v`.</span></span>

<span data-ttu-id="107eb-125">다음 예제에서는 형식 패턴과 `is` 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-125">The following example demonstrates the usage of the `is` operator with the type pattern:</span></span>

[!code-csharp-interactive[is with type pattern](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsTypePattern)]

<span data-ttu-id="107eb-126">형식 패턴 및 기타 지원되는 패턴에 대한 자세한 내용은 [is를 사용한 패턴 일치](../keywords/is.md#pattern-matching-with-is)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-126">For more information about the type pattern and other supported patterns, see [Pattern matching with is](../keywords/is.md#pattern-matching-with-is).</span></span>

## <a name="as-operator"></a><span data-ttu-id="107eb-127">as 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-127">as operator</span></span>

<span data-ttu-id="107eb-128">`as` 연산자는 식의 결과를 지정된 참조 또는 nullable 값 형식으로 명시적으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-128">The `as` operator explicitly converts the result of an expression to a given reference or nullable value type.</span></span> <span data-ttu-id="107eb-129">변환할 수 없는 경우 `as` 연산자가 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-129">If the conversion is not possible, the `as` operator returns `null`.</span></span> <span data-ttu-id="107eb-130">[캐스트 연산자 ()](#cast-operator-)와 달리, `as` 연산자는 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-130">Unlike the [cast operator ()](#cast-operator-), the `as` operator never throws an exception.</span></span>

<span data-ttu-id="107eb-131">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-131">The expression of the form</span></span>

```csharp
E as T
```

<span data-ttu-id="107eb-132">여기서 `E`는 값을 반환하는 식이고, `T`는 형식 또는 형식 매개 변수의 이름입니다. 이 식은 다음과 동일한 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-132">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter, produces the same result as</span></span>

```csharp
E is T ? (T)(E) : (T)null
```

<span data-ttu-id="107eb-133">단, `E`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-133">except that `E` is only evaluated once.</span></span>

<span data-ttu-id="107eb-134">`as` 연산자는 참조, nullable, boxing 및 unboxing 변환만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-134">The `as` operator considers only reference, nullable, boxing, and unboxing conversions.</span></span> <span data-ttu-id="107eb-135">`as` 연산자를 사용하여 사용자 정의 변환을 수행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-135">You cannot use the `as` operator to perform a user-defined conversion.</span></span> <span data-ttu-id="107eb-136">사용자 정의 변환을 수행하려면 [캐스트 연산자 ()](#cast-operator-)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-136">To do that, use the [cast operator ()](#cast-operator-).</span></span>

<span data-ttu-id="107eb-137">다음 예제에서는 `as` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-137">The following example demonstrates the usage of the `as` operator:</span></span>

[!code-csharp-interactive[as operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> <span data-ttu-id="107eb-138">앞의 예제와 같이, `as` 식의 결과를 `null`과 비교하여 변환에 성공했는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-138">As the preceding example shows, you need to compare the result of the `as` expression with `null` to check if the conversion is successful.</span></span> <span data-ttu-id="107eb-139">C# 7.0부터, [is 연산자](#type-testing-with-pattern-matching)를 사용하여 변환에 성공하는지 테스트하고, 성공한 경우 해당 결과를 새 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-139">Starting with C# 7.0, you can use the [is operator](#type-testing-with-pattern-matching) both to test if the conversion succeeds and, if it succeeds, assign its result to a new variable.</span></span>

## <a name="cast-operator-"></a><span data-ttu-id="107eb-140">캐스트 연산자 ()</span><span class="sxs-lookup"><span data-stu-id="107eb-140">Cast operator ()</span></span>

<span data-ttu-id="107eb-141">`(T)E` 형태의 캐스트 식은 `E` 식의 결과를 `T` 형식으로 명시적으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-141">A cast expression of the form `(T)E` performs an explicit conversion of the result of expression `E` to type `T`.</span></span> <span data-ttu-id="107eb-142">`E` 형식에서 `T` 형식으로의 명시적 변환이 없는 경우 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-142">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="107eb-143">런타임에 명시적 변환이 실패하고 캐스트 식이 예외를 throw할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-143">At run time, an explicit conversion might not succeed and a cast expression might throw an exception.</span></span>

<span data-ttu-id="107eb-144">다음 예제에서는 명시적 숫자 및 참조 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-144">The following example demonstrates explicit numeric and reference conversions:</span></span>

[!code-csharp-interactive[cast expression](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#Cast)]

<span data-ttu-id="107eb-145">지원되는 명시적 변환에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [명시적 변환](~/_csharplang/spec/conversions.md#explicit-conversions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-145">For information about supported explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="107eb-146">사용자 지정 명시적 또는 암시적 형식 변환을 정의하는 방법에 대한 자세한 내용은 [사용자 정의 변환 연산자](user-defined-conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-146">For information about how to define a custom explicit or implicit type conversion, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="107eb-147">다른 () 용도</span><span class="sxs-lookup"><span data-stu-id="107eb-147">Other usages of ()</span></span>

<span data-ttu-id="107eb-148">[메서드 또는 대리자를 호출](member-access-operators.md#invocation-operator-)하는 경우에도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-148">You also use parentheses to [call a method or invoke a delegate](member-access-operators.md#invocation-operator-).</span></span>

<span data-ttu-id="107eb-149">괄호를 사용하여 식에서 연산을 계산하는 순서를 지정하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-149">Other use of parentheses is to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="107eb-150">자세한 내용은 [연산자](../../programming-guide/statements-expressions-operators/operators.md) 문서의 [괄호 추가](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-150">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="107eb-151">우선 순위 수준에 따라 정렬된 연산자 목록은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-151">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="typeof-operator"></a><span data-ttu-id="107eb-152">typeof 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-152">typeof operator</span></span>

<span data-ttu-id="107eb-153">`typeof` 연산자는 형식의 <xref:System.Type?displayProperty=nameWithType> 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-153">The `typeof` operator obtains the <xref:System.Type?displayProperty=nameWithType> instance for a type.</span></span> <span data-ttu-id="107eb-154">`typeof` 연산자의 인수는 다음 예제와 같이 형식 또는 형식 매개 변수의 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-154">An argument of the `typeof` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[typeof operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOf)]

<span data-ttu-id="107eb-155">바인딩되지 않은 제네릭 형식과 `typeof` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-155">You also can use the `typeof` operator with unbound generic types.</span></span> <span data-ttu-id="107eb-156">바인딩되지 않은 제네릭 형식의 이름에는 형식 매개 변수 개수보다 하나 더 적은 적절한 개수의 쉼표가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-156">The name of an unbound generic type must contain the appropriate number of commas, which is one less than the number of type parameters.</span></span> <span data-ttu-id="107eb-157">다음 예제에서는 바인딩되지 않은 제네릭 형식과 `typeof` 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-157">The following example shows the usage of the `typeof` operator with an unbound generic type:</span></span>

[!code-csharp-interactive[typeof unbound generic](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

<span data-ttu-id="107eb-158">식은 `typeof` 연산자의 인수가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-158">An expression cannot be an argument of the `typeof` operator.</span></span> <span data-ttu-id="107eb-159">식 결과의 런타임 형식에 대한 <xref:System.Type?displayProperty=nameWithType> 인스턴스를 가져오려면 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-159">To get the <xref:System.Type?displayProperty=nameWithType> instance for the runtime type of the expression result, use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method.</span></span>

### <a name="type-testing-with-the-typeof-operator"></a><span data-ttu-id="107eb-160">`typeof` 연산자를 사용한 형식 테스트</span><span class="sxs-lookup"><span data-stu-id="107eb-160">Type testing with the `typeof` operator</span></span>

<span data-ttu-id="107eb-161">`typeof` 연산자를 사용하여 식 결과의 런타임 형식이 지정된 형식과 정확히 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-161">Use the `typeof` operator to check if the runtime type of the expression result exactly matches a given type.</span></span> <span data-ttu-id="107eb-162">다음 예제에서는 `typeof` 연산자와 [is 연산자](#is-operator)를 사용한 형식 검사의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-162">The following example demonstrates the difference between type checking performed with the `typeof` operator and the [is operator](#is-operator):</span></span>

[!code-csharp[typeof vs is](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a><span data-ttu-id="107eb-163">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="107eb-163">Operator overloadability</span></span>

<span data-ttu-id="107eb-164">`is`, `as` 및 `typeof` 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-164">The `is`, `as`, and `typeof` operators are not overloadable.</span></span>

<span data-ttu-id="107eb-165">사용자 정의 형식은 `()` 연산자를 오버로드할 수 없지만, 캐스트 식에서 수행할 수 있는 사용자 지정 형식 변환을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107eb-165">A user-defined type cannot overload the `()` operator, but can define custom type conversions that can be performed by a cast expression.</span></span> <span data-ttu-id="107eb-166">자세한 내용은 [사용자 정의 변환 연산자](user-defined-conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-166">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="107eb-167">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="107eb-167">C# language specification</span></span>

<span data-ttu-id="107eb-168">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107eb-168">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="107eb-169">is 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-169">The is operator</span></span>](~/_csharplang/spec/expressions.md#the-is-operator)
- [<span data-ttu-id="107eb-170">as 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-170">The as operator</span></span>](~/_csharplang/spec/expressions.md#the-as-operator)
- [<span data-ttu-id="107eb-171">캐스트 식</span><span class="sxs-lookup"><span data-stu-id="107eb-171">Cast expressions</span></span>](~/_csharplang/spec/expressions.md#cast-expressions)
- [<span data-ttu-id="107eb-172">typeof 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-172">The typeof operator</span></span>](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a><span data-ttu-id="107eb-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="107eb-173">See also</span></span>

- [<span data-ttu-id="107eb-174">C# 참조</span><span class="sxs-lookup"><span data-stu-id="107eb-174">C# reference</span></span>](../index.md)
- [<span data-ttu-id="107eb-175">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="107eb-175">C# operators</span></span>](index.md)
- [<span data-ttu-id="107eb-176">방법: 패턴 일치와 is 및 as 연산자를 사용하여 안전하게 캐스트</span><span class="sxs-lookup"><span data-stu-id="107eb-176">How to: safely cast by using pattern matching and the is and as operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
