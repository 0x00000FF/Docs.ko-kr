---
title: 날짜 및 시간 데이터
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: a4bbed1f115ef5cfb6b7b63156f2d84b071cf224
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127116"
---
# <a name="date-and-time-data"></a><span data-ttu-id="454c5-102">날짜 및 시간 데이터</span><span class="sxs-lookup"><span data-stu-id="454c5-102">Date and Time Data</span></span>
<span data-ttu-id="454c5-103">SQL Server 2008에서는 날짜 및 시간 정보를 처리하기 위한 새로운 데이터 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-103">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="454c5-104">새로운 데이터 형식에는 개별 날짜 형식과 시간 형식을 비롯하여 보다 큰 범위의 확장된 데이터 형식, 정밀도 및 표준 시간대 인식 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-104">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="454c5-105">.NET Framework 버전 3.5 SP(서비스 팩) 1부터는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)에 SQL Server 2008 데이터베이스 엔진의 새로운 모든 기능이 완벽하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-105">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="454c5-106">SqlClient에서 이러한 새 기능을 사용하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-106">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="454c5-107">SQL Server 2008 이전의 SQL Server 버전에서는 날짜 및 시간 값으로 작업할 때 `datetime` 및 `smalldatetime`의 두 가지 데이터 형식만 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-107">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="454c5-108">두 데이터 형식 모두 날짜 값과 시간 값을 모두 포함하므로 날짜나 시간 값만 가지고 작업하기 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-108">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="454c5-109">또한 이들 데이터 형식은 1753년 영국에 양력이 도입된 이후의 날짜만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-109">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="454c5-110">이와 같은 이전 데이터 형식은 표준 시간대를 고려하지 않으므로 여러 표준 시간대에서 발생하는 데이터를 처리하기도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-110">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="454c5-111">SQL Server 데이터 형식에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="454c5-111">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="454c5-112">다음 표에서는 날짜 및 시간 데이터에 대한 초급 수준의 항목을 버전별로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-112">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 **<span data-ttu-id="454c5-113">SQL Server 온라인 설명서</span><span class="sxs-lookup"><span data-stu-id="454c5-113">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="454c5-114">날짜 및 시간 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="454c5-114">Using Date and Time Data</span></span>](https://go.microsoft.com/fwlink/?LinkID=98361)  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="454c5-115">SQL Server 2008에 도입된 날짜/시간 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-115">Date/Time Data Types Introduced in SQL Server 2008</span></span>  
 <span data-ttu-id="454c5-116">다음 표에서는 새로운 날짜 및 시간 데이터 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-116">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="454c5-117">SQL Server 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-117">SQL Server data type</span></span>|<span data-ttu-id="454c5-118">설명</span><span class="sxs-lookup"><span data-stu-id="454c5-118">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="454c5-119">`date` 데이터 형식은 하루 단위이며 범위는 01년 1월 1일부터 9999년 12월 31일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-119">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="454c5-120">기본값은 1900년 1월 1일입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-120">The default value is January 1, 1900.</span></span> <span data-ttu-id="454c5-121">이 데이터 형식의 저장소 크기는 3바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-121">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="454c5-122">`time` 데이터 형식은 24시간제를 기준으로 시간 값만 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-122">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="454c5-123">`time` 데이터 형식은 100나노초 단위이며 범위는 00:00:00.0000000부터 23:59:59.9999999까지입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-123">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="454c5-124">기본값은 00:00:00.0000000(자정)입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-124">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="454c5-125">`time` 데이터 형식은 초에 대해 소수로 표현되는 사용자 정의 정밀도를 지원하며 지정된 정밀도에 따라 저장소 크기는 3바이트에서 6바이트까지의 범위 내에서 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-125">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="454c5-126">`datetime2` 데이터 형식은 `date` 및 `time` 데이터 형식의 범위와 정밀도를 하나의 데이터 형식으로 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-126">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="454c5-127">이 형식의 기본값과 문자열 리터럴 형식은 `date` 및 `time` 데이터 형식에 정의된 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-127">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="454c5-128">`datetimeoffset` 데이터 형식은 `datetime2`의 모든 기능을 포함하며 표준 시간대 오프셋 기능을 추가로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-128">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="454c5-129">표준 시간대 오프셋으로 표시 됩니다 [+&#124;-] hh: mm입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-129">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="454c5-130">HH는 00부터 14까지의 두 자리 숫자로, 표준 시간대 오프셋의 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-130">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="454c5-131">MM은 00부터 59까지의 두 자리 숫자로, 표준 시간대 오프셋의 분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-131">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="454c5-132">시간 형식은 100나노초까지 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-132">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="454c5-133">필수 값인 + 또는 - 부호는 현지 시간을 얻기 위해 표준 시간대 오프셋을 UTC(Universal Time Coordinate 또는 그리니치 표준시)에 더할 것인지 또는 UTC에서 뺄 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-133">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="454c5-134">`Type System Version` 키워드 사용에 대한 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="454c5-134">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="454c5-135">날짜 형식 및 날짜 순서</span><span class="sxs-lookup"><span data-stu-id="454c5-135">Date Format and Date Order</span></span>  
 <span data-ttu-id="454c5-136">SQL Server에서 날짜 및 시간 값을 구문 분석하는 방법은 형식 시스템 버전과 서버 버전뿐만 아니라 서버의 기본 언어 설정과 형식 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-136">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="454c5-137">특정 언어의 날짜 형식에 사용할 수 있는 날짜 문자열이라도 다른 언어와 날짜 형식 설정을 사용하는 연결에서 쿼리를 실행할 경우 인식되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-137">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="454c5-138">Transact-SQL SET LANGUAGE 문은 날짜 부분의 순서를 결정하는 DATEFORMAT을 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-138">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="454c5-139">연결에 SET DATEFORMAT Transact-SQL 문을 사용하면 날짜 부분을 MDY, DMY, YMD, YDM, MYD 또는 DYM 순서로 정렬하여 날짜 값을 명확하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-139">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="454c5-140">연결에 DATEFORMAT을 지정하지 않으면 SQL Server에서는 연결과 관련된 기본 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-140">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="454c5-141">예를 들어 '01/02/03'의 경우 언어가 영어(미국)로 설정된 서버에서는 MDY(January 2, 2003)로 해석되고 언어가 영어(영국)로 설정된 서버에서는 DMY(February 1, 2003)로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-141">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="454c5-142">연도는 세기 값의 구분 기준 날짜를 정의하는 SQL Server의 연도 구분 규칙을 사용하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-142">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="454c5-143">자세한 내용은 [two digit year cutoff 옵션](https://go.microsoft.com/fwlink/?LinkId=120473) SQL Server 온라인 설명서의 합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-143">For more information, see [two digit year cutoff Option](https://go.microsoft.com/fwlink/?LinkId=120473) in SQL Server Books Online.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="454c5-144">YDM 날짜 형식은 문자열 형식에서 `date`, `time`, `datetime2` 또는 `datetimeoffset`으로 변환할 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-144">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="454c5-145">SQL Server에서 날짜 및 시간 데이터를 해석 하는 방법에 대 한 자세한 내용은 참조 하세요. [날짜 및 시간 데이터 사용](https://go.microsoft.com/fwlink/?LinkID=98361) SQL Server 2008 Books Online에서.</span><span class="sxs-lookup"><span data-stu-id="454c5-145">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](https://go.microsoft.com/fwlink/?LinkID=98361) in SQL Server 2008 Books Online.</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="454c5-146">날짜/시간 데이터 형식 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="454c5-146">Date/Time Data Types and Parameters</span></span>  
 <span data-ttu-id="454c5-147">새 날짜 및 시간 데이터 형식을 지원하기 위해 다음 열거형이 <xref:System.Data.SqlDbType>에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-147">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
-   `SqlDbType.Date`  
  
-   `SqlDbType.Time`  
  
-   `SqlDbType.DateTime2`  
  
-   `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="454c5-148">데이터 형식을 지정할 수 있습니다는 <xref:System.Data.SqlClient.SqlParameter> 위의 중 하나를 사용 하 여 <xref:System.Data.SqlDbType> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-148">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span> 

> [!NOTE]
> <span data-ttu-id="454c5-149">설정할 수 없습니다는 `DbType` 의 속성을 `SqlParameter` 에 `SqlDbType.Date`입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-149">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="454c5-150">또한 <xref:System.Data.SqlClient.SqlParameter> 개체의 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 속성을 특정 `SqlParameter` 열거형 값으로 설정하면 일반적인 방식으로 <xref:System.Data.DbType>의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-150">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="454c5-151"><xref:System.Data.DbType> 및 `datetime2` 데이터 형식을 지원하기 위해 다음 열거형 값이 `datetimeoffset`에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-151">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
-   <span data-ttu-id="454c5-152">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="454c5-152">DbType.DateTime2</span></span>  
  
-   <span data-ttu-id="454c5-153">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-153">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="454c5-154">이러한 새 열거형은 이전 버전의 .NET Framework에서 사용할 수 있는 `Date`, `Time` 및 `DateTime` 열거형을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-154">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="454c5-155">매개 변수 개체의 .NET Framework 데이터 공급자 형식은 매개 변수 개체 값의 .NET Framework 형식이나 매개 변수 개체의 `DbType`에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-155">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="454c5-156">새 날짜 및 시간 데이터 형식을 지원하기 위해 도입된 새 <xref:System.Data.SqlTypes> 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-156">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="454c5-157">다음 표에서는 SQL Server 2008 날짜 및 시간 데이터 형식과 CLR 데이터 형식 간의 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-157">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="454c5-158">SQL Server 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-158">SQL Server data type</span></span>|<span data-ttu-id="454c5-159">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-159">.NET Framework type</span></span>|<span data-ttu-id="454c5-160">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="454c5-160">System.Data.SqlDbType</span></span>|<span data-ttu-id="454c5-161">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="454c5-161">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="454c5-162">date</span><span class="sxs-lookup"><span data-stu-id="454c5-162">date</span></span>|<span data-ttu-id="454c5-163">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-163">System.DateTime</span></span>|<span data-ttu-id="454c5-164">날짜</span><span class="sxs-lookup"><span data-stu-id="454c5-164">Date</span></span>|<span data-ttu-id="454c5-165">날짜</span><span class="sxs-lookup"><span data-stu-id="454c5-165">Date</span></span>|  
|<span data-ttu-id="454c5-166">시간</span><span class="sxs-lookup"><span data-stu-id="454c5-166">time</span></span>|<span data-ttu-id="454c5-167">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="454c5-167">System.TimeSpan</span></span>|<span data-ttu-id="454c5-168">시간</span><span class="sxs-lookup"><span data-stu-id="454c5-168">Time</span></span>|<span data-ttu-id="454c5-169">시간</span><span class="sxs-lookup"><span data-stu-id="454c5-169">Time</span></span>|  
|<span data-ttu-id="454c5-170">datetime2</span><span class="sxs-lookup"><span data-stu-id="454c5-170">datetime2</span></span>|<span data-ttu-id="454c5-171">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-171">System.DateTime</span></span>|<span data-ttu-id="454c5-172">DateTime2</span><span class="sxs-lookup"><span data-stu-id="454c5-172">DateTime2</span></span>|<span data-ttu-id="454c5-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="454c5-173">DateTime2</span></span>|  
|<span data-ttu-id="454c5-174">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="454c5-174">datetimeoffset</span></span>|<span data-ttu-id="454c5-175">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-175">System.DateTimeOffset</span></span>|<span data-ttu-id="454c5-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-176">DateTimeOffset</span></span>|<span data-ttu-id="454c5-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-177">DateTimeOffset</span></span>|  
|<span data-ttu-id="454c5-178">datetime</span><span class="sxs-lookup"><span data-stu-id="454c5-178">datetime</span></span>|<span data-ttu-id="454c5-179">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-179">System.DateTime</span></span>|<span data-ttu-id="454c5-180">DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-180">DateTime</span></span>|<span data-ttu-id="454c5-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-181">DateTime</span></span>|  
|<span data-ttu-id="454c5-182">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="454c5-182">smalldatetime</span></span>|<span data-ttu-id="454c5-183">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-183">System.DateTime</span></span>|<span data-ttu-id="454c5-184">DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-184">DateTime</span></span>|<span data-ttu-id="454c5-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-185">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="454c5-186">SqlParameter 속성</span><span class="sxs-lookup"><span data-stu-id="454c5-186">SqlParameter Properties</span></span>  
 <span data-ttu-id="454c5-187">다음 표에서는 날짜 및 시간 데이터 형식과 관련된 `SqlParameter` 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-187">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="454c5-188">속성</span><span class="sxs-lookup"><span data-stu-id="454c5-188">Property</span></span>|<span data-ttu-id="454c5-189">설명</span><span class="sxs-lookup"><span data-stu-id="454c5-189">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="454c5-190">값이 nullable인지 여부를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-190">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="454c5-191">서버에 null 매개 변수 값을 보낼 때는 <xref:System.DBNull>(Visual Basic에서는 `null`)이 아니라 `Nothing`을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-191">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="454c5-192">데이터베이스 null에 대한 자세한 내용은 [Handling Null Values](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="454c5-192">For more information about database nulls, see [Handling Null Values](../../../../../docs/framework/data/adonet/sql/handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="454c5-193">값을 나타내는 데 사용되는 최대 자릿수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-193">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="454c5-194">날짜 및 시간 데이터 형식에서는 이 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-194">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="454c5-195">값의 시간 부분에 대 한 확인 되는 소수 자릿수를 가져오거나 설정 합니다. `Time`하십시오 `DateTime2`, 및 `DateTimeOffset`합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-195">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="454c5-196">기본값은 0이며 이는 값에서 실제 자릿수가 유추되어 서버에 전송됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-196">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="454c5-197">날짜 및 시간 데이터 형식에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-197">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="454c5-198">매개 변수 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-198">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="454c5-199">매개 변수 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-199">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="454c5-200">시간 값이 0보다 작거나 24시간보다 크면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-200">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="454c5-201">매개 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="454c5-201">Creating Parameters</span></span>  
 <span data-ttu-id="454c5-202">만들 수 있습니다를 <xref:System.Data.SqlClient.SqlParameter> 해당 생성자를 사용 하 여 또는 추가 하 여 개체를 <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> 호출 하 여 컬렉션의 `Add` 메서드의 <xref:System.Data.SqlClient.SqlParameterCollection>.</span><span class="sxs-lookup"><span data-stu-id="454c5-202">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="454c5-203">`Add` 메서드는 생성자 인수 또는 기존 매개 변수 개체를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-203">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="454c5-204">이 항목의 다음 섹션에서는 날짜 및 시간 매개 변수를 지정하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-204">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="454c5-205">매개 변수를 사용 하 여 작업의 추가 예제를 참조 하세요 [구성 매개 변수 및 매개 변수 데이터 형식](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md) 하 고 [DataAdapter 매개 변수](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-205">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../../../../../docs/framework/data/adonet/dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="454c5-206">Date 예제</span><span class="sxs-lookup"><span data-stu-id="454c5-206">Date Example</span></span>  
 <span data-ttu-id="454c5-207">다음 코드 조각에서는 `date` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-207">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="454c5-208">Time 예제</span><span class="sxs-lookup"><span data-stu-id="454c5-208">Time Example</span></span>  
 <span data-ttu-id="454c5-209">다음 코드 조각에서는 `time` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-209">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="454c5-210">Datetime2 예제</span><span class="sxs-lookup"><span data-stu-id="454c5-210">Datetime2 Example</span></span>  
 <span data-ttu-id="454c5-211">다음 코드 조각에서는 날짜 부분과 시간 부분이 모두 포함된 `datetime2` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-211">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="454c5-212">DateTimeOffSet 예제</span><span class="sxs-lookup"><span data-stu-id="454c5-212">DateTimeOffSet Example</span></span>  
 <span data-ttu-id="454c5-213">다음 코드 예제에서는 날짜, 시간 및 표준 시간대 오프셋이 0으로 설정된 `DateTimeOffSet` 매개 변수를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-213">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="454c5-214">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="454c5-214">AddWithValue</span></span>  
 <span data-ttu-id="454c5-215">다음 코드 조각에서 볼 수 있는 것처럼 `AddWithValue`의 <xref:System.Data.SqlClient.SqlCommand> 메서드를 사용하여 매개 변수를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-215">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="454c5-216">그러나 `AddWithValue` 메서드를 사용할 경우 매개 변수에 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 또는 <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-216">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="454c5-217">합니다 `@date` 매개 변수를 매핑할 수는 `date`, `datetime`, 또는 `datetime2` 서버에서 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-217">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="454c5-218">새 `datetime` 데이터 형식을 사용할 때는 인스턴스의 데이터 형식을 매개 변수의 <xref:System.Data.SqlDbType> 속성에 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-218">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="454c5-219"><xref:System.Data.SqlDbType.Variant>를 사용하거나 암시적으로 매개 변수 값을 제공할 경우 `datetime` 및 `smalldatetime` 데이터 형식에 대한 이전 버전과의 호환성에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-219">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="454c5-220">다음 표에서는 각 CLR 형식에서 유추되는 `SqlDbTypes`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-220">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="454c5-221">CLR 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-221">CLR type</span></span>|<span data-ttu-id="454c5-222">유추되는 SqlDbType</span><span class="sxs-lookup"><span data-stu-id="454c5-222">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="454c5-223">DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-223">DateTime</span></span>|<span data-ttu-id="454c5-224">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="454c5-224">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="454c5-225">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="454c5-225">TimeSpan</span></span>|<span data-ttu-id="454c5-226">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="454c5-226">SqlDbType.Time</span></span>|  
|<span data-ttu-id="454c5-227">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-227">DateTimeOffset</span></span>|<span data-ttu-id="454c5-228">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="454c5-228">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="454c5-229">날짜 및 시간 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="454c5-229">Retrieving Date and Time Data</span></span>  
 <span data-ttu-id="454c5-230">다음 표에서는 SQL Server 2008 날짜 및 시간 값을 검색하는 데 사용되는 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-230">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="454c5-231">SqlClient 메서드</span><span class="sxs-lookup"><span data-stu-id="454c5-231">SqlClient method</span></span>|<span data-ttu-id="454c5-232">설명</span><span class="sxs-lookup"><span data-stu-id="454c5-232">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="454c5-233">지정된 열 값을 <xref:System.DateTime> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-233">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="454c5-234">지정된 열 값을 <xref:System.DateTimeOffset> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-234">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="454c5-235">필드의 기본 공급자별 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-235">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="454c5-236">새 날짜 및 시간 형식의 경우 `GetFieldType`과 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-236">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="454c5-237">지정된 열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-237">Retrieves the value of the specified column.</span></span> <span data-ttu-id="454c5-238">새 날짜 및 시간 형식의 경우 `GetValue`와 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-238">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="454c5-239">지정된 배열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-239">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="454c5-240">열 값을 <xref:System.Data.SqlTypes.SqlString>으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-240">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="454c5-241">데이터를 <xref:System.InvalidCastException>으로 표현할 수 없으면 `SqlString`이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-241">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="454c5-242">열 데이터를 해당 기본 `SqlDbType`으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-242">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="454c5-243">새 날짜 및 시간 형식의 경우 `GetValue`와 동일한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-243">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="454c5-244">지정된 배열의 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-244">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="454c5-245">Type System Version이 SQL Server 2005로 설정되어 있는 경우 열 값을 문자열로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-245">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="454c5-246">데이터를 문자열로 표현할 수 없으면 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-246">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="454c5-247">지정된 열 값을 <xref:System.TimeSpan> 구조체로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-247">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="454c5-248">지정된 열 값을 기본 CLR 형식으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-248">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="454c5-249">배열의 열 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-249">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="454c5-250">결과 집합의 메타데이터를 설명하는 <xref:System.Data.DataTable>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-250">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="454c5-251">SQL Server에서 in-process로 실행되는 코드에는 새 날짜 및 시간 `SqlDbTypes`이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-251">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="454c5-252">이러한 형식 중 하나를 서버에 전달하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-252">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="454c5-253">날짜 및 시간 값을 리터럴로 지정</span><span class="sxs-lookup"><span data-stu-id="454c5-253">Specifying Date and Time Values as Literals</span></span>  
 <span data-ttu-id="454c5-254">여러 가지 리터럴 문자열 형식을 사용하여 날짜 및 시간 데이터 형식을 지정할 수 있습니다. 이렇게 하면 SQL Server에서는 이러한 리터럴 문자열 형식을 런타임에 평가하여 내부 날짜/시간 구조체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-254">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="454c5-255">SQL Server에서는 작은따옴표(')로 묶인 날짜 및 시간 데이터를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-255">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="454c5-256">다음 예제에서는 몇 가지 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-256">The following examples demonstrate some formats:</span></span>  
  
-   <span data-ttu-id="454c5-257">`'October 15, 2006'`과 같은 알파벳 날짜 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-257">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
-   <span data-ttu-id="454c5-258">`'10/15/2006'`과 같은 숫자 날짜 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-258">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
-   <span data-ttu-id="454c5-259">`'20061015'`(ISO 표준 날짜 형식을 사용할 경우 2006년 10월 15일로 해석됨)와 같은 구분되지 않은 문자열 형식</span><span class="sxs-lookup"><span data-stu-id="454c5-259">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="454c5-260">날짜 및 시간 데이터 형식의 모든 리터럴 문자열 형식 및 기타 기능에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="454c5-260">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="454c5-261">시간 값이 0보다 작거나 24시간보다 크면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-261">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-2008-books-online"></a><span data-ttu-id="454c5-262">SQL Server 2008 온라인 설명서 리소스</span><span class="sxs-lookup"><span data-stu-id="454c5-262">Resources in SQL Server 2008 Books Online</span></span>  
 <span data-ttu-id="454c5-263">SQL Server 2008에서의 날짜 및 시간 값 사용 방법은 SQL Server 2008 온라인 설명서의 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="454c5-263">For more information about working with date and time values in SQL Server 2008, see the following resources in SQL Server 2008 Books Online.</span></span>  
  
|<span data-ttu-id="454c5-264">항목</span><span class="sxs-lookup"><span data-stu-id="454c5-264">Topic</span></span>|<span data-ttu-id="454c5-265">설명</span><span class="sxs-lookup"><span data-stu-id="454c5-265">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="454c5-266">날짜 및 시간 데이터 형식 및 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="454c5-266">Date and Time Data Types and Functions (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=98360)|<span data-ttu-id="454c5-267">모든 Transact-SQL 날짜 및 시간 데이터 형식 및 함수에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-267">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|[<span data-ttu-id="454c5-268">날짜 및 시간 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="454c5-268">Using Date and Time Data</span></span>](https://go.microsoft.com/fwlink/?LinkId=98361)|<span data-ttu-id="454c5-269">날짜 및 시간 데이터 형식과 함수를 비롯하여 이러한 데이터 형식의 사용 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-269">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="454c5-270">데이터 형식(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="454c5-270">Data Types (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=98362)|<span data-ttu-id="454c5-271">SQL Server 2008에 제공되는 시스템 데이터 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="454c5-271">Describes system data types in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="454c5-272">참고자료</span><span class="sxs-lookup"><span data-stu-id="454c5-272">See also</span></span>

- [<span data-ttu-id="454c5-273">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="454c5-273">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="454c5-274">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="454c5-274">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="454c5-275">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="454c5-275">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="454c5-276">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="454c5-276">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
