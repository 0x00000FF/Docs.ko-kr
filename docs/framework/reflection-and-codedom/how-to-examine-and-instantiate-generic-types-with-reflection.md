---
title: '방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69864e647a7cf4e6193f4eb76ce2b7bc93b09404
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622054"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a><span data-ttu-id="65950-102">방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="65950-102">How to: Examine and Instantiate Generic Types with Reflection</span></span>
<span data-ttu-id="65950-103">다른 형식에 대한 정보와 동일한 방식으로 제네릭 형식에 대한 정보를 가져올 수 있습니다. 제네릭 형식을 나타내는 <xref:System.Type> 개체를 검사하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65950-103">Information about generic types is obtained in the same way as information about other types: by examining a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="65950-104">원칙의 차이점은 제네릭 형식에는 제네릭 형식 매개 변수를 나타내는 <xref:System.Type> 개체 목록이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65950-104">The principle difference is that a generic type has a list of <xref:System.Type> objects representing its generic type parameters.</span></span> <span data-ttu-id="65950-105">이 섹션의 첫 번째 절차에서는 제네릭 형식을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-105">The first procedure in this section examines generic types.</span></span>  
  
 <span data-ttu-id="65950-106">형식 인수를 제네릭 형식 정의의 형식 매개 변수에 바인딩하여 생성된 형식을 나타내는 <xref:System.Type> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-106">You can create a <xref:System.Type> object that represents a constructed type by binding type arguments to the type parameters of a generic type definition.</span></span> <span data-ttu-id="65950-107">두 번째 절차에서 이 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65950-107">The second procedure demonstrates this.</span></span>  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a><span data-ttu-id="65950-108">제네릭 형식 및 해당 형식 매개 변수를 검사하려면</span><span class="sxs-lookup"><span data-stu-id="65950-108">To examine a generic type and its type parameters</span></span>  
  
1.  <span data-ttu-id="65950-109">제네릭 형식을 나타내는 <xref:System.Type> 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65950-109">Get an instance of <xref:System.Type> that represents the generic type.</span></span> <span data-ttu-id="65950-110">다음 코드에서는 C# `typeof` 연산자(Visual Basic에서는 `GetType`, Visual C++에서는 `typeid`)를 사용하여 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65950-110">In the following code, the type is obtained using the C# `typeof` operator (`GetType` in Visual Basic, `typeid` in Visual C++).</span></span> <span data-ttu-id="65950-111"><xref:System.Type> 개체를 가져오는 다른 방법은 <xref:System.Type> 클래스 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65950-111">See the <xref:System.Type> class topic for other ways to get a <xref:System.Type> object.</span></span> <span data-ttu-id="65950-112">이 절차의 나머지 부분에서는 `t`라는 메서드 매개 변수에 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-112">Note that in the rest of this procedure, the type is contained in a method parameter named `t`.</span></span>  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  <span data-ttu-id="65950-113"><xref:System.Type.IsGenericType%2A> 속성을 사용하여 형식이 제네릭인지 여부를 확인하고, <xref:System.Type.IsGenericTypeDefinition%2A> 속성을 사용하여 형식이 제네릭 형식 정의인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-113">Use the <xref:System.Type.IsGenericType%2A> property to determine whether the type is generic, and use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether the type is a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  <span data-ttu-id="65950-114"><xref:System.Type.GetGenericArguments%2A> 메서드를 사용하여 제네릭 형식 인수를 포함하는 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65950-114">Get an array that contains the generic type arguments, using the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  <span data-ttu-id="65950-115"><xref:System.Type.IsGenericParameter%2A> 속성을 사용하여 각 형식 인수가 형식 매개 변수인지(예: 제네릭 형식 정의에 있음), 아니면 형식 매개 변수에 대해 지정된 형식인지(예: 생성된 형식에 있음) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-115">For each type argument, determine whether it is a type parameter (for example, in a generic type definition) or a type that has been specified for a type parameter (for example, in a constructed type), using the <xref:System.Type.IsGenericParameter%2A> property.</span></span>  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  <span data-ttu-id="65950-116">형식 시스템에서 제네릭 형식 매개 변수는 일반 형식과 마찬가지로 <xref:System.Type> 인스턴스로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65950-116">In the type system, a generic type parameter is represented by an instance of <xref:System.Type>, just as ordinary types are.</span></span> <span data-ttu-id="65950-117">다음 코드는 제네릭 형식 매개 변수를 나타내는 <xref:System.Type> 개체의 이름 및 매개 변수 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-117">The following code displays the name and parameter position of a <xref:System.Type> object that represents a generic type parameter.</span></span> <span data-ttu-id="65950-118">매개 변수 위치는 여기서는 중요한 정보가 아니며 다른 제네릭 형식의 형식 인수로 사용된 형식 매개 변수를 검사하는 경우에 더 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-118">The parameter position is trivial information here; it is of more interest when you are examining a type parameter that has been used as a type argument of another generic type.</span></span>  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  <span data-ttu-id="65950-119"><xref:System.Type.GetGenericParameterConstraints%2A> 메서드를 통해 단일 배열의 모든 제약 조건을 가져와 제네릭 형식 매개 변수의 기본 형식 제약 조건 및 인터페이스 제약 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-119">Determine the base type constraint and the interface constraints of a generic type parameter by using the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain all the constraints in a single array.</span></span> <span data-ttu-id="65950-120">제약 조건의 순서는 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-120">Constraints are not guaranteed to be in any particular order.</span></span>  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  <span data-ttu-id="65950-121"><xref:System.Type.GenericParameterAttributes%2A> 속성을 사용하여 참조 형식이어야 함 등의 형식 매개 변수에 대한 특수 제약 조건을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-121">Use the <xref:System.Type.GenericParameterAttributes%2A> property to discover the special constraints on a type parameter, such as requiring that it be a reference type.</span></span> <span data-ttu-id="65950-122">속성에는 다음 코드와 같이 마스킹할 수 있는 차이를 나타내는 값도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-122">The property also includes values that represent variance, which you can mask off as shown in the following code.</span></span>  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  <span data-ttu-id="65950-123">특수 제약 조건 특성은 플래그이고, 특수 제약 조건 없음을 나타내는 동일한 플래그(<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>)는 또한 공변성(Covariance) 또는 반공변성(Contravariance) 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65950-123">The special constraint attributes are flags, and the same flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) that represents no special constraints also represents no covariance or contravariance.</span></span> <span data-ttu-id="65950-124">따라서 이러한 조건 중 하나를 테스트하려면 적절한 마스크를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-124">Thus, to test for either of these conditions you must use the appropriate mask.</span></span> <span data-ttu-id="65950-125">이 경우 <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType>을 사용하여 특수 제약 조건 플래그를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-125">In this case, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> to isolate the special constraint flags.</span></span>  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a><span data-ttu-id="65950-126">제네릭 형식 인스턴스 생성</span><span class="sxs-lookup"><span data-stu-id="65950-126">Constructing an Instance of a Generic Type</span></span>  
 <span data-ttu-id="65950-127">제네릭 형식은 템플릿과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-127">A generic type is like a template.</span></span> <span data-ttu-id="65950-128">제네릭 형식 매개 변수에 대해 실제 형식을 지정하지 않으면 해당 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-128">You cannot create instances of it unless you specify real types for its generic type parameters.</span></span> <span data-ttu-id="65950-129">런타임에 리플렉션을 사용하여 이 작업을 수행하려면 <xref:System.Type.MakeGenericType%2A> 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-129">To do this at run time, using reflection, requires the <xref:System.Type.MakeGenericType%2A> method.</span></span>  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a><span data-ttu-id="65950-130">제네릭 형식의 인스턴스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="65950-130">To construct an instance of a generic type</span></span>  
  
1.  <span data-ttu-id="65950-131">제네릭 형식을 나타내는 <xref:System.Type> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65950-131">Get a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="65950-132">다음 코드는 두 가지 방법으로 제네릭 형식 <xref:System.Collections.Generic.Dictionary%602>를 가져옵니다. 하나는 형식을 설명하는 문자열과 함께 <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> 메서드 오버로드를 사용하는 것이고, 다른 하나는 생성된 형식 `Dictionary\<String, Example>`(Visual Basic에서는 `Dictionary(Of String, Example)`)에서 <xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65950-132">The following code gets the generic type <xref:System.Collections.Generic.Dictionary%602> in two different ways: by using the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method overload with a string describing the type, and by calling the <xref:System.Type.GetGenericTypeDefinition%2A> method on the constructed type `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span></span> <span data-ttu-id="65950-133"><xref:System.Type.MakeGenericType%2A> 메서드에는 제네릭 형식 정의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-133">The <xref:System.Type.MakeGenericType%2A> method requires a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  <span data-ttu-id="65950-134">형식 매개 변수를 대체할 형식 인수 배열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-134">Construct an array of type arguments to substitute for the type parameters.</span></span> <span data-ttu-id="65950-135">배열에는 올바른 개수의 <xref:System.Type> 개체가 형식 매개 변수 목록에 표시되는 순서대로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-135">The array must contain the correct number of <xref:System.Type> objects, in the same order as they appear in the type parameter list.</span></span> <span data-ttu-id="65950-136">이 경우 키(첫 번째 형식 매개 변수)는 <xref:System.String> 형식이고, 사전에 있는 값은 `Example`이라는 클래스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="65950-136">In this case, the key (first type parameter) is of type <xref:System.String>, and the values in the dictionary are instances of a class named `Example`.</span></span>  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  <span data-ttu-id="65950-137"><xref:System.Type.MakeGenericType%2A> 메서드를 호출하여 형식 인수를 형식 매개 변수에 바인딩하고 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-137">Call the <xref:System.Type.MakeGenericType%2A> method to bind the type arguments to the type parameters and construct the type.</span></span>  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  <span data-ttu-id="65950-138"><xref:System.Activator.CreateInstance%28System.Type%29> 메서드 오버로드를 사용하여 생성된 형식의 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65950-138">Use the <xref:System.Activator.CreateInstance%28System.Type%29> method overload to create an object of the constructed type.</span></span> <span data-ttu-id="65950-139">다음 코드는 `Example` 클래스 인스턴스 두 개를 `Dictionary<String, Example>` 개체에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-139">The following code stores two instances of the `Example` class in the resulting `Dictionary<String, Example>` object.</span></span>  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="65950-140">예제</span><span class="sxs-lookup"><span data-stu-id="65950-140">Example</span></span>  
 <span data-ttu-id="65950-141">다음 코드 예제에서는 코드에서 사용된 제네릭 형식 정의 및 생성된 형식을 검사하고 해당 정보를 표시하는 `DisplayGenericType` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-141">The following code example defines a `DisplayGenericType` method to examine the generic type definitions and constructed types used in the code and display their information.</span></span> <span data-ttu-id="65950-142">`DisplayGenericType` 메서드는 <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> 및 <xref:System.Type.GenericParameterPosition%2A> 속성과 <xref:System.Type.GetGenericArguments%2A> 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65950-142">The `DisplayGenericType` method shows how to use the <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A>, and <xref:System.Type.GenericParameterPosition%2A> properties and the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
 <span data-ttu-id="65950-143">또한 이 예제에서는 제네릭 형식 매개 변수를 검사하고 해당 제약 조건을 표시하는 `DisplayGenericParameter` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-143">The example also defines a `DisplayGenericParameter` method to examine a generic type parameter and display its constraints.</span></span>  
  
 <span data-ttu-id="65950-144">코드 예제에서는 형식 매개 변수 제약 조건을 설명하는 제네릭 형식을 포함하여 테스트 형식 집합을 정의하고 이러한 형식에 대한 정보를 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65950-144">The code example defines a set of test types, including a generic type that illustrates type parameter constraints, and shows how to display information about these types.</span></span>  
  
 <span data-ttu-id="65950-145">예제에서는 형식 인수 배열을 만들고 <xref:System.Type.MakeGenericType%2A> 메서드를 호출하여 <xref:System.Collections.Generic.Dictionary%602> 클래스에서 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-145">The example constructs a type from the <xref:System.Collections.Generic.Dictionary%602> class by creating an array of type arguments and calling the <xref:System.Type.MakeGenericType%2A> method.</span></span> <span data-ttu-id="65950-146">프로그램은 <xref:System.Type.MakeGenericType%2A>을 사용하여 생성된 <xref:System.Type> 개체와 `typeof`(Visual Basic에서는 `GetType`)를 사용하여 가져온 <xref:System.Type> 개체를 비교하여 같음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65950-146">The program compares the <xref:System.Type> object constructed using <xref:System.Type.MakeGenericType%2A> with a <xref:System.Type> object obtained using `typeof` (`GetType` in Visual Basic), demonstrating that they are the same.</span></span> <span data-ttu-id="65950-147">마찬가지로, 프로그램은 <xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 사용하여 생성된 형식의 제네릭 형식 정의를 가져오고 <xref:System.Collections.Generic.Dictionary%602> 클래스를 나타내는 <xref:System.Type> 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-147">Similarly, the program uses the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition of the constructed type, and compares it to the <xref:System.Type> object representing the <xref:System.Collections.Generic.Dictionary%602> class.</span></span>  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65950-148">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="65950-148">Compiling the Code</span></span>  
  
-   <span data-ttu-id="65950-149">코드에는 컴파일하는 데 필요한 C# `using` 문(Visual Basic에서는 `Imports`)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-149">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="65950-150">추가 어셈블리 참조는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65950-150">No additional assembly references are required.</span></span>  
  
-   <span data-ttu-id="65950-151">csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-151">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="65950-152">Visual Studio에서 코드를 컴파일하려면 콘솔 애플리케이션 프로젝트 템플릿에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="65950-152">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65950-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65950-153">See also</span></span>
- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="65950-154">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="65950-154">Reflection and Generic Types</span></span>](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)
- [<span data-ttu-id="65950-155">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="65950-155">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="65950-156">제네릭</span><span class="sxs-lookup"><span data-stu-id="65950-156">Generics</span></span>](../../../docs/standard/generics/index.md)
