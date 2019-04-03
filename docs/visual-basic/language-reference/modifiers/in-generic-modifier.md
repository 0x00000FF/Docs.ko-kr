---
title: In(제네릭 한정자)(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d8d503f0814a89c977cdc208eced026b2d8cb1fd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838939"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="acccf-102">In(제네릭 한정자)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acccf-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="acccf-103">제네릭 형식 매개 변수에서 `In` 키워드는 형식 매개 변수를 반공변(contravariant)으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acccf-104">설명</span><span class="sxs-lookup"><span data-stu-id="acccf-104">Remarks</span></span>  
 <span data-ttu-id="acccf-105">반공변성(Contravariance)을 통해 제네릭 매개 변수에 지정된 것보다 적은 파생 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="acccf-106">따라서 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="acccf-107">자세한 내용은 [공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acccf-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="acccf-108">규칙</span><span class="sxs-lookup"><span data-stu-id="acccf-108">Rules</span></span>  
 <span data-ttu-id="acccf-109">제네릭 인터페이스 및 대리자에서 `In` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="acccf-110">형식 매개 변수 메서드 인수의 형식 으로만 사용 되 고 메서드 반환 형식으로 사용 되지 경우 제네릭 인터페이스 또는 대리자에서 반공 변을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="acccf-111">`ByRef` 매개 변수는 공변 (covariant) 일 수 없습니다 또는 반공 변입니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="acccf-112">반 공변성 (covariance) 및 참조 형식에 대 한 지원 및 값 형식에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="acccf-113">Visual basic에서 대리자 형식을 지정 하지 않고 반 공변성 인터페이스의 이벤트를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="acccf-114">또한 반 공변성 인터페이스 클래스, 열거형 또는 구조를 중첩 있을 수 없습니다. 하지만 인터페이스 중첩 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="acccf-115">동작</span><span class="sxs-lookup"><span data-stu-id="acccf-115">Behavior</span></span>  
 <span data-ttu-id="acccf-116">반공변(contravariant) 형식 매개 변수가 있는 인터페이스는 해당 메서드가 인터페이스 형식 매개 변수에 지정된 형식보다 덜 파생된 형식의 인수를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="acccf-117">예를 들어 .NET Framework 4의 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 T 형식은 반공변(contravariant)이므로 `Person`가 `Employee`을 상속하는 경우 특수 변환 메서드를 사용하지 않고 `IComparer(Of Person)` 형식의 개체를 `IComparer(Of Employee)` 형식의 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="acccf-118">반공변(contravariant) 대리자에 동일한 형식의 다른 대리자를 할당할 수 있지만 덜 파생된 제네릭 형식 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acccf-119">예제</span><span class="sxs-lookup"><span data-stu-id="acccf-119">Example</span></span>  
 <span data-ttu-id="acccf-120">다음 예제에서는 반공변(contravariant) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="acccf-121">또한 이 인터페이스를 구현하는 클래스에 대해 암시적 변환을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="acccf-122">예제</span><span class="sxs-lookup"><span data-stu-id="acccf-122">Example</span></span>  
 <span data-ttu-id="acccf-123">다음 예제에서는 반공변(contravariant) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="acccf-124">또한 대리자 형식을 암시적으로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acccf-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="acccf-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="acccf-125">See also</span></span>

- [<span data-ttu-id="acccf-126">제네릭 인터페이스의 가변성</span><span class="sxs-lookup"><span data-stu-id="acccf-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="acccf-127">Out</span><span class="sxs-lookup"><span data-stu-id="acccf-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
