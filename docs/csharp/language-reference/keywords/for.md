---
title: for(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: 9d7ab9e37be61384c33833381f44257169c81c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="for-c-reference"></a><span data-ttu-id="cdaf4-102">for(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-102">for (C# Reference)</span></span>
<span data-ttu-id="cdaf4-103">`for` 루프를 사용하면 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="cdaf4-104">이러한 종류의 루프는 배열을 반복하는 데 유용하며 루프를 반복할 횟수를 미리 알고 있는 다른 응용 프로그램에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdaf4-105">예</span><span class="sxs-lookup"><span data-stu-id="cdaf4-105">Example</span></span>  
 <span data-ttu-id="cdaf4-106">다음 예제에서 `i` 값은 콘솔에 기록되며 루프를 반복할 때마다 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 <span data-ttu-id="cdaf4-107">이전 예제에서 `for` 문은 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-107">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="cdaf4-108">먼저 `i` 변수의 초기 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="cdaf4-109">이 단계는 루프가 반복되는 횟수에 관계없이 한 번만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="cdaf4-110">이 초기화가 루프 프로세스 외부에서 발생한다고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-110">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="cdaf4-111">조건(`i <= 5`)을 평가하기 위해 `i` 값을 5와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="cdaf4-112">`i`가 5보다 작거나 같으면 조건이 `true`로 평가되고 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="cdaf4-113">루프 본문의 `Console.WriteLine` 문이 `i` 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="cdaf4-114">`i`의 값이 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="cdaf4-115">루프가 2단계의 시작 부분으로 돌아가 조건을 다시 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="cdaf4-116">`i`가 5보다 크면 조건이 `false`로 평가되고 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="cdaf4-117">`i`의 초기 값이 5보다 크면 루프의 본문이 한 번도 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="cdaf4-118">모든 `for` 문은 이니셜라이저, 조건 및 반복기 섹션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-118">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="cdaf4-119">이러한 섹션은 일반적으로 루프가 반복되는 횟수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-119">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="cdaf4-120">섹션은 다음과 같은 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-120">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="cdaf4-121">이니셜라이저 섹션은 초기 조건을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-121">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="cdaf4-122">이 섹션의 문은 루프가 시작되기 전에 한 번만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-122">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="cdaf4-123">섹션에는 다음 두 가지 옵션 중 하나만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-123">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="cdaf4-124">첫 번째 예제와 같이 로컬 루프 변수의 선언 및 초기화(`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="cdaf4-124">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="cdaf4-125">변수는 루프에 로컬이며 루프 외부에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-125">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="cdaf4-126">쉼표로 구분된 다음 목록의 문 식 0개 이상</span><span class="sxs-lookup"><span data-stu-id="cdaf4-126">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="cdaf4-127">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) 문</span><span class="sxs-lookup"><span data-stu-id="cdaf4-127">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="cdaf4-128">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="cdaf4-128">invocation of a method</span></span>  
  
        -   <span data-ttu-id="cdaf4-129">접두사 또는 후위 [increment](../../../csharp/language-reference/operators/increment-operator.md) 식(예: `++i` 또는`i++`)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-129">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="cdaf4-130">접두사 또는 후위 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 식(예: `--i` 또는`i--`)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-130">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="cdaf4-131">[new](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="cdaf4-131">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="cdaf4-132">[await](../../../csharp/language-reference/keywords/await.md) 식</span><span class="sxs-lookup"><span data-stu-id="cdaf4-132">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="cdaf4-133">조건 섹션에는 루프를 종료할지 다시 실행할지를 결정하기 위해 평가되는 부일 식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-133">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="cdaf4-134">반복기 섹션은 루프의 본문을 반복할 때마다 수행되는 업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-134">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="cdaf4-135">반복기 섹션에는 다음과 같은 문 식이 쉼표로 구분되어 0개 이상 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-135">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="cdaf4-136">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) 문</span><span class="sxs-lookup"><span data-stu-id="cdaf4-136">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="cdaf4-137">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="cdaf4-137">invocation of a method</span></span>  
  
    -   <span data-ttu-id="cdaf4-138">접두사 또는 후위 [increment](../../../csharp/language-reference/operators/increment-operator.md) 식(예: `++i` 또는`i++`)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-138">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="cdaf4-139">접두사 또는 후위 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 식(예: `--i` 또는`i--`)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-139">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="cdaf4-140">[new](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="cdaf4-140">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="cdaf4-141">[await](../../../csharp/language-reference/keywords/await.md) 식</span><span class="sxs-lookup"><span data-stu-id="cdaf4-141">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="cdaf4-142">루프의 본문은 문, 빈 문 또는 0개 이상의 문을 중괄호로 묶어 만드는 문 블록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-142">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="cdaf4-143">[break](../../../csharp/language-reference/keywords/break.md) 키워드를 사용하여 `for` 루프를 중단하거나, [continue](../../../csharp/language-reference/keywords/continue.md) 키워드를 사용하여 다음 반복을 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-143">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="cdaf4-144">또한 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 사용하여 루프를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-144">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="cdaf4-145">이 항목의 첫 번째 예제에서는 섹션에 대해 다음 중에서 선택할 수 있는 가장 일반적인 종류의 `for` 루프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-145">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="cdaf4-146">이니셜라이저는 루프의 반복 횟수를 유지 관리하는 로컬 루프 변수 `i`를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-146">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="cdaf4-147">조건은 알려진 최종 값 5에 대해 루프 변수의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-147">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="cdaf4-148">반복기 섹션에서는 후위 increment 문 `i++`를 사용하여 루프의 각 반복을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-148">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="cdaf4-149">다음 예제에서는 이니셜라이저 섹션에서 외부 루프 변수에 값 할당, 이니셜라이저와 반복기 섹션에서 `Console.WriteLine` 메서드 호출, 반복기 섹션에서 두 변수의 값 변경과 같이 여러 가지 덜 일반적인 선택 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-149">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 <span data-ttu-id="cdaf4-150">`for` 문을 정의하는 모든 식은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-150">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="cdaf4-151">예를 들어 다음 문은 무한 루프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cdaf4-151">For example, the following statement creates an infinite loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="cdaf4-152">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="cdaf4-152">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cdaf4-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdaf4-153">See Also</span></span>  
 [<span data-ttu-id="cdaf4-154">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cdaf4-154">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cdaf4-155">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cdaf4-155">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cdaf4-156">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="cdaf4-156">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="cdaf4-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="cdaf4-157">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="cdaf4-158">for 문(C++)</span><span class="sxs-lookup"><span data-stu-id="cdaf4-158">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
 [<span data-ttu-id="cdaf4-159">반복 문</span><span class="sxs-lookup"><span data-stu-id="cdaf4-159">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
