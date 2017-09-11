---
title: "개념 및 용어 (함수 변환) (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b07bfffbb4f5c9d833f821c9c548892aab0e606
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a><span data-ttu-id="8946e-102">개념 및 용어 (함수 변환) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8946e-102">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>
<span data-ttu-id="8946e-103">이 항목에서는 순수 함수 변형의 개념과 용어에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-103">This topic introduces the concepts and terminology of pure functional transformations.</span></span> <span data-ttu-id="8946e-104">데이터 변환에 대한 함수 변환 방법은 전통적인 명령형 프로그래밍보다 신속하게 프로그래밍할 수 있고 표현이 다양하며 디버깅과 유지 관리가 쉬운 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-104">The functional transformation approach to transforming data yields code that is often quicker to program, more expressive, and easier to debug and maintain than more traditional, imperative programming.</span></span>  
  
 <span data-ttu-id="8946e-105">이 단원의 항목에서는 함수형 프로그래밍에 대해 전체적으로 설명하지 않고</span><span class="sxs-lookup"><span data-stu-id="8946e-105">Note that the topics in this section are not intended to fully explain functional programming.</span></span> <span data-ttu-id="8946e-106">XML의 모양을 쉽게 변환하는 데 사용할 수 있는 몇 가지 함수형 프로그래밍 기능만 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-106">Instead, these topics identify some of the functional programming capabilities that make it easier to transform XML from one shape to another.</span></span>  
  
## <a name="what-is-pure-functional-transformation"></a><span data-ttu-id="8946e-107">순수 함수 변형이란?</span><span class="sxs-lookup"><span data-stu-id="8946e-107">What Is Pure Functional Transformation?</span></span>  
 <span data-ttu-id="8946e-108">*순수 함수 변환*, 호출 된 함수 집합 *순수 함수*을 원래 형태에서 구조화 된 데이터 집합을 다른 형식으로 변환 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-108">In *pure functional transformation*, a set of functions, called *pure functions*, define how to transform a set of structured data from its original form into another form.</span></span> <span data-ttu-id="8946e-109">"순수" 라는 단어는 함수는 나타냅니다 *구성 가능한*, 이들이 필요:</span><span class="sxs-lookup"><span data-stu-id="8946e-109">The word "pure" indicates that the functions are *composable*, which requires that they are:</span></span>  
  
-   <span data-ttu-id="8946e-110">*자체 포함 된*는 자유롭게 정렬 하 고 프로그램의 나머지 부분과 상호 종속 되거나 얽 없이 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-110">*Self-contained*, so that they can be freely ordered and rearranged without entanglement or interdependencies with the rest of the program.</span></span> <span data-ttu-id="8946e-111">순수 변형은 환경에 대한 지식이 없고 환경에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-111">Pure transformations have no knowledge of or effect upon their environment.</span></span> <span data-ttu-id="8946e-112">즉, 변환에 사용 되는 함수가 없는 *부작용*합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-112">That is, the functions used in the transformation have no *side effects*.</span></span>  
  
-   <span data-ttu-id="8946e-113">*상태 비저장*항상 같은 결과가 발생 합니다 동일한 입력에 대해 동일한 함수나 특정 함수 집합을 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-113">*Stateless*, so that executing the same function or specific set of functions on the same input will always result in the same output.</span></span> <span data-ttu-id="8946e-114">순수 변형은 이전 사용에 대한 기록을 갖고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-114">Pure transformations have no memory of their prior use.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8946e-115">이 자습서의 나머지 부분에서 "순수 함수"라는 용어는 특정 언어 기능이 아니라 프로그래밍 방법을 나타내기 위해 일반적인 의미에서 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-115">In the rest of this tutorial, the term "pure function" is used in a general sense to indicate a programming approach, and not a specific language feature.</span></span>  
>   
>  <span data-ttu-id="8946e-116">참고 Visual Basic에서는 함수로로 순수 함수를 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-116">Note that pure functions must be implemented as functions in Visual Basic.</span></span>  
>   
>  <span data-ttu-id="8946e-117">또한 순수 함수와 C++의 순수 가상 메서드를 혼동하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-117">Also, you should not confuse pure functions with pure virtual methods in C++.</span></span> <span data-ttu-id="8946e-118">순수 가상 메서드의 경우 포함하는 클래스가 추상 클래스이고 메서드 본문이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-118">The latter indicates that the containing class is abstract and that no method body is supplied.</span></span>  
  
### <a name="functional-programming"></a><span data-ttu-id="8946e-119">함수형 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8946e-119">Functional Programming</span></span>  
 <span data-ttu-id="8946e-120">*함수형 프로그래밍* 은 순수 함수 변환을 직접 지 원하는 프로그래밍 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-120">*Functional programming* is a programming approach that directly supports pure functional transformation.</span></span>  
  
 <span data-ttu-id="8946e-121">지금까지 기계 학습, Scheme, Haskell 및 F #와 같은 범용 함수형 프로그래밍 언어는 주로 학계 관심의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-121">Historically, general-purpose functional programming languages, such as ML, Scheme, Haskell, and F#, have been primarily of interest to the academic community.</span></span> <span data-ttu-id="8946e-122">항상 Visual Basic의 순수 함수 변환을 작성할 수 있었지만의 어려움 때문 하므로 없는 것에 대부분의 프로그래머가 쉽게 선택할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-122">Although it has always been possible to write pure functional transformations in Visual Basic, the difficulty of doing so has not made it an attractive option to most programmers.</span></span> <span data-ttu-id="8946e-123">그러나 이후 버전의 Visual Basic, 새로운 언어와 같은 구문이 람다 식 및 형식 유추를 사용 하면 함수형 프로그래밍 훨씬 쉽고 생산적입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-123">With later versions of Visual Basic, however, new language constructs such as lambda expressions and type inference make it functional programming much easier and more productive.</span></span>  
  
 <span data-ttu-id="8946e-124">함수형 프로그래밍에 대 한 자세한 내용은 참조 [vs 함수형 프로그래밍 합니다. 명령형 프로그래밍 비교 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-124">For more information about functional programming, see [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).</span></span>  
  
#### <a name="domain-specific-fp-languages"></a><span data-ttu-id="8946e-125">영역별 FP 언어</span><span class="sxs-lookup"><span data-stu-id="8946e-125">Domain-Specific FP Languages</span></span>  
 <span data-ttu-id="8946e-126">범용 프로그래밍 언어가 널리 채택되지는 않았지만 특정 영역별 함수형 프로그래밍 언어는 보다 성공적이었습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-126">Although general functional programming languages have not been widely adopted, specific domain-specific functional programming languages have had better success.</span></span> <span data-ttu-id="8946e-127">예를 들어, CSS 스타일시트는 많은 웹 페이지의 모양과 느낌을 결정하는 데 사용되고 XSLT(Extensible Stylesheet Language Transformation) 스타일시트는 XML 데이터 조작에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-127">For example, Cascading Style Sheets (CSS) are used to determine the look and feel of many Web pages, and Extensible Stylesheet Language Transformations (XSLT) style sheets are used extensively in XML data manipulation.</span></span> <span data-ttu-id="8946e-128">XSLT에 대 한 자세한 내용은 참조 [XSLT 변환을](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-128">For more information about XSLT, see [XSLT Transformations](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03).</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="8946e-129">용어</span><span class="sxs-lookup"><span data-stu-id="8946e-129">Terminology</span></span>  
 <span data-ttu-id="8946e-130">다음 표에는 함수 변환과 관련된 몇 가지 용어가 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-130">The following table defines some terms related to functional transformations.</span></span>  
  
 <span data-ttu-id="8946e-131">고차(1급) 함수</span><span class="sxs-lookup"><span data-stu-id="8946e-131">higher-order (first-class) function</span></span>  
 <span data-ttu-id="8946e-132">프로그램 개체로 취급할 수 있는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-132">A function that can be treated as a programmatic object.</span></span> <span data-ttu-id="8946e-133">예를 들어, 고차 함수는 다른 함수로 전달되거나 다른 함수에서 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-133">For example, a higher-order function can be passed to or returned from other functions.</span></span> <span data-ttu-id="8946e-134">Visual Basic의 경우 대리자와 람다 식은 지 더 높은 순서 기능을 지 원하는 언어 기능.</span><span class="sxs-lookup"><span data-stu-id="8946e-134">In Visual Basic, delegates and lambda expressions are language features that support higher-order functions.</span></span> <span data-ttu-id="8946e-135">고차 함수를 작성하려면 하나 이상의 인수를 선언하여 대리자를 사용하며, 고차 함수를 호출할 때는 흔히 람다 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-135">To write a higher-order function, you declare one or more arguments to take delegates, and you often use lambda expressions when calling it.</span></span> <span data-ttu-id="8946e-136">대부분의 표준 쿼리 연산자가 고차 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-136">Many of the standard query operators are higher-order functions.</span></span>  
  
 <span data-ttu-id="8946e-137">자세한 내용은 참조 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-137">For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="8946e-138">람다 식</span><span class="sxs-lookup"><span data-stu-id="8946e-138">lambda expression</span></span>  
 <span data-ttu-id="8946e-139">대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 인라인 익명 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-139">Essentially, an inline anonymous function that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="8946e-140">이는 람다 식에 대한 간략한 정의이지만 이 자습서의 목적에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-140">This is a simplified definition of lambda expressions, but it is adequate for the purposes of this tutorial.</span></span>  
  
 <span data-ttu-id="8946e-141">에 대 한 자세한 내용은 참조 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-141">For more information about, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="8946e-142">컬렉션</span><span class="sxs-lookup"><span data-stu-id="8946e-142">collection</span></span>  
 <span data-ttu-id="8946e-143">대개 동일한 형식을 갖고 있는 구조화된 데이터 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-143">A structured set of data, usually of a uniform type.</span></span> <span data-ttu-id="8946e-144">LINQ와 호환 되도록 컬렉션을 구현 해야는 <xref:System.Collections.IEnumerable>인터페이스 또는 <xref:System.Linq.IQueryable>인터페이스 (또는 해당 제네릭 요소 중 하나 <xref:System.Collections.Generic.IEnumerator%601>또는 <xref:System.Linq.IQueryable%601>).</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerator%601> </xref:System.Linq.IQueryable> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="8946e-144">To be compatible with LINQ, a collection must implement the <xref:System.Collections.IEnumerable> interface or the <xref:System.Linq.IQueryable> interface (or one of their generic counterparts, <xref:System.Collections.Generic.IEnumerator%601> or <xref:System.Linq.IQueryable%601>).</span></span>  
  
 <span data-ttu-id="8946e-145">튜플(익명 형식)</span><span class="sxs-lookup"><span data-stu-id="8946e-145">tuple (anonymous types)</span></span>  
 <span data-ttu-id="8946e-146">수학적 개념인 튜플은 각각 특정한 형식을 가진 개체의 유한 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-146">A mathematical concept, a tuple is a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="8946e-147">튜플을 정렬된 목록이라고 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-147">A tuple is also known as an ordered list.</span></span> <span data-ttu-id="8946e-148">익명 형식은 이 개념을 언어에 구현한 것입니다. 익명 형식을 사용하여 명명되지 않은 클래스 형식을 선언하고 해당 형식의 개체를 동시에 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-148">Anonymous types are a language implementation of this concept, which enable an unnamed class type to be declared and an object of that type to be instantiated at the same time.</span></span>  
  
 <span data-ttu-id="8946e-149">자세한 내용은 참조 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-149">For more information, see  [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="8946e-150">형식 유추(암시적 형식 지정)</span><span class="sxs-lookup"><span data-stu-id="8946e-150">type inference (implicit typing)</span></span>  
 <span data-ttu-id="8946e-151">명시적 형식 선언이 없는 경우 컴파일러에서 변수의 형식을 결정하도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-151">The ability of a compiler to determine the type of a variable in the absence of an explicit type declaration.</span></span>  
  
 <span data-ttu-id="8946e-152">자세한 내용은 참조 [로컬 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-152">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="8946e-153">지연된 실행 및 지연 계산</span><span class="sxs-lookup"><span data-stu-id="8946e-153">deferred execution and lazy evaluation</span></span>  
 <span data-ttu-id="8946e-154">확인된 값이 실제로 필요할 때까지 식의 계산을 지연하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-154">The delaying of evaluation of an expression until its resolved value is actually required.</span></span> <span data-ttu-id="8946e-155">지연된 실행은 컬렉션에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-155">Deferred execution is supported in collections.</span></span>  
  
 <span data-ttu-id="8946e-156">자세한 내용은 참조 [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) 및 [지연 된 실행과 지연 계산은 LINQ to XML (Visual Basic)에서](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-156">For more information, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) and [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="8946e-157">이러한 언어 기능은 이 단원 전반의 코드 샘플에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8946e-157">These language features will be used in code samples throughout this section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8946e-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8946e-158">See Also</span></span>  
 <span data-ttu-id="8946e-159">[순수 함수 변환 (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="8946e-159">[Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
<span data-ttu-id="8946e-160"> [함수형 프로그래밍과 명령형 프로그래밍 비교 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)</span><span class="sxs-lookup"><span data-stu-id="8946e-160"> [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)</span></span>
