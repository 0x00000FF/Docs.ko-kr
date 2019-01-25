---
title: 생성자 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: 68192e3b75a120c73b82c34005d4dee650540bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722170"
---
# <a name="constructor-design"></a><span data-ttu-id="23d29-102">생성자 디자인</span><span class="sxs-lookup"><span data-stu-id="23d29-102">Constructor Design</span></span>
<span data-ttu-id="23d29-103">생성자의 두 가지가: 생성자 및 인스턴스 생성자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="23d29-104">형식 생성자는 정적 이며 형식 사용 하기 전에 CLR에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="23d29-105">인스턴스 생성자에는 형식의 인스턴스를 만들 때 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="23d29-106">형식 생성자 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="23d29-107">인스턴스 생성자는 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-107">Instance constructors can.</span></span> <span data-ttu-id="23d29-108">매개 변수를 사용 하지는 인스턴스 생성자에 기본 생성자 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="23d29-109">생성자는 형식의 인스턴스를 만들기 위한 가장 자연 스러운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="23d29-110">대부분의 개발자가 검색 되며 인스턴스 (예: 팩터리 메서드)를 만드는 다른 방법으로 간주 되기 전에 생성자를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="23d29-111">**✓ CONSIDER** 단순, 이상적으로 기본적으로 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="23d29-112">간단한 생성자 매개 변수의 매우 작은 수 있고 모든 매개 변수는 기본 형식 또는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="23d29-113">이러한 간단한 생성자 프레임 워크의 유용성을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="23d29-114">**✓ CONSIDER** 원하는 작업의 의미 체계의 새 인스턴스를 생성에 직접 매핑되지 않는 경우 또는 비 자연 느낌 생성자 설계 지침을 따르는 경우 생성자를 대신 정적 팩터리 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="23d29-115">**✓ DO** 가기로 생성자 매개 변수를 사용 하 여 기본 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="23d29-116">사이 의미 없는 차이가 일부 속성 집합 뒤에 빈 생성자를 사용 하 고 생성자를 사용 하 여 여러 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="23d29-117">**✓ DO** 생성자 매개 변수는 단순히 속성을 설정 하는 데 사용 되는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="23d29-118">이러한 매개 변수 및 속성 간의 유일한 차이점 대/소문자 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="23d29-119">**✓ DO** 생성자에서 최소한의 작업만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="23d29-120">생성자 캡처 이외의 작업량 생성자 매개 변수를 수행 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="23d29-121">필요할 때 까지는 다른 처리를 지연 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="23d29-122">**✓ DO** 해당 되는 경우에 인스턴스 생성자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="23d29-123">**✓ DO** 이러한 생성자가 필요한 경우 클래스, public 기본 생성자를 명시적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="23d29-124">형식에 생성자를 명시적으로 선언 하지 수, 하는 경우 여러 언어 (예: C#), public 기본 생성자를 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="23d29-125">(추상 클래스는 protected 생성자를 가져옵니다.)</span><span class="sxs-lookup"><span data-stu-id="23d29-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="23d29-126">클래스에 매개 변수화 된 생성자를 추가 컴파일러를에서 기본 생성자를 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="23d29-127">이 오류는 실수로 인 한 주요 변경 내용 많은 경우.</span><span class="sxs-lookup"><span data-stu-id="23d29-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="23d29-128">**X AVOID** 구조체에 기본 생성자를 명시적으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="23d29-129">이렇게 하면 배열 만들기 빠르고 없기 때문에 기본 생성자를 정의 하지 않은 경우이 배열에 있는 모든 슬롯에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="23d29-130">Note 많은 컴파일러를 포함 하 여 C#의 경우이 매개 변수가 없는 생성자가 구조체를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="23d29-131">**X AVOID** 개체의 생성자 내에서 가상 멤버를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="23d29-132">가상 멤버를 호출 하면 가장 많이 파생 된 재정의 호출할 수는 가장 많이 파생 된 형식의 생성자에 완벽 하 게 아직 실행 되지 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="23d29-133">형식 생성자 지침</span><span class="sxs-lookup"><span data-stu-id="23d29-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="23d29-134">**✓ DO** 정적 생성자를 private입니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="23d29-135">클래스 생성자, 정적 생성자 형식을 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="23d29-136">CLR 형식의 첫 번째 인스턴스가 만들어지거나 정적 멤버가 해당 형식에 호출 됩니다 전에 정적 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="23d29-137">사용자가 정적 생성자가 호출 하는 경우 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="23d29-138">정적 생성자를 private 인 경우에 CLR 코드에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="23d29-139">생성자에서 수행 되는 작업에 따라이 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="23d29-140">C# 컴파일러를 전용 정적 생성자를 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="23d29-141">**X DO NOT** 정적 생성자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="23d29-142">형식 생성자에서 예외가 throw 되 면 형식을 사용할 수 없는 현재 응용 프로그램 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="23d29-143">**✓ CONSIDER** 런타임 형식에서 명시적으로 정의 된 정적 생성자를 갖지 않는의 성능을 최적화할 수 있기 때문에 정적 생성자를 사용 하 여 명시적으로 보다는 정적 필드 인라인을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d29-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="23d29-144">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="23d29-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="23d29-145">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="23d29-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d29-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="23d29-146">See also</span></span>

- [<span data-ttu-id="23d29-147">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="23d29-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="23d29-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="23d29-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
