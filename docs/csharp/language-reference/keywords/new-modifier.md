---
title: new 한정자(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 496339a7c3b95f16fd13479b096d90058b0799d4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213542"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="3ab9d-102">new 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3ab9d-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="3ab9d-103">선언 한정자로 사용되는 `new` 키워드는 기본 클래스에서 상속된 멤버를 명시적으로 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="3ab9d-104">상속된 멤버를 숨기면 파생 버전의 멤버로 기본 클래스 버전의 멤버를 대신하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="3ab9d-105">`new` 한정자를 사용하지 않고 멤버를 숨길 수도 있지만 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="3ab9d-106">`new`를 사용하여 멤버를 명시적으로 숨기면 이 경고가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="3ab9d-107">상속된 멤버를 숨기려면 동일한 멤버 이름을 사용하여 파생된 클래스에 해당 멤버를 선언한 다음 `new` 키워드를 사용하여 이를 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="3ab9d-108">예:</span><span class="sxs-lookup"><span data-stu-id="3ab9d-108">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="3ab9d-109">이 예제에서 `BaseC.Invoke`는 `DerivedC.Invoke`에 의해 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="3ab9d-110">`x` 필드는 비슷한 이름으로 숨겨져 있지 않기 때문에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="3ab9d-111">상속을 사용한 이름 숨기기는 다음 중 한 가지 형식을 취합니다. </span><span class="sxs-lookup"><span data-stu-id="3ab9d-111">Name hiding through inheritance takes one of the following forms:</span></span>

<span data-ttu-id="3ab9d-112">일반적으로 클래스 또는 구조체에 파생된 상수, 필드, 속성 또는 형식은 동일한 이름의 모든 기본 클래스 멤버를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="3ab9d-113">이 사항이 적용되지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-113">There are special cases.</span></span>  <span data-ttu-id="3ab9d-114">예를 들어 호출할 수 없는 형식이 포함된 `N`이라는 이름의 새 필드를 선언하고 기본 형식에서 `N`을 메서드로 선언하면 새 필드가 호출 구문에서 기본 선언을 숨기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="3ab9d-115">자세한 내용은 [C# 5.0 언어 사양](https://www.microsoft.com/download/details.aspx?id=7029)을 참조하세요("식" 섹션의 "멤버 조회" 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="3ab9d-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>

<span data-ttu-id="3ab9d-116">클래스 또는 구조체에 파생된 메서드는 기본 클래스에서 동일한 이름의 속성, 필드 및 형식을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="3ab9d-117">또한 시그니처가 동일한 기본 클래스 메서드도 모두 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-117">It also hides all base class methods that have the same signature.</span></span>

<span data-ttu-id="3ab9d-118">클래스 또는 구조체에 파생된 인덱서는 시그니처가 동일한 기본 클래스 인덱서를 모두 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="3ab9d-119">동일한 멤버에 대해 `new`와 [override](override.md)를 모두 사용하면 오류가 발생합니다. 두 한정자는 함께 사용할 수 없는 의미를 지니고 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-119">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="3ab9d-120">`new` 한정자는 동일한 이름의 새 멤버를 만들고 원래 멤버를 숨기도록 하는 반면,</span><span class="sxs-lookup"><span data-stu-id="3ab9d-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="3ab9d-121">`override` 한정자는 상속된 멤버에 대한 구현을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-121">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="3ab9d-122">상속된 멤버를 숨기지 않는 선언에 `new` 한정자를 사용하면 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="3ab9d-123">예</span><span class="sxs-lookup"><span data-stu-id="3ab9d-123">Example</span></span>

<span data-ttu-id="3ab9d-124">이 예제에서 기본 클래스 `BaseC` 및 파생 클래스 `DerivedC`는 동일한 필드 이름 `x`를 사용하므로 상속된 필드의 값이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="3ab9d-125">이 예제에서는 `new` 한정자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="3ab9d-126">또한 정규화된 이름을 사용하여 기본 클래스의 숨겨진 멤버에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="3ab9d-127">예</span><span class="sxs-lookup"><span data-stu-id="3ab9d-127">Example</span></span>

<span data-ttu-id="3ab9d-128">이 예제에서 중첩 클래스는 기본 클래스에서 이름이 동일한 클래스를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="3ab9d-129">이 예제에서는 `new` 한정자를 사용하여 경고 메시지를 제거하는 방법과 정규화된 이름을 사용하여 숨겨진 클래스 멤버에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="3ab9d-130">`new` 한정자를 제거해도 프로그램은 컴파일되고 실행되지만 다음과 같은 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3ab9d-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="3ab9d-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3ab9d-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3ab9d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ab9d-132">See also</span></span>

- [<span data-ttu-id="3ab9d-133">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3ab9d-133">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="3ab9d-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3ab9d-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3ab9d-135">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="3ab9d-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3ab9d-136">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="3ab9d-136">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="3ab9d-137">한정자</span><span class="sxs-lookup"><span data-stu-id="3ab9d-137">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="3ab9d-138">Override 및 New 키워드를 사용하여 버전 관리</span><span class="sxs-lookup"><span data-stu-id="3ab9d-138">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="3ab9d-139">Override 및 New 키워드를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="3ab9d-139">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
