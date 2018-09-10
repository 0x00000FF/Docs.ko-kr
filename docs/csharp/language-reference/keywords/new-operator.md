---
title: new 연산자(C# 참조)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 362217b247bd2ab7a2eec2f86cbaaf1a0652a3ad
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482114"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="fc813-102">new 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fc813-102">new operator (C# Reference)</span></span>

<span data-ttu-id="fc813-103">개체를 만들고 생성자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="fc813-104">예:</span><span class="sxs-lookup"><span data-stu-id="fc813-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="fc813-105">무명 형식의 인스턴스를 만드는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="fc813-106">또한 `new` 연산자는 값 형식에 대한 기본 생성자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="fc813-107">예:</span><span class="sxs-lookup"><span data-stu-id="fc813-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="fc813-108">앞의 문에서 `i`는 `int` 형식의 기본값인 `0`으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="fc813-109">이 문은 다음과 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="fc813-110">기본값의 전체 목록은 [기본값 표](default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc813-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="fc813-111">모든 값 형식에 암시적으로 공용 기본 생성자가 있기 때문에 [struct](struct.md)에 대한 기본 생성자를 선언하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-111">Remember that it is an error to declare a default constructor for a [struct](struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="fc813-112">구조체 형식에서 매개 변수가 있는 생성자를 선언하여 해당 초기 값을 설정할 수 있지만, 이 작업은 기본값이 아닌 값이 필요한 경우에만 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="fc813-113">구조체와 같은 값 유형 객체와 클래스와 같은 참조 유형 객체는 모두 자동으로 삭제되지만, 값 유형 객체는 포함된 컨텍스트가 제거될 때 삭제되는 반면에 참조 유형 객체는 마지막 참조가 삭제된 후 지정되지 않은 시간에 가비지 수집기에 의해 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="fc813-114">파일 핸들이나 네트워크 연결과 같은 리소스를 포함하는 유형의 경우에는 결정적 정리를 사용하여 포함된 리소스가 가능한 빨리 릴리스되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="fc813-115">자세한 내용은 [using 문](using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc813-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="fc813-116">`new` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="fc813-117">`new` 연산자가 메모리 할당에 실패할 경우 <xref:System.OutOfMemoryException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="fc813-118">예</span><span class="sxs-lookup"><span data-stu-id="fc813-118">Example</span></span>

<span data-ttu-id="fc813-119">다음 예제에서는 `new` 연산자를 사용하여 `struct` 개체 및 클래스 개체가 생성 및 초기화된 다음 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="fc813-120">기본값과 할당된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="fc813-121">예제에서는 문자열의 기본값이 `null`이므로</span><span class="sxs-lookup"><span data-stu-id="fc813-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="fc813-122">표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc813-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fc813-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fc813-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fc813-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc813-124">See also</span></span>

- [<span data-ttu-id="fc813-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fc813-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="fc813-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fc813-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fc813-127">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fc813-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fc813-128">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="fc813-128">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="fc813-129">new</span><span class="sxs-lookup"><span data-stu-id="fc813-129">new</span></span>](new.md)
- [<span data-ttu-id="fc813-130">익명 형식</span><span class="sxs-lookup"><span data-stu-id="fc813-130">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)