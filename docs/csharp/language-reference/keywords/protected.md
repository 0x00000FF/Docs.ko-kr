---
title: protected(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: 2da8211ac21a5016478e7b881e7f2f9925b49cef
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001336"
---
# <a name="protected-c-reference"></a><span data-ttu-id="86881-102">protected(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="86881-102">protected (C# Reference)</span></span>
<span data-ttu-id="86881-103">`protected` 키워드는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="86881-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="86881-104">이 페이지에서는 `protected` 액세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86881-104">This page covers `protected` access.</span></span> <span data-ttu-id="86881-105">`protected` 키워드는 [`protected internal`](./protected-internal.md) 및 [`private protected`](./private-protected.md) 액세스 한정자의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="86881-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="86881-106">protected 멤버는 해당 클래스 내에서 파생 클래스 인스턴스가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86881-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="86881-107">`protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86881-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="86881-108">예</span><span class="sxs-lookup"><span data-stu-id="86881-108">Example</span></span>  
 <span data-ttu-id="86881-109">기본 클래스의 protected 멤버는 파생 클래스 형식을 통해 액세스가 발생하는 경우에만 파생 클래스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86881-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="86881-110">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="86881-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="86881-111">`a.x = 10` 문은 정적 메서드 Main 내에서 작성되었으며 클래스 B의 인스턴스가 아니므로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="86881-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="86881-112">구조체를 상속할 수 없기 때문에 구조체 멤버는 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86881-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86881-113">예</span><span class="sxs-lookup"><span data-stu-id="86881-113">Example</span></span>  
 <span data-ttu-id="86881-114">이 예제에서 `DerivedPoint` 클래스는 `Point`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="86881-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="86881-115">따라서 파생 클래스에서 직접 기본 클래스의 protected 멤버를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86881-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="86881-116">`x` 및 `y`의 액세스 수준을 [private](../../../csharp/language-reference/keywords/private.md)로 변경하는 경우 컴파일러가 오류 메시지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86881-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="86881-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="86881-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## 

- [<span data-ttu-id="86881-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="86881-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="86881-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="86881-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="86881-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="86881-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="86881-121">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="86881-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="86881-122">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="86881-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="86881-123">한정자</span><span class="sxs-lookup"><span data-stu-id="86881-123">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="86881-124">public</span><span class="sxs-lookup"><span data-stu-id="86881-124">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="86881-125">private</span><span class="sxs-lookup"><span data-stu-id="86881-125">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="86881-126">internal</span><span class="sxs-lookup"><span data-stu-id="86881-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
- <span data-ttu-id="86881-127">[internal virtual 키워드에 대한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="86881-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>