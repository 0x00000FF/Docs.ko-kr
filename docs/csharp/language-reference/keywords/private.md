---
title: private(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9cc8f86166888b47a758e200182d319c68ca6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="private-c-reference"></a><span data-ttu-id="310aa-102">private(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="310aa-102">private (C# Reference)</span></span>
<span data-ttu-id="310aa-103">`private` 키워드는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="310aa-104">이 페이지에서는 `private` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-104">This page covers `private` access.</span></span> <span data-ttu-id="310aa-105">`private` 키워드 이기도의 일부로 [ `private protected` ](./private-protected.md) 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="310aa-106">private 액세스는 가장 낮은 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="310aa-107">private 멤버는 이 예제와 같이 선언된 클래스 또는 구조체의 본문 내에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="310aa-108">동일한 본문에 중첩된 형식도 이러한 private 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="310aa-109">선언된 클래스 또는 구조체 외부에서 private 멤버를 참조하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="310aa-110">`private` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="310aa-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="310aa-111">예제</span><span class="sxs-lookup"><span data-stu-id="310aa-111">Example</span></span>  
 <span data-ttu-id="310aa-112">이 예제에서 `Employee` 클래스는 두 전용 데이터 멤버인 `name` 및 `salary`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="310aa-113">private 멤버는 멤버 메서드에 의한 경우를 제외하고 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="310aa-114">`GetName` 및 `Salary`라는 public 메서드는 private 멤버에 제어된 액세스 권한을 허용하기 위해 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="310aa-115">`name` 멤버는 public 메서드를 통해 액세스하고, `salary` 멤버는 public 읽기 전용 속성을 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="310aa-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="310aa-116">자세한 내용은 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="310aa-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="310aa-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="310aa-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="310aa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="310aa-118">See Also</span></span>  
 [<span data-ttu-id="310aa-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="310aa-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="310aa-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="310aa-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="310aa-121">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="310aa-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="310aa-122">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="310aa-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="310aa-123">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="310aa-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="310aa-124">한정자</span><span class="sxs-lookup"><span data-stu-id="310aa-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="310aa-125">public</span><span class="sxs-lookup"><span data-stu-id="310aa-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="310aa-126">protected</span><span class="sxs-lookup"><span data-stu-id="310aa-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="310aa-127">internal</span><span class="sxs-lookup"><span data-stu-id="310aa-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
