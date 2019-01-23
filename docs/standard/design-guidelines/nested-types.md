---
title: 중첩 형식
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559543"
---
# <a name="nested-types"></a><span data-ttu-id="17278-102">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="17278-102">Nested Types</span></span>
<span data-ttu-id="17278-103">중첩된 형식은 바깥쪽 형식 이라고 하는 다른 형식의 범위 내에 정의 된 형식인 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="17278-104">중첩된 형식은 바깥쪽 형식의 모든 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="17278-105">예를 들어, 바깥쪽 형식 및 보호 된 바깥쪽 형식의 모든 상위 항목에 정의 된 필드를 정의 하는 전용 필드에 대 한 액세스를 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="17278-106">일반적으로 중첩된 형식 꼭 필요할 때만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="17278-107">여기에는 여러 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-107">There are several reasons for this.</span></span> <span data-ttu-id="17278-108">일부 개발자 들은 완전히 개념에 익숙하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="17278-109">이러한 개발자가 중첩 형식의 변수를 선언 구문 사용 하 여 문제가 예를 들어, 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="17278-110">중첩된 형식은 또한 매우 밀접 하 게 해당 바깥쪽 형식과 및 같이 범용 형식에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="17278-111">중첩 형식은 바깥쪽 해당 형식의 구현 세부 정보를 모델링 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="17278-112">최종 사용자는 중첩 된 형식의 변수를 선언할 필요가 거의 하 고 거의 발생 하지 않는다는 중첩된 형식을 명시적으로 인스턴스화할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="17278-113">예를 들어, 컬렉션의 열거자는 컬렉션의 중첩된 형식 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="17278-114">열거자, 바깥쪽 형식으로 일반적으로 인스턴스화됩니다 있고 다양 한 언어에서 foreach 문을 지원 하므로 열거자 변수 거의 최종 사용자가 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="17278-115">**✓ DO** 중첩된 형식 및 해당 외부 형식 간의 관계는 멤버 액세스 가능성 의미 체계는 바람직한 되도록 하는 경우 중첩 된 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="17278-116">**X DO NOT** 논리적 그룹으로 사용 하 여 공용 중첩된 형식은 생성;이 대 한 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="17278-117">**X AVOID** 중첩된 형식은 공개적으로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17278-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="17278-118">유일한 예외는 중첩 형식의 변수를 서브클래싱 또는 기타 고급 사용자 지정 시나리오와 같은 드문 시나리오 에서만에서 선언 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="17278-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="17278-119">**X DO NOT** 형식이 포함 하는 형식 외부에서 참조 될 가능성이 높은 경우 중첩 된 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="17278-120">예를 들어, 클래스에 정의 된 메서드에 전달 된 열거형 클래스에서 중첩 된 형식으로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="17278-121">**X DO NOT** 클라이언트 코드에서 인스턴스화 대상으로 해야 하는 경우 중첩 된 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="17278-122">형식에 public 생성자가 중첩 않을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="17278-123">형식을 인스턴스화할 수, 있으면 하는 것 처럼 보이지만 형식이 자체적으로 프레임 워크에서 (수를 만들고이 사용, 외부 형식을 사용할 필요 없이 제거), 따라서 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="17278-124">내부 형식 관계 없는 외부 형식 외부에서 광범위 하 게 재사용 되지 않아야 외부 형식으로 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="17278-125">**X DO NOT** 인터페이스의 구성원으로 중첩 된 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="17278-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="17278-126">대부분의 언어에서는 이러한 구문을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17278-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="17278-127">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="17278-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="17278-128">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="17278-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17278-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="17278-129">See also</span></span>

- [<span data-ttu-id="17278-130">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="17278-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="17278-131">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="17278-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
