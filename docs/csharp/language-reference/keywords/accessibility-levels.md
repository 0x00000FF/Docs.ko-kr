---
title: 액세스 가능성 수준(C# 참조)
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 4679fd2564454e7f1ade5cb4813729b65f433012
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45617061"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="9bc72-102">액세스 가능성 수준(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9bc72-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="9bc72-103">액세스 한정자 `public`, `protected`, `internal` 또는 `private`을 사용하여 멤버에 대해 다음과 같이 선언된 접근성 수준 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="9bc72-104">선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="9bc72-104">Declared accessibility</span></span>|<span data-ttu-id="9bc72-105">의미</span><span class="sxs-lookup"><span data-stu-id="9bc72-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="9bc72-106">액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="9bc72-107">액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="9bc72-108">액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="9bc72-109">액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="9bc72-110">액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="9bc72-111">액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="9bc72-112">C# 7.2부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="9bc72-113">`protected internal` 또는 `private protected` 조합을 사용할 경우를 제외하고 멤버 또는 형식에는 액세스 한정자가 하나만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="9bc72-114">네임스페이스에는 액세스 한정자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="9bc72-115">네임스페이스에는 액세스 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="9bc72-116">멤버 선언이 발생한 컨텍스트에 따라 특정 선언된 액세스 가능성만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="9bc72-117">액세스 한정자가 멤버 선언에서 지정되지 않으면 기본 액세스 가능성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="9bc72-118">다른 형식에 중첩되지 않은 최상위 형식에는 `internal` 또는 `public` 액세스 가능성만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="9bc72-119">이러한 형식에 대한 기본 액세스 가능성은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="9bc72-120">다음 표에 나와 있는 대로 다른 형식의 멤버인 중첩 형식에는 선언된 액세스 가능성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="9bc72-121">소속 그룹</span><span class="sxs-lookup"><span data-stu-id="9bc72-121">Members of</span></span>|<span data-ttu-id="9bc72-122">기본 멤버 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="9bc72-122">Default member accessibility</span></span>|<span data-ttu-id="9bc72-123">멤버의 허용된 선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="9bc72-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="9bc72-124">없음</span><span class="sxs-lookup"><span data-stu-id="9bc72-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="9bc72-125">없음</span><span class="sxs-lookup"><span data-stu-id="9bc72-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="9bc72-126">중첩된 형식의 액세스 가능성은 액세스 가능 도메인에 따라 다릅니다. [액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)은 멤버에 대해 선언된 액세스 가능성 및 한 수준 위 형식의 액세스 가능성 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="9bc72-127">그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bc72-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9bc72-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9bc72-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9bc72-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bc72-129">See Also</span></span>  
- [<span data-ttu-id="9bc72-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9bc72-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9bc72-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9bc72-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9bc72-132">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="9bc72-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="9bc72-133">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="9bc72-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="9bc72-134">접근성 도메인</span><span class="sxs-lookup"><span data-stu-id="9bc72-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
- [<span data-ttu-id="9bc72-135">접근성 수준 사용에 대한 제한</span><span class="sxs-lookup"><span data-stu-id="9bc72-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
- [<span data-ttu-id="9bc72-136">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="9bc72-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="9bc72-137">public</span><span class="sxs-lookup"><span data-stu-id="9bc72-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="9bc72-138">private</span><span class="sxs-lookup"><span data-stu-id="9bc72-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="9bc72-139">protected</span><span class="sxs-lookup"><span data-stu-id="9bc72-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
- [<span data-ttu-id="9bc72-140">internal</span><span class="sxs-lookup"><span data-stu-id="9bc72-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
