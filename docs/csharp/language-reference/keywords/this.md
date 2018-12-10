---
title: this 키워드(C# 참조)
description: this 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 52e7fce0ebeeccfbf5f56dbbcade9fae2890dfe1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130822"
---
# <a name="this-c-reference"></a><span data-ttu-id="68b17-103">this(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="68b17-103">this (C# Reference)</span></span>

<span data-ttu-id="68b17-104">`this` 키워드는 클래스의 현재 인스턴스를 가리키며 확장 메서드의 첫 번째 매개 변수에 대한 한정자로도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="68b17-105">이 문서에서는 클래스 인스턴스와 함께 `this`를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="68b17-106">확장 메서드에서 사용하는 방법에 대한 자세한 내용은 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68b17-106">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="68b17-107">`this`의 일반적인 사용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="68b17-108">비슷한 이름으로 숨겨진 멤버를 한정합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="68b17-109">개체를 다른 메서드에 매개 변수로 전달합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="68b17-110">인덱서를 선언합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="68b17-111">정적 멤버 함수는 개체의 일부가 아니라 클래스 수준에 있기 때문에 `this` 포인터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="68b17-112">정적 메서드에서 `this`를 참조하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="68b17-113">예</span><span class="sxs-lookup"><span data-stu-id="68b17-113">Example</span></span>

<span data-ttu-id="68b17-114">이 예제에서는 `this`를 사용하여 유사한 이름으로 숨겨진 `Employee` 클래스 멤버 `name` 및 `alias`를 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="68b17-115">다른 클래스에 속하는 `CalcTax` 메서드에 개체를 전달하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68b17-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="68b17-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="68b17-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="68b17-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68b17-117">See also</span></span>

- [<span data-ttu-id="68b17-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="68b17-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="68b17-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68b17-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="68b17-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="68b17-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="68b17-121">base</span><span class="sxs-lookup"><span data-stu-id="68b17-121">base</span></span>](base.md)
- [<span data-ttu-id="68b17-122">메서드</span><span class="sxs-lookup"><span data-stu-id="68b17-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
