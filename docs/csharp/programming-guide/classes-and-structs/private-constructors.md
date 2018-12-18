---
title: 전용 생성자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a0ff8f69f7725b40eaac01acef74857c2a99247c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240504"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="6f6c5-102">전용 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="6f6c5-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="6f6c5-103">전용 생성자는 특수 인스턴스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="6f6c5-104">일반적으로 정적 멤버만 포함하는 클래스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="6f6c5-105">클래스에 하나 이상의 private 생성자가 있고 public 생성자가 없는 경우 중첩 클래스를 제외한 다른 클래스는 이 클래스의 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="6f6c5-106">예:</span><span class="sxs-lookup"><span data-stu-id="6f6c5-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="6f6c5-107">빈 생성자를 선언하면 기본 생성자가 자동으로 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="6f6c5-108">액세스 한정자를 생성자와 함께 사용하지 않는 경우 기본적으로 여전히 private입니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="6f6c5-109">그러나 일반적으로 [private](../../../csharp/language-reference/keywords/private.md) 한정자는 명시적으로 사용되어 클래스를 인스턴스화할 수 없음을 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="6f6c5-110">private 생성자는 <xref:System.Math> 클래스 등의 인스턴스 필드 또는 메서드가 없는 경우 또는 메서드를 호출하여 클래스 인스턴스를 가져오는 경우 클래스 인스턴스를 만들 수 없도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="6f6c5-111">클래스의 모든 메서드가 정적인 경우 전체 클래스를 정적 클래스로 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="6f6c5-112">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f6c5-113">예제</span><span class="sxs-lookup"><span data-stu-id="6f6c5-113">Example</span></span>  
 <span data-ttu-id="6f6c5-114">다음은 private 생성자를 사용하는 클래스의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="6f6c5-115">예제에서 다음 문의 주석 처리를 제거하는 경우 보호 수준 때문에 생성자에 액세스할 수 없어 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f6c5-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6f6c5-116">C# Language Specification</span></span>  

<span data-ttu-id="6f6c5-117">자세한 내용은 [C# 언어 사양](../../language-reference/language-specification/index.md)의 [전용 생성자](~/_csharplang/spec/classes.md#private-constructors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="6f6c5-118">C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f6c5-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f6c5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f6c5-119">See Also</span></span>

- [<span data-ttu-id="6f6c5-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6f6c5-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6f6c5-121">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="6f6c5-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="6f6c5-122">생성자</span><span class="sxs-lookup"><span data-stu-id="6f6c5-122">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="6f6c5-123">종료자</span><span class="sxs-lookup"><span data-stu-id="6f6c5-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="6f6c5-124">private</span><span class="sxs-lookup"><span data-stu-id="6f6c5-124">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="6f6c5-125">public</span><span class="sxs-lookup"><span data-stu-id="6f6c5-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
