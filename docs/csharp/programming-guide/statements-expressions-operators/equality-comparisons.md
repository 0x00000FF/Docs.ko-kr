---
title: 같음 비교 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
ms.openlocfilehash: 7cbd1a2c1a9968ae8ed4f96d503d472bbe9b32c4
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545457"
---
# <a name="equality-comparisons-c-programming-guide"></a><span data-ttu-id="b048a-102">같음 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b048a-102">Equality comparisons (C# Programming Guide)</span></span>

<span data-ttu-id="b048a-103">두 값이 같은지를 비교해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-103">It is sometimes necessary to compare two values for equality.</span></span> <span data-ttu-id="b048a-104">때로는 두 변수에 포함된 값이 같음을 의미하는 *값 같음*(*동등*이라고도 함)을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-104">In some cases, you are testing for *value equality*, also known as *equivalence*, which means that the values that are contained by the two variables are equal.</span></span> <span data-ttu-id="b048a-105">다른 경우에는 두 변수가 메모리에서 동일한 기본 개체를 참조하는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-105">In other cases, you have to determine whether two variables refer to the same underlying object in memory.</span></span> <span data-ttu-id="b048a-106">이 유형의 같음을 *참조 같음* 또는 *ID*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-106">This type of equality is called *reference equality*, or *identity*.</span></span> <span data-ttu-id="b048a-107">이 항목에서는 이러한 두 종류의 같음을 설명하고 자세한 정보가 있는 다른 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-107">This topic describes these two kinds of equality and provides links to other topics for more information.</span></span>  
  
## <a name="reference-equality"></a><span data-ttu-id="b048a-108">참조 같음</span><span class="sxs-lookup"><span data-stu-id="b048a-108">Reference equality</span></span>

 <span data-ttu-id="b048a-109">참조 같음은 두 개체 참조가 동일한 기본 개체를 참조함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-109">Reference equality means that two object references refer to the same underlying object.</span></span> <span data-ttu-id="b048a-110">이러한 상황은 다음 예제와 같이 단순 할당을 통해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-110">This can occur through simple assignment, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideStatements#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#18)]  
  
 <span data-ttu-id="b048a-111">이 코드에서는 두 개체가 생성되지만 대입문 이후 두 참조가 동일한 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-111">In this code, two objects are created, but after the assignment statement, both references refer to the same object.</span></span> <span data-ttu-id="b048a-112">따라서 참조 같음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-112">Therefore they have reference equality.</span></span> <span data-ttu-id="b048a-113">두 참조가 동일한 개체를 참조하는지 확인하려면 <xref:System.Object.ReferenceEquals%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-113">Use the <xref:System.Object.ReferenceEquals%2A> method to determine whether two references refer to the same object.</span></span>  
  
 <span data-ttu-id="b048a-114">참조 같음의 개념은 참조 형식에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-114">The concept of reference equality applies only to reference types.</span></span> <span data-ttu-id="b048a-115">값 형식의 인스턴스가 변수에 할당될 때 값의 복사본이 생성되기 때문에 값 형식 개체에는 참조 같음이 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-115">Value type objects cannot have reference equality because when an instance of a value type is assigned to a variable, a copy of the value is made.</span></span> <span data-ttu-id="b048a-116">따라서 메모리의 동일한 위치를 참조하는 두 개의 unboxed 구조체가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-116">Therefore you can never have two unboxed structs that refer to the same location in memory.</span></span> <span data-ttu-id="b048a-117">또한 <xref:System.Object.ReferenceEquals%2A>를 사용하여 두 개의 값 형식을 비교하는 경우 개체에 포함된 값이 모두 동일한 경우에도 결과는 항상 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-117">Furthermore, if you use <xref:System.Object.ReferenceEquals%2A> to compare two value types, the result will always be `false`, even if the values that are contained in the objects are all identical.</span></span> <span data-ttu-id="b048a-118">각 변수가 별도의 개체 인스턴스에 boxed되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-118">This is because each variable is boxed into a separate object instance.</span></span> <span data-ttu-id="b048a-119">자세한 내용은 [방법: 참조 같음(ID) 테스트](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b048a-119">For more information, see [How to: Test for Reference Equality (Identity)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>  

## <a name="value-equality"></a><span data-ttu-id="b048a-120">값 같음</span><span class="sxs-lookup"><span data-stu-id="b048a-120">Value equality</span></span>

 <span data-ttu-id="b048a-121">값 같음은 두 개체에 동일한 값이 포함되어 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-121">Value equality means that two objects contain the same value or values.</span></span> <span data-ttu-id="b048a-122">[int](../../../csharp/language-reference/keywords/int.md) 또는 [bool](../../../csharp/language-reference/keywords/bool.md)과 같은 기본 값 형식의 경우 값 같음 테스트가 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-122">For primitive value types such as [int](../../../csharp/language-reference/keywords/int.md) or [bool](../../../csharp/language-reference/keywords/bool.md), tests for value equality are straightforward.</span></span> <span data-ttu-id="b048a-123">다음 예제와 같이 [==](../../../csharp/language-reference/operators/equality-operators.md#equality-operator-) 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-123">You can use the [==](../../../csharp/language-reference/operators/equality-operators.md#equality-operator-) operator, as shown in the following example.</span></span>  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 <span data-ttu-id="b048a-124">대부분의 다른 형식에서는 값 같음 테스트가 더 복잡한데, 형식에서 정의된 방식을 알아야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-124">For most other types, testing for value equality is more complex because it requires that you understand how the type defines it.</span></span> <span data-ttu-id="b048a-125">여러 필드나 속성이 있는 클래스 및 구조체의 경우 값 같음은 대체로 모든 필드 또는 속성에 동일한 값이 있다는 의미로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-125">For classes and structs that have multiple fields or properties, value equality is often defined to mean that all fields or properties have the same value.</span></span> <span data-ttu-id="b048a-126">예를 들어 pointA.X가 pointB.X와 같고 pointA.Y가 pointB.Y와 같으면 두 `Point` 개체가 동일한 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-126">For example, two `Point` objects might be defined to be equivalent if pointA.X is equal to pointB.X and pointA.Y is equal to pointB.Y.</span></span>  
  
 <span data-ttu-id="b048a-127">그러나 동등이 형식의 모든 필드를 기반으로 해야 한다는 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-127">However, there is no requirement that equivalence be based on all the fields in a type.</span></span> <span data-ttu-id="b048a-128">하위 집합을 기반으로 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-128">It can be based on a subset.</span></span> <span data-ttu-id="b048a-129">소유하지 않은 형식을 비교하는 경우 해당 형식에 대해 동등이 정의된 방식을 구체적으로 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-129">When you compare types that you do not own, you should make sure to understand specifically how equivalence is defined for that type.</span></span> <span data-ttu-id="b048a-130">사용자 고유의 클래스 및 구조체에서 값 같음을 정의하는 방법에 대한 자세한 내용은 [방법: 형식의 값 일치 정의](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b048a-130">For more information about how to define value equality in your own classes and structs, see [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>  
  
### <a name="value-equality-for-floating-point-values"></a><span data-ttu-id="b048a-131">부동 소수점 값에 대한 값 같음</span><span class="sxs-lookup"><span data-stu-id="b048a-131">Value equality for floating-point values</span></span>

 <span data-ttu-id="b048a-132">이진 컴퓨터의 부정확한 부동 소수점 연산 때문에 부동 소수점 값([double](../../../csharp/language-reference/keywords/double.md) 및 [float](../../../csharp/language-reference/keywords/float.md))의 같음 비교에서 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-132">Equality comparisons of floating-point values ([double](../../../csharp/language-reference/keywords/double.md) and [float](../../../csharp/language-reference/keywords/float.md)) are problematic because of the imprecision of floating-point arithmetic on binary computers.</span></span> <span data-ttu-id="b048a-133">자세한 내용은 <xref:System.Double?displayProperty=nameWithType> 항목의 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b048a-133">For more information, see the remarks in the topic <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="b048a-134">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b048a-134">Related topics</span></span>  
  
|<span data-ttu-id="b048a-135">제목</span><span class="sxs-lookup"><span data-stu-id="b048a-135">Title</span></span>|<span data-ttu-id="b048a-136">설명</span><span class="sxs-lookup"><span data-stu-id="b048a-136">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b048a-137">방법: 참조 같음(ID) 테스트</span><span class="sxs-lookup"><span data-stu-id="b048a-137">How to: Test for Reference Equality (Identity)</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|<span data-ttu-id="b048a-138">두 변수에 참조 같음이 있는지를 확인하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-138">Describes how to determine whether two variables have reference equality.</span></span>|  
|[<span data-ttu-id="b048a-139">방법: 형식의 값 일치 정의</span><span class="sxs-lookup"><span data-stu-id="b048a-139">How to: Define Value Equality for a Type</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|<span data-ttu-id="b048a-140">형식에 대한 값 같음의 사용자 지정 정의를 제공하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-140">Describes how to provide a custom definition of value equality for a type.</span></span>|  
|[<span data-ttu-id="b048a-141">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b048a-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)|<span data-ttu-id="b048a-142">.NET Framework를 통해 C#에 제공되는 기능 및 중요한 C# 언어 기능에 대한 자세한 정보 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-142">Provides links to detailed information about important C# language features and features that are available to C# through the .NET Framework.</span></span>|  
|[<span data-ttu-id="b048a-143">유형</span><span class="sxs-lookup"><span data-stu-id="b048a-143">Types</span></span>](../../../csharp/programming-guide/types/index.md)|<span data-ttu-id="b048a-144">C# 형식 시스템에 대한 정보 및 추가 정보 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b048a-144">Provides information about the C# type system and links to additional information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b048a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b048a-145">See also</span></span>

- [<span data-ttu-id="b048a-146">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b048a-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
