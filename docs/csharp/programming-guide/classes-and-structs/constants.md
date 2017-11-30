---
title: "상수(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81a085ff016fb9ee8f8a13167728c37ca799920a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="0e568-102">상수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0e568-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="0e568-103">상수는 컴파일 시간에 알려진 변경할 수 없는 값입니다. 프로그램 수명 동안 변경하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0e568-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="0e568-104">상수는 [const](../../../csharp/language-reference/keywords/const.md) 한정자로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="0e568-105">C# 기본 제공 형식(<xref:System.Object?displayProperty=nameWithType> 제외)만 `const`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=nameWithType>) may be declared as `const`.</span></span> <span data-ttu-id="0e568-106">기본 제공 형식 목록은 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e568-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="0e568-107">클래스, 구조체 및 배열을 비롯한 사용자 정의 형식은 `const`가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="0e568-108">[readonly](../../../csharp/language-reference/keywords/readonly.md) 한정자를 사용하여 런타임에 한 번 초기화되고(예: 생성자에서) 이후 변경할 수 없는 클래스, 구조체 또는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="0e568-109">C#에서는 `const` 메서드, 속성 또는 이벤트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="0e568-110">열거형 형식을 사용하여 정수 계열 기본 제공 형식(예: `int`, `uint`, `long` 등)에 대한 명명된 상수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="0e568-111">자세한 내용은 [enum](../../../csharp/language-reference/keywords/enum.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e568-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="0e568-112">상수는 선언될 때 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="0e568-113">예:</span><span class="sxs-lookup"><span data-stu-id="0e568-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 <span data-ttu-id="0e568-114">이 예제에서 `months` 상수는 항상 12이고 클래스 자체에 의해서도 변경될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-114">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="0e568-115">실제로 컴파일러는 C# 소스 코드에서 상수 식별자를 발견할 경우(예: `months`) 리터럴 값을 직접 컴파일러에서 생성하는 IL(중간 언어) 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-115">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="0e568-116">런타임에 상수와 연결된 변수 주소가 없으므로 `const` 필드는 참조를 통해 전달될 수 없고 식에 l-value로 표시될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-116">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e568-117">DLL과 같이 다른 코드에 정의된 상수 값을 참조할 경우 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="0e568-117">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="0e568-118">DLL의 새 버전에서 상수의 새 값을 정의할 경우 프로그램은 새 버전에 대해 다시 컴파일될 때까지 이전 리터럴 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-118">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="0e568-119">다음과 같이 같은 형식의 여러 상수를 동시에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-119">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 <span data-ttu-id="0e568-120">상수를 초기화하는 데 사용되는 식은 순환 참조를 만들지 않을 경우 다른 상수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-120">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="0e568-121">예:</span><span class="sxs-lookup"><span data-stu-id="0e568-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 <span data-ttu-id="0e568-122">로 상수를 표시할 수 있습니다 [공용](../../../csharp/language-reference/keywords/public.md), [개인](../../../csharp/language-reference/keywords/private.md), [보호](../../../csharp/language-reference/keywords/protected.md), [내부](../../../csharp/language-reference/keywords/internal.md), [내부보호](../../../csharp/language-reference/keywords/protected-internal.md)또는 [보호 된 개인](../../../csharp/language-reference/keywords/private-protected.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-122">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="0e568-123">이러한 액세스 한정자는 클래스의 사용자가 상수에 액세스하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-123">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="0e568-124">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e568-124">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="0e568-125">형식의 모든 인스턴스에 대한 상수 값이 같으므로 상수가 [static](../../../csharp/language-reference/keywords/static.md) 필드인 것처럼 상수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-125">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="0e568-126">상수를 선언하는 데 `static` 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-126">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="0e568-127">상수를 정의하는 클래스에 포함되지 않은 식은 상수에 액세스할 때 클래스 이름, 마침표 및 상수 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e568-127">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="0e568-128">예:</span><span class="sxs-lookup"><span data-stu-id="0e568-128">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0e568-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0e568-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0e568-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e568-130">See Also</span></span>  
 [<span data-ttu-id="0e568-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0e568-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0e568-132">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="0e568-132">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="0e568-133">속성</span><span class="sxs-lookup"><span data-stu-id="0e568-133">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="0e568-134">유형</span><span class="sxs-lookup"><span data-stu-id="0e568-134">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="0e568-135">readonly</span><span class="sxs-lookup"><span data-stu-id="0e568-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)  
 <span data-ttu-id="0e568-136">[Immutability in C# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)(C#의 불변성 1부: 불변성 종류)</span><span class="sxs-lookup"><span data-stu-id="0e568-136">[Immutability in C# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)</span></span>
