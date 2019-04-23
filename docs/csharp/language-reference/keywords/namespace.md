---
title: 네임스페이스 키워드 - C# 참조
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 4859c361b3321c1144204f63896152694f6ac5c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148761"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="8421d-102">namespace(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8421d-102">namespace (C# Reference)</span></span>

<span data-ttu-id="8421d-103">`namespace` 키워드는 관련 개체 집합을 포함하는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="8421d-104">네임스페이스를 사용하여 코드 요소를 구성하고 전역적으로 고유한 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="8421d-105">주의</span><span class="sxs-lookup"><span data-stu-id="8421d-105">Remarks</span></span>

<span data-ttu-id="8421d-106">네임스페이스 내에서 다음 형식 중 0개 이상을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="8421d-107">다른 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8421d-107">another namespace</span></span>

- [<span data-ttu-id="8421d-108">class</span><span class="sxs-lookup"><span data-stu-id="8421d-108">class</span></span>](class.md)

- [<span data-ttu-id="8421d-109">interface</span><span class="sxs-lookup"><span data-stu-id="8421d-109">interface</span></span>](interface.md)

- [<span data-ttu-id="8421d-110">struct</span><span class="sxs-lookup"><span data-stu-id="8421d-110">struct</span></span>](struct.md)

- [<span data-ttu-id="8421d-111">enum</span><span class="sxs-lookup"><span data-stu-id="8421d-111">enum</span></span>](enum.md)

- [<span data-ttu-id="8421d-112">delegate</span><span class="sxs-lookup"><span data-stu-id="8421d-112">delegate</span></span>](delegate.md)

<span data-ttu-id="8421d-113">C# 소스 파일에서 네임스페이스를 명시적으로 선언하는지 여부에 관계없이 컴파일러는 기본 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="8421d-114">전역 네임스페이스라고도 하는 이 명명되지 않은 네임스페이스는 모든 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="8421d-115">전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="8421d-116">네임스페이스는 암시적으로 공용 액세스를 사용하며 이 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="8421d-117">네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 설명은 [액세스 한정자](access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8421d-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="8421d-118">둘 이상의 선언에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="8421d-119">예를 들어 다음 예제에서는 `MyCompany` 네임스페이스의 일부로 두 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="8421d-120">예제</span><span class="sxs-lookup"><span data-stu-id="8421d-120">Example</span></span>

<span data-ttu-id="8421d-121">다음 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8421d-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="8421d-122">관련 참고 자료</span><span class="sxs-lookup"><span data-stu-id="8421d-122">Related resources</span></span>

<span data-ttu-id="8421d-123">네임스페이스를 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8421d-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="8421d-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8421d-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="8421d-125">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="8421d-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="8421d-126">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="8421d-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="8421d-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8421d-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8421d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8421d-128">See also</span></span>

- [<span data-ttu-id="8421d-129">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8421d-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="8421d-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8421d-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8421d-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8421d-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8421d-132">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="8421d-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="8421d-133">using</span><span class="sxs-lookup"><span data-stu-id="8421d-133">using</span></span>](using-directive.md)
- [<span data-ttu-id="8421d-134">using static</span><span class="sxs-lookup"><span data-stu-id="8421d-134">using static</span></span>](using-static.md)