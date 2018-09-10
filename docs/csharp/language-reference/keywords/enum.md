---
title: enum 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: a64559ac1127f5ec296cf3892dd521c3ad8ac2be
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086152"
---
# <a name="enum-c-reference"></a><span data-ttu-id="b720f-102">enum(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b720f-102">enum (C# Reference)</span></span>

<span data-ttu-id="b720f-103">`enum` 키워드는 열거자 목록이라고 하는 명명된 상수 집합으로 구성된 고유 형식인 열거형을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>  

<span data-ttu-id="b720f-104">대개 네임스페이스의 모든 클래스가 같은 수준으로 열거형에 액세스할 수 있도록 네임스페이스 내에서 직접 열거형을 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="b720f-105">하지만 특정 클래스나 구조체 내에 열거형이 중첩될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-105">However, an enum can also be nested within a class or struct.</span></span>

<span data-ttu-id="b720f-106">기본적으로 첫 번째 열거자 값은 0이며 그 이후의 열거자 값은 순서대로 1씩 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="b720f-107">예를 들어 다음 열거형에서 `Sat` 은 `0`, `Sun` 은 `1`, `Mon` 은 `2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="b720f-108">다음 예제와 같이 열거자는 이니셜라이저를 사용하여 기본값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="b720f-109">이 열거형에서 요소의 순서는 `1` 대신 `0`부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="b720f-110">그러나 값이 0인 상수를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="b720f-111">자세한 내용은 [열거형 형식](../../programming-guide/enumeration-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b720f-111">For more information, see [Enumeration Types](../../programming-guide/enumeration-types.md).</span></span>

<span data-ttu-id="b720f-112">모든 열거형 형식에는 기본 형식이 있으며, 해당 형식은 [char](char.md) 형식을 제외한 임의의 정수 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-112">Every enumeration type has an underlying type, which can be any integral type except [char](char.md).</span></span> <span data-ttu-id="b720f-113">열거형 요소의 기본적인 기본 형식은 i [int](int.md)입니다. [바이트](byte.md)와 같은 다른 정수 형식의 열거형을 선언하려면 다음 예제에서와 같이 콜론을 사용하여 identifier 다음에 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-113">The default underlying type of enumeration elements is [int](int.md). To declare an enum of another integral type, such as [byte](byte.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="b720f-114">열거형으로 승인된 형식은 [byte](byte.md), [sbyte](sbyte.md), [short](short.md), [ushort](ushort.md), [int](int.md), [uint](uint.md), [long](long.md) 또는 [ulong](ulong.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-114">The approved types for an enum are [byte](byte.md), [sbyte](sbyte.md), [short](short.md), [ushort](ushort.md), [int](int.md), [uint](uint.md), [long](long.md), or [ulong](ulong.md).</span></span>

<span data-ttu-id="b720f-115">`Day` 형식의 변수에는 명명된 상수뿐 아니라 기본 형식의 범위에 있는 모든 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-115">A variable of type `Day` can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>

<span data-ttu-id="b720f-116">`enum E` 의 기본값은 식 `(E)0`으로 계산된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>

> [!NOTE]
> <span data-ttu-id="b720f-117">열거자의 이름에는 공백이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-117">An enumerator cannot contain white space in its name.</span></span>

<span data-ttu-id="b720f-118">기본 형식은 각 열거자에 할당될 저장소 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="b720f-119">그러나 `enum` 형식에서 정수 계열 형식으로 변환하려면 명시적 캐스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="b720f-120">예를 들어 다음 문은 `Sun` 을 [로 변환하는 캐스트를 사용하여 열거자](int.md) 을 `enum` int `int`형식 변수에 대입합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](int.md) by using a cast to convert from `enum` to `int`.</span></span>

```csharp
int x = (int)Day.Sun;
```

<span data-ttu-id="b720f-121">일부 요소가 비트 <xref:System.FlagsAttribute?displayProperty=nameWithType> 연산으로 결합될 수 있는 열거형에 `OR` 를 적용하면 일부 도구에서 이 열거형을 사용할 때 해당 특성이 `enum` 의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="b720f-122"><xref:System.Console> 클래스 메서드 및 식 계산기 등의 도구를 사용할 때 이러한 변경 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="b720f-123">세 번째 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b720f-123">(See the third example.)</span></span>

## <a name="robust-programming"></a><span data-ttu-id="b720f-124">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b720f-124">Robust programming</span></span>

<span data-ttu-id="b720f-125">다른 상수와 마찬가지로, 컴파일 시간에 열거형의 개별 값에 대한 모든 참조는 숫자 리터럴로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="b720f-126">따라서 [상수](../../programming-guide/classes-and-structs/constants.md)에서 설명하는 버전 문제가 발생할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-126">This can create potential versioning issues as described in [Constants](../../programming-guide/classes-and-structs/constants.md).</span></span>

<span data-ttu-id="b720f-127">새 버전의 열거형에 값을 추가로 할당하거나 새 버전의 열거형 멤버 값을 변경하면 종속된 소스 코드에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="b720f-128">[switch](switch.md) 문에서 열거형 값이 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-128">Enum values often are used in [switch](switch.md) statements.</span></span> <span data-ttu-id="b720f-129">`enum` 형식에 요소가 추가되었으면 switch 문의 기본 섹션을 예기치 않게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>

<span data-ttu-id="b720f-130">다른 개발자가 코드를 사용할 경우 `enum` 형식에 새 요소가 추가된다면 해당 코드에서 이를 적절히 처리할 수 있도록 지침을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>

## <a name="example"></a><span data-ttu-id="b720f-131">예</span><span class="sxs-lookup"><span data-stu-id="b720f-131">Example</span></span>

<span data-ttu-id="b720f-132">다음 예제에서는 열거형 `Day`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-132">In the following example, an enumeration, `Day`, is declared.</span></span> <span data-ttu-id="b720f-133">두 개의 열거자를 명시적으로 정수로 변환하여 정수 변수에 대입합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a><span data-ttu-id="b720f-134">예</span><span class="sxs-lookup"><span data-stu-id="b720f-134">Example</span></span>

<span data-ttu-id="b720f-135">다음 예제에서는 base-type 옵션을 사용하여 멤버가 `enum` 형식인 `long`을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="b720f-136">열거형의 기본 형식이 `long`인 경우에도 캐스트를 사용하여 열거형 멤버를 `long` 형식으로 명시적으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a><span data-ttu-id="b720f-137">예</span><span class="sxs-lookup"><span data-stu-id="b720f-137">Example</span></span>

<span data-ttu-id="b720f-138">다음 코드 예제에서는 <xref:System.FlagsAttribute?displayProperty=nameWithType> 선언에 `enum` 특성을 사용하는 방법과 그 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a><span data-ttu-id="b720f-139">설명</span><span class="sxs-lookup"><span data-stu-id="b720f-139">Comments</span></span>

<span data-ttu-id="b720f-140">`Flags`를 제거하면 예에 다음 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b720f-140">If you remove `Flags`, the example displays the following values:</span></span>

`5`

`5`

## <a name="c-language-specification"></a><span data-ttu-id="b720f-141">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b720f-141">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b720f-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b720f-142">See also</span></span>

- [<span data-ttu-id="b720f-143">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b720f-143">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="b720f-144">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="b720f-144">Enumeration Types</span></span>](../../programming-guide/enumeration-types.md)  
- [<span data-ttu-id="b720f-145">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="b720f-145">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="b720f-146">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="b720f-146">Integral Types Table</span></span>](integral-types-table.md)  
- [<span data-ttu-id="b720f-147">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="b720f-147">Built-In Types Table</span></span>](built-in-types-table.md)  
- [<span data-ttu-id="b720f-148">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="b720f-148">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="b720f-149">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="b720f-149">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="b720f-150">열거형 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b720f-150">Enum Naming Conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
