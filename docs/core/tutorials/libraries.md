---
title: "플랫폼 간 도구로 라이브러리 개발"
description: ".NET Core CLI 도구를 사용하여 .NET용 라이브러리를 만드는 방법에 관해 알아봅니다."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 05/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 9f6e8679-bd7e-4317-b3f9-7255a260d9cf
ms.openlocfilehash: 21f8a4f4862cabd21ab9017056f3f71706e8e9a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="developing-libraries-with-cross-platform-tools"></a><span data-ttu-id="c75ad-104">플랫폼 간 도구로 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="c75ad-104">Developing Libraries with Cross Platform Tools</span></span>

<span data-ttu-id="c75ad-105">이 문서에서는 플랫폼 간 CLI 도구를 사용하여 .NET용 라이브러리를 작성하는 방법을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-105">This article covers how to write libraries for .NET using cross-platform CLI tools.</span></span> <span data-ttu-id="c75ad-106">CLI는 지원되는 운영 체제에서 작동하는 효율적인 하위 수준 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="c75ad-107">Visual Studio로 라이브러리를 빌드할 수 있습니다. 그러한 환경을 선호하는 경우 [Visual Studio 설명서를 참조하세요](libraries-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c75ad-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](libraries-with-vs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c75ad-108">필수 조건</span><span class="sxs-lookup"><span data-stu-id="c75ad-108">Prerequisites</span></span>

<span data-ttu-id="c75ad-109">컴퓨터에 [.NET Core SDK 및 CLI](https://www.microsoft.com/net/core)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-109">You need [the .NET Core SDK and CLI](https://www.microsoft.com/net/core) installed on your machine.</span></span>

<span data-ttu-id="c75ad-110">.NET Framework 버전을 다루는 이 문서의 섹션에서는 [.NET Framework](http://getdotnet.azurewebsites.net/)가 설치된 Windows 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](http://getdotnet.azurewebsites.net/) installed on a Windows machine.</span></span>

<span data-ttu-id="c75ad-111">또한 이전.NET Framework 대상을 지원하려는 경우 [.NET 대상 플랫폼 페이지](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html)에서 이전 프레임워크 버전용 타기팅/개발자 팩을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting/developer packs for older framework versions from the [.NET target platforms page](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span></span> <span data-ttu-id="c75ad-112">다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-112">Refer to this table:</span></span>

| <span data-ttu-id="c75ad-113">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="c75ad-113">.NET Framework Version</span></span> | <span data-ttu-id="c75ad-114">다운로드할 파일</span><span class="sxs-lookup"><span data-stu-id="c75ad-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="c75ad-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c75ad-115">4.6.1</span></span>                  | <span data-ttu-id="c75ad-116">.NET Framework 4.6.1 타기팅 팩</span><span class="sxs-lookup"><span data-stu-id="c75ad-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="c75ad-117">4.6</span><span class="sxs-lookup"><span data-stu-id="c75ad-117">4.6</span></span>                    | <span data-ttu-id="c75ad-118">.NET framework 4.6 타기팅 팩</span><span class="sxs-lookup"><span data-stu-id="c75ad-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="c75ad-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="c75ad-119">4.5.2</span></span>                  | <span data-ttu-id="c75ad-120">.NET framework 4.5.2 개발자 팩</span><span class="sxs-lookup"><span data-stu-id="c75ad-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="c75ad-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c75ad-121">4.5.1</span></span>                  | <span data-ttu-id="c75ad-122">.NET framework 4.5.1 개발자 팩</span><span class="sxs-lookup"><span data-stu-id="c75ad-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="c75ad-123">4.5</span><span class="sxs-lookup"><span data-stu-id="c75ad-123">4.5</span></span>                    | <span data-ttu-id="c75ad-124">Windows 8용 Windows 소프트웨어 개발 키트</span><span class="sxs-lookup"><span data-stu-id="c75ad-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="c75ad-125">4.0</span><span class="sxs-lookup"><span data-stu-id="c75ad-125">4.0</span></span>                    | <span data-ttu-id="c75ad-126">Windows 7 및 .NET Framework 4용 Windows SDK</span><span class="sxs-lookup"><span data-stu-id="c75ad-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="c75ad-127">2.0, 3.0 및 3.5</span><span class="sxs-lookup"><span data-stu-id="c75ad-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="c75ad-128">.NET Framework 3.5 SP1 런타임(또는 Windows 8 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="c75ad-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="c75ad-129">.NET 표준을 대상으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="c75ad-129">How to target the .NET Standard</span></span>

<span data-ttu-id="c75ad-130">.NET 표준에 익숙하지 않은 경우 자세한 내용은 [.NET 표준](../../standard/net-standard.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-130">If you're not quite familiar with the .NET Standard, refer to the [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="c75ad-131">이 문서에는 .NET 표준을 다양한 구현에 매핑하는 표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-131">In that article, there is a table which maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

<span data-ttu-id="c75ad-132">라이브러리 만들기 작업에서 이 표의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-132">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="c75ad-133">선택한 .NET Standard 버전에 따라 최신 API에 대한 액세스와 .NET 구현 및 .NET Standard 버전을 대상으로 지정할 수 있는 기능 간에 균형을 유지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-133">The version of the .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="c75ad-134">`netstandardX.X`(여기서 `X.X`는 버전 번호임) 버전을 선택하고 프로젝트 파일(`.csproj` 또는 `.fsproj`)에 추가하여 대상 지정이 가능한 플랫폼과 버전의 범위를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-134">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (Where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="c75ad-135">.NET 표준을 대상으로 할 때 요구에 따라 세 가지 기본 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-135">You have three primary options when targeting the .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="c75ad-136">템플릿에서 제공하는 기본 버전의 .NET 표준(`netstandard1.4`)을 사용할 수 있습니다. 이 버전을 통해 UWP, .NET Framework 4.6.1 및 예정된 .NET 표준 2.0과 호환성을 유지하면서 .NET 표준에 있는 대부분의 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-136">You can use the default version of the .NET Standard supplied by templates - `netstandard1.4` - which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and the forthcoming .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="c75ad-137">프로젝트 파일의 `TargetFramework` 노드에 있는 값을 수정하여 하위 또는 상위 버전의 .NET 표준을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-137">You can use a lower or higher version of the .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>
    
    <span data-ttu-id="c75ad-138">.NET 표준 버전은 이전 버전과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-138">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="c75ad-139">즉, `netstandard1.0` 라이브러리는 `netstandard1.1` 플랫폼 이상에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-139">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="c75ad-140">그러나 이후 버전과는 호환되지 않습니다. 더 낮은 .NET 표준 플랫폼은 더 높은 버전을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-140">However, there is no forward compatibility - lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="c75ad-141">즉, `netstandard1.0` 라이브러리는 `netstandard1.1` 이상을 대상으로 하는 라이브러리를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-141">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="c75ad-142">요구에 맞게 API와 플랫폼 지원이 올바르게 혼합된 표준 버전을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-142">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="c75ad-143">지금은 `netstandard1.4`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-143">We recommend `netstandard1.4` for now.</span></span>
    
3. <span data-ttu-id="c75ad-144">.NET Framework 버전 4.0 이하를 대상으로 하거나 .NET Framework에서는 사용 가능하지만 .NET 표준에서는 사용할 수 없는 API를 사용하려는 경우(예: `System.Drawing`) 다음 섹션을 읽어보고 멀티 타기팅 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-144">If you want to target the .NET Framework versions 4.0 or below, or you wish to use an API available in the .NET Framework but not in the .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-the-net-framework"></a><span data-ttu-id="c75ad-145">.NET Framework를 대상으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="c75ad-145">How to target the .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="c75ad-146">다음 지침은 컴퓨터에 .NET Framework가 설치된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-146">These instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="c75ad-147">설치된 종속성을 알아보려면 [필수 조건](#prerequisites)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-147">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="c75ad-148">여기서 사용된 .NET Framework 버전 중 일부는 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-148">Keep in mind that some of the .NET Framework versions used here are no longer in support.</span></span> <span data-ttu-id="c75ad-149">지원되지 않는 버전은 [.NET Framework Support Lifecycle Policy FAQ(.NET Framework 지원 수명 주기 정책 FAQ)](https://support.microsoft.com/gp/framework_faq/en-us)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-149">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="c75ad-150">가장 많은 수의 개발자 및 프로젝트에 도달하려면 기준 대상으로 .NET Framework 4.0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-150">If you want to reach the maximum number of developers and projects, use the .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="c75ad-151">.NET Framework를 대상으로 하려면 지원할 .NET Framework 버전에 해당하는 올바른 TFM(Target Framework Moniker)을 사용하여 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-151">To target the .NET Framework, you will need to begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.7   --> net47
```

<span data-ttu-id="c75ad-152">그런 다음 이 TFM을 프로젝트 파일의 `TargetFramework` 섹션에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-152">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="c75ad-153">예를 들어 .NET Framework 4.0을 대상으로 하는 라이브러리의 작성 방법을 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-153">For example, here's how you would write a library which targets the .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c75ad-154">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="c75ad-154">And that's it!</span></span> <span data-ttu-id="c75ad-155">이는 .NET Framework 4에 대해서만 컴파일되지만 이후 버전의 .NET Framework에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-155">Although this compiled only for the .NET Framework 4, you can use the library on newer versions of the .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="c75ad-156">멀티 타기팅 방법</span><span class="sxs-lookup"><span data-stu-id="c75ad-156">How to Multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="c75ad-157">다음 지침에서는 컴퓨터에 .NET Framework가 설치된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-157">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="c75ad-158">설치해야 할 종속성 및 다운로드할 위치에 대해 알아보려면 [필수 조건](#prerequisites) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-158">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="c75ad-159">프로젝트가 .NET Framework 및 .NET Core를 모두 지원하는 경우 이전 버전의 .NET Framework를 대상으로 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-159">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="c75ad-160">이 시나리오에서, 최신 대상에 최신 API 및 언어 구조를 사용하려는 경우 코드에 `#if` 지시문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-160">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="c75ad-161">각각의 경우에 필요한 API를 포함하기 위해 대상으로 지정하는 각 플랫폼마다 서로 다른 패키지와 종속성을 추가해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-161">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="c75ad-162">예를 들어 HTTP를 통해 네트워킹 작업을 수행하는 라이브러리가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-162">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="c75ad-163">.NET 표준 및 .NET Framework 버전 4.5 이상 경우 `System.Net.Http` 네임스페이스의 `HttpClient` 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-163">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="c75ad-164">그러나 이전 버전의 .NET Framework에는 `HttpClient` 클래스가 없으므로, 이에 대해 `System.Net` 네임스페이스의 `WebClient` 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-164">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="c75ad-165">프로젝트 파일이 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-165">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="c75ad-166">여기서 다음 세 가지 주요 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-166">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="c75ad-167">`TargetFramework` 노드가 `TargetFrameworks`로 대체되었으며, 세 개의 TFM이 내부에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-167">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="c75ad-168">`net40 ` 대상에는 .NET Framework 참조 하나를 끌어오는 `<ItemGroup>` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-168">There is an `<ItemGroup>` node for the `net40 ` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="c75ad-169">`net45` 대상에는 .NET Framework 참조 두 개를 끌어오는 `<ItemGroup>` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-169">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="c75ad-170">빌드 시스템은 `#if` 지시문에 사용된 다음의 전처리기 기호를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-170">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="c75ad-171">대상당 조건부 컴파일을 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-171">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "http://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="c75ad-172">`dotnet build`를 사용하여 이 프로젝트를 빌드하면 `bin/` 폴더 아래에 다음 3개의 디렉터리가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-172">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="c75ad-173">각 디렉터리에는 각 대상에 대한 `.dll` 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-173">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="c75ad-174">.NET Core에서 라이브러리를 테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="c75ad-174">How to test libraries on .NET Core</span></span>

<span data-ttu-id="c75ad-175">플랫폼 간에 테스트할 수 있는 기능이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-175">It's important to be able to test across platforms.</span></span> <span data-ttu-id="c75ad-176">기본적으로 [xUnit](http://xunit.github.io/) 또는 MSTest를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-176">You can use either [xUnit](http://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="c75ad-177">둘 다 .NET Core에서 라이브러리를 단위 테스트하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-177">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="c75ad-178">테스트 프로젝트로 솔루션을 설정하는 방법은 [솔루션 구조](#structuring-a-solution)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-178">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="c75ad-179">다음 예제에서는 테스트 및 원본 디렉터리가 동일한 최상위 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-179">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="c75ad-180">일부 [.NET Core CLI 명령](../tools/index.md)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-180">This uses some [.NET Core CLI commands](../tools/index.md).</span></span> <span data-ttu-id="c75ad-181">자세한 내용은 [dotnet new](../tools/dotnet-new.md) 및 [dotnet sln](../tools/dotnet-sln.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75ad-181">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="c75ad-182">솔루션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-182">Set up your solution.</span></span> <span data-ttu-id="c75ad-183">다음 명령을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-183">You can do so with the following commands:</span></span>

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="c75ad-184">그러면 프로젝트가 생성되고 솔루션에서 함께 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-184">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="c75ad-185">`SolutionWithSrcAndTest` 디렉터리가 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-185">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="c75ad-186">테스트 프로젝트의 디렉터리로 이동한 다음 `MyProject`의 `MyProject.Test`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-186">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="c75ad-187">패키지를 복원하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-187">Restore packages and build projects:</span></span>

   ```bash
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

1. <span data-ttu-id="c75ad-188">`dotnet test` 명령을 실행하여 xUnit가 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-188">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="c75ad-189">MSTest를 사용하도록 선택한 경우 MSTest 콘솔 실행기가 대신 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-189">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>
    
<span data-ttu-id="c75ad-190">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="c75ad-190">And that's it!</span></span> <span data-ttu-id="c75ad-191">이제 명령줄 도구를 사용하여 모든 플랫폼 라이브러리를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-191">You can now test your library across all platforms using command line tools.</span></span> <span data-ttu-id="c75ad-192">이제 모든 것이 설정되어 계속해서 테스트하려는 경우 라이브러리 테스트는 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-192">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="c75ad-193">라이브러리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-193">Make changes to your library.</span></span>
1. <span data-ttu-id="c75ad-194">명령줄의 테스트 디렉터리에서 `dotnet test` 명령으로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-194">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="c75ad-195">`dotnet test` 명령을 호출하면 자동으로 코드가 다시 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-195">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="c75ad-196">여러 프로젝트를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="c75ad-196">How to use multiple projects</span></span>

<span data-ttu-id="c75ad-197">더 큰 라이브러리의 경우 일반적으로 서로 다른 프로젝트에 기능을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-197">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="c75ad-198">자연스러운 C# 및 F#에 사용할 수 있는 라이브러리를 빌드하려 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-198">Imagine you wished to build a library which could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="c75ad-199">즉, 라이브러리의 소비자가 C# 및 F#에 자연스러운 방식으로 라이브러리를 사용한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-199">That would mean that consumers of your library consume them in ways which are natural to C# or F#.</span></span> <span data-ttu-id="c75ad-200">예를 들어 C#에서 다음과 같이 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-200">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="c75ad-201">F#에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-201">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="c75ad-202">이와 같은 사용 시나리오는, 액세스하는 API가 C# 및 F#에 대해 다른 구조를 가지고 있어야 한다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-202">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="c75ad-203">이를 수행하는 일반적인 방법은 Core 프로젝트로 호출하는 API 계층을 정의하는 C# 및 F# 프로젝트에서 라이브러리의 모든 논리를 해당 Core 프로젝트로 팩터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-203">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="c75ad-204">섹션의 나머지 부분에서는 다음 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-204">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="c75ad-205">**AwesomeLibrary.Core** - 라이브러리에 대한 모든 논리를 포함하는 Core 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c75ad-205">**AwesomeLibrary.Core** - A core project which contains all logic for the library</span></span>
* <span data-ttu-id="c75ad-206">**AwesomeLibrary.CSharp** - C#에서 사용하기 위한 공용 API가 포함된 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c75ad-206">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="c75ad-207">**AwesomeLibrary.FSharp** - F#에서 사용하기 위한 공용 API가 포함된 프로젝트</span><span class="sxs-lookup"><span data-stu-id="c75ad-207">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="c75ad-208">터미널에서 다음 명령을 실행하면 이 가이드와 동일한 구조를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-208">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```console
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang F#
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="c75ad-209">그러면 위의 세 가지 프로젝트와 프로젝트를 함께 연결하는 솔루션 파일 하나가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-209">This will add the three projects above and a solution file which links them together.</span></span> <span data-ttu-id="c75ad-210">솔루션 파일을 만들고 프로젝트를 연결하면 최상위 수준에서 프로젝트를 복원하고 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-210">Creating the solution file and linking projects will allow you to restore and build projects from a top-level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="c75ad-211">프로젝트 간 참조</span><span class="sxs-lookup"><span data-stu-id="c75ad-211">Project-to-project referencing</span></span>

<span data-ttu-id="c75ad-212">프로젝트를 참조하는 가장 좋은 방법은 .NET Core CLI를 사용하여 프로젝트 참조를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-212">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="c75ad-213">**AwesomeLibrary.CSharp** 및 **AwesomeLibrary.FSharp** 프로젝트 디렉터리에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-213">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```console
$ dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="c75ad-214">이제 **AwesomeLibrary.CSharp** 및 **AwesomeLibrary.FSharp** 둘 다의 프로젝트 파일에서 **AwesomeLibrary.Core**를 `ProjectReference` 대상으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-214">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="c75ad-215">프로젝트 파일을 검사하고 파일에서 다음을 통해 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-215">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="c75ad-216">.NET Core CLI를 사용하지 않으려는 경우 이 섹션을 각 프로젝트 파일에 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-216">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="c75ad-217">솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="c75ad-217">Structuring a solution</span></span>

<span data-ttu-id="c75ad-218">다중 프로젝트 솔루션의 또 다른 중요한 측면은 전체 프로젝트 구조를 올바르게 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-218">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="c75ad-219">코드를 원하는 대로 구성할 수 있으며, `dotnet sln add`를 사용하여 각 프로젝트를 솔루션 파일에 연결하기만 하면 솔루션 수준에서 `dotnet restore` 및 `dotnet build`를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75ad-219">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
