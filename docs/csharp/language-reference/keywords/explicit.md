---
title: "explicit(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
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
ms.openlocfilehash: f11a930f0be5d504c92271b66009613de5d68579
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-c-reference"></a><span data-ttu-id="1af49-102">explicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1af49-102">explicit (C# Reference)</span></span>
<span data-ttu-id="1af49-103">`explicit` 키워드는 캐스트를 통해 호출해야 하는 사용자 정의 형식 변환 연산자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="1af49-104">예를 들어 이 연산자는 Fahrenheit라는 클래스를 Celsius라는 클래스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 <span data-ttu-id="1af49-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1af49-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span></span>  
  
 <span data-ttu-id="1af49-106">이 변환 연산자는 다음과 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-106">This conversion operator can be invoked like this:</span></span>  
  
 <span data-ttu-id="1af49-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1af49-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span></span>  
  
 <span data-ttu-id="1af49-108">변환 연산자는 소스 형식을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-108">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="1af49-109">소스 형식은 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-109">The source type provides the conversion operator.</span></span> <span data-ttu-id="1af49-110">암시적 변환과 달리 명시적 변환 연산자는 캐스트를 통해 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-110">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="1af49-111">변환 연산으로 인해 예외가 발생하거나 정보가 손실될 경우 `explicit`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-111">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="1af49-112">이렇게 하면 컴파일러가 결과를 예측할 수 없는 변환 연산을 자동으로 호출하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-112">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="1af49-113">캐스트를 생략하면 컴파일 시간 오류 CS0266이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-113">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="1af49-114">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1af49-114">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1af49-115">예제</span><span class="sxs-lookup"><span data-stu-id="1af49-115">Example</span></span>  
 <span data-ttu-id="1af49-116">다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공하며, 각 클래스는 다른 클래스에 명시적 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-116">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 <span data-ttu-id="1af49-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1af49-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1af49-118">예제</span><span class="sxs-lookup"><span data-stu-id="1af49-118">Example</span></span>  
 <span data-ttu-id="1af49-119">다음 예제에서는 한 자리 숫자를 나타내는 `Digit` 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-119">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="1af49-120">`byte`에서 `Digit`로 변환하는 연산자를 정의하지만 일부 바이트는 `Digit`로 변환할 수 없기 때문에 명시적 변환이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af49-120">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 <span data-ttu-id="1af49-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1af49-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1af49-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1af49-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1af49-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1af49-123">See Also</span></span>  
 <span data-ttu-id="1af49-124">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1af49-125">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1af49-126">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1af49-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="1af49-128">[연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-128">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="1af49-129">[방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span><span class="sxs-lookup"><span data-stu-id="1af49-129">[How to: Implement User-Defined Conversions Between Structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span></span>  
 <span data-ttu-id="1af49-130">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)(C#의 연결된 사용자 정의 명시적 변환)</span><span class="sxs-lookup"><span data-stu-id="1af49-130">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>

