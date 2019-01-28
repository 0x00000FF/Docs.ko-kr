---
title: '@ - C# 참조'
ms.custom: seodec18
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2302c2602411455c0f3f0371579fc9be200004d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660855"
---
# <a name="-c-reference"></a><span data-ttu-id="af0e0-102">@(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="af0e0-102">@ (C# Reference)</span></span>

<span data-ttu-id="af0e0-103">`@` 특수 문자는 축자 식별자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="af0e0-104">다음과 같은 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="af0e0-105">C# 키워드를 식별자로 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="af0e0-106">`@` 문자는 컴파일러가 C# 키워드가 아닌 식별자로 해석할 코드 요소의 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="af0e0-107">다음 예제에서는 `@` 문자를 사용하여 `for` 루프에서 사용되는 `for`라는 이름의 식별자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="af0e0-108">문자열 리터럴이 축자로 해석될 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="af0e0-109">이 인스턴스의 `@` 문자는 *축자 문자 문자열*을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="af0e0-110">단순 이스케이프 시퀀스(예: 백슬래시에 `"\\"`), 16진수 이스케이프 시퀀스(예: 대문자 A에 `"\x0041"`), 유니코드 이스케이프 시퀀스(예: 대문자 A에 `"\u0041"`)는 문자 그대로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="af0e0-111">인용 부호 이스케이프 시퀀스(`""`)만 문자 그대로 해석되지 않고, 단일 작은따옴표를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="af0e0-112">또한 축자 [보간된 문자열](interpolated.md) 중괄호 이스케이프 시퀀스(`{{` 및 `}}`)는 그대로 해석되지 않습니다. 단일 중괄호 문자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="af0e0-113">다음 예제에서는 각각 일반 문자열 리터럴 및 축자 문자열 리터럴을 사용하여 두 개의 동일한 파일 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="af0e0-114">이것은 축자 문자열 리터럴의 일반적인 사용법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="af0e0-115">다음 예제에서는 동일한 문자 시퀀스를 포함한 일반 문자열 리터럴 및 축자 문자열 리터럴의 효과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="af0e0-116">이름이 서로 충돌하는 경우 특성 간에 구분하기 위해 컴파일러를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="af0e0-117">특성은 <xref:System.Attribute>에서 파생되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-117">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="af0e0-118">컴파일러는 이 규칙을 적용하지 않지만, 형식 이름에는 일반적으로 **Attribute** 접미사가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="af0e0-119">전체 이름(예: `[InfoAttribute]`) 또는 약식 이름(예: `[Info]`)으로 코드에서 특성을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="af0e0-120">그러나 두 개의 약식 특성 유형 이름이 동일하고 한 유형 이름에만 **Attribute** 접미사가 포함된 경우 이름 충돌이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="af0e0-121">다음 예에서는 컴파일러가 `Info` 및 `InfoAttribute` 특성 중 무엇을 `Example` 클래스에 적용할지 결정할 수 없으므로 코드가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af0e0-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="af0e0-122">자세한 내용은 [CS1614](../compiler-messages/cs1614.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af0e0-122">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="af0e0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af0e0-123">See also</span></span>

- [<span data-ttu-id="af0e0-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="af0e0-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="af0e0-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="af0e0-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="af0e0-126">C# 특수 문자</span><span class="sxs-lookup"><span data-stu-id="af0e0-126">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)
