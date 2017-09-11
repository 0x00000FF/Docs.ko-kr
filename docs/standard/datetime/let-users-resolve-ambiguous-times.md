---
title: "방법: 사용자의 모호한 시간 확인 작업 허용"
description: "사용자가 모호한 시간을 확인하도록 허용하는 방법"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="0f4b0-104">방법: 사용자의 모호한 시간 확인 작업 허용</span><span class="sxs-lookup"><span data-stu-id="0f4b0-104">How to: let users resolve ambiguous times</span></span>

<span data-ttu-id="0f4b0-105">모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="0f4b0-106">표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="0f4b0-107">모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="0f4b0-108">모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="0f4b0-109">시간을 UTC로 매핑하는 방법에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-109">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="0f4b0-110">예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-110">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="0f4b0-111">이 문서에서는 사용자가 모호한 시간을 확인하도록 허용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-111">This article shows how to let a user resolve an ambiguous time.</span></span>

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="0f4b0-112">사용자가 모호한 시간을 확인하도록 허용하려면</span><span class="sxs-lookup"><span data-stu-id="0f4b0-112">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="0f4b0-113">사용자가 입력한 시간과 날짜를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-113">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="0f4b0-114">[IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) 또는 [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) 메서드를 호출하여 시간이 모호한지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-114">Call the [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="0f4b0-115">사용자가 원하는 오프셋을 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-115">Let the user select the desired offset.</span></span>

4. <span data-ttu-id="0f4b0-116">현지 시간에서 사용자가 선택한 오프셋을 빼서 UTC 날짜 및 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

5. <span data-ttu-id="0f4b0-117">`static`(Visual basic의 `Shared`) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 메서드를 호출하여 UTC 날짜 및 시간 값의 [Kind](xref:System.DateTime.Kind) 속성을 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-117">Call the `static` (`Shared` in Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="0f4b0-118">예제</span><span class="sxs-lookup"><span data-stu-id="0f4b0-118">Example</span></span>

<span data-ttu-id="0f4b0-119">다음 예제에서는 날짜와 시간을 입력하라는 메시지가 표시되며 모호한 경우 모호한 시간이 매핑하는 UTC 시간을 사용자가 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span> <span data-ttu-id="0f4b0-120">예제에서는 [DateTime](xref:System.DateTime) 개체를 사용합니다. 원하는 경우 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-120">The example uses a [DateTime](xref:System.DateTime) object; you can substitute a [DateTimeOffset](xref:System.DateTimeOffset) object if desired.</span></span>

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

<span data-ttu-id="0f4b0-121">예제 코드의 코어에서는 [TimeSpan](xref:System.TimeSpan) 개체의 배열을 사용하여 UTC에서 모호한 시간의 가능한 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-121">The core of the example code uses an array of [TimeSpan](xref:System.TimeSpan) objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="0f4b0-122">그러나 이러한 오프셋은 사용자에게 유용하지 않을 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-122">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="0f4b0-123">오프셋의 의미를 분명히 하기 위해 코드는 오프셋이 현지 표준 시간대의 표준 시간 또는 일광 절약 시간을 나타내는지를 적어둡니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-123">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="0f4b0-124">코드는 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 속성의 값을 가진 오프셋을 비교하여 표준 시간 및 월광 절약 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-124">The code determines which time is standard and which time is daylight by comparing the offset with the value of the [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span> <span data-ttu-id="0f4b0-125">이 속성은 UTC와 표준 시간대의 표준 시간 사이의 차이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-125">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="0f4b0-126">이 예제에서는 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 속성을 통해 현지 표준 시간대를 알아보았습니다. 로컬 표준 시간대는 개체 변수에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-126">In this example, all references to the local time zone are made through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="0f4b0-127">다른 호출은 캐시된 데이터를 지우고 현지 표준 시간대를 할당한 모든 개체를 무효화하기 때문에 이 방법이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-127">This is a recommended practice because another call could clear the cached data and invalidate any objects that the local time zone is assigned to.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f4b0-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f4b0-128">See Also</span></span>

[<span data-ttu-id="0f4b0-129">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="0f4b0-129">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="0f4b0-130">방법: 모호한 시간 확인</span><span class="sxs-lookup"><span data-stu-id="0f4b0-130">How to: resolve ambiguous times</span></span>](resolve-ambiguous-times.md)


