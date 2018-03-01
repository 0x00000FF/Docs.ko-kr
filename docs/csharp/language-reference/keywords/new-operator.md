---
title: "new 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="25406-102">new 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="25406-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="25406-103">개체를 만들고 생성자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="25406-104">예:</span><span class="sxs-lookup"><span data-stu-id="25406-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="25406-105">무명 형식의 인스턴스를 만드는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="25406-106">또한 `new` 연산자는 값 형식에 대한 기본 생성자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="25406-107">예:</span><span class="sxs-lookup"><span data-stu-id="25406-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="25406-108">앞의 문에서 `i`는 `int` 형식의 기본값인 `0`으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="25406-109">이 문은 다음과 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25406-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="25406-110">기본값의 전체 목록은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25406-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="25406-111">모든 값 형식에 암시적으로 공용 기본 생성자가 있기 때문에 [struct](../../../csharp/language-reference/keywords/struct.md)에 대한 기본 생성자를 선언하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="25406-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="25406-112">구조체 형식에서 매개 변수가 있는 생성자를 선언하여 해당 초기 값을 설정할 수 있지만, 이 작업은 기본값이 아닌 값이 필요한 경우에만 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="25406-113">구조체와 같은 값 형식 개체는 스택에 생성되는 반면, 클래스와 같은 참조 형식 개체는 힙에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="25406-114">두 개체 형식 모두 자동으로 제거되지만 값 형식을 기반으로 하는 개체는 범위를 벗어날 때 제거되는 반면, 참조 형식을 기반으로 하는 개체는 마지막 참조가 제거된 후 지정되지 않은 시간에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="25406-115">많은 양의 메모리, 파일 핸들, 네트워크 연결 등의 고정된 리소스를 사용하는 참조 형식의 경우 때로는 명확한 종료를 사용하여 개체가 최대한 빨리 제거되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25406-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="25406-116">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25406-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="25406-117">`new` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25406-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="25406-118">`new` 연산자가 메모리 할당에 실패할 경우 <xref:System.OutOfMemoryException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="25406-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25406-119">예제</span><span class="sxs-lookup"><span data-stu-id="25406-119">Example</span></span>  
 <span data-ttu-id="25406-120">다음 예제에서는 `new` 연산자를 사용하여 `struct` 개체 및 클래스 개체가 생성 및 초기화된 다음 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="25406-121">기본값과 할당된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25406-121">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="25406-122">예제에서는 문자열의 기본값이 `null`이므로</span><span class="sxs-lookup"><span data-stu-id="25406-122">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="25406-123">표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25406-123">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="25406-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="25406-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25406-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25406-125">See Also</span></span>  
 [<span data-ttu-id="25406-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="25406-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="25406-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="25406-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="25406-128">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="25406-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="25406-129">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="25406-129">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="25406-130">new</span><span class="sxs-lookup"><span data-stu-id="25406-130">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="25406-131">익명 형식</span><span class="sxs-lookup"><span data-stu-id="25406-131">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
