---
title: 정적으로 확인된 형식 매개 변수(F#)
description: 'F #을 사용 하는 방법은 런타임 대신 컴파일 시간에 실제 형식으로 대체 되는 정적으로 확인 된 형식 매개 변수입니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206171"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="76117-103">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="76117-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="76117-104">A *정적으로 확인 된 형식 매개 변수* 은 런타임 대신 컴파일 시간에 실제 형식으로 대체 되는 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="76117-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="76117-105">캐럿 (^) 기호가 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="76117-106">구문</span><span class="sxs-lookup"><span data-stu-id="76117-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="76117-107">설명</span><span class="sxs-lookup"><span data-stu-id="76117-107">Remarks</span></span>

<span data-ttu-id="76117-108">F # 언어에서 두 가지 종류의 형식 매개 변수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="76117-109">첫 번째 종류에는 표준 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="76117-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="76117-110">이러한 에서처럼 아포스트로피 (')로 표시 됩니다 `'T` 고 `'U`입니다.</span><span class="sxs-lookup"><span data-stu-id="76117-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="76117-111">제네릭 형식 매개 변수에 다른.NET Framework 언어에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="76117-112">다른 종류 정적으로 해결 되 고 에서처럼 캐럿 기호 나타난 `^T` 고 `^U`입니다.</span><span class="sxs-lookup"><span data-stu-id="76117-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="76117-113">정적으로 확인 된 형식 매개 변수는 형식 인수 있어야 특정 멤버를 사용할 수 있도록 지정할 수 있도록 하는 제약 조건 멤버 제약 조건과 함께에서 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="76117-114">일반 제네릭 형식 매개 변수를 사용 하 여이 유형의 제약 조건 만드는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="76117-115">다음 표에서 유사성과 두 종류의 형식 매개 변수 간의 차이점을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="76117-116">기능</span><span class="sxs-lookup"><span data-stu-id="76117-116">Feature</span></span>|<span data-ttu-id="76117-117">제네릭</span><span class="sxs-lookup"><span data-stu-id="76117-117">Generic</span></span>|<span data-ttu-id="76117-118">정적으로 확인 된</span><span class="sxs-lookup"><span data-stu-id="76117-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="76117-119">구문</span><span class="sxs-lookup"><span data-stu-id="76117-119">Syntax</span></span>|<span data-ttu-id="76117-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="76117-120">`'T`, `'U`</span></span>|<span data-ttu-id="76117-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="76117-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="76117-122">해결 시간</span><span class="sxs-lookup"><span data-stu-id="76117-122">Resolution time</span></span>|<span data-ttu-id="76117-123">런타임</span><span class="sxs-lookup"><span data-stu-id="76117-123">Run time</span></span>|<span data-ttu-id="76117-124">컴파일 시간</span><span class="sxs-lookup"><span data-stu-id="76117-124">Compile time</span></span>|
|<span data-ttu-id="76117-125">멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="76117-125">Member constraints</span></span>|<span data-ttu-id="76117-126">멤버 제약 조건과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="76117-127">멤버 제약 조건과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="76117-128">코드 생성</span><span class="sxs-lookup"><span data-stu-id="76117-128">Code generation</span></span>|<span data-ttu-id="76117-129">표준 제네릭 형식 매개 변수를 사용 하 여 형식 (또는 메서드)는 단일 제네릭 형식 또는 메서드의 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76117-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="76117-130">여러 인스턴스화 형식 및 메서드 생성 됩니다, 그리고 하나는 각 형식에 대 한 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="76117-131">형식 사용</span><span class="sxs-lookup"><span data-stu-id="76117-131">Use with types</span></span>|<span data-ttu-id="76117-132">형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-132">Can be used on types.</span></span>|<span data-ttu-id="76117-133">형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="76117-134">인라인 함수와 함께 사용</span><span class="sxs-lookup"><span data-stu-id="76117-134">Use with inline functions</span></span>|<span data-ttu-id="76117-135">아니요.</span><span class="sxs-lookup"><span data-stu-id="76117-135">No.</span></span> <span data-ttu-id="76117-136">인라인 함수는 표준 제네릭 형식 매개 변수를 사용 하 여 매개 변수화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="76117-137">예.</span><span class="sxs-lookup"><span data-stu-id="76117-137">Yes.</span></span> <span data-ttu-id="76117-138">함수 또는 메서드에서 인라인이 아닌 정적으로 확인 된 형식 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="76117-139">대부분 F # 핵심 라이브러리 함수, 특히 연산자가 정적으로 확인 된 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="76117-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="76117-140">이러한 함수 및 연산자에는 인라인 및 숫자 계산을 위한 효율적인 코드 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="76117-141">인라인 메서드 및 연산자를 사용 하거나 형식 매개 변수를 정적으로 해결 하는 다른 함수를 사용 하는 함수에는 자체 정적으로 확인 된 형식 매개 변수를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="76117-142">종종 형식 유추와 같은 인라인 함수가 정적으로 확인 된 형식 매개 변수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="76117-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="76117-143">다음 예제에서는 정적으로 확인 된 형식 매개 변수가으로 유추 되는 연산자 정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76117-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="76117-144">확인 된 형식 `(+@)` 사용을 기반으로 `(+)` 및 `(*)`두 멤버 제약 조건을 정적으로 확인 된 형식 매개 변수에서 유추 하는 형식 유추를 발생 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="76117-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="76117-145">확인 된 형식, F # 인터프리터를에서 같이 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="76117-146">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="76117-147">F # 4.1 부터는 정적으로 확인 된 형식 매개 변수 서명에서 구체적인 형식 이름을도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="76117-148">언어의 이전 버전에서는 형식 이름을 컴파일러에서 유추할 수 실제로 하지만 실제로 지정할 수 없습니다 시그니처에서.</span><span class="sxs-lookup"><span data-stu-id="76117-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="76117-149">F # 4.1을 기준으로 정적으로 확인 된 형식 매개 변수 서명에서 구체적인 형식 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="76117-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76117-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="76117-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="76117-151">See also</span></span>

- [<span data-ttu-id="76117-152">제네릭</span><span class="sxs-lookup"><span data-stu-id="76117-152">Generics</span></span>](index.md)
- [<span data-ttu-id="76117-153">형식 유추</span><span class="sxs-lookup"><span data-stu-id="76117-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="76117-154">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="76117-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="76117-155">제약 조건</span><span class="sxs-lookup"><span data-stu-id="76117-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="76117-156">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="76117-156">Inline Functions</span></span>](../functions/inline-functions.md)
