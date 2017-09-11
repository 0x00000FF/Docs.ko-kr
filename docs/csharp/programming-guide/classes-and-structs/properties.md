---
title: "속성(C# 프로그래밍 가이드)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="67bf3-102">속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="67bf3-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="67bf3-103">속성은 전용 필드의 값을 읽거나 쓰거나 계산하는 유연한 메커니즘을 제공하는 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="67bf3-104">공용 데이터 멤버인 것처럼 속성을 사용할 수 있지만, 실제로 *접근자*라는 특수 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="67bf3-105">이렇게 하면 데이터에 쉽게 액세스할 수 있으며 메서드의 안전성과 유연성 수준을 올리는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="67bf3-106">속성 개요</span><span class="sxs-lookup"><span data-stu-id="67bf3-106">Properties overview</span></span>  
  
- <span data-ttu-id="67bf3-107">속성을 사용하면 클래스가 구현 또는 검증 코드를 숨기는 동시에 값을 가져오고 설정하는 방법을 공개적으로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="67bf3-108">[get](../../../csharp/language-reference/keywords/get.md) 속성 접근자는 속성 값을 반환하는 데 사용되고 [set](../../../csharp/language-reference/keywords/set.md) 속성 접근자는 새 값을 할당하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="67bf3-109">이러한 접근자는 각기 다른 액세스 수준을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-109">These accessors can have different access levels.</span></span> <span data-ttu-id="67bf3-110">자세한 내용은 [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67bf3-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="67bf3-111">[value](../../../csharp/language-reference/keywords/value.md) 키워드는 `set` 접근자가 할당하는 값을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="67bf3-112">속성은 *읽기/쓰기*(`get` 및 `set` 접근자 모두 포함), *읽기 전용*(`get` 접근자는 포함하지만 `set` 접근자는 포함 안 함) 또는 *쓰기 전용*(`set` 접근자는 포함하지만 `get` 접근자는 포함 안 함)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="67bf3-113">쓰기 전용 속성은 거의 없으며 주로 중요한 데이터에 대한 액세스를 제한하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="67bf3-114">사용자 지정 접근자 코드가 필요 없는 단순한 속성은 식 본문 정의나 [자동 구현 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="67bf3-115">지원 필드가 있는 속성</span><span class="sxs-lookup"><span data-stu-id="67bf3-115">Properties with backing fields</span></span>

<span data-ttu-id="67bf3-116">속성을 구현하는 한 가지 기본 패턴에는 private 지원 필드를 사용하여 속성 값을 설정 및 검색하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="67bf3-117">`get` 접근자는 private 필드의 값을 반환하고 `set` 접근자는 private 필드에 값을 할당하기 전에 데이터 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="67bf3-118">또한 두 접근자 모두 데이터를 저장 또는 반환하기 전에 데이터에 대한 변환이나 계산을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="67bf3-119">다음 예제에서 이 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="67bf3-120">이 예제에서 `TimePeriod` 클래스는 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="67bf3-121">내부적으로 이 클래스는 `seconds`라는 private 필드에 시간 간격을 초 단위로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-121">Internally, the class stores the time interval in seconds in a private field named `seconds`.</span></span> <span data-ttu-id="67bf3-122">`Hours`라는 읽기/쓰기 속성을 사용하면 고객이 시간 간격을 시간 단위로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="67bf3-123">`get` 및 `set` 접근자 모두 필요에 따라 시간 및 초 간의 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="67bf3-124">또한 `set` 접근자는 데이터의 유효성을 검사하고 시간(시)이 잘못된 경우 @System.ArgumentOutOfRangeException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-124">In addition, the `set` accessor validates the data and throws an @System.ArgumentOutOfRangeException if the number of hours is invalid.</span></span> 
   
 <span data-ttu-id="67bf3-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="67bf3-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="67bf3-126">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="67bf3-126">Expression body definitions</span></span>  

 <span data-ttu-id="67bf3-127">속성 접근자는 식의 결과를 할당하거나 반환하기만 하는 한 줄로 된 문으로 구성되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-127">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="67bf3-128">이러한 속성은 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-128">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="67bf3-129">식 본문 정의는 `=>` 기호와 속성에 할당하거나 속성에서 검색할 식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-129">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="67bf3-130">C# 6부터 읽기 전용 속성에서 `get` 접근자를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-130">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="67bf3-131">이 경우 `get` 접근자 키워드나 `return` 키워드를 모두 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-131">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="67bf3-132">다음 예제에서는 읽기 전용 `Name` 속성을 식 본문 멤버로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-132">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 <span data-ttu-id="67bf3-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="67bf3-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span></span>  

 <span data-ttu-id="67bf3-134">C# 7부터 `get` 및 `set` 접근자 모두를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-134">Starting with C# 7, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="67bf3-135">이 경우 `get` 및 `set` 키워드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-135">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="67bf3-136">다음 예제에서는 두 접근자에 대해 식 본문 정의를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-136">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="67bf3-137">`return` 키워드는 `get` 접근자와 함께 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-137">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  <span data-ttu-id="67bf3-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="67bf3-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span></span>  

## <a name="auto-implemented-properties"></a><span data-ttu-id="67bf3-139">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="67bf3-139">Auto-implemented properties</span></span>

<span data-ttu-id="67bf3-140">경우에 따라 `get` 속성과 `set` 접근자에서 지원 필드에 값을 할당하거나 지원 필드에서 값을 검색하기만 하고 추가 논리를 포함하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-140">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="67bf3-141">자동 구현 속성을 사용하면 코드를 간소화할 수 있을 뿐 아니라 C# 컴파일러에서 지원 필드를 투명하게 제공하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-141">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="67bf3-142">속성에 `get` 및 `set` 접근자가 모두 포함된 경우 두 접근자를 모두 자동 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-142">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="67bf3-143">구현을 제공하지 않고 `get` 및 `set` 키워드를 사용하여 자동 구현 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-143">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="67bf3-144">다음 예제에서는 `Name` 및 `Price`가 자동 구현 속성인 점만 제외하고 이전 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-144">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="67bf3-145">이 예제에서는 매개 변수화된 생성자도 제거하므로 `SaleItem` 개체가 [개체 이니셜라이저](object-and-collection-initializers.md) 및 기본 생성자에 대한 호출로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf3-145">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the default constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  <span data-ttu-id="67bf3-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="67bf3-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span></span>  

## <a name="related-sections"></a><span data-ttu-id="67bf3-147">관련 단원</span><span class="sxs-lookup"><span data-stu-id="67bf3-147">Related sections</span></span>  
  
-   [<span data-ttu-id="67bf3-148">속성 사용</span><span class="sxs-lookup"><span data-stu-id="67bf3-148">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="67bf3-149">인터페이스 속성</span><span class="sxs-lookup"><span data-stu-id="67bf3-149">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="67bf3-150">속성 및 인덱서 비교</span><span class="sxs-lookup"><span data-stu-id="67bf3-150">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="67bf3-151">접근자 접근성 제한</span><span class="sxs-lookup"><span data-stu-id="67bf3-151">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [<span data-ttu-id="67bf3-152">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="67bf3-152">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="67bf3-153">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="67bf3-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67bf3-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67bf3-154">See also</span></span>
 <span data-ttu-id="67bf3-155">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="67bf3-155">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="67bf3-156">[속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="67bf3-156">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="67bf3-157">[인덱서](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="67bf3-157">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="67bf3-158">[get 키워드](../../../csharp/language-reference/keywords/get.md)  </span><span class="sxs-lookup"><span data-stu-id="67bf3-158">[get keyword](../../../csharp/language-reference/keywords/get.md)  </span></span>  
 [<span data-ttu-id="67bf3-159">set 키워드</span><span class="sxs-lookup"><span data-stu-id="67bf3-159">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)    

