---
title: 형식 약어(F#)
description: '형식에 이름을 더 의미 있는 코드를 쉽게 읽을 수 있도록 하기 위해 F # 형식 약어에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 259cd6c84e22fc7c98e08255d3e0ded5b87af352
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44336474"
---
# <a name="type-abbreviations"></a><span data-ttu-id="37da6-103">형식 약어</span><span class="sxs-lookup"><span data-stu-id="37da6-103">Type Abbreviations</span></span>

<span data-ttu-id="37da6-104">A *형식 약어* 별칭 또는 형식의 이름을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="37da6-105">구문</span><span class="sxs-lookup"><span data-stu-id="37da6-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="37da6-106">설명</span><span class="sxs-lookup"><span data-stu-id="37da6-106">Remarks</span></span>

<span data-ttu-id="37da6-107">형식에 이름을 더 의미 있는, 코드를 쉽게 읽을 수 있도록 하기 위해 형식 약어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="37da6-108">그렇지 않은 경우에 번거로운 작업 작성 하는 형식에 대 한 사용 하기 쉬운 이름을 만들 수 에서도 사용할 수 있습니다. 또한 쉽게 형식을 사용 하는 모든 코드를 변경 하지 않고 내부 형식을 변경할 수 있도록 형식 약어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="37da6-109">다음은 간단한 형식 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="37da6-110">기본적으로 형식 약어의 접근성 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="37da6-111">형식 약어에는 다음 코드와 같이 제네릭 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="37da6-112">이전 코드에서 `Transform` 형식의 단일 인수를 사용 하는 함수를 나타내는 형식 약어 이며 동일한 형식의 단일 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="37da6-113">.NET Framework MSIL 코드에서 형식 약어 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="37da6-114">따라서 다른.NET Framework 언어에서 F # 어셈블리를 사용 하면 형식 약어에 대 한 기본 형식 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="37da6-115">측정 단위 형식 약어를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="37da6-116">자세한 내용은 [측정 단위를](units-of-measure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="37da6-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="37da6-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="37da6-117">See also</span></span>

- [<span data-ttu-id="37da6-118">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="37da6-118">F# Language Reference</span></span>](index.md)
