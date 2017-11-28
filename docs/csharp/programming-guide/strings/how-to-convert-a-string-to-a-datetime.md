---
title: "방법: 문자열을 DateTime으로 변환(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: strings [C#], converting to DateTIme
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b459f245f0090fff16918bceb12a0082f6944331
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-convert-a-string-to-a-datetime-c-programming-guide"></a><span data-ttu-id="0af2c-102">방법: 문자열을 DateTime으로 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0af2c-102">How to: Convert a String to a DateTime (C# Programming Guide)</span></span>
<span data-ttu-id="0af2c-103">사용자가 날짜를 문자열 값으로 입력할 수 있도록 하는 프로그램에서 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-103">It is common for programs to enable users to enter dates as string values.</span></span> <span data-ttu-id="0af2c-104">문자열 기반 날짜를 <xref:System.DateTime?displayProperty=nameWithType> 개체로 변환하려면 다음 예제와 같이 <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType> 메서드 또는 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 정적 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-104">To convert a string-based date to a <xref:System.DateTime?displayProperty=nameWithType> object, you can use the <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType> method or the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> static method, as shown in the following example.</span></span>  
  
 <span data-ttu-id="0af2c-105">**문화권**.</span><span class="sxs-lookup"><span data-stu-id="0af2c-105">**Culture**.</span></span>  <span data-ttu-id="0af2c-106">세계의 각 문화권은 서로 다른 방법으로 날짜 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-106">Different cultures in the world write date strings in different ways.</span></span>  <span data-ttu-id="0af2c-107">예를 들어 미국에서 01/20/2008은 2008년 1월 20일입니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-107">For example, in the US 01/20/2008 is January 20th, 2008.</span></span>  <span data-ttu-id="0af2c-108">프랑스에서는 InvalidFormatException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-108">In France this will throw an InvalidFormatException.</span></span> <span data-ttu-id="0af2c-109">이는 프랑스에서는 날짜-시간을 일/월/연도로 읽고 미국에서는 월/일/연도이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-109">This is because France reads date-times as Day/Month/Year, and in the US it is Month/Day/Year.</span></span>  
  
 <span data-ttu-id="0af2c-110">따라서 20/01/2008과 같은 문자열은 프랑스에서는 2008년 1월 20일로 구문 분석되고 미국에서는 InvalidFormatException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-110">Consequently, a string like 20/01/2008 will parse to January 20th, 2008 in France, and then throw an InvalidFormatException in the US.</span></span>  
  
 <span data-ttu-id="0af2c-111">현재 문화권 설정을 확인하려면 System.Globalization.CultureInfo.CurrentCulture를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-111">To determine your current culture settings, you can use System.Globalization.CultureInfo.CurrentCulture.</span></span>  
  
 <span data-ttu-id="0af2c-112">문자열을 dateTime으로 변환하는 간단한 예는 아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0af2c-112">See the example below for a simple example of converting a string to dateTime.</span></span>  
  
 <span data-ttu-id="0af2c-113">날짜 문자열의 자세한 예는 <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0af2c-113">For more examples of date strings, see <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
```csharp  
string dateTime = "01/08/2008 14:50:50.42";  
            DateTime dt = Convert.ToDateTime(dateTime);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond);  
            // Specify exactly how to interpret the string.  
            IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true);  
  
            // Alternate choice: If the string has been input by an end user, you might    
            // want to format it according to the current culture:   
            // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture;  
            DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond  
/* Output (assuming first culture is en-US and second is fr-FR):  
    Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Press any key to continue . . .  
 */  
```  
  
## <a name="example"></a><span data-ttu-id="0af2c-114">예제</span><span class="sxs-lookup"><span data-stu-id="0af2c-114">Example</span></span>  
 [!code-csharp[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-a-string-to-a-datetime_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0af2c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0af2c-115">See Also</span></span>  
 [<span data-ttu-id="0af2c-116">문자열</span><span class="sxs-lookup"><span data-stu-id="0af2c-116">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
