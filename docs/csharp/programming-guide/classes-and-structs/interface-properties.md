---
title: 인터페이스 속성 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: ff892a35f4be6600c00bc0c72c2f789ef6eb4408
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705537"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="ada04-102">인터페이스 속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ada04-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="ada04-103">[interface](../../language-reference/keywords/interface.md)에 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="ada04-104">다음은 인터페이스 속성 접근자의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-104">The following is an example of an interface property accessor:</span></span>

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

<span data-ttu-id="ada04-105">인터페이스 속성의 접근자에는 본문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="ada04-106">따라서 접근자의 목적은 속성이 읽기/쓰기인지, 읽기 전용인지, 쓰기 전용인지를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>

## <a name="example"></a><span data-ttu-id="ada04-107">예제</span><span class="sxs-lookup"><span data-stu-id="ada04-107">Example</span></span>

<span data-ttu-id="ada04-108">이 예제에서 `IEmployee` 인터페이스에는 읽기/쓰기 속성 `Name`과 읽기 전용 속성 `Counter`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="ada04-109">`Employee` 클래스는 `IEmployee` 인터페이스를 구현하고 이러한 두 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="ada04-110">프로그램은 새 직원의 이름과 현재 직원 수를 읽고 직원 이름과 계산된 직원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="ada04-111">멤버가 선언된 인터페이스를 참조하는 속성의 정규화된 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="ada04-112">예:</span><span class="sxs-lookup"><span data-stu-id="ada04-112">For example:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="ada04-113">이를 [명시적 인터페이스 구현](../interfaces/explicit-interface-implementation.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-113">This is called [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="ada04-114">예를 들어 `Employee` 클래스가 두 인터페이스 `ICitizen` 및 `IEmployee`를 구현하고 두 인터페이스에 모두 `Name` 속성이 있으면 명시적 인터페이스 멤버 구현이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="ada04-115">즉, 다음과 같은 속성 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-115">That is, the following property declaration:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="ada04-116">이 선언은 `IEmployee` 인터페이스의 `Name` 속성을 구현합니다. 또한 다음과 같은 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

<span data-ttu-id="ada04-117">이 선언은 `ICitizen` 인터페이스의 `Name` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ada04-117">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="ada04-118">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="ada04-118">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="ada04-119">참조</span><span class="sxs-lookup"><span data-stu-id="ada04-119">See also</span></span>

- [<span data-ttu-id="ada04-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ada04-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ada04-121">속성</span><span class="sxs-lookup"><span data-stu-id="ada04-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="ada04-122">속성 사용</span><span class="sxs-lookup"><span data-stu-id="ada04-122">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="ada04-123">속성 및 인덱서 비교</span><span class="sxs-lookup"><span data-stu-id="ada04-123">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="ada04-124">인덱서</span><span class="sxs-lookup"><span data-stu-id="ada04-124">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="ada04-125">인터페이스</span><span class="sxs-lookup"><span data-stu-id="ada04-125">Interfaces</span></span>](../interfaces/index.md)
