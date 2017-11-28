---
title: "struct(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e8a848d5543291ef335e72cb7806158827e865dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="struct-c-reference"></a><span data-ttu-id="b6956-102">struct(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b6956-102">struct (C# Reference)</span></span>
<span data-ttu-id="b6956-103">`struct` 형식은 인벤토리의 항목 특성이나 사각형의 좌표와 같은 관련 변수의 소규모 그룹을 캡슐화하는 데 일반적으로 사용되는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6956-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="b6956-104">다음 예제에서는 간단한 구조체 선언을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6956-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b6956-105">설명</span><span class="sxs-lookup"><span data-stu-id="b6956-105">Remarks</span></span>  
 <span data-ttu-id="b6956-106">구조체는 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md), [상수](../../../csharp/programming-guide/classes-and-structs/constants.md), [필드](../../../csharp/programming-guide/classes-and-structs/fields.md), [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md), [인덱서](../../../csharp/programming-guide/indexers/index.md), [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [이벤트](../../../csharp/programming-guide/events/index.md) 및 [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)도 포함할 수 있습니다. 그러나 이러한 멤버가 여러 개 필요한 경우에는 구조체 대신 클래스 형식을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6956-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="b6956-107">예제를 보려면 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6956-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="b6956-108">구조체는 인터페이스를 구현할 수는 있지만 다른 구조체를 상속할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6956-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="b6956-109">그러므로 구조체 멤버를 `protected`로 선언할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6956-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="b6956-110">자세한 내용은 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6956-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b6956-111">예제</span><span class="sxs-lookup"><span data-stu-id="b6956-111">Examples</span></span>  
 <span data-ttu-id="b6956-112">예제 및 자세한 내용은 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6956-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b6956-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b6956-113">C# Language Specification</span></span>  
 <span data-ttu-id="b6956-114">예제를 보려면 [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6956-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6956-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6956-115">See Also</span></span>  
 [<span data-ttu-id="b6956-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b6956-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b6956-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b6956-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b6956-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="b6956-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b6956-119">기본값 표</span><span class="sxs-lookup"><span data-stu-id="b6956-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="b6956-120">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="b6956-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="b6956-121">유형</span><span class="sxs-lookup"><span data-stu-id="b6956-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b6956-122">값 형식</span><span class="sxs-lookup"><span data-stu-id="b6956-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="b6956-123">class</span><span class="sxs-lookup"><span data-stu-id="b6956-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="b6956-124">interface</span><span class="sxs-lookup"><span data-stu-id="b6956-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="b6956-125">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="b6956-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
