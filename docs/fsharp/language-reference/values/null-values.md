---
title: Null 값
description: Null 값 사용 되는 방식을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 58c54065a98a84c4d4e912cbc42d59cfea8c6de1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610998"
---
# <a name="null-values"></a><span data-ttu-id="f596f-103">Null 값</span><span class="sxs-lookup"><span data-stu-id="f596f-103">Null Values</span></span>

<span data-ttu-id="f596f-104">이 항목의 null 값은 사용 하는 방법을 설명 합니다. F#입니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="f596f-105">Null 값</span><span class="sxs-lookup"><span data-stu-id="f596f-105">Null Value</span></span>

<span data-ttu-id="f596f-106">에 null 값은 일반적으로 사용 되지 F# 값 또는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="f596f-107">그러나 null 특정 상황에서 비정상적인 값으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="f596f-108">형식에 정의 된 경우 F#, 하지 않는 한 일반 값으로 null 허용 되지 않습니다 합니다 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) 특성 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="f596f-109">Null은 가능한 값 형식을 정의 하는 몇 가지 다른.NET 언어로, 하는 경우 이러한 형식과 상호 작용 하는 경우에 F# 코드는 null 값을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="f596f-110">에 정의 된 형식에 대 한 F# 에서 엄격 하 게 사용 F#, 유일한 방법은 사용 하 여 null 값에는 F# 라이브러리는 직접 사용 하는 [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) 또는 [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span><span class="sxs-lookup"><span data-stu-id="f596f-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="f596f-111">그러나는 F# 다른.NET 언어에서 사용 되는 형식에 작성 되지 않은 API를 사용 하 여 해당 형식을 사용 하는 경우 또는 F#,.NET Framework 같은 null 값이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="f596f-112">사용할 수는 `option` 입력 F# 경우 다른.NET 언어를 사용할 수 있는 null 값을 사용 하 여 참조 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="f596f-113">Null을 대신 사용 하 여는 F# `option` 형식 옵션 값을 사용 하면 `None` 개체가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="f596f-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="f596f-114">옵션 값을 사용 하면 `Some(obj)` 개체를 사용 하 여 `obj` 개체인 경우.</span><span class="sxs-lookup"><span data-stu-id="f596f-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="f596f-115">자세한 내용은 [옵션](../options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-115">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="f596f-116">합니다 `null` 키워드는 유효한 키워드를 F# 하면 언어 및.NET Framework Api 또는 다른.NET 언어로 작성 된 다른 Api를 사용 하 여 작업할 때 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-116">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="f596f-117">Null 값을 해야 할 수도 있습니다는 두 가지 경우.NET API를 호출 하 고 null 값을 인수로 전달 하는 경우 반환 값 또는.NET 메서드 호출에서 출력 매개 변수를 해석할 때 되며.</span><span class="sxs-lookup"><span data-stu-id="f596f-117">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="f596f-118">Null 값에는.NET 메서드를 전달 하려면 사용 된 `null` 호출 코드의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-118">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="f596f-119">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-119">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="f596f-120">.NET 메서드에서 가져온 null 값을 해석할 수 있는 경우 패턴 일치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-120">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="f596f-121">다음 코드 예제에서 반환 되는 null 값을 해석 하 패턴 일치를 사용 하는 방법을 보여 줍니다 `ReadLine` 입력 스트림의 끝을 넘어 읽으려고 시도할 때.</span><span class="sxs-lookup"><span data-stu-id="f596f-121">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="f596f-122">Null 값에 대 한 F# 형식을 사용 하는 경우와 같이 다른 방법으로 생성할 수도 있습니다 `Array.zeroCreate`를 호출 하는 `Unchecked.defaultof`합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-122">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="f596f-123">캡슐화 된 null 값을 유지 하는 이러한 코드를 사용 하 여 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-123">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="f596f-124">만 위한 라이브러리에서 F#에서 모든 함수에서 null 값을 확인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-124">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="f596f-125">다른.NET 언어와의 상호 운용성에 대 한 라이브러리를 작성 하는 것이 있으면 null 검사 입력 매개 변수 및 throw를 추가 하는 `ArgumentNullException`, C# 또는 Visual Basic 코드에서와 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-125">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="f596f-126">임의의 값을 null 인지 확인 하려면 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f596f-126">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="f596f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f596f-127">See also</span></span>

- [<span data-ttu-id="f596f-128">값</span><span class="sxs-lookup"><span data-stu-id="f596f-128">Values</span></span>](index.md)
- [<span data-ttu-id="f596f-129">일치 식</span><span class="sxs-lookup"><span data-stu-id="f596f-129">Match Expressions</span></span>](../match-expressions.md)