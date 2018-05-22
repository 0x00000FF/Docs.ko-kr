---
title: 변환 연산자(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 97e93230658b5d1da676b029169b63bc9006ddb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="eda32-102">변환 연산자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="eda32-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="eda32-103">C#을 사용하면 프로그래머가 클래스 또는 구조체를 다른 클래스 또는 구조체나 기본 형식으로/에서 변환할 수 있도록 클래스 또는 구조체에서 변환을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="eda32-104">변환은 연산자처럼 정의되며 변환 결과의 형식에 따라 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="eda32-105">변환할 인수의 형식이나 변환 결과의 형식 중 하나만 포함 형식이어야 하며 둘 다 포함 형식이면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="eda32-106">변환 연산자 개요</span><span class="sxs-lookup"><span data-stu-id="eda32-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="eda32-107">변환 연산자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="eda32-108">`implicit`로 선언된 변환은 필요한 경우 자동으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="eda32-109">`explicit`로 선언된 변환은 캐스트를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="eda32-110">모든 변환은 `static`으로 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eda32-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eda32-111">관련 단원</span><span class="sxs-lookup"><span data-stu-id="eda32-111">Related Sections</span></span>  
 <span data-ttu-id="eda32-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="eda32-112">For more information:</span></span>  
  
-   [<span data-ttu-id="eda32-113">변환 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="eda32-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="eda32-114">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="eda32-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="eda32-115">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="eda32-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="eda32-116">explicit</span><span class="sxs-lookup"><span data-stu-id="eda32-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="eda32-117">implicit</span><span class="sxs-lookup"><span data-stu-id="eda32-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="eda32-118">static</span><span class="sxs-lookup"><span data-stu-id="eda32-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="eda32-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eda32-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="eda32-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eda32-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="eda32-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)(C#의 연결된 사용자 정의 명시적 변환)</span><span class="sxs-lookup"><span data-stu-id="eda32-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
