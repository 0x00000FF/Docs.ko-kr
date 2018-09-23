---
title: 클래스, 구조체 및 인터페이스의 이름
ms.date: 03/30/2017
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c56f840bc5ebd5070c9b686384751acab3f0203
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2018
ms.locfileid: "46705603"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="7e97e-102">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="7e97e-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="7e97e-103">명명 지침을 따르는 일반 형식 이름에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="7e97e-104">**✓ DO** 명사 또는 명사구를 PascalCasing를 사용 하 여으로 클래스 및 구조체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="7e97e-105">이 메서드의 동사구를 사용 하 여 명명 된 형식 이름을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="7e97e-106">**✓ DO** 형용사 구 또는 경우에 따라 명사 또는 명사구 인터페이스 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="7e97e-107">명사 및 명사구를 거의 사용 해야 하며 형식을 추상 클래스와 인터페이스 하지 되어야 함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="7e97e-108">**X DO NOT** 클래스 이름 (예: "C")는 접두사를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="7e97e-109">**✓ CONSIDER** 기본 클래스의 이름으로 클래스를 파생 종료 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="7e97e-110">이 매우 읽기가 가능 하며 명확 하 게 관계에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="7e97e-111">이 코드의 예로: `ArgumentOutOfRangeException`는 일종의 `Exception`, 및 `SerializableAttribute`, 종류는의 `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="7e97e-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="7e97e-112">그러나 반드시이 지침은; 적용할 합리적인 판단을 사용 하 여 예를 들어 합니다 `Button` 클래스는 일종의 `Control` 이벤트 있지만 `Control` 이름에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="7e97e-113">**✓ DO** 문자로 접두사 인터페이스 이름을 I, 유형을 인터페이스 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="7e97e-114">예를 들어 `IComponent` (설명이 포함 된 명사) `ICustomAttributeProvider` (명사구) 및 `IPersistable` (명사)은 적절 한 인터페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="7e97e-115">다른 형식 이름과 마찬가지로 약어를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="7e97e-116">**✓ DO** 이름으로 "I" 접두사 인터페이스 이름에는 클래스는 인터페이스의 표준 구현 클래스-인터페이스 쌍을 정의 하는 경우에 다른 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="7e97e-117">제네릭 형식 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="7e97e-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="7e97e-118">제네릭은은.NET Framework 2.0에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="7e97e-119">기능 도입 라는 식별자의 새 종류 *형식 매개 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="7e97e-120">**✓ DO** 단일 문자 이름을 완전히 자체 설명 하 고 설명 하는 이름 값을 더 하지 않는 경우 제외 설명적인 이름으로 name 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="7e97e-121">**✓ CONSIDER** 를 사용 하 여 `T` 단일 문자 형식 매개 변수를 사용 하는 형식에 대 한 형식 매개 변수 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="7e97e-122">**✓ DO** 설명적인 형식 매개 변수 이름 앞에 `T`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="7e97e-123">**✓ CONSIDER** 제약 조건을 나타내는 매개 변수 이름의 형식 매개 변수에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="7e97e-124">매개 변수를 제한 하는 예를 들어 `ISession` 이라고 할 수 있습니다 `TSession`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="7e97e-125">공용 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="7e97e-125">Names of Common Types</span></span>  
 <span data-ttu-id="7e97e-126">**✓ DO** 또는 특정.NET Framework 형식이 구현에서 파생 된 형식의 이름을 지정할 때 다음 표에 설명 된 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="7e97e-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="7e97e-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="7e97e-127">Base Type</span></span>|<span data-ttu-id="7e97e-128">파생 된 구현 형식 지침</span><span class="sxs-lookup"><span data-stu-id="7e97e-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="7e97e-129">**✓ DO** 사용자 지정 특성 클래스의 이름에 "특성" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="7e97e-130">**✓ DO** 이벤트에 사용 되는 대리자의 이름에 "EventHandler" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="7e97e-131">**✓ DO** 이외의 이벤트 처리기로 사용 되는 접미사 "Callback" 이름에 대리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="7e97e-132">**X DO NOT** "대리자" 접미사는 대리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="7e97e-133">**✓ DO** "EventArgs입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="7e97e-134">**X DO NOT** 대신 해당 언어에서 지 원하는 키워드를 사용 하 여; 예를 들어 C#에서 사용 하 여이 클래스에서 파생 된 `enum` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="7e97e-135">**X DO NOT** "열거형" 또는 "Flag" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="7e97e-136">**✓ DO** "예외" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="7e97e-137">**✓ DO** "사전입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="7e97e-138">`IDictionary` 는 컬렉션의 특정 형식 이지만이 지침은 보다 일반적인 컬렉션 지침 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="7e97e-139">**✓ DO** "Collection" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="7e97e-140">**✓ DO** "스트림입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="7e97e-141">**✓ DO** "권한" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="7e97e-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="7e97e-142">열거형 이름 지정</span><span class="sxs-lookup"><span data-stu-id="7e97e-142">Naming Enumerations</span></span>  
 <span data-ttu-id="7e97e-143">일반적 열거형 형식 (열거형이 라고도 함)의 이름은 표준 형식 명명 규칙 (PascalCasing 등) 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="7e97e-144">그러나 열거형에 특별히 적용 되는 추가 사용 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="7e97e-145">**✓ DO** 비트 필드에 해당 값이 경우가 아니면 열거형에 대 한 단수형 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="7e97e-146">**✓ DO** 라고도 함 플래그 열거형 값으로 비트 필드 열거형에 대 한 복수 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="7e97e-147">**X DO NOT** enum 형식 이름에 "열거형" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="7e97e-148">**X DO NOT** "플래그를"를 사용 하 여 또는 열거형에서 "Flags" 접미사 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="7e97e-149">**X DO NOT** 서식 있는 텍스트 열거형 등에 대 한 열거형 값 이름 (예: "ad" 열거형의 ADO.), "rtf"에 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e97e-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="7e97e-150">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="7e97e-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7e97e-151">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="7e97e-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e97e-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e97e-152">See also</span></span>

- [<span data-ttu-id="7e97e-153">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="7e97e-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="7e97e-154">명명 지침</span><span class="sxs-lookup"><span data-stu-id="7e97e-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
