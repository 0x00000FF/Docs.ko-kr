---
title: DateTime XAML 구문
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: c9fb030e6f819b1ca463199a76acd32cb1865f33
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458946"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="b58e4-102">DateTime XAML 구문</span><span class="sxs-lookup"><span data-stu-id="b58e4-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="b58e4-103"><xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker>와 같은 일부 컨트롤에는 <xref:System.DateTime> 형식을 사용 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="b58e4-104">일반적으로 런타임에 코드 숨김으로 이러한 컨트롤에 대해 초기 날짜 또는 시간을 지정하지만 XAML로 초기 날짜 또는 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="b58e4-105">WPF XAML 파서는 기본 제공 XAML 텍스트 구문을 사용 하 여 <xref:System.DateTime> 값의 구문 분석을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="b58e4-106">이 항목에서는 <xref:System.DateTime> XAML 텍스트 구문의 세부 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="b58e4-107">DateTime XAML 구문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="b58e4-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="b58e4-108">날짜를 항상 XAML로 설정할 필요가 없으며 이 방법이 바람직하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="b58e4-109">예를 들어, <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 속성을 사용 하 여 런타임에 날짜를 초기화 하거나 사용자 입력을 기반으로 코드 숨김으로 된 달력에 대 한 모든 날짜 조정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="b58e4-110">그러나 날짜를 <xref:System.Windows.Controls.Calendar>에 하드 코딩 하 고 컨트롤 템플릿에서 <xref:System.Windows.Controls.DatePicker> 수 있는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="b58e4-111">이러한 시나리오에는 <xref:System.DateTime> XAML 구문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="b58e4-112">DateTime XAML 구문이 기본 동작임</span><span class="sxs-lookup"><span data-stu-id="b58e4-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="b58e4-113"><xref:System.DateTime>은 CLR의 기본 클래스 라이브러리에 정의 된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="b58e4-114">기본 클래스 라이브러리가 CLR의 나머지 부분과 관련 되는 방식 때문에 <xref:System.ComponentModel.TypeConverterAttribute>를 클래스에 적용 하 고 형식 변환기를 사용 하 여 XAML의 문자열을 처리 하 고 런타임 개체 모델의 <xref:System.DateTime>로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="b58e4-115">변환 동작을 제공하는 `DateTimeConverter` 클래스가 없습니다. 이 항목에서 설명하는 변환 동작은 WPF XAML 파서의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="b58e4-116">DateTime XAML 구문의 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="b58e4-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="b58e4-117">서식 문자열을 사용 하 여 <xref:System.DateTime> 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="b58e4-118">형식 문자열은 값을 생성하는 데 사용할 수 있는 텍스트 구문을 공식화합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="b58e4-119">기존 WPF 컨트롤의 <xref:System.DateTime> 값은 일반적으로 시간 구성 요소가 아닌 <xref:System.DateTime>의 날짜 구성 요소만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="b58e4-120">XAML에서 <xref:System.DateTime>를 지정 하는 경우 형식 문자열을 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="b58e4-121">이 항목에 구체적으로 표시되지 않은 형식 및 형식 문자열을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="b58e4-122">기술적으로, WPF XAML 파서에서 지정 하 고 구문 분석 하는 모든 <xref:System.DateTime> 값에 대 한 XAML은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>에 대 한 내부 호출을 사용 하므로 XAML 입력에 대해 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>에서 허용 하는 모든 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="b58e4-123">자세한 내용은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b58e4-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b58e4-124">DateTime XAML 구문은 항상 네이티브 변환에 대 한 <xref:System.Globalization.CultureInfo>로 `en-us`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="b58e4-125">Xaml 특성 수준 형식 변환이 해당 컨텍스트 없이 작동 하기 때문에이는 XAML의 <xref:System.Windows.FrameworkElement.Language%2A> 값 또는 `xml:lang` 값의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="b58e4-126">일과 월이 표시되는 순서와 같은 문화적 차이로 인해 여기에 표시된 형식 문자열을 보간하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b58e4-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="b58e4-127">여기에 표시된 형식 문자열은 다른 문화권 설정에 관계없이 XAML을 구문 분석할 때 사용되는 정확한 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="b58e4-128">다음 섹션에서는 몇 가지 일반적인 <xref:System.DateTime> 형식 문자열에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="b58e4-129">간단한 날짜 패턴("d")</span><span class="sxs-lookup"><span data-stu-id="b58e4-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="b58e4-130">다음은 XAML의 <xref:System.DateTime>에 대 한 간단한 날짜 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="b58e4-131">WPF 컨트롤에서 일반적으로 사용하는 데 필요한 모든 정보를 지정하는 가장 간단한 형식이며 실수에 의한 표준 시간대 오프셋 및 시간 구성 요소의 영향을 받지 않으므로 다른 형식에 비해 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="b58e4-132">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="b58e4-133">자세한 내용은 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b58e4-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="b58e4-134">정렬 가능한 DateTime 패턴("s")</span><span class="sxs-lookup"><span data-stu-id="b58e4-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="b58e4-135">다음은 XAML의 정렬 가능한 <xref:System.DateTime> 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="b58e4-136">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="b58e4-137">RFC1123 패턴("r")</span><span class="sxs-lookup"><span data-stu-id="b58e4-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="b58e4-138">RFC1123 패턴은 문화권이 고정되어 있다는 이유로 RFC1123 패턴도 사용하는 다른 날짜 생성기의 문자열 입력이 될 수 있기 때문에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="b58e4-139">다음은 XAML의 RFC1123 <xref:System.DateTime> 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="b58e4-140">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="b58e4-141">기타 형식 및 패턴</span><span class="sxs-lookup"><span data-stu-id="b58e4-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="b58e4-142">앞에서 설명한 대로 XAML의 <xref:System.DateTime> <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>입력으로 허용 되는 임의의 문자열로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b58e4-143">여기에는 다른 공식화 된 형식 (예: <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) 및 특정 <xref:System.Globalization.DateTimeFormatInfo> 양식으로 형식화 되지 않은 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="b58e4-144">예를 들어 `YYYY/mm/dd` 폼은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>입력으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b58e4-145">이 항목에서는 작동 가능한 모든 형식에 대해 설명하려고 하지 않으며 대신 간단한 날짜 패턴을 표준 사례로 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="b58e4-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58e4-146">참조</span><span class="sxs-lookup"><span data-stu-id="b58e4-146">See also</span></span>

- [<span data-ttu-id="b58e4-147">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="b58e4-147">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
