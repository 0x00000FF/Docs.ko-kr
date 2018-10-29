---
title: 열거형 형식 대신 열거형 클래스 사용
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 열거형 형식 대신 열거형 클래스 사용
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 60d8c8e88cca19c92f6a1364bf2fbbf0500081c3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195725"
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="459c1-103">열거형 형식 대신 열거형 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="459c1-103">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="459c1-104">[열거형](../../../../docs/csharp/language-reference/keywords/enum.md)(또는 줄여서 *열거형 형식*)은 정수 형식에 대한 씬 언어 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="459c1-105">닫힌 값 집합에서 값을 저장하는 경우 해당 사용을 제한해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="459c1-106">크기(소규모, 중간 규모, 대규모)를 기반으로 하는 분류가 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="459c1-107">제어 흐름 또는 추가 추상화에 열거형을 사용하는 것은 [코드 스멜](https://deviq.com/code-smells/)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="459c1-108">이 형식으로 사용하면 열거형의 값을 확인하는 여러 제어 흐름 문을 사용하여 취약한 코드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="459c1-109">대신 개체 지향 언어의 모든 풍부한 기능을 활성화하는 열거형 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="459c1-110">그러나 중요한 항목은 아니며 대부분의 경우에 간단한 설명을 위해 기본 설정된 기본 [열거형 형식](../../../../docs/csharp/language-reference/keywords/enum.md)을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="459c1-111">열거형 기본 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="459c1-111">Implementing an Enumeration base class</span></span>

<span data-ttu-id="459c1-112">다음 예제와 같이 eShopOnContainers의 마이크로 서비스를 정렬하면 샘플 열거형 기본 클래스 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-112">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }
    
    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | BindingFlags.Static | BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

<span data-ttu-id="459c1-113">엔터티 또는 값 개체에서 이 클래스를 다음 CardType 열거형 클래스와 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="459c1-113">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public abstract class CardType : Enumeration
{
    public static CardType Amex = new AmexCardType();
    public static CardType Visa = new VisaCardType();
    public static CardType MasterCard = new MasterCardType();

    protected CardType(int id, string name)
        : base(id, name)
    {
    }

    private class AmexCardType : CardType
    {
        public AmexCardType(): base(1, "Amex")
        { }
    }
    
    private class VisaCardType : CardType
    {
        public VisaCardType(): base(2, "Visa")
        { }
    }
    
    private class MasterCardType : CardType
    {
        public MasterCardType(): base(3, "MasterCard")
        { }
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="459c1-114">추가 자료</span><span class="sxs-lookup"><span data-stu-id="459c1-114">Additional resources</span></span>

-   <span data-ttu-id="459c1-115">**열거형을 의심할 것 - 업데이트**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="459c1-115">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="459c1-116">**Daniel Hardman 열거형이 질병을 전파하는 방법 - 및 질병 치료 방법**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="459c1-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="459c1-117">**Jimmy Bogard. 열거형 클래스**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="459c1-117">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="459c1-118">**Steve Smith. C#의 열거형 옵션**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="459c1-118">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="459c1-119">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="459c1-119">**Enumeration.cs.**</span></span> <span data-ttu-id="459c1-120">eShopOnContainers의 기본 열거형 클래스 [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="459c1-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="459c1-121">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="459c1-121">**CardType.cs**.</span></span> <span data-ttu-id="459c1-122">eShopOnContainers의 샘플 열거형 클래스</span><span class="sxs-lookup"><span data-stu-id="459c1-122">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="459c1-123">[이전](implement-value-objects.md)
[다음](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="459c1-123">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
