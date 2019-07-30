---
title: 네임스페이스 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 79b7057b1f6a9cdba2215124160b28efb9a1c0be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629526"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="d2a41-102">네임스페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d2a41-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="d2a41-103">네임스페이스는 C# 프로그래밍에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="d2a41-104">첫째, .NET Framework는 네임스페이스를 사용하여 다음과 같이 많은 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="d2a41-105">`System`은 네임스페이스이고 `Console`은 해당 네임스페이스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="d2a41-106">전체 키워드가 필요하지 않으므로 다음 예처럼 `using` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="d2a41-107">자세한 내용은 [using 지시문](../../language-reference/keywords/using-directive.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a41-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="d2a41-108">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="d2a41-109">다음 예와 같이 [네임스페이스](../../language-reference/keywords/namespace.md) 키워드를 사용하여 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="d2a41-110">네임스페이스 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="d2a41-111">네임스페이스 개요</span><span class="sxs-lookup"><span data-stu-id="d2a41-111">Namespaces Overview</span></span>  

<span data-ttu-id="d2a41-112">네임스페이스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="d2a41-113">대규모 코드 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-113">They organize large code projects.</span></span>  
- <span data-ttu-id="d2a41-114">`.` 연산자를 사용하여 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="d2a41-115">`using` 지시문은 모든 클래스에 대해 네임스페이스 이름을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="d2a41-116">`global` 네임스페이스는 “루트” 네임스페이스입니다. `global::System`은 항상 .NET <xref:System> 네임스페이스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d2a41-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="d2a41-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d2a41-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2a41-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a41-118">See also</span></span>

- [<span data-ttu-id="d2a41-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d2a41-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d2a41-120">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="d2a41-120">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="d2a41-121">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="d2a41-121">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="d2a41-122">방법: My 네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="d2a41-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="d2a41-123">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="d2a41-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="d2a41-124">using 지시문</span><span class="sxs-lookup"><span data-stu-id="d2a41-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="d2a41-125">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="d2a41-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
