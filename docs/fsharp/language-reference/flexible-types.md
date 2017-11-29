---
title: "유연한 형식(F#)"
description: "F # 유연한 형식의 주석을 매개 변수, 변수 또는 값에는 지정 된 형식과 호환 되는 형식을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a><span data-ttu-id="99b72-104">유연한 형식</span><span class="sxs-lookup"><span data-stu-id="99b72-104">Flexible Types</span></span>

<span data-ttu-id="99b72-105">A *유연한 형식 주석* 매개 변수, 변수 또는 값 클래스 또는 인터페이스의 개체 지향 계층에서 위치에 따라 호환성 결정 되는 지정 된 형식과 호환 되는 형식에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-105">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="99b72-106">유연한 형식을 사용 특히 형식 계층에서 더 높은 형식으로 자동 변환이 발생 하지 않습니다는 계층 구조의 형식으로 또는 인터페이스를 구현 하는 모든 형식을 사용 하 여 기능을 사용 하도록 설정 하려면.</span><span class="sxs-lookup"><span data-stu-id="99b72-106">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="99b72-107">구문</span><span class="sxs-lookup"><span data-stu-id="99b72-107">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="99b72-108">설명</span><span class="sxs-lookup"><span data-stu-id="99b72-108">Remarks</span></span>

<span data-ttu-id="99b72-109">위 구문에서 *형식* 기본 형식 또는 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-109">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="99b72-110">유연한 형식에 허용 되는 형식과 기본 또는 인터페이스 형식과 호환 되는 형식으로 제한 하는 제약 조건이 있는 제네릭 형식을 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-110">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="99b72-111">즉, 다음 두 줄의 코드는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-111">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="99b72-112">유연한 형식은 여러 가지 상황에서에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-112">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="99b72-113">예를 들어, 고차 함수 (함수를 인수로 사용 하는 함수)을 사용 하는 경우 유용 종종 유연한 형식을 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-113">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="99b72-114">다음 예제에 시퀀스 인수가 있는 유연한 형식을 사용 하 여 `iterate2` 시퀀스, 배열, 목록 및 기타 열거 가능한 형식을 생성 하는 함수를 사용 하 여 고차 함수를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-114">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="99b72-115">유연한 형식은 다른 반환 순서는 반환, 하나는 다음 두 가지 기능을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-115">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="99b72-116">또 다른 예로 [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) 라이브러리 함수:</span><span class="sxs-lookup"><span data-stu-id="99b72-116">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="99b72-117">이 함수에 있는 다음 열거 가능한 시퀀스를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-117">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="99b72-118">목록의 목록</span><span class="sxs-lookup"><span data-stu-id="99b72-118">A list of lists</span></span>
- <span data-ttu-id="99b72-119">배열 목록</span><span class="sxs-lookup"><span data-stu-id="99b72-119">A list of arrays</span></span>
- <span data-ttu-id="99b72-120">목록의 배열</span><span class="sxs-lookup"><span data-stu-id="99b72-120">An array of lists</span></span>
- <span data-ttu-id="99b72-121">시퀀스의 배열</span><span class="sxs-lookup"><span data-stu-id="99b72-121">An array of sequences</span></span>
- <span data-ttu-id="99b72-122">열거 가능한 시퀀스의 다른 조합</span><span class="sxs-lookup"><span data-stu-id="99b72-122">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="99b72-123">다음 코드에서는 `Seq.concat` 유연한 형식을 사용 하 여 지원할 수 있는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-123">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="99b72-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-124">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="99b72-125">F #에서 다른 개체 지향 언어와 마찬가지로 없는 컨텍스트는 파생된 형식 또는 인터페이스를 구현 하는 형식을 자동으로 변환 된 기본 형식 또는 인터페이스 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-125">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="99b72-126">이러한 자동 변환의 형식은 형식 인수 또는 반환 형식이 함수 형식인 같은 보다 복잡 한 형식의 일부로 종속 된 위치에 때가 아니라 하지만 직접 인수를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-126">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="99b72-127">따라서 되 게 적용 하는 형식을 더 복잡 한 유형의 일부인 경우 유연한 형식 표기법은 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b72-127">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="99b72-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99b72-128">See Also</span></span>

[<span data-ttu-id="99b72-129">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="99b72-129">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="99b72-130">제네릭</span><span class="sxs-lookup"><span data-stu-id="99b72-130">Generics</span></span>](generics/index.md)
