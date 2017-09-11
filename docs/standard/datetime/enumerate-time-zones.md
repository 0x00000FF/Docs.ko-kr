---
title: "방법: 컴퓨터에 있는 표준 시간대 열거"
description: "컴퓨터에 있는 표준 시간대를 열거하는 방법"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="49dfc-104">방법: 컴퓨터에 있는 표준 시간대 열거</span><span class="sxs-lookup"><span data-stu-id="49dfc-104">How to: enumerate time zones present on a computer</span></span>

<span data-ttu-id="49dfc-105">지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대 관련 정보를 시스템에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-105">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="49dfc-106">예를 들어 Windows 운영 체제에서는 이 정보를 레지스트리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-106">For example, the Windows operating system stores this information in the registry.</span></span> <span data-ttu-id="49dfc-107">그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-107">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="49dfc-108">또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-108">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="49dfc-109">따라서 언제나 응용 프로그램에서 특정 표준 시간대가 정의되어 있고 시스템에서 사용할 수 있다고 가정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-109">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="49dfc-110">표준 시간대 정보 응용 프로그램을 사용하는 많은 응용 프로그램의 첫 번째 단계는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-110">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="49dfc-111">이렇게 하려면 응용 프로그램에서 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-111">This requires that an application enumerate the time zones defined on a local system.</span></span> 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="49dfc-112">로컬 시스템에 있는 표준 시간대를 열거하려면</span><span class="sxs-lookup"><span data-stu-id="49dfc-112">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="49dfc-113">[TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-113">Call the [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) method.</span></span> <span data-ttu-id="49dfc-114">이 메서드는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체의 제네릭 [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-114">The method returns a generic [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects.</span></span> <span data-ttu-id="49dfc-115">컬렉션의 엔트리는 해당 [DisplayName](xref:System.TimeZoneInfo.DisplayName) 속성을 기준으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-115">The entries in the collection are sorted by their [DisplayName](xref:System.TimeZoneInfo.DisplayName) property.</span></span> <span data-ttu-id="49dfc-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-116">For example:</span></span>

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. <span data-ttu-id="49dfc-117">`foreach` 루프(C#의 경우) 또는 `For Each…Next` 루프(Visual Basic의 경우)를 사용하여 컬렉션의 개별 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 열거하고 각 개체에 필요한 처리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-117">Enumerate the individual [TimeZoneInfo](xref:System.TimeZoneInfo) objects in the collection by using a `foreach` loop (in C#) or a `For Each…Next` loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="49dfc-118">예를 들어 다음 코드에서는 1단계에서 반환된 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체의 [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) 컬렉션을 열거하고 각 표준 시간대의 표시 이름을 콘솔에 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="49dfc-118">For example, the following code enumerates the [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a><span data-ttu-id="49dfc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49dfc-119">See Also</span></span>

[<span data-ttu-id="49dfc-120">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="49dfc-120">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="49dfc-121">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="49dfc-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)


