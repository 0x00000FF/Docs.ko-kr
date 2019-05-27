---
title: 포인터 형식 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 7f04cfbac72008332a429c4e0ad8bd3f4e60cc83
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880322"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="e737f-102">포인터 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e737f-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="e737f-103">안전하지 않은 컨텍스트에서는 형식이 포인터 형식, 값 형식 또는 참조 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="e737f-104">포인터 형식 선언은 다음 형식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="e737f-105">포인터 형식에서 `*` 앞에 지정된 형식을 **참조 형식**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="e737f-106">참조 형식은 다음과 같은 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="e737f-107">모든 정수 형식: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="e737f-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="e737f-108">모든 부동 소수점 형식: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="e737f-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="e737f-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="e737f-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="e737f-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="e737f-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="e737f-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="e737f-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="e737f-112">모든 [enum](../../language-reference/keywords/enum.md) 형식</span><span class="sxs-lookup"><span data-stu-id="e737f-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="e737f-113">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="e737f-113">Any pointer type.</span></span> <span data-ttu-id="e737f-114">`void**`과 같은 식이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="e737f-115">관리되지 않는 형식의 필드만 포함하는 임의의 사용자 정의 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="e737f-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="e737f-116">포인터 형식은 [개체](../../language-reference/keywords/object.md)에서 상속되지 않으며 포인터 형식과 `object`는 서로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="e737f-117">또한 boxing과 unboxing은 포인터를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="e737f-118">그러나 다른 포인터 형식 간의 변환 및 포인터 형식과 정수 형식 사이의 변환은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="e737f-119">동일한 선언에서 여러 포인터를 선언하는 경우 별표(\*)는 기본 형식에만 함께 사용되고 각 포인터 이름의 접두사로는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="e737f-120">예:</span><span class="sxs-lookup"><span data-stu-id="e737f-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="e737f-121">개체 참조는 포인터가 해당 개체 참조를 가리키는 경우에도 가비지 수집될 수 있으므로 포인터는 참조나 참조가 들어 있는 [구조체](../../language-reference/keywords/struct.md)를 가리킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="e737f-122">가비지 수집기는 포인터 형식에서 개체를 가리키는지 여부를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="e737f-123">`myType*` 형식의 포인터 변수 값은 `myType` 형식의 변수 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="e737f-124">다음은 포인터 형식 선언의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="e737f-125">예제</span><span class="sxs-lookup"><span data-stu-id="e737f-125">Example</span></span>|<span data-ttu-id="e737f-126">설명</span><span class="sxs-lookup"><span data-stu-id="e737f-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="e737f-127">`p`는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="e737f-128">`p`는 정수에 대한 포인터를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="e737f-129">`p`는 정수에 대한 포인터의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="e737f-130">`p`는 문자에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="e737f-131">`p`는 알 수 없는 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="e737f-132">포인터 간접 참조 연산자 \*를 사용하면 포인터 변수가 가리키는 위치의 내용에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="e737f-133">예를 들어, 다음 선언을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e737f-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="e737f-134">여기서 `*myVariable` 식은 `int`에 포함된 주소에 있는 `myVariable` 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="e737f-135">[fixed 문](../../language-reference/keywords/fixed-statement.md) 및 [포인터 변환](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) 항목에 포인터에 대한 몇 가지 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="e737f-136">다음 예제는 `unsafe` 키워드 및 `fixed` 문을 사용하고 정수 포인터를 증분하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="e737f-137">이 코드를 실행하려면 콘솔 애플리케이션의 주 함수에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="e737f-138">이러한 예제는 [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션 집합으로 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="e737f-139">`void*` 형식의 포인터에는 간접 참조 연산자를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="e737f-140">그러나 캐스트를 사용하여 void 포인터를 다른 포인터 형식으로 변환하거나 반대로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="e737f-141">포인터는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-141">A pointer can be `null`.</span></span> <span data-ttu-id="e737f-142">null 포인터에 간접 참조 연산자를 적용할 때 발생하는 동작은 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="e737f-143">메서드 사이에 포인터를 전달하면 정의되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="e737f-144">`in`, `out` 또는 `ref` 매개 변수를 통해, 또는 함수 결과로 지역 변수에 포인터를 반환하는 메서드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="e737f-145">fixed 블록에서 포인터가 설정되면 이 포인터가 가리키는 변수의 고정 상태가 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="e737f-146">다음 표에서는 안전하지 않은 컨텍스트에서 포인터에 대해 수행할 수 있는 연산자와 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="e737f-147">연산자/문</span><span class="sxs-lookup"><span data-stu-id="e737f-147">Operator/Statement</span></span>|<span data-ttu-id="e737f-148">기능</span><span class="sxs-lookup"><span data-stu-id="e737f-148">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="e737f-149">포인터 간접 참조를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-149">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="e737f-150">포인터를 통해 구조체 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-150">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="e737f-151">포인터를 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-151">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="e737f-152">변수 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-152">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="e737f-153">`++` 및 `--`</span><span class="sxs-lookup"><span data-stu-id="e737f-153">`++` and `--`</span></span>|<span data-ttu-id="e737f-154">포인터를 증가 및 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-154">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="e737f-155">`+` 및 `-`</span><span class="sxs-lookup"><span data-stu-id="e737f-155">`+` and `-`</span></span>|<span data-ttu-id="e737f-156">포인터 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-156">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="e737f-157">`==`, `!=`, `<`, `>`, `<=` 및 `>=`</span><span class="sxs-lookup"><span data-stu-id="e737f-157">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="e737f-158">포인터를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-158">Compares pointers.</span></span>|
|[<span data-ttu-id="e737f-159">`stackalloc` 연산자</span><span class="sxs-lookup"><span data-stu-id="e737f-159">`stackalloc` operator</span></span>](../../language-reference/keywords/stackalloc.md)|<span data-ttu-id="e737f-160">스택에 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-160">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="e737f-161">`fixed` statement</span><span class="sxs-lookup"><span data-stu-id="e737f-161">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="e737f-162">해당 주소를 찾을 수 있도록 임시로 변수를 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="e737f-162">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="e737f-163">포인터에 관련 연산자에 대한 자세한 내용은 [포인터 관련 연산자](../../language-reference/operators/pointer-related-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e737f-163">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e737f-164">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e737f-164">C# language specification</span></span>

<span data-ttu-id="e737f-165">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [포인터 형식](~/_csharplang/spec/unsafe-code.md#pointer-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e737f-165">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e737f-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e737f-166">See also</span></span>

- [<span data-ttu-id="e737f-167">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e737f-167">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e737f-168">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="e737f-168">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="e737f-169">포인터 변환</span><span class="sxs-lookup"><span data-stu-id="e737f-169">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="e737f-170">유형</span><span class="sxs-lookup"><span data-stu-id="e737f-170">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="e737f-171">unsafe</span><span class="sxs-lookup"><span data-stu-id="e737f-171">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
