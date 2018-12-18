---
title: 기본값 표 - C# 참조
ms.custom: seodec18
description: C# 값 형식의 기본 값은 무엇인지 알아봅니다.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 19e9e4f94ab573f2313c185a08192d89103b98fd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237040"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="a5864-103">기본값 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a5864-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="a5864-104">다음 표는 [값 형식](value-types.md)의 기본값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="a5864-105">값 형식</span><span class="sxs-lookup"><span data-stu-id="a5864-105">Value type</span></span>|<span data-ttu-id="a5864-106">기본값</span><span class="sxs-lookup"><span data-stu-id="a5864-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="a5864-107">bool</span><span class="sxs-lookup"><span data-stu-id="a5864-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="a5864-108">byte</span><span class="sxs-lookup"><span data-stu-id="a5864-108">byte</span></span>](byte.md)|<span data-ttu-id="a5864-109">0</span><span class="sxs-lookup"><span data-stu-id="a5864-109">0</span></span>|
|[<span data-ttu-id="a5864-110">char</span><span class="sxs-lookup"><span data-stu-id="a5864-110">char</span></span>](char.md)|<span data-ttu-id="a5864-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="a5864-111">'\0'</span></span>|
|[<span data-ttu-id="a5864-112">decimal</span><span class="sxs-lookup"><span data-stu-id="a5864-112">decimal</span></span>](decimal.md)|<span data-ttu-id="a5864-113">0M</span><span class="sxs-lookup"><span data-stu-id="a5864-113">0M</span></span>|
|[<span data-ttu-id="a5864-114">double</span><span class="sxs-lookup"><span data-stu-id="a5864-114">double</span></span>](double.md)|<span data-ttu-id="a5864-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="a5864-115">0.0D</span></span>|
|[<span data-ttu-id="a5864-116">enum</span><span class="sxs-lookup"><span data-stu-id="a5864-116">enum</span></span>](enum.md)|<span data-ttu-id="a5864-117">식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="a5864-118">float</span><span class="sxs-lookup"><span data-stu-id="a5864-118">float</span></span>](float.md)|<span data-ttu-id="a5864-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="a5864-119">0.0F</span></span>|
|[<span data-ttu-id="a5864-120">int</span><span class="sxs-lookup"><span data-stu-id="a5864-120">int</span></span>](int.md)|<span data-ttu-id="a5864-121">0</span><span class="sxs-lookup"><span data-stu-id="a5864-121">0</span></span>|
|[<span data-ttu-id="a5864-122">long</span><span class="sxs-lookup"><span data-stu-id="a5864-122">long</span></span>](long.md)|<span data-ttu-id="a5864-123">0L</span><span class="sxs-lookup"><span data-stu-id="a5864-123">0L</span></span>|
|[<span data-ttu-id="a5864-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="a5864-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="a5864-125">0</span><span class="sxs-lookup"><span data-stu-id="a5864-125">0</span></span>|
|[<span data-ttu-id="a5864-126">short</span><span class="sxs-lookup"><span data-stu-id="a5864-126">short</span></span>](short.md)|<span data-ttu-id="a5864-127">0</span><span class="sxs-lookup"><span data-stu-id="a5864-127">0</span></span>|
|[<span data-ttu-id="a5864-128">struct</span><span class="sxs-lookup"><span data-stu-id="a5864-128">struct</span></span>](struct.md)|<span data-ttu-id="a5864-129">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="a5864-130">uint</span><span class="sxs-lookup"><span data-stu-id="a5864-130">uint</span></span>](uint.md)|<span data-ttu-id="a5864-131">0</span><span class="sxs-lookup"><span data-stu-id="a5864-131">0</span></span>|
|[<span data-ttu-id="a5864-132">ulong</span><span class="sxs-lookup"><span data-stu-id="a5864-132">ulong</span></span>](ulong.md)|<span data-ttu-id="a5864-133">0</span><span class="sxs-lookup"><span data-stu-id="a5864-133">0</span></span>|
|[<span data-ttu-id="a5864-134">ushort</span><span class="sxs-lookup"><span data-stu-id="a5864-134">ushort</span></span>](ushort.md)|<span data-ttu-id="a5864-135">0</span><span class="sxs-lookup"><span data-stu-id="a5864-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5864-136">설명</span><span class="sxs-lookup"><span data-stu-id="a5864-136">Remarks</span></span>

<span data-ttu-id="a5864-137">C#에서 초기화되지 않은 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="a5864-138">해당 형식의 기본값을 사용하여 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="a5864-139">또한 형식의 기본 값을 사용하여 메서드의 [선택적 인수](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments)의 기본값을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="a5864-140">[기본값 식](../../programming-guide/statements-expressions-operators/default-value-expressions.md)을 사용하여 다음 예제와 같이 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="a5864-141">C# 7.1부터 [`default` 리터럴](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)을 사용하여 해당 형식의 기본값으로 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="a5864-142">기본 생성자 또는 암시적 기본 생성자를 사용하여 다음 예제와 같이 값 형식의 기본값을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-142">You also can use the default constructor or the implicit default constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="a5864-143">생성자에 대한 자세한 내용은 [생성자](../../programming-guide/classes-and-structs/constructors.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5864-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="a5864-144">모든 [참조 형식](reference-types.md)의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="a5864-145">[nullable 형식](../../programming-guide/nullable-types/index.md)의 기본값은 <xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5864-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5864-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5864-146">See also</span></span>

- [<span data-ttu-id="a5864-147">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a5864-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5864-148">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a5864-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a5864-149">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a5864-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a5864-150">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="a5864-150">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="a5864-151">값 형식</span><span class="sxs-lookup"><span data-stu-id="a5864-151">Value types</span></span>](value-types.md)
- [<span data-ttu-id="a5864-152">값 형식 표</span><span class="sxs-lookup"><span data-stu-id="a5864-152">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="a5864-153">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="a5864-153">Built-in types table</span></span>](built-in-types-table.md)
