---
title: out 키워드(제네릭 한정자)(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: fedbdb12c1da108d17636770fb5c628195dce0d4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44206132"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="bba62-102">out(제네릭 한정자)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bba62-102">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="bba62-103">제네릭 형식 매개 변수에서 `out` 키워드는 형식 매개 변수를 공변(covariant)으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="bba62-104">제네릭 인터페이스 및 대리자에서 `out` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="bba62-105">공변성(covariance)을 통해 제네릭 매개 변수에 지정된 것보다 많은 파생 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="bba62-106">따라서 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="bba62-107">공변성(Covariance) 및 반공변성(Contravariance)은 참조 형식에 대해 지원되고 값 형식에 대해서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="bba62-108">공변(covariant) 형식 매개 변수가 있는 인터페이스는 해당 메서드가 형식 인터페이스에 지정된 것보다 많은 파생 형식을 반환할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="bba62-109">예를 들어 .NET Framework 4의 <xref:System.Collections.Generic.IEnumerable%601>에서 T 형식은 공변(covariant)이므로 특수 변환 메서드를 사용하지 않고 `IEnumerable(Of String)` 형식의 개체를 `IEnumerable(Of Object)` 형식의 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="bba62-110">공변(covariant) 대리자에 동일한 형식의 다른 대리자를 할당할 수 있지만 더 파생된 제네릭 형식 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="bba62-111">자세한 내용은 [공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bba62-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="bba62-112">예제 - 공변(covariant) 제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bba62-112">Example - covariant generic interface</span></span>

<span data-ttu-id="bba62-113">다음 예제에서는 공변(covariant) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="bba62-114">또한 공변(covariant) 인터페이스를 구현하는 클래스에 대해 암시적 변환을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="bba62-115">제네릭 인터페이스에서 형식 매개 변수가 다음 조건을 충족하는 경우 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="bba62-116">형식 매개 변수는 인터페이스 메서드의 반환 형식으로만 사용되고 메서드 인수의 형식으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bba62-117">그러나 이 규칙에는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-117">There is one exception to this rule.</span></span> <span data-ttu-id="bba62-118">공변(covariant) 인터페이스에 메서드 매개 변수로 반공변(contravariant) 제네릭 대리자가 있는 경우 공변(covariant) 형식을 이 대리자에 대한 제네릭 형식 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="bba62-119">공변(covariant) 및 반공변(contravariant) 제네릭 대리자에 대한 자세한 내용은 [대리자의 가변성](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자에 가변성 사용](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bba62-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="bba62-120">형식 매개 변수는 인터페이스 메서드에 대한 제네릭 제약 조건으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="bba62-121">예제 - 공변(covariant) 제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="bba62-121">Example - covariant generic delegate</span></span>

<span data-ttu-id="bba62-122">다음 예제에서는 공변(covariant) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="bba62-123">또한 대리자 형식을 암시적으로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-123">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="bba62-124">제네릭 대리자에서 형식이 메서드 반환 형식으로만 사용되고 메서드 인수에 사용되지 않는 경우 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba62-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bba62-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bba62-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bba62-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bba62-126">See also</span></span>

- [<span data-ttu-id="bba62-127">제네릭 인터페이스의 가변성</span><span class="sxs-lookup"><span data-stu-id="bba62-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="bba62-128">in</span><span class="sxs-lookup"><span data-stu-id="bba62-128">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="bba62-129">한정자</span><span class="sxs-lookup"><span data-stu-id="bba62-129">Modifiers</span></span>](modifiers.md)