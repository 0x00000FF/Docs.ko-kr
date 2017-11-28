---
title: "식 트리 요약"
description: "식 트리를 사용하여 코드를 데이터로 해석하고 해당 코드를 기반으로 하는 새 기능을 빌드하는 동적 프로그램을 만드는 방법을 요약합니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 8088ce0c138cdb05a6e4a4fb6467e43efd252ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="expression-trees-summary"></a><span data-ttu-id="84160-104">식 트리 요약</span><span class="sxs-lookup"><span data-stu-id="84160-104">Expression Trees Summary</span></span>

[<span data-ttu-id="84160-105">이전 -- 식 변환</span><span class="sxs-lookup"><span data-stu-id="84160-105">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="84160-106">이 시리즈에서는 *식 트리*를 사용하여 코드를 데이터로 해석하고 해당 코드에 기반한 새 기능을 구축하는 동적 프로그램을 만드는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-106">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="84160-107">식 트리를 검사하여 알고리즘의 의도를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-107">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="84160-108">해당 코드 검사 이상을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-108">You can not only examine that code.</span></span> <span data-ttu-id="84160-109">원래 코드의 수정된 버전을 나타내는 새로운 식 트리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-109">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="84160-110">또한 식 트리를 사용하여 알고리즘을 확인하고 해당 알고리즘을 다른 언어나 환경으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-110">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="84160-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="84160-111">Limitations</span></span>

<span data-ttu-id="84160-112">식 트리로 잘 변환되지 않는 최신 C# 언어 요소가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-112">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="84160-113">식 트리에는 `await` 식이나 `async` 람다 식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-113">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="84160-114">C# 6 릴리스에서 추가된 많은 기능이 식 트리에 작성된 대로 정확하게 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-114">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="84160-115">대신 최신 기능은 해당되는 이전 구문으로 식 트리에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="84160-115">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="84160-116">생각만큼 큰 제한 사항이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-116">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="84160-117">실제로는 새로운 언어 기능이 도입되어도 식 트리를 해석하는 코드가 동일하게 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-117">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="84160-118">이러한 제한 사항에도 불구하고 식 트리를 사용하면 데이터 구조로 표시되는 코드를 해석하고 수정하는 동적 알고리즘을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84160-118">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represetned as a data structure.</span></span> <span data-ttu-id="84160-119">식 트리는 강력한 도구이며 기능을 수행하기 위해 Entity Framework와 같은 풍부한 라이브러리를 사용하는 .NET 에코시스템의 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="84160-119">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>

