---
title: dateTimeInvalidLocalFormat MDA
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb5777e275fd7c48f7125b9e0315b08d3095c373
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357808"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="a1051-102">dateTimeInvalidLocalFormat MDA</span><span class="sxs-lookup"><span data-stu-id="a1051-102">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="a1051-103">UTC(협정 세계 표준시)로 저장된 <xref:System.DateTime> 인스턴스가 로컬 <xref:System.DateTime> 인스턴스에만 사용해야 하는 형식을 사용하여 형식이 지정되면 `dateTimeInvalidLocalFormat` MDA가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-103">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="a1051-104">미지정 또는 기본 <xref:System.DateTime> 인스턴스의 경우 이 MDA는 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-104">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="a1051-105">증상</span><span class="sxs-lookup"><span data-stu-id="a1051-105">Symptom</span></span>  
 <span data-ttu-id="a1051-106">응용 프로그램이 로컬 형식을 사용하여 수동으로 UTC <xref:System.DateTime> 인스턴스를 직렬화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-106">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="a1051-107">원인</span><span class="sxs-lookup"><span data-stu-id="a1051-107">Cause</span></span>  
 <span data-ttu-id="a1051-108"><xref:System.DateTime.ToString%2A?displayProperty=nameWithType> 메서드에 대한 ‘z’ 형식에는 로컬 표준 시간대 오프셋이 포함됩니다(예: 시드니 시간의 경우 “+10:00”).</span><span class="sxs-lookup"><span data-stu-id="a1051-108">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="a1051-109">이와 같이 <xref:System.DateTime> 값이 로컬인 경우 이 형식은 의미 있는 결과만 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-109">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="a1051-110">값이 UTC 시간인 경우 <xref:System.DateTime.ToString%2A?displayProperty=nameWithType>에는 로컬 표준 시간대 오프셋이 포함되지만 표준 시간대 지정자를 표시하거나 조정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-110">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="a1051-111">해결</span><span class="sxs-lookup"><span data-stu-id="a1051-111">Resolution</span></span>  
 <span data-ttu-id="a1051-112">UTC <xref:System.DateTime> 인스턴스는 UTC임을 나타내는 방식으로 형식이 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-112">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="a1051-113">‘Z’를 사용하여 UTC 시간을 나타내기 위한 권장 형식:</span><span class="sxs-lookup"><span data-stu-id="a1051-113">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="a1051-114">인스턴스가 로컬, UTC 또는 미지정인지 여부에 관계없이 올바르게 직렬화되는 <xref:System.DateTime.Kind%2A> 속성을 사용하여 <xref:System.DateTime>을 직렬화하는 “o” 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-114">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a1051-115">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="a1051-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="a1051-116">이 MDA는 런타임에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-116">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a1051-117">출력</span><span class="sxs-lookup"><span data-stu-id="a1051-117">Output</span></span>  
 <span data-ttu-id="a1051-118">이 MDA 활성화로 인한 특별한 출력은 없습니다. 그러나 호출 스택을 사용하여 MDA를 활성화한 <xref:System.DateTime.ToString%2A> 호출의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-118">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a1051-119">구성</span><span class="sxs-lookup"><span data-stu-id="a1051-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="a1051-120">예제</span><span class="sxs-lookup"><span data-stu-id="a1051-120">Example</span></span>  
 <span data-ttu-id="a1051-121">다음 방식으로 <xref:System.Xml.XmlConvert> 또는 <xref:System.Data.DataSet>을 사용하여 UTC <xref:System.DateTime> 값을 간접적으로 직렬화하고 있는 응용 프로그램을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a1051-121">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="a1051-122"><xref:System.Xml.XmlConvert> 및 <xref:System.Data.DataSet> serialization은 기본적으로 serialization에 로컬 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-122">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="a1051-123">UTC와 같은 다른 종류의 <xref:System.DateTime> 값을 직렬화하려면 추가 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-123">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="a1051-124">이 특정 예제에서는 `XmlDateTimeSerializationMode.RoundtripKind`를 `XmlConvert`의 `ToString` 호출에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-124">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="a1051-125">이렇게 하면 데이터가 UTC 시간으로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-125">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="a1051-126"><xref:System.Data.DataSet>을 사용할 경우 <xref:System.Data.DataColumn>의 <xref:System.Data.DataColumn.DateTimeMode%2A> 속성을 <xref:System.Data.DataSetDateTime.Utc>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1051-126">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1051-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1051-127">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="a1051-128">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="a1051-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
