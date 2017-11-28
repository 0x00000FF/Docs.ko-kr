---
title: ".NET Core CLI 도구 원격 분석"
description: "어떤 데이터가 수집되고 수집 기능을 사용하지 않도록 설정하는 방법에 대한 분석을 위해 사용 정보를 수집하는 .NET Core 도구 원격 분석 기능을 살펴봅니다."
keywords: ".NET, .NET Core, 원격 분석"
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.openlocfilehash: 34183792a235391f66fbec211ff00f06f85134fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="70377-104">.NET Core CLI 도구 원격 분석</span><span class="sxs-lookup"><span data-stu-id="70377-104">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="70377-105">[.NET Core SDK](index.md)에는 사용 정보를 수집하는 [원격 분석 기능](https://github.com/dotnet/cli/pull/2145)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-105">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="70377-106">.NET 팀이 개선을 위해 도구 사용 방법을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-106">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="70377-107">자세한 내용은 [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)(.NET Core SDK 원격 분석에서 배운 내용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70377-107">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="70377-108">수집된 데이터는 익명이며 Microsoft 및 커뮤니티에서 사용할 집계 형식으로 [Creative Commons Attribution 라이선스](https://creativecommons.org/licenses/by/4.0/)에 따라 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-108">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="70377-109">범위</span><span class="sxs-lookup"><span data-stu-id="70377-109">Scope</span></span>

<span data-ttu-id="70377-110">`dotnet` 명령은 앱 및 .NET Core CLI를 시작하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-110">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="70377-111">`dotnet` 명령 자체는 원격 분석을 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-111">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="70377-112">`dotnet` 명령에 따라 실행되는 .NET Core CLI 명령은 원격 분석을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-112">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="70377-113">연결된 명령 없이 `dotnet` 명령만 사용할 경우 원격 분석을 *사용할 수 없습니다*.</span><span class="sxs-lookup"><span data-stu-id="70377-113">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="70377-114">다음과 같은 [.NET Core CLI 명령](index.md)을 사용할 경우 원격 분석을 *사용할 수 있습니다*.</span><span class="sxs-lookup"><span data-stu-id="70377-114">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="70377-115">동작</span><span class="sxs-lookup"><span data-stu-id="70377-115">Behavior</span></span>

<span data-ttu-id="70377-116">.NET Core CLI 도구 원격 분석 기능은 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-116">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="70377-117">`DOTNET_CLI_TELEMETRY_OPTOUT` 환경 변수를 `1` 또는 `true`로 설정하여 원격 분석 기능을 옵트아웃(opt out)합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-117">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="70377-118">데이터 요소</span><span class="sxs-lookup"><span data-stu-id="70377-118">Data points</span></span>

<span data-ttu-id="70377-119">이 기능은 다음 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-119">The feature collects the following data:</span></span>

- <span data-ttu-id="70377-120">호출의 타임스탬프&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-120">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="70377-121">호출된 명령(예: “build”)&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-121">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="70377-122">지리적 위치를 확인하는 데 사용되는 8진수 IP 주소 3개&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-122">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="70377-123">명령의 `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="70377-123">`ExitCode` of the command</span></span>
- <span data-ttu-id="70377-124">Test Runner(테스트 프로젝트의 경우)</span><span class="sxs-lookup"><span data-stu-id="70377-124">Test runner (for test projects)</span></span>
- <span data-ttu-id="70377-125">운영 체제 및 버전&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-125">Operating system and version&#8224;</span></span>
- <span data-ttu-id="70377-126">런타임 ID가 런타임 노드에 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="70377-126">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="70377-127">.NET Core SDK 버전&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-127">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="70377-128">&#8224;이 메트릭은 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-128">&#8224;This metric is published.</span></span>

<span data-ttu-id="70377-129">.NET Core SDK 2.0부터 새 데이터 요소가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-129">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="70377-130">`dotnet` 명령 인수 및 옵션: 알려진 인수 및 옵션만 수집됩니다(임의 문자열이 아님).</span><span class="sxs-lookup"><span data-stu-id="70377-130">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="70377-131">SDK가 컨테이너에서 실행 중인지 여부.</span><span class="sxs-lookup"><span data-stu-id="70377-131">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="70377-132">대상 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="70377-132">Target frameworks.</span></span>
- <span data-ttu-id="70377-133">해시된 MAC 주소: 컴퓨터에 대한 암호화된(SHA256) 익명 및 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-133">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="70377-134">이 메트릭은 게시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-134">This metric is not published.</span></span>
- <span data-ttu-id="70377-135">해시된 현재 작업 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="70377-135">Hashed current working directory.</span></span>

<span data-ttu-id="70377-136">이 기능은 사용자 이름이나 전자 메일 주소 등의 개인 데이터를 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-136">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="70377-137">코드를 검사하지 않고 이름, 리포지토리 또는 작성자와 같은 중요한 프로젝트 수준 데이터를 추출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-137">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="70377-138">데이터는 [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 기술을 사용하여 Microsoft 서버로 안전하게 전송되고, 제한된 액세스를 기준으로 보관되고, 안전한 [Azure Storage](https://azure.microsoft.com/services/storage/) 시스템에서 엄격한 보안 제어에 따라 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-138">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="70377-139">도구를 사용하여 무엇을 빌드하는지가 아니라 도구 사용 방법과 도구가 제대로 작동하는지 알고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-139">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="70377-140">원격 분석이 중요한 데이터를 수집하고 있는지 또는 데이터가 안전하지 않거나 부적절한 방식으로 처리되고 있는지 의심스러운 경우 조사를 위해 [dotnet/cli 리포지토리 문제에서 문제를 보고](https://github.com/dotnet/cli/issues)하세요.</span><span class="sxs-lookup"><span data-stu-id="70377-140">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="70377-141">게시된 데이터</span><span class="sxs-lookup"><span data-stu-id="70377-141">Published data</span></span>

<span data-ttu-id="70377-142">게시된 데이터는 분기별로 제공되고 [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)(.NET Core SDK 사용 데이터)에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-142">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="70377-143">데이터 파일 열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-143">The columns of a data file are:</span></span>
- <span data-ttu-id="70377-144">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="70377-144">Timestamp</span></span>
- <span data-ttu-id="70377-145">발생&#8224;</span><span class="sxs-lookup"><span data-stu-id="70377-145">Occurrences&#8224;</span></span>
- <span data-ttu-id="70377-146">명령</span><span class="sxs-lookup"><span data-stu-id="70377-146">Command</span></span>
- <span data-ttu-id="70377-147">지리&#8225;</span><span class="sxs-lookup"><span data-stu-id="70377-147">Geography&#8225;</span></span>
- <span data-ttu-id="70377-148">OSFamily</span><span class="sxs-lookup"><span data-stu-id="70377-148">OSFamily</span></span>
- <span data-ttu-id="70377-149">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="70377-149">RuntimeID</span></span>
- <span data-ttu-id="70377-150">OSVersion</span><span class="sxs-lookup"><span data-stu-id="70377-150">OSVersion</span></span>
- <span data-ttu-id="70377-151">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="70377-151">SDKVersion</span></span>

<span data-ttu-id="70377-152">&#8224;*발생* 열에는 해당 날짜에 해당 행 메트릭에 대한 해당 명령 사용의 집계 개수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-152">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="70377-153">&#8225;일반적으로 *지리* 열에는 국가 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-153">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="70377-154">경우에 따라 연구원이 남극에서 .NET Core를 사용하거나 위치 데이터가 정확하지 않아 남극 대륙이 이 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-154">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="70377-155">예제</span><span class="sxs-lookup"><span data-stu-id="70377-155">Example</span></span>

| <span data-ttu-id="70377-156">타임스탬프</span><span class="sxs-lookup"><span data-stu-id="70377-156">Timestamp</span></span>      | <span data-ttu-id="70377-157">발생</span><span class="sxs-lookup"><span data-stu-id="70377-157">Occurrences</span></span> | <span data-ttu-id="70377-158">명령</span><span class="sxs-lookup"><span data-stu-id="70377-158">Command</span></span> | <span data-ttu-id="70377-159">지리</span><span class="sxs-lookup"><span data-stu-id="70377-159">Geography</span></span> | <span data-ttu-id="70377-160">OSFamily</span><span class="sxs-lookup"><span data-stu-id="70377-160">OSFamily</span></span> | <span data-ttu-id="70377-161">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="70377-161">RuntimeID</span></span>     | <span data-ttu-id="70377-162">OSVersion</span><span class="sxs-lookup"><span data-stu-id="70377-162">OSVersion</span></span> | <span data-ttu-id="70377-163">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="70377-163">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="70377-164">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="70377-164">4/16/2017 0:00</span></span> | <span data-ttu-id="70377-165">9</span><span class="sxs-lookup"><span data-stu-id="70377-165">8</span></span>           | <span data-ttu-id="70377-166">실행</span><span class="sxs-lookup"><span data-stu-id="70377-166">run</span></span>     | <span data-ttu-id="70377-167">우간다</span><span class="sxs-lookup"><span data-stu-id="70377-167">Uganda</span></span>    | <span data-ttu-id="70377-168">Darwin</span><span class="sxs-lookup"><span data-stu-id="70377-168">Darwin</span></span>   | <span data-ttu-id="70377-169">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="70377-169">osx.10.12-x64</span></span> | <span data-ttu-id="70377-170">10.12</span><span class="sxs-lookup"><span data-stu-id="70377-170">10.12</span></span>     | <span data-ttu-id="70377-171">1.0.1</span><span class="sxs-lookup"><span data-stu-id="70377-171">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="70377-172">데이터 집합</span><span class="sxs-lookup"><span data-stu-id="70377-172">Datasets</span></span>

[<span data-ttu-id="70377-173">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="70377-173">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="70377-174">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="70377-174">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="70377-175">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="70377-175">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="70377-176">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="70377-176">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="70377-177">표준 URL 형식을 사용하여 추가 데이터 집합이 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-177">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="70377-178">`<YEAR>`를 연도로 바꾸고 `<QUARTER>`를 해당 연도의 분기로 바꿉니다(`1`, `2`, `3` 또는 `4` 사용).</span><span class="sxs-lookup"><span data-stu-id="70377-178">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="70377-179">파일은 *TSV*(탭으로 구분된 값) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-179">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="70377-180">라이선스</span><span class="sxs-lookup"><span data-stu-id="70377-180">License</span></span>

<span data-ttu-id="70377-181">.NET Core의 Microsoft 배포는 [MICROSOFT.NET 라이브러리 EULA](https://aka.ms/dotnet-core-eula)로 허가됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-181">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="70377-182">이 라이선스에는 원격 분석을 구현하기 위한 “DATA” 섹션이 포함됩니다(아래 참조).</span><span class="sxs-lookup"><span data-stu-id="70377-182">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="70377-183">[.NET NuGet 패키지](https://www.nuget.org/profiles/dotnetframework)에는 동일한 라이선스가 사용되지만 원격 분석을 구현하지 않습니다([범위](#scope) 참조).</span><span class="sxs-lookup"><span data-stu-id="70377-183">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="70377-184">데이터.</span><span class="sxs-lookup"><span data-stu-id="70377-184">DATA.</span></span> <span data-ttu-id="70377-185">소프트웨어에서 사용자 및 사용자의 소프트웨어 사용에 대한 정보를 수집하고 이 정보를 Microsoft에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-185">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="70377-186">Microsoft에서는 제품 및 서비스 향상을 위해 이 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-186">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="70377-187">데이터 수집 및 사용에 대한 자세한 내용은 도움말 문서 및 개인정보처리방침(http://go.microsoft.com/fwlink/?LinkId=528096)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70377-187">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="70377-188">소프트웨어를 사용하려면 이러한 사례에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-188">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="70377-189">공개</span><span class="sxs-lookup"><span data-stu-id="70377-189">Disclosure</span></span>

<span data-ttu-id="70377-190">사용자가 명령 중 하나를 처음 실행하면(예: `dotnet restore`) .NET Core CLI 도구에 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-190">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="70377-191">실행 중인 SDK 버전에 따라 텍스트가 약간 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-191">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="70377-192">이 "첫 실행" 경험이 Microsoft가 사용자에게 데이터 수집에 대해 알리는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-192">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="70377-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70377-193">See also</span></span>

<span data-ttu-id="70377-194">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)(.NET Core SDK 원격 분석에서 배운 내용)</span><span class="sxs-lookup"><span data-stu-id="70377-194">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)</span></span>  
<span data-ttu-id="70377-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) (원격 분석 참조 소스(dotnet/cli 리포지토리, 릴리스/2.0.0 분기))</span><span class="sxs-lookup"><span data-stu-id="70377-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span></span>  
<span data-ttu-id="70377-196">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)(.NET Core SDK 사용 데이터)</span><span class="sxs-lookup"><span data-stu-id="70377-196">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)</span></span>
