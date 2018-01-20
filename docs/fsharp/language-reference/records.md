---
title: "레코드(F#)"
description: "F # 레코드 멤버와 필요에 따라 명명 된 값의 간단한 집계를 표시 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a3701ea-4308-4fa1-9b5c-b955c470f17a
ms.openlocfilehash: 478ab74ad32cc6e53daffd1bd6229729149d2a1e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="records"></a><span data-ttu-id="ccf11-104">레코드</span><span class="sxs-lookup"><span data-stu-id="ccf11-104">Records</span></span>

<span data-ttu-id="ccf11-105">레코드는 명명된 값의 간단한 집계(경우에 따라 멤버가 포함된)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-105">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="ccf11-106">F # 4.1 부터는 하거나 구조체 또는 참조 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-106">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="ccf11-107">기본적으로 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-107">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccf11-108">구문</span><span class="sxs-lookup"><span data-stu-id="ccf11-108">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="ccf11-109">설명</span><span class="sxs-lookup"><span data-stu-id="ccf11-109">Remarks</span></span>
<span data-ttu-id="ccf11-110">위 구문에서 *typename* 레코드 종류의 이름인 *label1* 및 *label2* 는 라고 값의 이름 *레이블을*, 및 *type1* 및 *type2* 이러한 값의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-110">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="ccf11-111">*멤버 목록* 멤버 유형에 대 한 선택적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-111">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="ccf11-112">사용할 수는 `[<Struct>]` 특성 참조 형식인 하는 레코드 대신 구조체 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-112">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="ccf11-113">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-113">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="ccf11-114">각 레이블에 이면 별도 줄에 세미콜론 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-114">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="ccf11-115">라고 하는 식의 값을 설정할 수 *식 기록*합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-115">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="ccf11-116">컴파일러에는 (레이블이 있는 경우 충분히 구별의 다른 레코드 종류)을 사용 하는 레이블 중에서 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-116">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="ccf11-117">중괄호 ({}) 레코드 식을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-117">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="ccf11-118">다음 코드에서는 세 개의 float 요소 레이블 사용 하 여 레코드를 초기화 하는 레코드 식을 `x`, `y` 및 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-118">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="ccf11-119">다른 형식에도 동일한 레이블이 될 수 있는 경우에 축소 된 형식을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ccf11-119">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="ccf11-120">이전에 선언 된 형식 보다 우선 순위가 높으므로 가장 최근에 선언 된 형식 변수의 여러 레이블을 앞의 예제에는 `mypoint3D` 것으로 유추 `Point3D`합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-120">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="ccf11-121">다음 코드 에서처럼 레코드 종류를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-121">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="ccf11-122">클래스 형식 마찬가지로 레코드 형식에 대 한 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-122">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="ccf11-123">레코드 식을 사용 하 여 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="ccf11-123">Creating Records by Using Record Expressions</span></span>
<span data-ttu-id="ccf11-124">레코드에 정의 되는 레이블을 사용 하 여 레코드를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-124">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="ccf11-125">이 작업을 수행 하는 식 이라고는 *식 기록*합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-125">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="ccf11-126">레코드 식을 묶는 및 구분 기호로 세미콜론을 사용 하 여 중괄호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-126">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="ccf11-127">다음 예제에는 레코드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-127">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="ccf11-128">레코드 식에서 및 형식 정의의 마지막 필드 뒤에 세미콜론은 필드 모두 한 줄에에서 있는지에 관계 없이 선택적 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-128">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="ccf11-129">레코드를 만들 때 각 필드에 대 한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-129">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="ccf11-130">모든 필드에 대 한 초기화 식의 다른 필드의 값을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-130">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="ccf11-131">다음 코드의 형식 `myRecord2` 필드의 이름에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-131">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="ccf11-132">필요에 따라 형식 이름을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-132">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="ccf11-133">레코드 생성의 또 다른 형태 기존 레코드를 복사 하 고 필드 값의 일부를 변경 해야 할 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-133">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="ccf11-134">다음 코드 줄은이입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-134">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="ccf11-135">이 레코드 식이 형식의 라고는 *복사 및 업데이트 레코드 식*합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-135">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="ccf11-136">레코드는 기본적으로 변경할 수 없습니다. 그러나 복사 및 업데이트 식을 사용 하 여 수정 된 레코드를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-136">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="ccf11-137">변경 가능한 필드를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-137">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="ccf11-138">DefaultValue 특성 레코드 필드와 함께 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ccf11-138">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="ccf11-139">기본값으로 초기화 된 필드와 레코드의 기본 인스턴스를 정의 합니다. 다음 복사본을 사용 및 업데이트 레코드 식 기본 값과 다른 모든 필드를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-139">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="ccf11-140">레코드를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="ccf11-140">Pattern Matching with Records</span></span>
<span data-ttu-id="ccf11-141">레코드 패턴 일치에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-141">Records can be used with pattern matching.</span></span> <span data-ttu-id="ccf11-142">일부 필드를 명시적으로 지정 하 고 일치 하는 항목이 때 할당 되는 다른 필드에 대 한 값을 제공할 수 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-142">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="ccf11-143">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-143">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="ccf11-144">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-144">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="ccf11-145">레코드 및 클래스 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="ccf11-145">Differences Between Records and Classes</span></span>
<span data-ttu-id="ccf11-146">레코드 필드 속성으로 노출 되어 자동으로 생성에 사용 되 고 레코드의 복사 한다는 점에서 클래스에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-146">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="ccf11-147">레코드 생성 클래스 생성에서도 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-147">Record construction also differs from class construction.</span></span> <span data-ttu-id="ccf11-148">레코드 종류에는 생성자를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-148">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="ccf11-149">대신,이 항목에서 설명한 구문이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-149">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="ccf11-150">클래스는 생성자 매개 변수, 필드 및 속성 간 직접 관계가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-150">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="ccf11-151">공용 구조체 및 구조체 형식 처럼 레코드 구조적 같음 의미 체계를 가져야합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-151">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="ccf11-152">클래스에는 참조 같음 의미 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-152">Classes have reference equality semantics.</span></span> <span data-ttu-id="ccf11-153">다음 코드 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-153">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="ccf11-154">클래스를 사용 하 여 동일한 코드를 작성 하는 경우 두 클래스 개체가 같지 주소만 비교 되며 하 고 두 값은 힙의 두 개체를 나타냅니다 (해당 클래스 형식에서 `System.Object.Equals` 메서드).</span><span class="sxs-lookup"><span data-stu-id="ccf11-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="ccf11-155">레코드에 대 한 같음을 참조 하 고 필요한 경우 추가 특성 `[<ReferenceEquality>]` 레코드 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf11-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccf11-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccf11-156">See Also</span></span>
[<span data-ttu-id="ccf11-157">F# 형식</span><span class="sxs-lookup"><span data-stu-id="ccf11-157">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="ccf11-158">클래스</span><span class="sxs-lookup"><span data-stu-id="ccf11-158">Classes</span></span>](classes.md)

[<span data-ttu-id="ccf11-159">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ccf11-159">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ccf11-160">Reference-Equality</span><span class="sxs-lookup"><span data-stu-id="ccf11-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[<span data-ttu-id="ccf11-161">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="ccf11-161">Pattern Matching</span></span>](pattern-matching.md)
