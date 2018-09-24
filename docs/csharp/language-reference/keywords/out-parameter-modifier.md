---
title: out 매개 변수 한정자(C# 참조)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc31ae202ccbfee467dc0f6fa2cf515c751825ed
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696510"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="701cd-102">out 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="701cd-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="701cd-103">`out` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="701cd-104">이러한 방식은 [ref](ref.md) 키워드와 비슷합니다. 단, `ref`의 경우에는 변수를 전달하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="701cd-105">`in`이 호출된 메서드에서 인수 값 수정을 허용하지 않는 것을 제외하고 [in](in-parameter-modifier.md) 키워드와도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="701cd-106">`out` 매개 변수를 사용하려면 메서드 정의와 호출 메서드가 모두 명시적으로 `out` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="701cd-107">예:</span><span class="sxs-lookup"><span data-stu-id="701cd-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="701cd-108">`out` 키워드를 제네릭 형식 매개 변수와 함께 사용하여 형식 매개 변수를 공변(covariant)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="701cd-109">이 컨텍스트에서 `out` 키워드를 사용하는 방법에 대한 자세한 내용은 [out(제네릭 한정자)](out-generic-modifier.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="701cd-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="701cd-110">`out` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화할 필요가 없지만</span><span class="sxs-lookup"><span data-stu-id="701cd-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="701cd-111">호출된 메서드는 메서드가 반환되기 전에 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="701cd-112">`in`, `ref` 및 `out` 키워드는 서로 다른 런타임 동작을 수행하지만 컴파일 시간에 메서드 시그니처의 일부로 간주되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="701cd-113">따라서 메서드 하나는 `ref` 또는 `in` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="701cd-114">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="701cd-115">그러나 다음과 같이 메서드 하나는 `ref`, `in` 또는 `out` 인수를 사용하고 다른 하나는 해당 한정자를 갖지 않는 경우에는 오버로드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="701cd-116">컴파일러는 메서드 호출에 사용되는 매개 변수 한정자에 호출 사이트에서 매개 변수 한정자를 일치하여 적합한 오버로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="701cd-117">속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="701cd-118">다음과 같은 종류의 메서드에는 `in`, `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-118">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="701cd-119">[async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="701cd-119">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="701cd-120">[yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="701cd-120">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="701cd-121">`out` 인수 선언</span><span class="sxs-lookup"><span data-stu-id="701cd-121">Declaring `out` arguments</span></span>   

 <span data-ttu-id="701cd-122">메서드가 여러 값을 반환하도록 하려는 경우 `out` 인수를 사용하여 메서드를 선언하면 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-122">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="701cd-123">다음 예제에서는 `out`을 사용하여 단일 메서드 호출로 3개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-123">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="701cd-124">세 번째 인수는 null에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-124">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="701cd-125">따라서 메서드가 값을 선택적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-125">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="701cd-126">[Try 패턴](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md)은 `bool`을 반환하여 작업의 성공 또는 실패를 나타내고 작업에서 생성된 값을 `out` 인수에 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-126">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded or failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="701cd-127">[DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 메서드와 같은 다양한 구문 분석 메서드에서 이 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-127">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="701cd-128">`out` 인수를 사용하여 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="701cd-128">Calling a method with an `out` argument</span></span>

<span data-ttu-id="701cd-129">C# 6 및 이전 버전에서는 `out` 인수로 전달하기 전에 별도 문에서 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-129">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="701cd-130">다음 예제에서는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드에 전달되기 전에 `number`라는 변수를 선언합니다. 이 메서드는 문자열을 숫자로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-130">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="701cd-131">C# 7.0부터 별도 변수 선언이 아니라 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-131">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="701cd-132">이렇게 하면 보다 간결하고 읽기 쉬운 코드가 생성되며 메서드 호출 전에 실수로 변수에 값이 할당되는 경우를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-132">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="701cd-133">다음 예제는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드 호출에서 `number` 변수를 정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-133">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="701cd-134">앞의 예제에서 `number` 변수는 `int`로 강력하게 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-134">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="701cd-135">다음 예제와 같이 암시적 형식 지역 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701cd-135">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="701cd-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="701cd-136">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="701cd-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="701cd-137">See Also</span></span>

- [<span data-ttu-id="701cd-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="701cd-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="701cd-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="701cd-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="701cd-140">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="701cd-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="701cd-141">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="701cd-141">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
