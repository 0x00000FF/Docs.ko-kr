---
title: 인덱서 사용(C# 프로그래밍 가이드)
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 0bb7b848f5484b78e8dae0c40320e7945b78eea0
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873461"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="45556-102">인덱서 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="45556-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="45556-103">인덱서는 클라이언트 응용 프로그램이 배열처럼 액세스할 수 있는 [class](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md), [interface](../../../csharp/language-reference/keywords/interface.md)를 만들 수 있게 해주는 편리한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="45556-103">Indexers are a syntactic convenience that enable you to create a [class](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md), or [interface](../../../csharp/language-reference/keywords/interface.md) that client applications can access just as an array.</span></span> <span data-ttu-id="45556-104">인덱서는 내부 컬렉션 또는 배열을 캡슐화하는 데 주로 사용되는 형식에서 자주 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="45556-104">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="45556-105">예를 들어 24시간 동안 10회 기록된 화씨온도를 나타내는 `TempRecord`라는 클래스가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-105">For example, suppose you have a class `TempRecord` that represents the temperature in Farenheit as recorded at 10 different times during a 24 hour period.</span></span> <span data-ttu-id="45556-106">클래스에는 온도 값을 저장할 `float[]` 형식의 배열 `temps`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="45556-106">The class contains an array `temps` of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="45556-107">이 클래스에서 인덱서를 구현하면 클라이언트가 `TempRecord` 인스턴스의 온도에 `float temp = tr.temps[4]` 대신 `float temp = tr[4]`로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-107">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tr[4]` instead of as `float temp = tr.temps[4]`.</span></span> <span data-ttu-id="45556-108">인덱서 표기법은 클라이언트 응용 프로그램에 대한 구문을 간소화할 뿐 아니라 클래스와 해당 용도를 다른 개발자가 이해하기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45556-108">The indexer notation not only simplifies the syntax for client applications; it also makes the class and its purpose more intuitive for other developers to understand.</span></span>  
  
<span data-ttu-id="45556-109">클래스 또는 구조체에서 인덱서를 선언하려면 다음 예제에 표시된 대로 [this](../../../csharp/language-reference/keywords/this.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-109">To declare an indexer on a class or struct, use the [this](../../../csharp/language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a><span data-ttu-id="45556-110">설명</span><span class="sxs-lookup"><span data-stu-id="45556-110">Remarks</span></span>

<span data-ttu-id="45556-111">인덱서의 형식과 해당 매개 변수의 형식은 최소한 인덱서 자체만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-111">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="45556-112">접근성 수준에 대한 자세한 내용은 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45556-112">For more information about accessibility levels, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="45556-113">인터페이스와 함께 인덱서를 사용하는 방법에 대한 자세한 내용은 [인터페이스 인덱서](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45556-113">For more information about how to use indexers with an interface, see [Interface Indexers](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).</span></span>  
  
 <span data-ttu-id="45556-114">인덱서의 시그니처는 정식 매개 변수의 형식 및 개수로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="45556-114">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="45556-115">정식 매개 변수의 이름이나 인덱서 형식은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-115">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="45556-116">동일한 클래스에서 둘 이상의 인덱서를 선언하는 경우 다른 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-116">If you declare more than one indexer in the same class, they must have different signatures.</span></span>  
  
 <span data-ttu-id="45556-117">인덱서 값은 변수로 분류되지 않으므로 인덱서 값을 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-117">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>  
  
 <span data-ttu-id="45556-118">다른 언어에서 사용할 수 있는 이름을 인덱서에 제공하려면 다음 예제에 표시된 대로 <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-118">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

<span data-ttu-id="45556-119">이 인덱서의 이름은 `TheItem`입니다.</span><span class="sxs-lookup"><span data-stu-id="45556-119">This indexer will have the name `TheItem`.</span></span> <span data-ttu-id="45556-120">이름 특성을 제공하지 않을 경우 기본 이름은 `Item`입니다.</span><span class="sxs-lookup"><span data-stu-id="45556-120">Not providing the name attribute would make `Item` the default name.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="45556-121">예제 1</span><span class="sxs-lookup"><span data-stu-id="45556-121">Example 1</span></span>  
  
<span data-ttu-id="45556-122">다음 예제에서는 전용 배열 필드, `temps`, 인덱서를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45556-122">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="45556-123">인덱서를 사용하면 `tempRecord[i]` 인스턴스에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-123">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="45556-124">인덱서를 사용하지 않으려면 배열을 [public](../../../csharp/language-reference/keywords/public.md) 멤버로 선언하고 해당 멤버인 `tempRecord.temps[i]`에 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-124">The alternative to using the indexer is to declare the array as a [public](../../../csharp/language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>  
  
 <span data-ttu-id="45556-125">인덱서의 액세스가 `Console.Write` 문 등에서 평가될 때 [get](../../../csharp/language-reference/keywords/get.md) 접근자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="45556-125">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../../csharp/language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="45556-126">따라서 `get` 접근자가 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-126">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>  
  
[!code-csharp[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## <a name="indexing-using-other-values"></a><span data-ttu-id="45556-127">다른 값을 사용하여 인덱싱</span><span class="sxs-lookup"><span data-stu-id="45556-127">Indexing using other values</span></span>

<span data-ttu-id="45556-128">C#에서는 인덱스 형식이 정수로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-128">C# doesn't limit the index type to integer.</span></span> <span data-ttu-id="45556-129">예를 들어 인덱서와 함께 문자열을 사용하면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-129">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="45556-130">이러한 인덱서는 컬렉션에서 문자열을 검색하고 적절한 값을 반환하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-130">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="45556-131">접근자를 오버로드할 수 있기 때문에 문자열 및 정수 버전이 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-131">As accessors can be overloaded, the string and integer versions can co-exist.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="45556-132">예제 2</span><span class="sxs-lookup"><span data-stu-id="45556-132">Example 2</span></span>  
  
<span data-ttu-id="45556-133">다음 예제에서는 요일을 저장하는 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-133">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="45556-134">`get` 접근자는 문자열인 요일 이름을 사용하고 해당 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-134">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="45556-135">예를 들어 “일요일”이면 0을 반환하고, “월요일”이면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-135">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>  
  
[!code-csharp[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="45556-136">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="45556-136">Robust programming</span></span>

 <span data-ttu-id="45556-137">인덱서의 보안과 안정성을 향상할 수 있는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-137">There are two main ways in which the security and reliability of indexers can be improved:</span></span>  
  
- <span data-ttu-id="45556-138">클라이언트 코드에서 잘못된 인덱스 값을 전달할 가능성을 처리하는 일부 유형의 오류 처리 전략을 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-138">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="45556-139">이 항목의 앞부분에 있는 첫 번째 예제에서 TempRecord 클래스는 클라이언트 코드에서 입력을 인덱서에 전달하기 전에 확인할 수 있게 해주는 Length 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-139">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="45556-140">인덱서 자체 안에 오류 처리 코드를 넣을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45556-140">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="45556-141">사용자를 위해 인덱서 접근자 내에서 throw하는 모든 예외를 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-141">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>  
  
- <span data-ttu-id="45556-142">[get](../../../csharp/language-reference/keywords/get.md) 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자의 접근성을 적절하게 제한적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-142">Set the accessibility of the [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="45556-143">특히 `set` 접근자의 경우 이 작업이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="45556-143">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="45556-144">자세한 내용은 [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45556-144">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45556-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45556-145">See also</span></span>

- [<span data-ttu-id="45556-146">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="45556-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="45556-147">인덱서</span><span class="sxs-lookup"><span data-stu-id="45556-147">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="45556-148">속성</span><span class="sxs-lookup"><span data-stu-id="45556-148">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
