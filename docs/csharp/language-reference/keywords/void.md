---
title: void - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: af79d39282ea38811777ea1f23054120afc39d2c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632946"
---
# <a name="void-c-reference"></a><span data-ttu-id="ecba1-102">void(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ecba1-102">void (C# Reference)</span></span>

<span data-ttu-id="ecba1-103">메서드에 대한 반환 형식으로 사용될 경우 `void`는 메서드가 값을 반환하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ecba1-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="ecba1-104">`void`는 메서드의 매개 변수 목록에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecba1-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="ecba1-105">매개 변수를 사용하지 않고 값을 반환하지 않는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecba1-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="ecba1-106">`void`는 또한 알 수 없는 형식에 대한 포인터를 선언하기 위해 안전하지 않은 컨텍스트에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecba1-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="ecba1-107">자세한 내용은 [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecba1-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="ecba1-108">`void`는 .NET Framework <xref:System.Void?displayProperty=nameWithType> 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ecba1-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ecba1-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ecba1-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ecba1-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecba1-110">See also</span></span>

- [<span data-ttu-id="ecba1-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ecba1-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ecba1-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ecba1-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ecba1-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="ecba1-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ecba1-114">참조 형식</span><span class="sxs-lookup"><span data-stu-id="ecba1-114">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="ecba1-115">값 형식</span><span class="sxs-lookup"><span data-stu-id="ecba1-115">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="ecba1-116">메서드</span><span class="sxs-lookup"><span data-stu-id="ecba1-116">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="ecba1-117">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="ecba1-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
