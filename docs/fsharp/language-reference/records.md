---
title: 레코드(F#)
description: 'F # 레코드에서 멤버를 사용 하 여 필요에 따라 명명 된 값의 간단한 집계를 표시 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 6103d96b6b80a9e2ed168755958dbe800f7fa862
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2018
ms.locfileid: "48261292"
---
# <a name="records"></a><span data-ttu-id="157e3-103">레코드</span><span class="sxs-lookup"><span data-stu-id="157e3-103">Records</span></span>

<span data-ttu-id="157e3-104">레코드는 명명된 값의 간단한 집계(경우에 따라 멤버가 포함된)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-104">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="157e3-105">F # 4.1 부터는 이러한 수 구조체 또는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-105">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="157e3-106">기본적으로 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="157e3-107">구문</span><span class="sxs-lookup"><span data-stu-id="157e3-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="157e3-108">설명</span><span class="sxs-lookup"><span data-stu-id="157e3-108">Remarks</span></span>

<span data-ttu-id="157e3-109">이전 구문에서 *typename* 이름 레코드 형식입니다 *label1* 하 고 *label2* 라고 하는 값의 이름이 *레이블*, 및 *type1* 하 고 *type2* 유형은 다음이 값 중입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="157e3-110">*멤버 목록* 멤버 유형에 대 한 선택적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="157e3-111">사용할 수는 `[<Struct>]` 특성 참조 형식인 레코드 대신 구조체 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="157e3-112">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="157e3-113">각 레이블에 이면 별도 줄에 세미콜론 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="157e3-114">라고 하는 식의 값을 설정할 수 있습니다 *식을 기록*합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="157e3-115">컴파일러는 (레이블은 다른 레코드 형식의 충분히 다릅니다) 하는 경우 사용 되는 레이블에서 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="157e3-116">중괄호 ({}) 레코드 식을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="157e3-117">다음 코드에서는 레이블과 함께 float 요소를 세 개를 사용 하 여 레코드를 초기화 하는 레코드 식이 `x`하십시오 `y` 및 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="157e3-118">다른 형식에도 동일한 레이블이 될 수 있는 경우에 축약 형태를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="157e3-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="157e3-119">가장 최근에 선언 된 형식의 레이블을 우선 이전에 선언 된 형식의 따라서 앞의 예에서 `mypoint3D` 로 유추 됩니다 `Point3D`합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="157e3-120">레코드 형식은 다음 코드와 같이 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="157e3-121">클래스 형식에서와 마찬가지로 레코드 유형에 대 한 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="157e3-122">레코드 식을 사용 하 여 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="157e3-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="157e3-123">레코드에서 정의 되는 레이블을 사용 하 여 레코드를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="157e3-124">이 작업을 수행 하는 식 이라고 하는 *식 기록*합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="157e3-125">중괄호를 사용 하 여 레코드 식을 묶는를 구분 기호로 세미콜론을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="157e3-126">다음 예제에서는 레코드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="157e3-127">레코드 식에 형식 정의의 마지막 필드 뒤에 세미콜론은 여부에 관계 없이 필드를 모두 한 줄 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="157e3-128">레코드를 만든 경우 각 필드에 대 한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="157e3-129">모든 필드에 대 한 초기화 식에서 다른 필드의 값을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="157e3-130">다음 코드에서 형식의 `myRecord2` 필드의 이름에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="157e3-131">필요에 따라 형식 이름을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="157e3-132">다른 형식의 레코드 생성 된 기존 레코드를 복사 하 고 필드 값의 일부 변경 해야 할 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="157e3-133">다음 코드 줄이에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="157e3-134">이 형태의 레코드 식 이라고 합니다 *복사 및 업데이트 레코드 식*합니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="157e3-135">레코드를 기본적으로 변경할 수 없는 경우 그러나 복사 및 업데이트 식을 사용 하 여 수정 된 레코드를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="157e3-136">변경 가능한 필드를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="157e3-137">레코드 필드를 사용 하 여 DefaultValue 특성을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="157e3-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="157e3-138">기본값으로 초기화 되는 필드를 사용 하 여 레코드의 기본 인스턴스를 정의 및 다음 복사본을 사용 하 여 업데이트 레코드 식의 기본 값과 다른 모든 필드를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="157e3-139">레코드를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="157e3-139">Pattern Matching with Records</span></span>

<span data-ttu-id="157e3-140">레코드 패턴 일치에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-140">Records can be used with pattern matching.</span></span> <span data-ttu-id="157e3-141">일부 필드를 명시적으로 지정 하 고 일치 하는 경우에 할당 되는 다른 필드에 대 한 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-141">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="157e3-142">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="157e3-143">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-143">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="157e3-144">레코드와 클래스 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="157e3-144">Differences Between Records and Classes</span></span>

<span data-ttu-id="157e3-145">레코드 필드에는 자동으로 속성으로 노출 된 것 이며 생성에 사용 되 고 레코드의 복사 클래스에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-145">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="157e3-146">레코드 생성 클래스 생성에서도 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-146">Record construction also differs from class construction.</span></span> <span data-ttu-id="157e3-147">레코드 형식에서 생성자를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-147">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="157e3-148">대신이 항목에 설명 된 구문이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-148">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="157e3-149">클래스는 생성자 매개 변수, 필드 및 속성 간에 직접 관계가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="157e3-149">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="157e3-150">공용 구조체 및 구조체 형식과 마찬가지로 레코드 구조적 같음 의미 체계를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-150">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="157e3-151">클래스에는 참조 같음 의미 체계.</span><span class="sxs-lookup"><span data-stu-id="157e3-151">Classes have reference equality semantics.</span></span> <span data-ttu-id="157e3-152">다음 코드 예제에서는 이 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-152">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="157e3-153">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-153">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="157e3-154">클래스를 사용 하 여 동일한 코드를 작성 하는 경우 두 클래스 개체가 같지 두 값 힙에 두 개체를 나타내는 것 이므로 주소만 비교 됨 (해당 클래스 형식는 `System.Object.Equals` 메서드).</span><span class="sxs-lookup"><span data-stu-id="157e3-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="157e3-155">레코드에 대 한 같음, 참조 해야 하는 경우 추가 특성 `[<ReferenceEquality>]` 레코드 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="157e3-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="157e3-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="157e3-156">See also</span></span>

- [<span data-ttu-id="157e3-157">F# 형식</span><span class="sxs-lookup"><span data-stu-id="157e3-157">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="157e3-158">클래스</span><span class="sxs-lookup"><span data-stu-id="157e3-158">Classes</span></span>](classes.md)
- [<span data-ttu-id="157e3-159">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="157e3-159">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="157e3-160">참조 같음</span><span class="sxs-lookup"><span data-stu-id="157e3-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="157e3-161">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="157e3-161">Pattern Matching</span></span>](pattern-matching.md)
