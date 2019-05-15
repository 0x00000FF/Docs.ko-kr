---
title: 익명 함수 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: c949bf5af441728b311391ecb42623951d0145ab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608143"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="8c264-102">익명 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8c264-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="8c264-103">익명 함수는 대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 “인라인” 문 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="8c264-104">이를 사용하여 명명된 대리자를 초기화하거나 명명된 대리자 형식 대신 이를 메서드 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="8c264-105">익명 함수에는 두 가지가 있고 각각 다음 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
- <span data-ttu-id="8c264-106">[람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8c264-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
- [<span data-ttu-id="8c264-107">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="8c264-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="8c264-108">람다 식은 식 트리 및 대리자에 바인딩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="8c264-109">C\#에서 대리자의 발전</span><span class="sxs-lookup"><span data-stu-id="8c264-109">The Evolution of Delegates in C\#</span></span>
 <span data-ttu-id="8c264-110">C# 1.0에서는 코드의 다른 위치에 정의된 메서드를 사용하여 명시적으로 초기화하는 방식으로 대리자의 인스턴스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="8c264-111">C# 2.0에서는 대리자 호출에서 실행될 수 있는 이름 없는 인라인 문 블록을 작성하는 방법으로 무명 메서드의 개념을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="8c264-112">C# 3.0에서는 개념적으로 무명 메서드와 비슷하지만 더 간결하고 표현이 다양한 람다 식을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="8c264-113">이러한 두 기능을 함께 *익명 함수*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="8c264-114">일반적으로 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 버전 3.5 이상을 대상으로 하는 애플리케이션은 람다 식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="8c264-115">다음 예제에서는 C# 1.0에서 C# 3.0까지 대리자 만들기의 발전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c264-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c264-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8c264-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c264-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c264-117">See also</span></span>

- [<span data-ttu-id="8c264-118">문, 식, 연산자</span><span class="sxs-lookup"><span data-stu-id="8c264-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="8c264-119">람다 식</span><span class="sxs-lookup"><span data-stu-id="8c264-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="8c264-120">대리자</span><span class="sxs-lookup"><span data-stu-id="8c264-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="8c264-121">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="8c264-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
