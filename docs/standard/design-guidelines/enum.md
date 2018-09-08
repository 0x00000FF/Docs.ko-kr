---
title: 열거형 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dea187b5f3911114e551d640e0bb0aa6fac1143
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213292"
---
# <a name="enum-design"></a><span data-ttu-id="552e7-102">열거형 디자인</span><span class="sxs-lookup"><span data-stu-id="552e7-102">Enum Design</span></span>
<span data-ttu-id="552e7-103">열거형은 값 형식의 특수 한 종류입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="552e7-104">두 가지 종류의 열거형: 단순 열거형 및 플래그 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="552e7-105">단순 열거형 선택 닫힌된 작은 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="552e7-106">단순 열거형의 일반적인 예로 색 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="552e7-107">플래그 열거형은 열거형 값에 비트 작업을 지원 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="552e7-108">플래그 열거형의 일반적인 예로 옵션 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="552e7-109">**✓ DO** 열거형을 사용 하 여 강력한 형식의 매개 변수, 속성 및 값 집합을 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="552e7-110">**✓ DO** 정적 상수 대신 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="552e7-111">**X DO NOT** 집합 (예: 운영 체제 버전, 친구, 등의 이름입니다.)에 대 한 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="552e7-112">**X DO NOT** 나중에 사용할 수는 예약 된 열거형 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="552e7-113">이후 단계에서 기존 열거형에 값을 항상 간단히 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="552e7-114">참조 [열거형에 값 추가](#add_value) 열거형에 값을 추가 하는 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="552e7-115">예약 된 값만 실제 값 집합을 손상 시 키 지 하 고 사용자 오류가 발생 하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="552e7-116">**X AVOID** 열거형 값을 하나만로 공개적으로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="552e7-117">C Api의 향후 확장성을 보장 하기 위한 일반적인 방법은 예약 된 매개 변수 메서드 시그니처를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="552e7-118">이러한 예약 된 매개 변수는 단일 기본 값을 사용 하 여 열거형으로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="552e7-119">관리 되는 Api에서 수행 되어야이 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="552e7-120">메서드 오버 로드 매개 변수는 이후 릴리스에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="552e7-121">**X DO NOT** 열거형에 센티널 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="552e7-122">Framework 개발자에 게 도움이 되기도 하지만 sentinel 값은 프레임 워크의 사용자에 게 혼동 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="552e7-123">열거형을 나타내는 집합에서 값 중 하나가 되 고 아니라 열거형의 상태를 추적에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="552e7-124">**✓ DO** 단순 열거형에는 0 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="552e7-125">"None"입니다. 같은 값을 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="552e7-126">이러한 값이 특정 열거형에 대 한 적합 하지 않은 경우 0의 내부 값을 열거형에 대 한 가장 일반적인 기본 값을 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="552e7-127">**✓ CONSIDER** 를 사용 하 여 <xref:System.Int32> (대부분의 프로그래밍 언어의 기본값) 열거형의 내부 형식으로 다음 중 하나에 해당 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="552e7-128">열거형 플래그 열거형 이며 32 개 플래그 했거나 나중에 더 하기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="552e7-129">기본 형식이 다를 수 해야 <xref:System.Int32> 다른 크기로 열거형을 예상 하는 관리 되지 않는 코드를 사용 하 여 원활한 상호 운용성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="552e7-130">작은 기본 형식 결과로 공간이 크게 절약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="552e7-131">제어 흐름에 대 한 인수로 서 주로 사용할 열거형을 예상 하는 경우 크기가 거의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="552e7-132">한 크기 절감 효과가 매우 길어질 수 있습니다 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="552e7-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="552e7-133">예상한 매우 자주 인스턴스화된 구조체 또는 클래스의 필드로 사용할 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="552e7-134">예상한 큰 배열 또는 열거형 인스턴스의 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="552e7-135">Serialize 할 열거형의 인스턴스 수가 많은 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="552e7-136">메모리 사용량에 대 한 관리 되는 개체는 수 항상 `DWORD`-정렬 되므로 효과적으로 여러 열거형 또는 총 인스턴스 크기는 항상 때문에 차이 확인 하기 위해 사용 하 여 더 작은 열거형을 압축 인스턴스에 다른 작은 구조 로 반올림 됨 것인지는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="552e7-137">**✓ DO** 단 수 명사 또는 명사구 단순 열거형 및 플래그 열거형 복수 명사 또는 명사구로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="552e7-138">**X DO NOT** 확장 <xref:System.Enum?displayProperty=nameWithType> 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="552e7-139"><xref:System.Enum?displayProperty=nameWithType> 특별 한 형식에서 데 CLR 사용자 정의 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="552e7-140">대부분의 프로그래밍 언어에는이 기능에 액세스할 수 있는 프로그래밍 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="552e7-141">예를 들어 C#에서 `enum` 키워드 열거형을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="552e7-142">디자인 플래그 열거형</span><span class="sxs-lookup"><span data-stu-id="552e7-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="552e7-143">**✓ DO** 적용 된 <xref:System.FlagsAttribute?displayProperty=nameWithType> 플래그 열거형에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="552e7-144">단순 열거형에는이 특성을 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="552e7-145">**✓ DO** 수 자유롭게 결합 비트 OR 연산을 사용 하 여 플래그 열거형 값에 2의 제곱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="552e7-146">**✓ CONSIDER** 플래그의 조합을 사용 되는 일반적으로 특수 한 열거 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="552e7-147">비트 연산은 고급 개념 및 간단한 작업에 대 한 요구 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="552e7-148"><xref:System.IO.FileAccess.ReadWrite> 이러한 특수 값의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="552e7-149">**X AVOID** 만들기 플래그 열거형 값의 조합이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="552e7-150">**X AVOID** 값 "플래그를 모두 선택 취소"를 나타내는 적절 하 게 다음 지침에서 설명 했 듯이 라는 하지 않는 한 enum 값이 0 인 플래그를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="552e7-151">**✓ DO** 0 플래그 열거형의 값 이름을 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="552e7-152">플래그 열거형에 대 한 값을 항상 수도 "플래그를 모두 취소 됩니다."</span><span class="sxs-lookup"><span data-stu-id="552e7-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="552e7-153">열거형에 값 추가</span><span class="sxs-lookup"><span data-stu-id="552e7-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="552e7-154">것은 매우 일반적 검색 후 이미 운송 열거형에 값을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="552e7-155">잠재적인 응용 프로그램 호환성 문제가 있습니다 새로 추가 된 값이 기존 API에서 반환 되 면 잘못 작성 된 응용 프로그램 새 값을 올바르게 처리 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="552e7-156">**✓ CONSIDER** 작은 호환성 위험 불구 하 고 열거형에 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="552e7-157">열거형에 대 한 추가 하 여 발생 하는 응용 프로그램 호환성 문제에 대 한 실제 데이터를 사용 하는 경우 새 일정과 이전 값을 반환 하는 새 API를 추가 하는 것이 좋습니다. 및 이전 값만 반환을 계속 해야 하는 이전 API의 사용을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="552e7-158">이렇게 하면 기존 응용 프로그램 호환성을 유지 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="552e7-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="552e7-159">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="552e7-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="552e7-160">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="552e7-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="552e7-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="552e7-161">See also</span></span>

- [<span data-ttu-id="552e7-162">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="552e7-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="552e7-163">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="552e7-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
