---
title: 멤버 액세스 연산자 - C# 참조
description: 형식 멤버에 액세스하는 데 사용하는 C# 연산자에 대해 알아봅니다.
ms.date: 09/18/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: 45af31d10d77f4c63b27b34595b97fdd11ef95a1
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71116133"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="be8a4-103">멤버 액세스 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="be8a4-103">Member access operators (C# reference)</span></span>

<span data-ttu-id="be8a4-104">형식 멤버에 액세스할 때 다음과 같은 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="be8a4-105">[`.` (멤버 액세스)](#member-access-operator-): 네임스페이스 또는 형식의 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="be8a4-106">[`[]` (배열 요소 또는 인덱서 액세스)](#indexer-operator-): 배열 요소 또는 형식 인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="be8a4-107">[`?.` 및 `?[]`(null 조건부 연산자)](#null-conditional-operators--and-): 피연산자가 null이 아닌 경우에만 멤버 또는 요소 액세스 작업 수행</span><span class="sxs-lookup"><span data-stu-id="be8a4-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="be8a4-108">[`()` (호출)](#invocation-operator-): 액세스된 메서드나 대리자 호출</span><span class="sxs-lookup"><span data-stu-id="be8a4-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="be8a4-109">[`^`(끝부터 인덱스)](#index-from-end-operator-): 요소 위치가 시퀀스의 끝에서 시작됨을 표시</span><span class="sxs-lookup"><span data-stu-id="be8a4-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="be8a4-110">[`..`(범위)](#range-operator-): 시퀀스 요소의 범위를 가져오는 데 사용할 수 있는 인덱스 범위를 지정</span><span class="sxs-lookup"><span data-stu-id="be8a4-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="be8a4-111">멤버 액세스 연산자</span><span class="sxs-lookup"><span data-stu-id="be8a4-111">Member access operator .</span></span>

<span data-ttu-id="be8a4-112">다음 예제와 같이 `.` 토큰을 사용하여 네임스페이스 또는 형식의 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="be8a4-113">[ `using` 지시문](../keywords/using-directive.md)의 다음 예제와 같이 `.`을 사용하여 네임스페이스 내에 중첩된 네임스페이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="be8a4-114">다음 코드와 같이 `.`을 사용하여 ‘정규화된 이름’을 만들고 네임스페이스 내의 형식에 액세스합니다. </span><span class="sxs-lookup"><span data-stu-id="be8a4-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="be8a4-115">[`using` 지시문](../keywords/using-directive.md)을 사용하여 정규화된 이름 사용을 선택 사항으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="be8a4-116">다음 코드와 같이 `.`을 사용하여 정적 및 비정적 [형식 멤버](../../programming-guide/classes-and-structs/index.md#members)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="be8a4-117">`.`을 사용하여 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="be8a4-118">인덱서 연산자 []</span><span class="sxs-lookup"><span data-stu-id="be8a4-118">Indexer operator []</span></span>

<span data-ttu-id="be8a4-119">대괄호 `[]`는 일반적으로 배열, 인덱서 또는 포인터 요소 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="be8a4-120">배열 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-120">Array access</span></span>

<span data-ttu-id="be8a4-121">다음 예제는 배열 요소에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="be8a4-122">배열 인덱스가 배열의 해당 차원 범위를 벗어난 경우 <xref:System.IndexOutOfRangeException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="be8a4-123">앞의 예제와 같이, 배열 형식을 선언하거나 배열 인스턴스를 인스턴스화할 때도 대괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="be8a4-124">배열에 대한 자세한 내용은 [배열](../../programming-guide/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="be8a4-125">인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-125">Indexer access</span></span>

<span data-ttu-id="be8a4-126">다음 예제는 .NET <xref:System.Collections.Generic.Dictionary%602> 형식을 사용하여 인덱서 액세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-126">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="be8a4-127">인덱서를 사용하면 배열 인덱싱과 비슷한 방법으로 사용자 정의 형식의 인스턴스를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="be8a4-128">정수여야 하는 배열 인덱스와 달리, 인덱서 인수는 임의 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-128">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="be8a4-129">인덱서에 대한 자세한 내용은 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="be8a4-130">다른 [] 용도</span><span class="sxs-lookup"><span data-stu-id="be8a4-130">Other usages of []</span></span>

<span data-ttu-id="be8a4-131">포인터 요소 액세스에 대한 자세한 내용은 [포인터 관련 연산자](pointer-related-operators.md) 문서의 [포인터 요소 액세스 연산자](pointer-related-operators.md#pointer-element-access-operator-) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="be8a4-132">또한 대괄호를 사용하여 [특성](../../programming-guide/concepts/attributes/index.md)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="be8a4-133">Null 조건부 연산자 ?.</span><span class="sxs-lookup"><span data-stu-id="be8a4-133">Null-conditional operators ?.</span></span> <span data-ttu-id="be8a4-134">및 ?[]</span><span class="sxs-lookup"><span data-stu-id="be8a4-134">and ?[]</span></span>

<span data-ttu-id="be8a4-135">C# 6 이상에서 사용할 수 있는 null 조건부 연산자는 피연산자가 null이 아닌 것으로 평가되었을 때만 멤버 액세스 `?.`, 또는 요소 액세스 `?[]` 연산을 피연산자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-135">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="be8a4-136">피연산자가 `null`로 평가되면 연산자 적용 결과가 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-136">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="be8a4-137">Null 조건부 멤버 액세스 연산자 `?.`를 Elvis 연산자라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-137">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="be8a4-138">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-138">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="be8a4-139">즉 조건부 멤버나 요소 액세스 작업의 한 체인의 작업에서 `null`을 반환하면 나머지 체인은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-139">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="be8a4-140">다음 예제에서 `A`가 `null`로 평가되면 `B`가 평가되지 않고, `A` 또는 `B`가 `null`로 평가되면 `C`가 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-140">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="be8a4-141">다음 예제에서는 `?.` 및 `?[]` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-141">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="be8a4-142">위의 예제에서는 [null 병합 연산자](null-coalescing-operator.md)의 사용법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-142">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="be8a4-143">null 병합 연산자를 사용하여 null 조건부 연산 결과가 `null`인 경우 평가하는 대체 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-143">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="be8a4-144">스레드로부터 안전한 대리자 호출</span><span class="sxs-lookup"><span data-stu-id="be8a4-144">Thread-safe delegate invocation</span></span>

<span data-ttu-id="be8a4-145">다음 코드에서처럼 `?.` 연산자를 사용하여 대리자가 null이 아닌지 확인하고 스레드로부터 안전한 방식으로 호출합니다(예: [이벤트 발생 시](../../../standard/events/how-to-raise-and-consume-events.md)).</span><span class="sxs-lookup"><span data-stu-id="be8a4-145">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="be8a4-146">이 코드는 C# 5 및 그 이전에서 사용하는 다음 코드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-146">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="be8a4-147">호출 연산자()</span><span class="sxs-lookup"><span data-stu-id="be8a4-147">Invocation operator ()</span></span>

<span data-ttu-id="be8a4-148">괄호(`()`)를 사용하여 [메서드](../../programming-guide/classes-and-structs/methods.md) 또는 [대리자](../../programming-guide/delegates/index.md)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-148">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="be8a4-149">다음 예제는 인수를 사용하거나 사용하지 않고 메서드를 호출하는 방법과 대리자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-149">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="be8a4-150">[`new`](new-operator.md) 연산자를 사용하여 [생성자](../../programming-guide/classes-and-structs/constructors.md)를 호출하는 경우에도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-150">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="be8a4-151">다른 () 용도</span><span class="sxs-lookup"><span data-stu-id="be8a4-151">Other usages of ()</span></span>

<span data-ttu-id="be8a4-152">또한 괄호를 사용하여 식에서 연산을 계산하는 순서를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-152">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="be8a4-153">자세한 내용은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-153">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="be8a4-154">명시적 형식 변환을 수행하는 [캐스트 식](type-testing-and-cast.md#cast-operator-)도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-154">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="be8a4-155">끝부터 인덱스 연산자 ^</span><span class="sxs-lookup"><span data-stu-id="be8a4-155">Index from end operator ^</span></span>

<span data-ttu-id="be8a4-156">C# 8.0 이상에서 사용할 수 있는 연산자 `^`는 요소 위치가 시퀀스의 끝에서 시작함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-156">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="be8a4-157">시퀀스 길이 `length`의 경우 `^n`은 시퀀스의 시작에서 오프셋 `length - n`인 요소를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-157">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="be8a4-158">예를 들어 `^1`은 시퀀스의 마지막 요소를 가리키고, `^length`는 시퀀스의 첫 번째 요소를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-158">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="be8a4-159">위 예제에서와 같이 식 `^e`는 <xref:System.Index?displayProperty=nameWithType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-159">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="be8a4-160">식 `^e`에서 `e`의 결과는 암시적으로 `int`으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-160">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="be8a4-161">또한 `^` 연산자를 [범위 연산자](#range-operator-)와 함께 사용하여 인덱스 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-161">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="be8a4-162">자세한 내용은 [인덱스와 범위](../../tutorials/ranges-indexes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-162">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="be8a4-163">범위 연산자 ..</span><span class="sxs-lookup"><span data-stu-id="be8a4-163">Range operator ..</span></span>

<span data-ttu-id="be8a4-164">C# 8.0 이상에서 사용 가능한 연산자 `..`은 인덱스 범위의 시작과 끝을 피연산자로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-164">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="be8a4-165">왼쪽 피연산자는 범위의 시작(*포함*)입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-165">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="be8a4-166">오른쪽 피연산자는 범위의 끝(*제외*)입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-166">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="be8a4-167">다음 예제에서와 같이 피연산자 중 하나는 시퀀스의 시작부터 또는 끝부터 인덱스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-167">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="be8a4-168">위 예제에서와 같이 식 `a..b`는 <xref:System.Range?displayProperty=nameWithType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-168">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="be8a4-169">식 `a..b`에서 `a` 및 `b`의 결과는 암시적으로 `int` 또는 <xref:System.Index>로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-169">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="be8a4-170">`..` 연산자의 피연산자 중 하나를 생략하여 개방형 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-170">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="be8a4-171">`a..`는 `a..^0`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-171">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="be8a4-172">`..b`는 `0..b`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-172">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="be8a4-173">`..`는 `0..^0`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-173">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="be8a4-174">자세한 내용은 [인덱스와 범위](../../tutorials/ranges-indexes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-174">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="be8a4-175">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="be8a4-175">Operator overloadability</span></span>

<span data-ttu-id="be8a4-176">`.`, `()`, `^` 및 `..` 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-176">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="be8a4-177">`[]` 연산자도 오버로드할 수 없는 연산자로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-177">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="be8a4-178">[인덱서](../../programming-guide/indexers/index.md)를 사용하여 사용자 정의 형식의 인덱싱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="be8a4-178">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="be8a4-179">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="be8a4-179">C# language specification</span></span>

<span data-ttu-id="be8a4-180">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be8a4-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="be8a4-181">멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-181">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="be8a4-182">요소 액세스</span><span class="sxs-lookup"><span data-stu-id="be8a4-182">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="be8a4-183">Null 조건부 연산자</span><span class="sxs-lookup"><span data-stu-id="be8a4-183">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="be8a4-184">호출 식</span><span class="sxs-lookup"><span data-stu-id="be8a4-184">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="be8a4-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be8a4-185">See also</span></span>

- [<span data-ttu-id="be8a4-186">C# 참조</span><span class="sxs-lookup"><span data-stu-id="be8a4-186">C# reference</span></span>](../index.md)
- [<span data-ttu-id="be8a4-187">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="be8a4-187">C# operators</span></span>](index.md)
- [<span data-ttu-id="be8a4-188">??(Null 병합 연산자)</span><span class="sxs-lookup"><span data-stu-id="be8a4-188">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="be8a4-189">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="be8a4-189">:: operator</span></span>](namespace-alias-qualifier.md)
