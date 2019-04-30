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
ms.openlocfilehash: d7fe5f15f79ab068e88c3fb6f7b7cac0986aa636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052926"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="11437-102">DateTime XAML 구문</span><span class="sxs-lookup"><span data-stu-id="11437-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="11437-103">와 같은 일부 컨트롤 <xref:System.Windows.Controls.Calendar> 하 고 <xref:System.Windows.Controls.DatePicker>를 사용 하는 속성이 <xref:System.DateTime> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="11437-104">일반적으로 런타임에 코드 숨김으로 이러한 컨트롤에 대해 초기 날짜 또는 시간을 지정하지만 XAML로 초기 날짜 또는 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11437-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="11437-105">WPF XAML 파서를 구문 분석을 처리 <xref:System.DateTime> 기본 제공 XAML 텍스트 구문을 사용 하 여 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="11437-106">이 항목의 세부 정보를 설명 합니다 <xref:System.DateTime> XAML 텍스트 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="11437-107">DateTime XAML 구문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="11437-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="11437-108">날짜를 항상 XAML로 설정할 필요가 없으며 이 방법이 바람직하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11437-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="11437-109">예를 들어 사용할 수 있습니다는 <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 속성을 초기화 하거나 실행된 시간에서 날짜를 달력 사용자 입력을 기반으로 하는 코드 숨김에 대해 모든 날짜를 조정할을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11437-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="11437-110">그러나 시나리오에 하드 코딩 날짜를 저장할 수 있습니다.는 <xref:System.Windows.Controls.Calendar> 고 <xref:System.Windows.Controls.DatePicker> 컨트롤 템플릿에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="11437-111"><xref:System.DateTime> 이러한 시나리오에 대 한 XAML 구문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="11437-112">DateTime XAML 구문이 기본 동작임</span><span class="sxs-lookup"><span data-stu-id="11437-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="11437-113"><xref:System.DateTime> CLR의 기본 클래스 라이브러리에 정의 된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="11437-114">적용할 수 없으면 기본 클래스 라이브러리의 관계 CLR의 나머지 부분을 때문 <xref:System.ComponentModel.TypeConverterAttribute> 클래스를 사용 하 여 XAML에서 문자열을 처리 하도록 변환 하는 형식 변환기 <xref:System.DateTime> 런타임 개체 모델에서.</span><span class="sxs-lookup"><span data-stu-id="11437-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="11437-115">변환 동작을 제공하는 `DateTimeConverter` 클래스가 없습니다. 이 항목에서 설명하는 변환 동작은 WPF XAML 파서의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="11437-116">DateTime XAML 구문의 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="11437-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="11437-117">형식을 지정할 수 있습니다는 <xref:System.DateTime> 형식 문자열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="11437-118">형식 문자열은 값을 생성하는 데 사용할 수 있는 텍스트 구문을 공식화합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="11437-119"><xref:System.DateTime> 기존 WPF의 날짜 구성 요소를 일반적으로 사용 하 여 컨트롤에 대해 값 <xref:System.DateTime> 및 시간 구성 요소는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11437-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="11437-120">지정 하는 경우는 <xref:System.DateTime> , XAML에서 교대로 사용할 수 있습니다 하는 형식 문자열 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="11437-121">이 항목에 구체적으로 표시되지 않은 형식 및 형식 문자열을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11437-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="11437-122">에 대 한 XAML 기술적으로 보면 <xref:System.DateTime> 지정 되 고 WPF XAML 파서에서 구문 분석 된 값에 대 한 내부 호출을 사용 하 여 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>에서 허용 하는 모든 문자열을 사용할 수 있습니다 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 에 XAML에 대 한 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="11437-123">자세한 내용은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11437-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11437-124">DateTime XAML 구문을 사용 하 여 항상 `en-us` 으로 <xref:System.Globalization.CultureInfo> 기본 변환을 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="11437-125">이 영향을 받지 <xref:System.Windows.FrameworkElement.Language%2A> 값 또는 `xml:lang` XAML 특성 수준 형식 변환은 해당 컨텍스트 없이 동작 하기 때문에 XAML의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="11437-126">일과 월이 표시되는 순서와 같은 문화적 차이로 인해 여기에 표시된 형식 문자열을 보간하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="11437-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="11437-127">여기에 표시된 형식 문자열은 다른 문화권 설정에 관계없이 XAML을 구문 분석할 때 사용되는 정확한 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="11437-128">다음 섹션에서는 일부의 일반적인 <xref:System.DateTime> 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="11437-129">간단한 날짜 패턴("d")</span><span class="sxs-lookup"><span data-stu-id="11437-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="11437-130">다음의 간단한 날짜 형식을 보여 줍니다는 <xref:System.DateTime> XAML에서:</span><span class="sxs-lookup"><span data-stu-id="11437-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="11437-131">WPF 컨트롤에서 일반적으로 사용하는 데 필요한 모든 정보를 지정하는 가장 간단한 형식이며 실수에 의한 표준 시간대 오프셋 및 시간 구성 요소의 영향을 받지 않으므로 다른 형식에 비해 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="11437-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="11437-132">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="11437-133">자세한 내용은 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11437-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="11437-134">정렬 가능한 DateTime 패턴("s")</span><span class="sxs-lookup"><span data-stu-id="11437-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="11437-135">다음은 정렬 가능한 <xref:System.DateTime> XAML에서 패턴:</span><span class="sxs-lookup"><span data-stu-id="11437-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="11437-136">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="11437-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="11437-137">RFC1123 패턴("r")</span><span class="sxs-lookup"><span data-stu-id="11437-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="11437-138">RFC1123 패턴은 문화권이 고정되어 있다는 이유로 RFC1123 패턴도 사용하는 다른 날짜 생성기의 문자열 입력이 될 수 있기 때문에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="11437-139">다음은 RFC1123 <xref:System.DateTime> XAML에서 패턴:</span><span class="sxs-lookup"><span data-stu-id="11437-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="11437-140">예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="11437-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="11437-141">기타 형식 및 패턴</span><span class="sxs-lookup"><span data-stu-id="11437-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="11437-142">앞서 설명한 대로 <xref:System.DateTime> XAML에서 허용 되는 모든 문자열로 지정할 수 있습니다에 대 한 입력으로 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11437-143">여기에 다른 공식화 된 형식 (예를 들어 <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), 특정으로 공식화 되지 않은 형식과 <xref:System.Globalization.DateTimeFormatInfo> 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="11437-144">예를 들어 폼 `YYYY/mm/dd` 허용 되는 대 한 입력으로 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="11437-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11437-145">이 항목에서는 작동 가능한 모든 형식에 대해 설명하려고 하지 않으며 대신 간단한 날짜 패턴을 표준 사례로 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="11437-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11437-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="11437-146">See also</span></span>

- [<span data-ttu-id="11437-147">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="11437-147">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
