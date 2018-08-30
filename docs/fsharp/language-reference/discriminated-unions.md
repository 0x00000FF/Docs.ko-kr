---
title: Discriminated Unions(F#)
description: 'F #을 사용 하는 방법을 알아봅니다 구별 된 공용 구조체입니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 3340933ac8e2b6fe0215c684691d216a28b64787
ms.sourcegitcommit: 875ecc3ab2437e299b1d50076bd9b878fa8c64de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43238526"
---
# <a name="discriminated-unions"></a><span data-ttu-id="d5bf5-103">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d5bf5-103">Discriminated Unions</span></span>

<span data-ttu-id="d5bf5-104">구별 된 공용 구조체 형식과 다른 값을 사용 하 여 각 명명 된 사례 수 중 하나가 될 수 있는 값에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="d5bf5-105">구별 된 공용 구조체 유형이 다른 데이터에 유용 유효한을 비롯 한 특수 사례 및 오류 사례; 가질 수 있는 데이터 한 인스턴스에서 다른; 형식에 따라 달라 지는 데이터 및 작은 개체 계층에 대 한 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="d5bf5-106">또한 재귀적인 구별 된 공용 구조체 트리 데이터 구조를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5bf5-107">구문</span><span class="sxs-lookup"><span data-stu-id="d5bf5-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="d5bf5-108">설명</span><span class="sxs-lookup"><span data-stu-id="d5bf5-108">Remarks</span></span>

<span data-ttu-id="d5bf5-109">구별 된 공용 구조체는 다른 언어의 공용 구조체 형식과 비슷하지만 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="d5bf5-110">으로 c + +에서 공용 구조체 형식 또는 Visual Basic의 variant 형식과 값에 저장 된 데이터를 수정 하지 않으면; 여러 가지 옵션 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="d5bf5-111">그러나와 달리 이러한 기타 언어의 공용 구조체, 각각 가능한 옵션은 부여는 *케이스 식별자*합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="d5bf5-112">케이스 식별자는이 형식의 개체 수; 값의 가능한 다양 한 형식에 이름이 값은 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="d5bf5-113">값이 있는 경우에 해당 열거형 케이스 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="d5bf5-114">값이 있는 경우 각 값에는 단일 값, 지정된 된 형식 또는 같거나 다른 형식의 여러 필드를 집계 하는 튜플 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="d5bf5-115">이름을 개별 필드를 지정할 수 있습니다 하지만 같은 사례의 다른 필드 라고 하는 경우에 이름은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="d5bf5-116">구별 된 공용 구조체에 대 한 내게 필요한 옵션을 기본값으로 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="d5bf5-117">예를 들어, 다음 Shape 형식 선언의 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="d5bf5-118">위의 코드는 선언 구별된 된 공용 구조체의 세 가지 경우 중 하나는 값을 포함할 수 있는 셰이프: 사각형, 원 및 프리즘 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="d5bf5-119">각각의 경우에는 다른 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-119">Each case has a different set of fields.</span></span> <span data-ttu-id="d5bf5-120">사각형 경우 두 개의 명명 된 필드의 형식은 모두 `float`, 이름 너비 및 길이가 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="d5bf5-121">원형 케이스는 하나의 명명 된 필드, 반지름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="d5bf5-122">프리즘의 경우 세 개의 필드가 있는 (너비 및 높이)의 두 필드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="d5bf5-123">명명 되지 않은 필드는 익명 필드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="d5bf5-124">다음 예제에 따라 명명 된 형식과 익명 필드에 대 한 값을 제공 하 여 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="d5bf5-125">이 코드는 초기화에서 명명된 된 필드를 사용할 수 있습니다 하거나 선언에서 필드의 순서에 의존 하 고 차례로 각 필드에 대 한 값을 방금 제공 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="d5bf5-126">에 대 한 생성자 호출 `rect` 이전 코드에서 명명된 된 필드를 하지만 대 한 생성자 호출을 사용 하 여 `circ` 순서 지정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="d5bf5-127">순서가 지정 된 필드를 혼합할 수 및 생성와 같이 라는 `prism`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="d5bf5-128">`option` 형식은 F # 핵심 라이브러리의 간단한 구별 된 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="d5bf5-129">`option` 형식을 다음과 같이 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="d5bf5-130">앞의 코드를 지정 하는 형식을 `Option` 이라는 두 케이스가 있는 구별된 된 공용 구조체는 `Some` 고 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="d5bf5-131">합니다 `Some` 사례에 해당 형식을 형식 매개 변수로 표현 하는 익명 필드 하나로 구성 된 연결된 값 `'a`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="d5bf5-132">`None` 케이스에 관련된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-132">The `None` case has no associated value.</span></span> <span data-ttu-id="d5bf5-133">따라서는 `option` 형식은 하거나 일부 형식 또는 값이 없는 값을 가진 제네릭 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="d5bf5-134">형식 `Option` 소문자 형식 별칭을 역시 `option`, 즉 더 일반적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="d5bf5-135">케이스 식별자는 구별 된 공용 구조체 형식에 대 한 생성자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="d5bf5-136">예를 들어, 다음 코드는 값을 만드는 데는 `option` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="d5bf5-137">케이스 식별자는 패턴 일치 식에에서도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="d5bf5-138">패턴 일치 식에서 식별자는 개별 사례와 연결 된 값에 대해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="d5bf5-139">예를 들어, 다음 코드에서에서 `x` 식별자와 연결 된 값이 지정 되는 `Some` 케이스는 `option` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="d5bf5-140">패턴 일치 식에서에서 구별 된 공용 구조체 일치 항목을 지정 하려면 명명 된 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="d5bf5-141">이전에 선언 된 셰이프 형식의 필드의 값을 추출 하려면 다음 코드와 같이 명명된 된 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="d5bf5-142">일반적으로 케이스 식별자는 공용 구조체의 이름으로 정규화 하지 않고도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="d5bf5-143">공용 구조체의 이름이 항상 정규화 하려면 이름, 원하는 경우 적용할 수 있습니다 합니다 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 공용 구조체 형식 정의에 대 한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="d5bf5-144">래핑 해제 구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d5bf5-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="d5bf5-145">F # 구별 된 공용 구조체의에서 자주 사용 되 도메인 모델링 래핑 단일 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="d5bf5-146">패턴으로 일치를 통해 기본 값을 추출 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="d5bf5-147">일치 식을 사용 하 여 단일 사례에 대 한 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="d5bf5-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="d5bf5-149">구조체를 구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d5bf5-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="d5bf5-150">F # 4.1 부터는 구조체로 구별 된 공용 구조체를도 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="d5bf5-151">그러려면는 `[<Struct>]` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="d5bf5-152">없기 때문에 이러한 값 형식이 며 형식을 참조 하지, 추가 구별 된 공용 구조체 참조에 비해 고려 사항:</span><span class="sxs-lookup"><span data-stu-id="d5bf5-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="d5bf5-153">이러한 값 형식으로 복사 되 고 값 형식 의미 체계를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="d5bf5-154">Multicase 구조체 구별 된 공용 구조체를 사용 하 여 재귀 형식 정의 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="d5bf5-155">Multicase 구조체 구별 된 공용 구조체에 대 한 사례 고유한 이름을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="d5bf5-156">개체 계층 구조 대신 구별 된 공용 구조체를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d5bf5-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="d5bf5-157">흔히 작은 개체 계층에 단순한 대안인 구별된 된 공용 구조체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="d5bf5-158">대신 다음과 같은 구별 된 공용 구조체를 사용할 수 있습니다 예를 들어, 한 `Shape` 기본 클래스에 대 한 파생 형식이 원, 정사각형 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="d5bf5-159">대신 면적이 나 둘레를 계산 하는 가상 메서드로, 사용 되는 개체 지향 구현에서 적절 한 수식으로 분기에 패턴 일치를 사용 하 여 이러한 수량을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="d5bf5-160">다음 예제에서는 서로 다른 수식은 면적을 계산 합니다, 도형에 따라 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="d5bf5-161">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="d5bf5-162">구별 된 공용 구조체를 사용 하 여 트리 데이터 구조에 대 한</span><span class="sxs-lookup"><span data-stu-id="d5bf5-162">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="d5bf5-163">구별 된 공용 구조체는 재귀 공용 구조체 자체가 하나 이상의 경우의 형식에 포함 될 수 있는지를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="d5bf5-164">재귀 구별 된 공용 구조체는 프로그래밍 언어에서 식을 모델링 하는 데 사용 되는 트리 구조를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="d5bf5-165">다음 코드에서는 재귀적인 구별 된 공용 구조체는 이진 트리 데이터 구조를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="d5bf5-166">두 경우의 통합 구성 `Node`, 정수 값과 왼쪽 및 오른쪽 하위 트리 노드인 및 `Tip`, 트리를 종료 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="d5bf5-167">이전 코드에서 `resultSumTree` 값 10이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="d5bf5-168">다음 그림에 대 한 트리 구조를 보여 줍니다. `myTree`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Mytree의 트리 구조](../media/TreeStructureDiagram.png)

<span data-ttu-id="d5bf5-170">구별 된 공용 구조체에는 트리에서 노드 유형이 다른 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="d5bf5-171">다음 코드에서 형식 `Expression` 숫자와 변수의 곱하기 및 추가 지 원하는 간단한 프로그래밍 언어에서 식의 추상 구문 트리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="d5bf5-172">재귀 없는 공용 구조체 케이스의 일부 및 중 하나를 나타내고 (`Number`) 또는 변수 (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="d5bf5-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="d5bf5-173">다른 경우는 재귀적 이며 및 작업을 나타내는 (`Add` 및 `Multiply`), 피연산자가 식도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="d5bf5-174">`Evaluate` 함수를 재귀적으로 처리 구문 트리 일치 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="d5bf5-175">이 코드를 실행할 때, 변수의 `result` 은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="d5bf5-176">공통 특성</span><span class="sxs-lookup"><span data-stu-id="d5bf5-176">Common Attributes</span></span>

<span data-ttu-id="d5bf5-177">다음 특성은 일반적으로 구별 된 공용 구조체에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]`

## <a name="see-also"></a><span data-ttu-id="d5bf5-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5bf5-178">See Also</span></span>

[<span data-ttu-id="d5bf5-179">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d5bf5-179">F# Language Reference</span></span>](index.md)
