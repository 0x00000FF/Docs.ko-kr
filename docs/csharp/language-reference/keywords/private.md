---
title: private 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: a20c0a6fd729c2fc34449167eb92cb774bc3b84e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602018"
---
# <a name="private-c-reference"></a><span data-ttu-id="8c86b-102">private(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8c86b-102">private (C# Reference)</span></span>

<span data-ttu-id="8c86b-103">`private` 키워드는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="8c86b-104">이 페이지에서는 `private` 액세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-104">This page covers `private` access.</span></span> <span data-ttu-id="8c86b-105">`private` 키워드는 [`private protected`](./private-protected.md) 액세스 한정자의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="8c86b-106">private 액세스는 가장 낮은 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="8c86b-107">private 멤버는 이 예제와 같이 선언된 클래스 또는 구조체의 본문 내에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="8c86b-108">동일한 본문에 중첩된 형식도 이러한 private 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="8c86b-109">선언된 클래스 또는 구조체 외부에서 private 멤버를 참조하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="8c86b-110">`private` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](accessibility-levels.md) 및 [액세스 한정자](../../programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c86b-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="8c86b-111">예제</span><span class="sxs-lookup"><span data-stu-id="8c86b-111">Example</span></span>

<span data-ttu-id="8c86b-112">이 예제에서 `Employee` 클래스는 두 전용 데이터 멤버인 `name` 및 `salary`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="8c86b-113">private 멤버는 멤버 메서드에 의한 경우를 제외하고 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="8c86b-114">`GetName` 및 `Salary`라는 public 메서드는 private 멤버에 제어된 액세스 권한을 허용하기 위해 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="8c86b-115">`name` 멤버는 public 메서드를 통해 액세스하고, `salary` 멤버는 public 읽기 전용 속성을 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="8c86b-116">자세한 내용은 [속성](../../programming-guide/classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c86b-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="8c86b-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8c86b-117">C# language specification</span></span>  

<span data-ttu-id="8c86b-118">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [선언된 내게 필요한 옵션](~/_csharplang/spec/basic-concepts.md#declared-accessibility)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c86b-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="8c86b-119">C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c86b-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c86b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c86b-120">See also</span></span>

- [<span data-ttu-id="8c86b-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8c86b-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8c86b-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8c86b-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8c86b-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8c86b-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8c86b-124">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="8c86b-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="8c86b-125">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8c86b-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="8c86b-126">한정자</span><span class="sxs-lookup"><span data-stu-id="8c86b-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="8c86b-127">public</span><span class="sxs-lookup"><span data-stu-id="8c86b-127">public</span></span>](public.md)
- [<span data-ttu-id="8c86b-128">protected</span><span class="sxs-lookup"><span data-stu-id="8c86b-128">protected</span></span>](protected.md)
- [<span data-ttu-id="8c86b-129">internal</span><span class="sxs-lookup"><span data-stu-id="8c86b-129">internal</span></span>](internal.md)
