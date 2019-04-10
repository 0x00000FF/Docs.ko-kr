---
title: 대리자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: fa69a03d160e7079f532e8e00245a7af3f3a8999
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088745"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="929a0-102">대리자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="929a0-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="929a0-103">[대리자](../../../csharp/language-reference/keywords/delegate.md)는 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="929a0-104">대리자를 인스턴스화하면 모든 메서드가 있는 인스턴스를 호환되는 시그니처 및 반환 형식에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="929a0-105">대리자 인스턴스를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="929a0-106">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="929a0-107">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="929a0-108">사용자 지정 메서드를 만들면 Windows 컨트롤 같은 클래스가 특정 이벤트가 발생했을 때 해당 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="929a0-109">다음 예제에서는 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 <span data-ttu-id="929a0-110">액세스 가능한 클래스 또는 대리자 형식과 일치하는 구조의 모든 메서드는 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="929a0-111">메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="929a0-112">메서드를 대리자에 할당하면 프로그래밍 방식으로 메서드 호출을 변경하고 기존 클래스에 새 코드를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="929a0-113">메서드 오버로드의 컨텍스트에서는 메서드 시그니처에 반환 값이 포함되지 않지만</span><span class="sxs-lookup"><span data-stu-id="929a0-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="929a0-114">대리자 컨텍스트에서는 시그니처에 반환 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="929a0-115">즉 메서드의 반환 형식이 대리자의 반환 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="929a0-116">대리자에서는 이와 같이 메서드를 매개 변수로 취급할 수 있으므로 대리자는 콜백 메서드 정의에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="929a0-117">예를 들어, 두 개체를 비교하는 메서드에 대한 참조를 정렬 알고리즘에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="929a0-118">비교 코드는 별도의 절차이기 때문에 정렬 알고리즘을 보다 일반적인 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="929a0-119">대리자 개요</span><span class="sxs-lookup"><span data-stu-id="929a0-119">Delegates Overview</span></span>  
 <span data-ttu-id="929a0-120">대리자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="929a0-121">대리자는 C++ 함수 포인터와 유사하지만 C++ 함수 포인터와 달리 멤버 함수에 대해 완전히 개체 지향입니다. 대리자는 개체 인스턴스 및 메서드를 모두 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-121">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
  
-   <span data-ttu-id="929a0-122">대리자를 통해 메서드를 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="929a0-123">대리자를 사용하여 콜백 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="929a0-124">여러 대리자를 연결할 수 있습니다. 예를 들어 단일 이벤트에 대해 여러 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="929a0-125">메서드와 대리자 형식이 정확히 일치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="929a0-126">자세한 내용은 [대리자의 가변성 사용](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="929a0-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="929a0-127">C# 버전 2.0에는 별도로 정의된 메서드 대신 코드 블록을 매개 변수로 전달할 수 있도록 하는 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)라는 개념이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="929a0-128">C# 3.0에는 인라인 코드 블록을 더 간단하게 작성할 수 있는 람다 식이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="929a0-129">특정 컨텍스트에서는 무명 메서드와 람다 식 모두 대리자 형식으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="929a0-130">이 두 기능을 익명 함수라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="929a0-131">람다 식에 대한 자세한 내용은 [익명 함수](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="929a0-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="929a0-132">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="929a0-132">In This Section</span></span>  
  
-   [<span data-ttu-id="929a0-133">대리자 사용</span><span class="sxs-lookup"><span data-stu-id="929a0-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="929a0-134">인터페이스(C# 프로그래밍 가이드) 대신 대리자를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="929a0-134">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))  
  
-   [<span data-ttu-id="929a0-135">대리자 비교: 명명된 메서드 및 무명 메서드</span><span class="sxs-lookup"><span data-stu-id="929a0-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="929a0-136">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="929a0-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="929a0-137">대리자에서 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="929a0-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="929a0-138">방법: 대리자 조합(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="929a0-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="929a0-139">방법: 대리자 선언, 인스턴스화 및 사용</span><span class="sxs-lookup"><span data-stu-id="929a0-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  

## <a name="c-language-specification"></a><span data-ttu-id="929a0-140">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="929a0-140">C# Language Specification</span></span>  

<span data-ttu-id="929a0-141">자세한 내용은 [대리자](~/_csharplang/spec/delegates.md) 에 [ C# 언어 사양](../../language-reference/language-specification/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-141">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="929a0-142">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="929a0-142">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="929a0-143">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="929a0-143">Featured Book Chapters</span></span>  
 <span data-ttu-id="929a0-144">[대리자, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) 에 [ C# 3.0 Cookbook, Third Edition: 250 개 이상의 솔루션에 대 한 C# 3.0 프로그래머](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="929a0-144">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="929a0-145">[대리자 및 이벤트](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) 에 [학습 C# 3.0. 기본 사항 마스터 C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="929a0-145">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929a0-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="929a0-146">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="929a0-147">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="929a0-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="929a0-148">이벤트</span><span class="sxs-lookup"><span data-stu-id="929a0-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)
