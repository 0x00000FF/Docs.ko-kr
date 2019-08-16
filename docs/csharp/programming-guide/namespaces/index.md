---
title: 네임스페이스 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: cf5a7f239cf7d3cd3a6e39f31d16adb830646afc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039491"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="36464-102">네임스페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="36464-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="36464-103">네임스페이스는 C# 프로그래밍에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36464-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="36464-104">첫째, .NET Framework는 네임스페이스를 사용하여 다음과 같이 많은 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36464-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="36464-105">`System`은 네임스페이스이고 `Console`은 해당 네임스페이스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="36464-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="36464-106">전체 키워드가 필요하지 않으므로 다음 예처럼 `using` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36464-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="36464-107">자세한 내용은 [using 지시문](../../language-reference/keywords/using-directive.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36464-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="36464-108">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36464-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="36464-109">다음 예와 같이 [네임스페이스](../../language-reference/keywords/namespace.md) 키워드를 사용하여 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="36464-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="36464-110">네임스페이스 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36464-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="36464-111">네임스페이스 개요</span><span class="sxs-lookup"><span data-stu-id="36464-111">Namespaces Overview</span></span>  

<span data-ttu-id="36464-112">네임스페이스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36464-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="36464-113">대규모 코드 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36464-113">They organize large code projects.</span></span>  
- <span data-ttu-id="36464-114">`.` 연산자를 사용하여 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="36464-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="36464-115">`using` 지시문은 모든 클래스에 대해 네임스페이스 이름을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36464-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="36464-116">`global` 네임스페이스는 “루트” 네임스페이스입니다. `global::System`은 항상 .NET <xref:System> 네임스페이스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="36464-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="36464-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="36464-117">C# language specification</span></span>

<span data-ttu-id="36464-118">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [네임스페이스](~/_csharplang/spec/namespaces.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36464-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36464-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36464-119">See also</span></span>

- [<span data-ttu-id="36464-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="36464-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="36464-121">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="36464-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="36464-122">방법: My 네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="36464-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="36464-123">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="36464-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="36464-124">using 지시문</span><span class="sxs-lookup"><span data-stu-id="36464-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="36464-125">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="36464-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
