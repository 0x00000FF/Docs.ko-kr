---
title: 대상 프레임워크
description: .NET Core 앱 및 라이브러리의 대상 프레임워크에 대해 알아봅니다.
author: richlander
ms.author: mairaw
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 2721266c90e183616a907803ff209258956a37b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727406"
---
# <a name="target-frameworks"></a><span data-ttu-id="8dcde-103">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="8dcde-103">Target frameworks</span></span>

<span data-ttu-id="8dcde-104">앱 또는 라이브러리에서 프레임워크를 대상으로 지정하면 앱 또는 라이브러리에서 사용할 수 있도록 하려는 API 집합을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-104">When you target a framework in an app or library, you're specifying the set of APIs that you'd like to make available to the app or library.</span></span> <span data-ttu-id="8dcde-105">TFM(대상 프레임워크 모니터)을 사용하여 프로젝트 파일에서 대상 프레임워크를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-105">You specify the target framework in your project file using Target Framework Monikers (TFMs).</span></span>

<span data-ttu-id="8dcde-106">앱 또는 라이브러리는 [.NET Standard](~/docs/standard/net-standard.md) 버전을 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-106">An app or library can target a version of [.NET Standard](~/docs/standard/net-standard.md).</span></span> <span data-ttu-id="8dcde-107">.NET Standard 버전은 모든 .NET 구현체에서 사용할 수 있는 표준화된 API 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-107">.NET Standard versions represent standardized sets of APIs across all .NET implementations.</span></span> <span data-ttu-id="8dcde-108">예를 들어 .NET Standard 1.6을 대상으로 하는 라이브러리는 동일한 코드 기반의 .NET Core 및 .NET Framework에서 동작하는 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-108">For example, a library can target .NET Standard 1.6 and gain access to APIs that function across .NET Core and .NET Framework using the same codebase.</span></span>

<span data-ttu-id="8dcde-109">앱 또는 라이브러리는 특정 .NET 구현체을 대상으로 지정하여 구현체 관련 API에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-109">An app or library can also target a specific .NET implementation to gain access to implementation-specific APIs.</span></span> <span data-ttu-id="8dcde-110">예를 들어 Xamarin.iOS(예: `Xamarin.iOS10`)를 대상으로 하는 앱은 Xamarin에서 제공하는 iOS 10용 iOS API 래퍼에 액세스하고, UWP(유니버설 Windows 플랫폼, `uap10.0`)를 대상으로 하는 앱은 Windows 10이 실행되는 디바이스용으로 컴파일하는 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-110">For example, an app that targets Xamarin.iOS (for example, `Xamarin.iOS10`) gets access to Xamarin-provided iOS API wrappers for iOS 10, or an app that targets the Universal Windows Platform (UWP, `uap10.0`) has access to APIs that compile for devices that run Windows 10.</span></span>

<span data-ttu-id="8dcde-111">일부 대상 프레임워크(예: .NET Framework)의 API는 프레임워크에서 시스템에 설치하는 어셈블리에 의해 정의되고 애플리케이션 프레임워크 API(예: ASP.NET)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-111">For some target frameworks (for example, the .NET Framework), the APIs are defined by the assemblies that the framework installs on a system and may include application framework APIs (for example, ASP.NET).</span></span>

<span data-ttu-id="8dcde-112">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 API는 앱이나 라이브러리에 포함된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-112">For package-based target frameworks (for example, .NET Standard and .NET Core), the APIs are defined by the packages included in the app or library.</span></span> <span data-ttu-id="8dcde-113">*메타패키지*는 고유한 내용은 없고 종속성(다른 패키지) 목록만 있는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-113">A *metapackage* is a NuGet package that has no content of its own but is a list of dependencies (other packages).</span></span> <span data-ttu-id="8dcde-114">NuGet 패키지 기반 대상 프레임워크는 프레임워크를 구성하는 모든 패키지를 참조하는 메타패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-114">A NuGet package-based target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

## <a name="latest-target-framework-versions"></a><span data-ttu-id="8dcde-115">최신 대상 프레임워크 버전</span><span class="sxs-lookup"><span data-stu-id="8dcde-115">Latest target framework versions</span></span>

<span data-ttu-id="8dcde-116">다음 표에서는 가장 일반적인 대상 프레임워크, 프레임워크가 참조되는 방법 및 프레임워크에서 구현하는 [.NET Standard](~/docs/standard/net-standard.md)의 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-116">The following table defines the most common target frameworks, how they're referenced, and which version of the [.NET Standard](~/docs/standard/net-standard.md) they implement.</span></span> <span data-ttu-id="8dcde-117">이러한 대상 프레임워크 버전은 안정적인 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-117">These target framework versions are the latest stable versions.</span></span> <span data-ttu-id="8dcde-118">시험판 버전은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-118">Pre-release versions aren't shown.</span></span> <span data-ttu-id="8dcde-119">TFM(대상 프레임워크 모니커)은 .NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위해 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-119">A Target Framework Moniker (TFM) is a standardized token format for specifying the target framework of a .NET app or library.</span></span>

| <span data-ttu-id="8dcde-120">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="8dcde-120">Target Framework</span></span>      | <span data-ttu-id="8dcde-121">최신</span><span class="sxs-lookup"><span data-stu-id="8dcde-121">Latest</span></span> <br/> <span data-ttu-id="8dcde-122">안정적인 버전</span><span class="sxs-lookup"><span data-stu-id="8dcde-122">Stable Version</span></span> | <span data-ttu-id="8dcde-123">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="8dcde-123">Target Framework Moniker (TFM)</span></span> | <span data-ttu-id="8dcde-124">구현된</span><span class="sxs-lookup"><span data-stu-id="8dcde-124">Implemented</span></span> <br/> <span data-ttu-id="8dcde-125">.NET 표준 버전</span><span class="sxs-lookup"><span data-stu-id="8dcde-125">.NET Standard Version</span></span> |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| <span data-ttu-id="8dcde-126">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="8dcde-126">.NET Standard</span></span>         | <span data-ttu-id="8dcde-127">2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-127">2.0</span></span>                         | <span data-ttu-id="8dcde-128">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-128">netstandard2.0</span></span>                 | <span data-ttu-id="8dcde-129">N/A</span><span class="sxs-lookup"><span data-stu-id="8dcde-129">N/A</span></span>                                     |
| <span data-ttu-id="8dcde-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8dcde-130">.NET Core</span></span>             | <span data-ttu-id="8dcde-131">2.2</span><span class="sxs-lookup"><span data-stu-id="8dcde-131">2.2</span></span>                         | <span data-ttu-id="8dcde-132">netcoreapp2.2</span><span class="sxs-lookup"><span data-stu-id="8dcde-132">netcoreapp2.2</span></span>                  | <span data-ttu-id="8dcde-133">2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-133">2.0</span></span>                                     |
| <span data-ttu-id="8dcde-134">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="8dcde-134">.NET Framework</span></span>        | <span data-ttu-id="8dcde-135">4.7.2</span><span class="sxs-lookup"><span data-stu-id="8dcde-135">4.7.2</span></span>                       | <span data-ttu-id="8dcde-136">net472</span><span class="sxs-lookup"><span data-stu-id="8dcde-136">net472</span></span>                         | <span data-ttu-id="8dcde-137">2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-137">2.0</span></span>                                     |

## <a name="supported-target-framework-versions"></a><span data-ttu-id="8dcde-138">지원되는 대상 프레임워크 버전</span><span class="sxs-lookup"><span data-stu-id="8dcde-138">Supported target framework versions</span></span>

<span data-ttu-id="8dcde-139">대상 프레임워크는 일반적으로 TFM에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-139">A target framework is typically referenced by a TFM.</span></span> <span data-ttu-id="8dcde-140">다음 표에서는 .NET Core SDK 및 NuGet 클라이언트에서 지원되는 대상 프레임워크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-140">The following table shows the target frameworks supported by the .NET Core SDK and the NuGet client.</span></span> <span data-ttu-id="8dcde-141">동일한 항목은 대괄호 내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-141">Equivalents are shown within brackets.</span></span> <span data-ttu-id="8dcde-142">예를 들어 `win81`은 `netcore451`과 동일한 TFM입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-142">For example, `win81` is an equivalent TFM to `netcore451`.</span></span>

| <span data-ttu-id="8dcde-143">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="8dcde-143">Target Framework</span></span>           | <span data-ttu-id="8dcde-144">TFM</span><span class="sxs-lookup"><span data-stu-id="8dcde-144">TFM</span></span> |
| -------------------------- | --- |
| <span data-ttu-id="8dcde-145">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="8dcde-145">.NET Standard</span></span>              | <span data-ttu-id="8dcde-146">netstandard1.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-146">netstandard1.0</span></span><br><span data-ttu-id="8dcde-147">netstandard1.1</span><span class="sxs-lookup"><span data-stu-id="8dcde-147">netstandard1.1</span></span><br><span data-ttu-id="8dcde-148">netstandard1.2</span><span class="sxs-lookup"><span data-stu-id="8dcde-148">netstandard1.2</span></span><br><span data-ttu-id="8dcde-149">netstandard1.3</span><span class="sxs-lookup"><span data-stu-id="8dcde-149">netstandard1.3</span></span><br><span data-ttu-id="8dcde-150">netstandard1.4</span><span class="sxs-lookup"><span data-stu-id="8dcde-150">netstandard1.4</span></span><br><span data-ttu-id="8dcde-151">netstandard1.5</span><span class="sxs-lookup"><span data-stu-id="8dcde-151">netstandard1.5</span></span><br><span data-ttu-id="8dcde-152">netstandard1.6</span><span class="sxs-lookup"><span data-stu-id="8dcde-152">netstandard1.6</span></span><br><span data-ttu-id="8dcde-153">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-153">netstandard2.0</span></span> |
| <span data-ttu-id="8dcde-154">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8dcde-154">.NET Core</span></span>                  | <span data-ttu-id="8dcde-155">netcoreapp1.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-155">netcoreapp1.0</span></span><br><span data-ttu-id="8dcde-156">netcoreapp1.1</span><span class="sxs-lookup"><span data-stu-id="8dcde-156">netcoreapp1.1</span></span><br><span data-ttu-id="8dcde-157">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-157">netcoreapp2.0</span></span><br><span data-ttu-id="8dcde-158">netcoreapp2.1</span><span class="sxs-lookup"><span data-stu-id="8dcde-158">netcoreapp2.1</span></span><br><span data-ttu-id="8dcde-159">netcoreapp2.2</span><span class="sxs-lookup"><span data-stu-id="8dcde-159">netcoreapp2.2</span></span> |
| <span data-ttu-id="8dcde-160">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="8dcde-160">.NET Framework</span></span>             | <span data-ttu-id="8dcde-161">net11</span><span class="sxs-lookup"><span data-stu-id="8dcde-161">net11</span></span><br><span data-ttu-id="8dcde-162">net20</span><span class="sxs-lookup"><span data-stu-id="8dcde-162">net20</span></span><br><span data-ttu-id="8dcde-163">net35</span><span class="sxs-lookup"><span data-stu-id="8dcde-163">net35</span></span><br><span data-ttu-id="8dcde-164">net40</span><span class="sxs-lookup"><span data-stu-id="8dcde-164">net40</span></span><br><span data-ttu-id="8dcde-165">net403</span><span class="sxs-lookup"><span data-stu-id="8dcde-165">net403</span></span><br><span data-ttu-id="8dcde-166">net45</span><span class="sxs-lookup"><span data-stu-id="8dcde-166">net45</span></span><br><span data-ttu-id="8dcde-167">net451</span><span class="sxs-lookup"><span data-stu-id="8dcde-167">net451</span></span><br><span data-ttu-id="8dcde-168">net452</span><span class="sxs-lookup"><span data-stu-id="8dcde-168">net452</span></span><br><span data-ttu-id="8dcde-169">net46</span><span class="sxs-lookup"><span data-stu-id="8dcde-169">net46</span></span><br><span data-ttu-id="8dcde-170">net461</span><span class="sxs-lookup"><span data-stu-id="8dcde-170">net461</span></span><br><span data-ttu-id="8dcde-171">net462</span><span class="sxs-lookup"><span data-stu-id="8dcde-171">net462</span></span><br><span data-ttu-id="8dcde-172">net47</span><span class="sxs-lookup"><span data-stu-id="8dcde-172">net47</span></span><br><span data-ttu-id="8dcde-173">net471</span><span class="sxs-lookup"><span data-stu-id="8dcde-173">net471</span></span><br><span data-ttu-id="8dcde-174">net472</span><span class="sxs-lookup"><span data-stu-id="8dcde-174">net472</span></span> |
| <span data-ttu-id="8dcde-175">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="8dcde-175">Windows Store</span></span>              | <span data-ttu-id="8dcde-176">netcore [netcore45]</span><span class="sxs-lookup"><span data-stu-id="8dcde-176">netcore [netcore45]</span></span><br><span data-ttu-id="8dcde-177">netcore45 [win] [win8]</span><span class="sxs-lookup"><span data-stu-id="8dcde-177">netcore45 [win] [win8]</span></span><br><span data-ttu-id="8dcde-178">netcore451 [win81]</span><span class="sxs-lookup"><span data-stu-id="8dcde-178">netcore451 [win81]</span></span> |
| <span data-ttu-id="8dcde-179">.NET Micro Framework</span><span class="sxs-lookup"><span data-stu-id="8dcde-179">.NET Micro Framework</span></span>       | <span data-ttu-id="8dcde-180">netmf</span><span class="sxs-lookup"><span data-stu-id="8dcde-180">netmf</span></span> |
| <span data-ttu-id="8dcde-181">Silverlight</span><span class="sxs-lookup"><span data-stu-id="8dcde-181">Silverlight</span></span>                | <span data-ttu-id="8dcde-182">sl4</span><span class="sxs-lookup"><span data-stu-id="8dcde-182">sl4</span></span><br><span data-ttu-id="8dcde-183">sl5</span><span class="sxs-lookup"><span data-stu-id="8dcde-183">sl5</span></span> |
| <span data-ttu-id="8dcde-184">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="8dcde-184">Windows Phone</span></span>              | <span data-ttu-id="8dcde-185">wp [wp7]</span><span class="sxs-lookup"><span data-stu-id="8dcde-185">wp [wp7]</span></span><br><span data-ttu-id="8dcde-186">wp7</span><span class="sxs-lookup"><span data-stu-id="8dcde-186">wp7</span></span><br><span data-ttu-id="8dcde-187">wp75</span><span class="sxs-lookup"><span data-stu-id="8dcde-187">wp75</span></span><br><span data-ttu-id="8dcde-188">wp8</span><span class="sxs-lookup"><span data-stu-id="8dcde-188">wp8</span></span><br><span data-ttu-id="8dcde-189">wp81</span><span class="sxs-lookup"><span data-stu-id="8dcde-189">wp81</span></span><br><span data-ttu-id="8dcde-190">wpa81</span><span class="sxs-lookup"><span data-stu-id="8dcde-190">wpa81</span></span> |
| <span data-ttu-id="8dcde-191">UWP</span><span class="sxs-lookup"><span data-stu-id="8dcde-191">Universal Windows Platform</span></span> | <span data-ttu-id="8dcde-192">uap [uap10.0]</span><span class="sxs-lookup"><span data-stu-id="8dcde-192">uap [uap10.0]</span></span><br><span data-ttu-id="8dcde-193">uap10.0 [win10] [netcore50]</span><span class="sxs-lookup"><span data-stu-id="8dcde-193">uap10.0 [win10] [netcore50]</span></span> |

## <a name="how-to-specify-target-frameworks"></a><span data-ttu-id="8dcde-194">대상 프레임워크를 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="8dcde-194">How to specify target frameworks</span></span>

<span data-ttu-id="8dcde-195">대상 프레임워크는 프로젝트 파일에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-195">Target frameworks are specified in your project file.</span></span> <span data-ttu-id="8dcde-196">단일 대상 프레임워크를 지정하는 경우 **TargetFramework** 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-196">When a single target framework is specified, use the **TargetFramework** element.</span></span> <span data-ttu-id="8dcde-197">다음 콘솔 앱 프로젝트 파일에서는 .NET Core 2.2를 대상 프레임워크로 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-197">The following console app project file demonstrates how to target .NET Core 2.2:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="8dcde-198">여러 대상 프레임워크를 지정하는 경우 각 대상 프레임워크에 대한 어셈블리를 조건에 따라 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-198">When you specify multiple target frameworks, you may conditionally reference assemblies for each target framework.</span></span> <span data-ttu-id="8dcde-199">코드에서는 *if-then-else* 로직에 전처리기 기호를 사용하여 해당 어셈블리를 조건에 따라 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-199">In your code, you can conditionally compile against those assemblies by using preprocessor symbols with *if-then-else* logic.</span></span>

<span data-ttu-id="8dcde-200">다음 라이브러리 프로젝트 파일은 .NET Standard(`netstandard1.4`)의 API 및 .NET Framework(`net40` 및 `net45`)의 API를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-200">The following library project file targets APIs of .NET Standard (`netstandard1.4`) and APIs of the .NET Framework (`net40` and `net45`).</span></span> <span data-ttu-id="8dcde-201">여러 대상 프레임워크에는 복수형 **TargetFrameworks** 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-201">Use the plural **TargetFrameworks** element with multiple target frameworks.</span></span> <span data-ttu-id="8dcde-202">라이브러리를 두 개의 .NET Framework TFM에 대해 컴파일하려면 `Condition` 특성에 구현체 관련 패키지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-202">Note how the `Condition` attributes include implementation-specific packages when the library is compiled for the two .NET Framework TFMs:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="8dcde-203">라이브러리나 앱에서, 조건에 따라 각 대상 프레임워크에 대해 컴파일하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-203">Within your library or app, you write conditional code to compile for each target framework:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

<span data-ttu-id="8dcde-204">빌드 시스템은 [지원되는 대상 프레임워크 버전](#supported-target-framework-versions) 표에 표시된 대상 프레임워크를 나타내는 전처리기 기호를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-204">The build system is aware of preprocessor symbols representing the target frameworks shown in the [Supported target framework versions](#supported-target-framework-versions) table.</span></span> <span data-ttu-id="8dcde-205">.NET Standard 또는 .NET Core TFM을 나타내는 기호를 사용할 경우 점을 밑줄로 바꾸고 소문자를 대문자로 변경합니다. 예를 들어 `netstandard1.4`에 대한 기호는 `NETSTANDARD1_4`입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-205">When using a symbol that represents a .NET Standard or .NET Core TFM, replace the dot with an underscore and change lowercase letters to uppercase (for example, the symbol for `netstandard1.4` is `NETSTANDARD1_4`).</span></span>

<span data-ttu-id="8dcde-206">다음은 .NET Core 대상 프레임워크에 대한 전체 전처리기 기호 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-206">The complete list of preprocessor symbols for .NET Core target frameworks is:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a><span data-ttu-id="8dcde-207">사용되지 않는 대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="8dcde-207">Deprecated target frameworks</span></span>

<span data-ttu-id="8dcde-208">다음 대상 프레임워크는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-208">The following target frameworks are deprecated.</span></span> <span data-ttu-id="8dcde-209">이러한 대상 프레임워크를 대상으로 하는 패키지는 지정된 대체 항목으로 마이그레이션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcde-209">Packages targeting these target frameworks should migrate to the indicated replacements.</span></span>

| <span data-ttu-id="8dcde-210">사용되지 않는 TFM</span><span class="sxs-lookup"><span data-stu-id="8dcde-210">Deprecated TFM</span></span>                                                                             | <span data-ttu-id="8dcde-211">Replacement</span><span class="sxs-lookup"><span data-stu-id="8dcde-211">Replacement</span></span> |
| ------------------------------------------------------------------------------------------ | ----------- |
| <span data-ttu-id="8dcde-212">aspnet50</span><span class="sxs-lookup"><span data-stu-id="8dcde-212">aspnet50</span></span><br><span data-ttu-id="8dcde-213">aspnetcore50</span><span class="sxs-lookup"><span data-stu-id="8dcde-213">aspnetcore50</span></span><br><span data-ttu-id="8dcde-214">dnxcore50</span><span class="sxs-lookup"><span data-stu-id="8dcde-214">dnxcore50</span></span><br><span data-ttu-id="8dcde-215">dnx</span><span class="sxs-lookup"><span data-stu-id="8dcde-215">dnx</span></span><br><span data-ttu-id="8dcde-216">dnx45</span><span class="sxs-lookup"><span data-stu-id="8dcde-216">dnx45</span></span><br><span data-ttu-id="8dcde-217">dnx451</span><span class="sxs-lookup"><span data-stu-id="8dcde-217">dnx451</span></span><br><span data-ttu-id="8dcde-218">dnx452</span><span class="sxs-lookup"><span data-stu-id="8dcde-218">dnx452</span></span>                  | <span data-ttu-id="8dcde-219">netcoreapp</span><span class="sxs-lookup"><span data-stu-id="8dcde-219">netcoreapp</span></span>  |
| <span data-ttu-id="8dcde-220">dotnet</span><span class="sxs-lookup"><span data-stu-id="8dcde-220">dotnet</span></span><br><span data-ttu-id="8dcde-221">dotnet50</span><span class="sxs-lookup"><span data-stu-id="8dcde-221">dotnet50</span></span><br><span data-ttu-id="8dcde-222">dotnet51</span><span class="sxs-lookup"><span data-stu-id="8dcde-222">dotnet51</span></span><br><span data-ttu-id="8dcde-223">dotnet52</span><span class="sxs-lookup"><span data-stu-id="8dcde-223">dotnet52</span></span><br><span data-ttu-id="8dcde-224">dotnet53</span><span class="sxs-lookup"><span data-stu-id="8dcde-224">dotnet53</span></span><br><span data-ttu-id="8dcde-225">dotnet54</span><span class="sxs-lookup"><span data-stu-id="8dcde-225">dotnet54</span></span><br><span data-ttu-id="8dcde-226">dotnet55</span><span class="sxs-lookup"><span data-stu-id="8dcde-226">dotnet55</span></span><br><span data-ttu-id="8dcde-227">dotnet56</span><span class="sxs-lookup"><span data-stu-id="8dcde-227">dotnet56</span></span> | <span data-ttu-id="8dcde-228">netstandard</span><span class="sxs-lookup"><span data-stu-id="8dcde-228">netstandard</span></span> |
| <span data-ttu-id="8dcde-229">netcore50</span><span class="sxs-lookup"><span data-stu-id="8dcde-229">netcore50</span></span>                                                                                  | <span data-ttu-id="8dcde-230">uap10.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-230">uap10.0</span></span>     |
| <span data-ttu-id="8dcde-231">win</span><span class="sxs-lookup"><span data-stu-id="8dcde-231">win</span></span>                                                                                        | <span data-ttu-id="8dcde-232">netcore45</span><span class="sxs-lookup"><span data-stu-id="8dcde-232">netcore45</span></span>   |
| <span data-ttu-id="8dcde-233">win8</span><span class="sxs-lookup"><span data-stu-id="8dcde-233">win8</span></span>                                                                                       | <span data-ttu-id="8dcde-234">netcore45</span><span class="sxs-lookup"><span data-stu-id="8dcde-234">netcore45</span></span>   |
| <span data-ttu-id="8dcde-235">win81</span><span class="sxs-lookup"><span data-stu-id="8dcde-235">win81</span></span>                                                                                      | <span data-ttu-id="8dcde-236">netcore451</span><span class="sxs-lookup"><span data-stu-id="8dcde-236">netcore451</span></span>  |
| <span data-ttu-id="8dcde-237">win10</span><span class="sxs-lookup"><span data-stu-id="8dcde-237">win10</span></span>                                                                                      | <span data-ttu-id="8dcde-238">uap10.0</span><span class="sxs-lookup"><span data-stu-id="8dcde-238">uap10.0</span></span>     |
| <span data-ttu-id="8dcde-239">winrt</span><span class="sxs-lookup"><span data-stu-id="8dcde-239">winrt</span></span>                                                                                      | <span data-ttu-id="8dcde-240">netcore45</span><span class="sxs-lookup"><span data-stu-id="8dcde-240">netcore45</span></span>   |

## <a name="see-also"></a><span data-ttu-id="8dcde-241">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dcde-241">See also</span></span>

- [<span data-ttu-id="8dcde-242">패키지, 메타패키지 및 프레임워크</span><span class="sxs-lookup"><span data-stu-id="8dcde-242">Packages, Metapackages and Frameworks</span></span>](../core/packages.md)
- [<span data-ttu-id="8dcde-243">여러 플랫폼에서 사용할 수 있는 도구로 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="8dcde-243">Developing Libraries with Cross Platform Tools</span></span>](../core/tutorials/libraries.md)
- [<span data-ttu-id="8dcde-244">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="8dcde-244">.NET Standard</span></span>](net-standard.md)
- [<span data-ttu-id="8dcde-245">.NET Core 버전 관리</span><span class="sxs-lookup"><span data-stu-id="8dcde-245">.NET Core Versioning</span></span>](../core/versions/index.md)
- <span data-ttu-id="8dcde-246">[dotnet/standard GitHub repository](https://github.com/dotnet/standard)(dotnet/표준 GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="8dcde-246">[dotnet/standard GitHub repository](https://github.com/dotnet/standard)</span></span>
- <span data-ttu-id="8dcde-247">[NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools)(NuGet 도구 GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="8dcde-247">[NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools)</span></span>
- <span data-ttu-id="8dcde-248">[Framework Profiles in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)(.NET의 프레임워크 프로필)</span><span class="sxs-lookup"><span data-stu-id="8dcde-248">[Framework Profiles in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)</span></span>
