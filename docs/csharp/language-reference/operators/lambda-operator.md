---
title: =&gt; 연산자 - C# 참조
ms.custom: seodec18
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: c193a91eaffe2e56a5df2afa8d66989981123a48
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238795"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="a0443-102">=&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a0443-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="a0443-103">`=>` 연산자는 C#에서 두 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="a0443-104">[람다 식](../../lambda-expressions.md)에서 [람다 연산자](#lamba-operator)로, 람다 본문에서 입력 변수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="a0443-105">[식 본문 정의](#expression-body-definition)에서는 멤버 구현에서 멤버 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="a0443-106">람다 연산자</span><span class="sxs-lookup"><span data-stu-id="a0443-106">Lambda operator</span></span>

<span data-ttu-id="a0443-107">`=>` 토큰을 람다 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="a0443-108">이 연산자는 *람다 식*에서 왼쪽의 입력 변수를 오른쪽의 람다 본문과 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="a0443-109">람다 식은 무명 메서드와 유사한 인라인 식이지만 보다 유연하며, 메서드 구문으로 표현되는 LINQ 쿼리에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="a0443-110">자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0443-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="a0443-111">다음 예제에서는 문자열 배열에서 가장 짧은 문자열 길이를 찾아 표시하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="a0443-112">예제의 첫 번째 부분에서는 람다 식(`w => w.Length`)을 `words` 배열의 각 요소에 적용한 다음 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 가장 짧은 길이를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="a0443-113">비교를 위해 예제의 두 번째 부분에서는 쿼리 구문을 사용하여 동일한 작업을 수행하는 더 긴 솔루션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a><span data-ttu-id="a0443-114">설명</span><span class="sxs-lookup"><span data-stu-id="a0443-114">Remarks</span></span>  
 <span data-ttu-id="a0443-115">`=>` 연산자는 할당 연산자(`=`)와 우선 순위가 같으며 오른쪽 결합성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="a0443-116">입력 변수의 형식을 명시적으로 지정하거나 컴파일러에서 유추하도록 할 수 있습니다. 두 경우 모두 변수는 컴파일 시간에 강력한 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="a0443-117">다음 예제와 같이 형식을 지정할 때 형식 이름과 변수 이름을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="a0443-118">예</span><span class="sxs-lookup"><span data-stu-id="a0443-118">Example</span></span>  
 <span data-ttu-id="a0443-119">다음 예제에서는 두 개의 인수를 사용하는 표준 쿼리 연산자 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>의 오버로드에 대한 람다 식을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="a0443-120">람다 식에는 둘 이상의 매개 변수가 사용되므로 매개 변수를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="a0443-121">두 번째 매개 변수 `index`는 컬렉션에서 현재 요소의 인덱스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="a0443-122">`Where` 식은 길이가 배열의 해당 인덱스 위치보다 작은 모든 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
## <a name="expression-body-definition"></a><span data-ttu-id="a0443-123">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="a0443-123">Expression body definition</span></span>

<span data-ttu-id="a0443-124">식 본문 정의는 간결하고 읽을 수 있는 형식으로 멤버 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="a0443-125">다음과 같은 일반적인 구문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="a0443-126">여기서 *expression*은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="a0443-127">*식*은 멤버의 반환 형식이 `void`이거나 멤버가 생성자 또는 종료자인 경우에만 *statement 식*일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="a0443-128">메서드 및 속성 가져오기 문에 대한 식 본문 정의는 C# 6부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="a0443-129">생성자, 종료자, 속성 설정 문 및 인덱서에 대한 식 본문 정의는 C# 7부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="a0443-130">`Person.ToString` 메서드에 대한 식 본문 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="a0443-131">다음과 같은 메서드 정의의 약식 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a0443-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="a0443-132">식 본문 정의에 대한 자세한 내용은 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0443-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0443-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0443-133">See Also</span></span>

- [<span data-ttu-id="a0443-134">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a0443-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)   
- [<span data-ttu-id="a0443-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a0443-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)   
- [<span data-ttu-id="a0443-136">람다 식</span><span class="sxs-lookup"><span data-stu-id="a0443-136">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
- <span data-ttu-id="a0443-137">[식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)</span><span class="sxs-lookup"><span data-stu-id="a0443-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>