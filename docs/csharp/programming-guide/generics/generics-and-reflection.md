---
title: "제네릭 및 리플렉션(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
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
ms.openlocfilehash: 201806cca08be0633d41e10ecb7641a0f03c975b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-reflection-c-programming-guide"></a><span data-ttu-id="81e2c-102">제네릭 및 리플렉션(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="81e2c-102">Generics and Reflection (C# Programming Guide)</span></span>
<span data-ttu-id="81e2c-103">CLR(공용 언어 런타임)은 런타임에 제네릭 형식 정보에 액세스할 수 있으므로 제네릭이 아닌 형식에 대한 방법과 동일한 방법으로 리플렉션을 사용하여 제네릭 형식에 대한 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-103">Because the Common Language Runtime (CLR) has access to generic type information at run time, you can use reflection to obtain information about generic types in the same way as for non-generic types.</span></span> <span data-ttu-id="81e2c-104">자세한 내용은 [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e2c-104">For more information, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="81e2c-105">[!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)]에서는 제네릭 형식에 대한 런타임 정보를 사용할 수 있도록 <xref:System.Type> 클래스에 여러 개의 새 멤버가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-105">In the [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] several new members are added to the <xref:System.Type> class to enable run-time information for generic types.</span></span> <span data-ttu-id="81e2c-106">이러한 메서드 및 속성을 사용하는 방법에 대한 자세한 내용은 이러한 클래스에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e2c-106">See the documentation on these classes for more information on how to use these methods and properties.</span></span> <span data-ttu-id="81e2c-107"><xref:System.Reflection.Emit> 네임스페이스에도 제네릭을 지원하는 새 멤버가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-107">The <xref:System.Reflection.Emit> namespace also contains new members that support generics.</span></span> <span data-ttu-id="81e2c-108">[방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e2c-108">See [How to: Define a Generic Type with Reflection Emit](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).</span></span>  
  
 <span data-ttu-id="81e2c-109">제네릭 리플렉션에 사용되는 용어의 고정 조건 목록은 <xref:System.Type.IsGenericType%2A> 속성 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e2c-109">For a list of the invariant conditions for terms used in generic reflection, see the <xref:System.Type.IsGenericType%2A> property remarks.</span></span>  
  
|<span data-ttu-id="81e2c-110">System.Type 멤버 이름</span><span class="sxs-lookup"><span data-stu-id="81e2c-110">System.Type Member Name</span></span>|<span data-ttu-id="81e2c-111">설명</span><span class="sxs-lookup"><span data-stu-id="81e2c-111">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|<span data-ttu-id="81e2c-112">형식이 제네릭이면 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-112">Returns true if a type is generic.</span></span>|  
|<xref:System.Type.GetGenericArguments%2A>|<span data-ttu-id="81e2c-113">생성된 형식에 제공된 형식 인수 또는 제네릭 형식 정의의 형식 매개 변수를 나타내는 `Type` 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-113">Returns an array of `Type` objects that represent the type arguments supplied for a constructed type, or the type parameters of a generic type definition.</span></span>|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|<span data-ttu-id="81e2c-114">현재 생성된 형식에 대 한 기본 제네릭 형식 정의 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-114">Returns the underlying generic type definition for the current constructed type.</span></span>|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|<span data-ttu-id="81e2c-115">현재 제네릭 형식 매개 변수에 대한 제약 조건을 나타내는 `Type` 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-115">Returns an array of `Type` objects that represent the constraints on the current generic type parameter.</span></span>|  
|<xref:System.Type.ContainsGenericParameters%2A>|<span data-ttu-id="81e2c-116">형식 또는 바깥쪽 형식이나 메서드에 제공되지 않은 특정 형식에 대한 형식 매개 변수가 포함된 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-116">Returns true if the type or any of its enclosing types or methods contain type parameters for which specific types have not been supplied.</span></span>|  
|<xref:System.Type.GenericParameterAttributes%2A>|<span data-ttu-id="81e2c-117">현재 제네릭 형식 매개 변수의 특수 제약 조건을 설명하는 `GenericParameterAttributes` 플래그의 조합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-117">Gets a combination of `GenericParameterAttributes` flags that describe the special constraints of the current generic type parameter.</span></span>|  
|<xref:System.Type.GenericParameterPosition%2A>|<span data-ttu-id="81e2c-118">`Type` 개체가 형식 매개 변수를 나타내는 경우 형식 매개 변수를 선언한 제네릭 형식 정의 또는 제네릭 메서드 정의의 형식 매개 변수 목록에서 해당 형식 매개 변수의 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-118">For a `Type` object that represents a type parameter, gets the position of the type parameter in the type parameter list of the generic type definition or generic method definition that declared the type parameter.</span></span>|  
|<xref:System.Type.IsGenericParameter%2A>|<span data-ttu-id="81e2c-119">현재 `Type`이 제네릭 형식 또는 메서드 정의의 형식 매개 변수를 나타내는지를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-119">Gets a value that indicates whether the current `Type` represents a type parameter of a generic type or method definition.</span></span>|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|<span data-ttu-id="81e2c-120">현재 <xref:System.Type>이 다른 제네릭 형식을 생성하는 데 사용될 수 있는 제네릭 형식 정의를 나타내는지 여부를 가리키는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-120">Gets a value that indicates whether the current <xref:System.Type> represents a generic type definition, from which other generic types can be constructed.</span></span> <span data-ttu-id="81e2c-121">형식이 제네릭 형식의 정의를 나타내는 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-121">Returns true if the type represents the definition of a generic type.</span></span>|  
|<xref:System.Type.DeclaringMethod%2A>|<span data-ttu-id="81e2c-122">현재 제네릭 형식 매개 변수를 정의한 제네릭 메서드를 반환하거나 형식 매개 변수가 제네릭 메서드에 의해 정의되지 않은 경우 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-122">Returns the generic method that defined the current generic type parameter, or null if the type parameter was not defined by a generic method.</span></span>|  
|<xref:System.Type.MakeGenericType%2A>|<span data-ttu-id="81e2c-123">형식 배열의 요소를 현재 제네릭 형식 정의의 형식 매개 변수로 대체하고 생성된 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-123">Substitutes the elements of an array of types for the type parameters of the current generic type definition, and returns a <xref:System.Type> object representing the resulting constructed type.</span></span>|  
  
 <span data-ttu-id="81e2c-124">또한 제네릭 메서드에 대한 런타임 정보를 사용할 수 있도록 <xref:System.Reflection.MethodInfo> 클래스에 새 멤버가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-124">In addition, new members are added to the <xref:System.Reflection.MethodInfo> class to enable run-time information for generic methods.</span></span> <span data-ttu-id="81e2c-125">제네릭 메서드를 반영하는 데 사용되는 용어에 대한 고정 조건 목록은 <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> 속성 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e2c-125">See the <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> property remarks for a list of invariant conditions for terms used to reflect on generic methods.</span></span>  
  
|<span data-ttu-id="81e2c-126">System.Reflection.MemberInfo 멤버 이름</span><span class="sxs-lookup"><span data-stu-id="81e2c-126">System.Reflection.MemberInfo Member Name</span></span>|<span data-ttu-id="81e2c-127">설명</span><span class="sxs-lookup"><span data-stu-id="81e2c-127">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|<span data-ttu-id="81e2c-128">메서드가 제네릭인 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-128">Returns true if a method is generic.</span></span>|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|<span data-ttu-id="81e2c-129">생성된 제네릭 메서드의 형식 인수나 제네릭 메서드 정의의 형식 매개 변수를 나타내는 Type 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-129">Returns an array of Type objects that represent the type arguments of a constructed generic method or the type parameters of a generic method definition.</span></span>|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|<span data-ttu-id="81e2c-130">현재 생성된 메서드에 대한 기본 제네릭 메서드 정의를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-130">Returns the underlying generic method definition for the current constructed method.</span></span>|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|<span data-ttu-id="81e2c-131">메서드 또는 바깥쪽 형식에 제공되지 않은 특정 형식에 대한 형식 매개 변수가 포함된 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-131">Returns true if the method or any of its enclosing types contain any type parameters for which specific types have not been supplied.</span></span>|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|<span data-ttu-id="81e2c-132">현재 <xref:System.Reflection.MethodInfo>가 제네릭 메서드의 정의를 나타내는 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-132">Returns true if the current <xref:System.Reflection.MethodInfo> represents the definition of a generic method.</span></span>|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|<span data-ttu-id="81e2c-133">현재 제네릭 메서드 정의의 형식 매개 변수를 형식 배열의 요소로 대체하고, 결과로 생성된 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81e2c-133">Substitutes the elements of an array of types for the type parameters of the current generic method definition, and returns a <xref:System.Reflection.MethodInfo> object representing the resulting constructed method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81e2c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81e2c-134">See Also</span></span>  
 <span data-ttu-id="81e2c-135">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="81e2c-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="81e2c-136">[제네릭](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="81e2c-136">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="81e2c-137">[리플렉션 및 제네릭 형식](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="81e2c-137">[Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) </span></span>  
 [<span data-ttu-id="81e2c-138">제네릭</span><span class="sxs-lookup"><span data-stu-id="81e2c-138">Generics</span></span>](~/docs/standard/generics/index.md)

