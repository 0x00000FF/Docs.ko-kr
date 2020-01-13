---
title: 생성자 - C# 프로그래밍 가이드
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 9c57ff6dd9acd8a8bcff6de4fce7d898f1135703
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714960"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="7c665-102">생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7c665-102">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="7c665-103">[class](../../language-reference/keywords/class.md) 또는 [struct](../../language-reference/keywords/struct.md)를 만들 때마다 해당 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-103">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="7c665-104">클래스 또는 구조체에는 서로 다른 인수를 사용하는 여러 생성자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="7c665-105">프로그래머는 생성자를 통해 기본값을 설정하고, 인스턴스화를 제한하며, 유연하고 읽기 쉬운 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="7c665-106">자세한 내용 및 예제는 [생성자 사용](./using-constructors.md) 및 [인스턴스 생성자](./instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c665-106">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="7c665-107">매개 변수 없는 생성자</span><span class="sxs-lookup"><span data-stu-id="7c665-107">Parameterless constructors</span></span>
  
<span data-ttu-id="7c665-108">클래스에 대한 생성자를 제공하지 않으면 C#이 기본적으로 개체를 인스턴스화하고 멤버 변수를 [기본값 표](../../language-reference/keywords/default-values-table.md)에 나열된 기본값으로 설정하는 생성자를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="7c665-109">구조체에 대한 생성자를 제공하지 않으면 C#이 *암시적 매개 변수 없는 생성자*에서 응답하여 값 형식의 각 필드를 [기본값 표](../../language-reference/keywords/default-values-table.md)에 나열된 기본값으로 자동으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-109">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="7c665-110">자세한 내용 및 예제는 [인스턴스 생성자](./instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c665-110">For more information and examples, see [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="7c665-111">생성자 구문</span><span class="sxs-lookup"><span data-stu-id="7c665-111">Constructor syntax</span></span>

<span data-ttu-id="7c665-112">생성자는 이름이 해당 형식의 이름과 동일한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="7c665-113">해당 메서드 시그니처에는 메서드 이름과 매개 변수 목록만 포함되고 반환 형식은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="7c665-114">다음 예제에서는 `Person`이라는 클래스에 대한 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="7c665-115">생성자를 단일 문으로 구현할 수 있는 경우 [식 본문 정의](../statements-expressions-operators/expression-bodied-members.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="7c665-116">다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="7c665-117">식 본문 정의에서 `locationName` 필드에 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="7c665-118">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="7c665-118">Static constructors</span></span>

<span data-ttu-id="7c665-119">앞의 예제에서는 새 개체를 만드는 인스턴스 생성자를 모두 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="7c665-120">클래스 또는 구조체에 형식의 정적 멤버를 초기화하는 정적 생성자도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="7c665-121">정적 생성자에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-121">Static constructors are parameterless.</span></span> <span data-ttu-id="7c665-122">정적 필드를 초기화하는 정적 생성자를 제공하지 않으면 C# 컴파일러는 정적 필드를 [기본값 표](../../language-reference/keywords/default-values-table.md)에 나열된 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-122">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span>

<span data-ttu-id="7c665-123">다음 예제에서는 정적 생성자를 사용하여 정적 필드를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="7c665-124">다음 예제와 같이 식 본문 정의를 사용하여 정적 생성자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c665-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="7c665-125">자세한 내용 및 예제는 [정적 생성자](./static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c665-125">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c665-126">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7c665-126">In This Section</span></span>  
 [<span data-ttu-id="7c665-127">생성자 사용</span><span class="sxs-lookup"><span data-stu-id="7c665-127">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="7c665-128">인스턴스 생성자</span><span class="sxs-lookup"><span data-stu-id="7c665-128">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="7c665-129">전용 생성자</span><span class="sxs-lookup"><span data-stu-id="7c665-129">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="7c665-130">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="7c665-130">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="7c665-131">복사 생성자 작성 방법</span><span class="sxs-lookup"><span data-stu-id="7c665-131">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c665-132">참조</span><span class="sxs-lookup"><span data-stu-id="7c665-132">See also</span></span>

- [<span data-ttu-id="7c665-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7c665-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7c665-134">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="7c665-134">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7c665-135">종료자</span><span class="sxs-lookup"><span data-stu-id="7c665-135">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="7c665-136">static</span><span class="sxs-lookup"><span data-stu-id="7c665-136">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="7c665-137">이니셜라이저가 생성자와 반대 순서로 실행되는 이유는 무엇인가요? 1부</span><span class="sxs-lookup"><span data-stu-id="7c665-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
