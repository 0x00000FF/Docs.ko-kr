---
title: "is(C# 참조)"
keywords: "is 키워드(C#), is(C#)"
ms.date: 2017-02-17
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
dev_langs:
- CSharp
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58b18284b12ca0c636ed3fa923c43d94f202597f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="is-c-reference"></a><span data-ttu-id="c2666-103">is(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c2666-103">is (C# Reference)</span></span> #

<span data-ttu-id="c2666-104">개체가 지정된 형식과 호환되는지 확인하거나 C# 7부터는 패턴에 대해 식을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-104">Checks if an object is compatible with a given type, or (starting with C# 7) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="c2666-105">형식 호환성 테스트</span><span class="sxs-lookup"><span data-stu-id="c2666-105">Testing for type compatibility</span></span> ##

<span data-ttu-id="c2666-106">`is` 키워드는 런타임에 형식 호환성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-106">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="c2666-107">개체 인스턴스 또는 식의 결과를 지정된 형식으로 변환할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-107">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="c2666-108">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-108">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="c2666-109">여기서 *expr*은 일부 형식의 인스턴스로 평가되는 식이고 *type*은 *expr*의 결과가 변환될 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-109">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="c2666-110">`is` 문은 *expr*이 null이 아니고 식을 평가한 결과 개체를 *type*으로 변환할 수 있으면 `true`이고, 그러지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-110">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="c2666-111">예를 들어 다음 코드는 `obj`를 `Person` 형식의 인스턴스로 캐스트할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-111">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

<span data-ttu-id="c2666-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2666-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span></span>

<span data-ttu-id="c2666-113">`is` 문은 다음과 같은 경우 true입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-113">The `is` statement is true if:</span></span>

- <span data-ttu-id="c2666-114">*expr*이 *type*과 동일한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-114">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c2666-115">*expr*이 *type*에서 파생된 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-115">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c2666-116">즉, *expr*의 결과를 *type*의 인스턴스로 업캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-116">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c2666-117">*expr*의 컴파일 시간 형식은 *type*의 기본 클래스이고 *expr*의 런타임 형식은 *type*이거나 *type*에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-117">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c2666-118">변수의 *컴파일 시간 형식*은 해당 선언에 정의된 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-118">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="c2666-119">변수의 *런타임 형식*은 해당 변수에 할당된 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-119">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c2666-120">*expr*이 *type* 인터페이스를 구현하는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-120">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c2666-121">다음 예제에서는 `is` 식이 이러한 각 변환에 대해 `true`로 평가되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-121">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

<span data-ttu-id="c2666-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="c2666-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span></span>

<span data-ttu-id="c2666-123">식이 항상 `true`이거나 `false`인 것으로 알려진 경우 `is` 키워드는 컴파일 시간 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-123">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="c2666-124">참조 변환, boxing 변환 및 unboxing 변환만 고려하고 사용자 정의 변환이나 형식의 [implicit](implicit.md) 및 [explicit](explicit.md) 연산자로 정의된 변환은 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-124">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="c2666-125">다음 예제에서는 변환의 결과가 컴파일 시간에 알려지기 때문에 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-125">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="c2666-126">`int`에서 `long` 및 `double`로 변환하기 위한 `is` 식에서 false를 반환하는데, 이러한 변환이 [implicit](implicit.md) 연산자에 의해 처리되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-126">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

<span data-ttu-id="c2666-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="c2666-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span></span>

<span data-ttu-id="c2666-128">`expr`은 무명 메서드 및 람다 식을 제외하고 값을 반환하는 모든 식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-128">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="c2666-129">다음 예제에서는 `is`를 사용하여 메서드 호출의 반환 값을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-129">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
<span data-ttu-id="c2666-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span><span class="sxs-lookup"><span data-stu-id="c2666-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span></span>

<span data-ttu-id="c2666-131">C# 7부터는 [형식 패턴](#type)을 사용한 패턴 일치를 통해 `is` 문을 사용하는 보다 간결한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-131">Starting with C# 7, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="c2666-132">`is`를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="c2666-132">Pattern matching with `is`</span></span> ##

<span data-ttu-id="c2666-133">C# 7부터는 `is` 및 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 패턴 일치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-133">Starting with C# 7, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="c2666-134">`is` 키워드는 다음과 같은 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-134">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="c2666-135">[형식 패턴](#type) - 식을 지정된 형식으로 변환할 수 있는지 여부를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-135">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="c2666-136">[상수 패턴](#constant) - 식이 지정된 상수 값으로 평가되는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-136">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="c2666-137">[var 패턴](#var) - 항상 성공하고 식의 값을 새 로컬 변수에 바인딩하는 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-137">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="c2666-138"><a name="type" /> 형식 패턴 </a></span><span class="sxs-lookup"><span data-stu-id="c2666-138"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="c2666-139">형식 패턴을 사용하여 패턴 일치를 수행하는 경우 `is`는 식을 지정된 형식으로 변환할 수 있는지 여부를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-139">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="c2666-140">간결한 형식 평가 및 변환을 사용하는 `is` 문의 간단한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-140">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="c2666-141">`is` 형식 패턴의 일반적인 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-141">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="c2666-142">여기서 *expr*은 일부 형식의 인스턴스로 평가되는 식이고 *type*은 *expr*의 결과가 변환될 형식의 이름이며 *varname*은 `is` 테스트가 `true`인 경우 *expr*의 결과가 변환되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-142">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="c2666-143">`is` 식은 다음 중 하나에 해당되는 경우 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-143">The `is` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="c2666-144">*expr*이 *type*과 동일한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-144">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c2666-145">*expr*이 *type*에서 파생된 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-145">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c2666-146">즉, *expr*의 결과를 *type*의 인스턴스로 업캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-146">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c2666-147">*expr*의 컴파일 시간 형식은 *type*의 기본 클래스이고 *expr*의 런타임 형식은 *type*이거나 *type*에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-147">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c2666-148">변수의 *컴파일 시간 형식*은 해당 선언에 정의된 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-148">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="c2666-149">변수의 *런타임 형식*은 해당 변수에 할당된 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-149">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c2666-150">*expr*이 *type* 인터페이스를 구현하는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-150">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c2666-151">*exp*가 `true`이고 `is`가 `if` 문에서 사용되는 경우 *varname*이 할당되며 `if` 문 내의 로컬 범위만 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-151">If *exp* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="c2666-152">다음 예제에서는 `is` 형식 패턴을 사용하여 형식의 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> 메서드 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-152">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> method.</span></span>

<span data-ttu-id="c2666-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span><span class="sxs-lookup"><span data-stu-id="c2666-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span></span>

<span data-ttu-id="c2666-154">패턴 일치를 사용하지 않을 경우 이 코드를 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-154">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="c2666-155">형식 패턴 일치를 사용하면 변환 결과가 `null`인지 여부를 테스트할 필요가 없으므로 보다 간결하고 읽기 쉬운 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-155">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

<span data-ttu-id="c2666-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span><span class="sxs-lookup"><span data-stu-id="c2666-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span></span>

<span data-ttu-id="c2666-157">또한 `is` 형식 패턴은 값 형식의 형식을 확인할 때 보다 간결한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-157">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="c2666-158">다음 예제에서는 `is` 형식 패턴을 사용하여 개체가 `Person` 인스턴스인지 `Dog` 인스턴스인지를 확인한 후 적절한 속성의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-158">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

<span data-ttu-id="c2666-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span><span class="sxs-lookup"><span data-stu-id="c2666-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span></span>

<span data-ttu-id="c2666-160">패턴 일치를 사용하지 않는 동일한 코드에는 명시적 캐스트를 포함하는 별도의 할당이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-160">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

<span data-ttu-id="c2666-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span><span class="sxs-lookup"><span data-stu-id="c2666-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span></span>

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="c2666-162"><a name="constant" /> 상수 패턴</span><span class="sxs-lookup"><span data-stu-id="c2666-162"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="c2666-163">상수 패턴을 사용한 패턴 일치를 수행하는 경우 `is`는 식이 지정된 상수와 같은지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-163">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="c2666-164">C# 6 이전 버전에서는 상수 패턴이 [switch](switch.md) 문에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-164">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="c2666-165">C# 7부터는 `is` 문에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-165">Starting with C# 7, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="c2666-166">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-166">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="c2666-167">여기서 *expr*은 평가할 식이고 *constant*는 테스트할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-167">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="c2666-168">*constant*는 다음 상수 식 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="c2666-169">리터럴 값.</span><span class="sxs-lookup"><span data-stu-id="c2666-169">A literal value.</span></span>

- <span data-ttu-id="c2666-170">선언된 `const` 변수의 이름.</span><span class="sxs-lookup"><span data-stu-id="c2666-170">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="c2666-171">열거형 상수.</span><span class="sxs-lookup"><span data-stu-id="c2666-171">An enumeration constant.</span></span>

<span data-ttu-id="c2666-172">상수 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-172">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="c2666-173">*expr* 및 *constant*가 정수 형식인 경우 C# 같음 연산자는 식에서 `true`를 반환하는지 여부 즉, `expr == constant`인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-173">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="c2666-174">정수 형식이 아닌 경우 정적 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 메서드 호출을 통해 식의 값이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-174">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="c2666-175">다음 예제에서는 형식 패턴과 상수 패턴을 결합하여 개체가 `Dice` 인스턴스인지 여부를 테스트하고, 그럴 경우 주사위 굴리기 값이 6인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-175">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

<span data-ttu-id="c2666-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span><span class="sxs-lookup"><span data-stu-id="c2666-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span></span>
 
### <span data-ttu-id="c2666-177"><a name="var" /> var 패턴 </a></span><span class="sxs-lookup"><span data-stu-id="c2666-177"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="c2666-178">var 패턴을 사용한 패턴 일치는 항상 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-178">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="c2666-179">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-179">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="c2666-180">여기서 *expr*의 값은 항상 *varname*이라는 로컬 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-180">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="c2666-181">*varname*은 *expr*과 동일한 형식의 정적 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-181">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="c2666-182">다음 예제에서는 var 패턴을 사용하여 `obj`라는 변수에 식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-182">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="c2666-183">그런 다음 `obj`의 값과 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-183">It then displays the value and the type of `obj`.</span></span>

<span data-ttu-id="c2666-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span><span class="sxs-lookup"><span data-stu-id="c2666-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span></span>

<span data-ttu-id="c2666-185">*expr*이 `null`인 경우에도 `is` 식은 true이고 *varname*에 `null`을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c2666-185">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="c2666-186">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c2666-186">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2666-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2666-187">See also</span></span>  
 <span data-ttu-id="c2666-188">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2666-188">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c2666-189">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2666-189">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c2666-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="c2666-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="c2666-191">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="c2666-191">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 [<span data-ttu-id="c2666-192">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="c2666-192">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

