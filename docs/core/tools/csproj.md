---
title: .NET Core용 csproj 형식에 대한 추가 사항
description: 기존 및 .NET Core csproj 파일 간의 차이점에 대해 알아보기
author: blackdwarf
ms.date: 09/22/2017
ms.openlocfilehash: 74cde39a0bbba65d252d64bcedb91c3949dcf6f2
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222066"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="2898e-103">.NET Core용 csproj 형식에 대한 추가 사항</span><span class="sxs-lookup"><span data-stu-id="2898e-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="2898e-104">이 문서는 *project.json*에서 *csproj* 및 [MSBuild](https://github.com/Microsoft/MSBuild)로 프로젝트 시스템을 전환함에 따라 프로젝트 파일에 추가된 변경 내용을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="2898e-105">일반 프로젝트 파일 구문 및 참조에 대한 자세한 내용은 [MSBuild 프로젝트 파일](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2898e-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="2898e-106">암시적 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="2898e-106">Implicit package references</span></span>
<span data-ttu-id="2898e-107">메타패키지는 프로젝트 파일의 `<TargetFramework>` 또는 `<TargetFrameworks>` 속성에 지정된 대상 프레임워크를 기준으로 암시적으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="2898e-108">`<TargetFramework>`가 지정된 경우 `<TargetFrameworks>`는 순서와 관계없이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="2898e-109">권장 사항</span><span class="sxs-lookup"><span data-stu-id="2898e-109">Recommendations</span></span>
<span data-ttu-id="2898e-110">`Microsoft.NETCore.App` 또는 `NetStandard.Library` 메타패키지가 암시적으로 참조되기 때문에 권장되는 모범 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="2898e-111">.NET Core 또는 .NET Standard를 대상으로 하는 경우 절대로 프로젝트 파일의 `<PackageReference>` 항목을 통해 `Microsoft.NETCore.App` 또는 `NetStandard.Library` 메타패키지를 명시적으로 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="2898e-112">.NET Core를 대상으로 할 때 특정 버전의 런타임이 필요한 경우 메타패키지를 참조하는 대신 프로젝트의 `<RuntimeFrameworkVersion>` 속성(예: `1.0.4`)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="2898e-113">예를 들어 [자체 포함 배포](../deploying/index.md#self-contained-deployments-scd)를 사용하고, 1.0.0 LTS 런타임이라는 특정 패치 버전이 필요한 경우 이런 일이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="2898e-114">.NET Standard를 대상으로 할 때 특정 버전의 `NetStandard.Library` 메타패키지가 필요한 경우 `<NetStandardImplicitPackageVersion>` 속성을 사용하고 필요한 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="2898e-115">.NET Framework 프로젝트의 `Microsoft.NETCore.App` 또는 `NetStandard.Library` 메타패키지에 참조를 명시적으로 추가하거나 업데이트하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2898e-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="2898e-116">.NET Standard 기반 NuGet 패키지를 사용할 때 모든 버전의 `NetStandard.Library`가 필요한 경우 NuGet은 자동으로 해당 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="2898e-117">.NET Core 프로젝트의 기본 컴파일 포함 사항</span><span class="sxs-lookup"><span data-stu-id="2898e-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="2898e-118">최신 SDK 버전의 *csproj* 형식으로 전환하면서 컴파일 항목에 대한 기본 포함 사항과 제외 사항 및 포함 리소스를 SDK 속성 파일로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="2898e-119">따라서 더 이상 프로젝트 파일에서 컴파일 항목을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="2898e-120">이렇게 하는 주된 이유는 프로젝트 파일에서 혼란을 줄이기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="2898e-121">SDK의 기본값은 가장 일반적인 사용 사례를 다루므로 개발자가 만드는 모든 프로젝트에서 반복할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="2898e-122">결과적으로 프로젝트 파일 수가 줄어 훨씬 쉽게 이해하고 편집(필요한 경우)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="2898e-123">다음 표에는 SDK에 모두 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="2898e-124">요소</span><span class="sxs-lookup"><span data-stu-id="2898e-124">Element</span></span>           | <span data-ttu-id="2898e-125">GLOB 포함</span><span class="sxs-lookup"><span data-stu-id="2898e-125">Include glob</span></span>                              | <span data-ttu-id="2898e-126">GLOB 제외</span><span class="sxs-lookup"><span data-stu-id="2898e-126">Exclude glob</span></span>                                                  | <span data-ttu-id="2898e-127">GLOB 제거</span><span class="sxs-lookup"><span data-stu-id="2898e-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="2898e-128">Compile</span><span class="sxs-lookup"><span data-stu-id="2898e-128">Compile</span></span>           | <span data-ttu-id="2898e-129">\*\*/\*.cs(또는 기타 언어 확장)</span><span class="sxs-lookup"><span data-stu-id="2898e-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="2898e-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2898e-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="2898e-131">N/A</span><span class="sxs-lookup"><span data-stu-id="2898e-131">N/A</span></span>                        |
| <span data-ttu-id="2898e-132">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="2898e-132">EmbeddedResource</span></span>  | <span data-ttu-id="2898e-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="2898e-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="2898e-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2898e-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="2898e-135">N/A</span><span class="sxs-lookup"><span data-stu-id="2898e-135">N/A</span></span>                        |
| <span data-ttu-id="2898e-136">없음</span><span class="sxs-lookup"><span data-stu-id="2898e-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="2898e-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="2898e-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="2898e-138">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="2898e-138">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="2898e-139">프로젝트에 GLOB가 있고 최신 SDK를 사용하여 빌드하려는 경우 다음 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-139">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="2898e-140">중복된 컴파일 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-140">Duplicate Compile items were included.</span></span> <span data-ttu-id="2898e-141">.NET SDK에는 기본적으로 프로젝트 디렉터리의 컴파일 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-141">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="2898e-142">프로젝트 파일에서 이러한 항목을 제거하거나, 프로젝트 파일에서 이러한 항목을 명시적으로 포함하려면 'EnableDefaultCompileItems' 속성을 'false'로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="2898e-143">이 오류를 해결하려면 이전 표에 나열된 항목과 일치하는 명시적인 `Compile` 항목을 제거하거나 다음과 같이 `<EnableDefaultCompileItems>` 속성을 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-143">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="2898e-144">이 속성을 `false`로 설정하면 암시적인 포함이 사용되지 않도록 설정되고, 프로젝트에서 기본 GLOB를 지정해야 했던 이전 SDK로 동작이 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-144">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="2898e-145">이러한 변경으로 인해 다른 포함 항목의 기본 메커니즘이 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-145">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="2898e-146">그러나 예를 들어 일부 파일을 지정하여 앱에 게시하려는 경우 해당 사항에 대해 *csproj*의 알려진 메커니즘을 계속 사용할 수 있습니다(예: `<Content>` 요소).</span><span class="sxs-lookup"><span data-stu-id="2898e-146">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="2898e-147">`<EnableDefaultCompileItems>`는 `Compile` glob를 비활성화하지만 암시적 `None` glob와 같은 다른 glob에 영향을 주지 않습니다. \*.cs 항목에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-147">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="2898e-148">따라서 **솔루션 탐색기**는 `None` 항목으로 포함된 프로젝트의 일부로 \*.cs 항목을 계속해서 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-148">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="2898e-149">이와 비슷한 방식으로 `<EnableDefaultNoneItems>`를 사용하여 암시적 `None` glob를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-149">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="2898e-150">**모든 암시적 glob**를 비활성화하기 위해 다음 예제와 같이 `<EnableDefaultItems>` 속성을 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-150">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="2898e-151">MSBuild에서 보는 것처럼 전체 프로젝트를 보는 방법</span><span class="sxs-lookup"><span data-stu-id="2898e-151">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="2898e-152">해당 csproj 변경 내용은 프로젝트 파일을 크게 간소화하지만 SDK 및 해당 대상이 포함된 후 MSBuild에서 보는 것처럼 완전히 확장된 프로젝트를 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-152">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="2898e-153">가져온 파일, 해당 소스 및 실제로 프로젝트를 빌드하지 않는 빌드에 대한 기여를 보여 주는 [`dotnet msbuild`](dotnet-msbuild.md) 명령의 [`/pp` 스위치](/visualstudio/msbuild/msbuild-command-line-reference#preprocess)를 사용하여 프로젝트를 전처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-153">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="2898e-154">프로젝트에 대상 프레임워크가 여러 개 있는 경우 명령의 결과는 대상을 MSBuild 속성으로 지정하여 대상 프레임워크 중 하나에만 초점을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-154">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="2898e-155">추가</span><span class="sxs-lookup"><span data-stu-id="2898e-155">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="2898e-156">SDK 특성</span><span class="sxs-lookup"><span data-stu-id="2898e-156">Sdk attribute</span></span> 
<span data-ttu-id="2898e-157">*.csproj* 파일의 루트 `<Project>` 요소에 `Sdk`라고 하는 새 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-157">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="2898e-158">`Sdk`는 프로젝트에서 사용될 SDK를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-158">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="2898e-159">[레이어 문서](cli-msbuild-architecture.md)에 설명된 것처럼 SDK는 .NET Core 코드를 빌드할 수 있는 MSBuild [작업](/visualstudio/msbuild/msbuild-tasks) 및 [대상](/visualstudio/msbuild/msbuild-targets)의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-159">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="2898e-160">.NET Core 도구와 함께 다음 세 가지 주요 SDK가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-160">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="2898e-161">`Microsoft.NET.Sdk`의 ID와 함께 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2898e-161">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="2898e-162">`Microsoft.NET.Sdk.Web`의 ID와 함께 .NET Core 웹 SDK</span><span class="sxs-lookup"><span data-stu-id="2898e-162">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="2898e-163">`Microsoft.NET.Sdk.Razor`의 ID와 함께 .NET Core Razor 클래스 라이브러리 SDK</span><span class="sxs-lookup"><span data-stu-id="2898e-163">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="2898e-164">.NET Core 도구를 사용하고 코드를 빌드하려면 `<Project>` 요소의 해당 ID 중 하나에 대한 `Sdk` 특성 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-164">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="2898e-165">PackageReference</span><span class="sxs-lookup"><span data-stu-id="2898e-165">PackageReference</span></span>
<span data-ttu-id="2898e-166">프로젝트의 NuGet 종속성을 지정하는 `<PackageReference>` 항목 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-166">A `<PackageReference>` item element specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="2898e-167">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-167">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="2898e-168">버전</span><span class="sxs-lookup"><span data-stu-id="2898e-168">Version</span></span>
<span data-ttu-id="2898e-169">`Version`은 복원할 패키지 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-169">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="2898e-170">이 특성은 [NuGet 버전 지정](/nuget/create-packages/dependency-versions#version-ranges) 체계의 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-170">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="2898e-171">기본 동작은 정확한 버전 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-171">The default behavior is an exact version match.</span></span> <span data-ttu-id="2898e-172">예를 들어 `Version="1.2.3"`을 지정하는 것은 정확한 1.2.3 버전의 패키지에 대한 NuGet 표기법 `[1.2.3]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-172">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="2898e-173">IncludeAssets, ExcludeAssets 및 PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="2898e-173">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="2898e-174">`IncludeAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-174">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="2898e-175">`ExcludeAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용하면 안 되는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-175">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="2898e-176">`PrivateAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용하지만 다음 프로젝트로 전달하지 말아야 하는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-176">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="2898e-177">`PrivateAssets`는 *project.json*/*xproj* `SuppressParent` 요소와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-177">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="2898e-178">이러한 특성은 다음 항목 중 하나 이상을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-178">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="2898e-179">`Compile` - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-179">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="2898e-180">`Runtime` - 런타임 폴더의 콘텐츠가 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-180">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="2898e-181">`ContentFiles` - *contentfiles* 폴더의 콘텐츠가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-181">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="2898e-182">`Build` - 빌드 폴더의 속성/대상이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-182">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="2898e-183">`Native` - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-183">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="2898e-184">`Analyzers` – 분석기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-184">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="2898e-185">또는 다음 특성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-185">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="2898e-186">`None` – 자산이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-186">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="2898e-187">`All` – 모든 자산이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-187">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="2898e-188">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="2898e-188">DotNetCliToolReference</span></span>
<span data-ttu-id="2898e-189">`<DotNetCliToolReference>` 항목 요소는 사용자가 프로젝트의 컨텍스트에서 복원할 CLI 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-189">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="2898e-190">이 요소는 *project.json*의 `tools` 노드를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-190">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="2898e-191">버전</span><span class="sxs-lookup"><span data-stu-id="2898e-191">Version</span></span>
<span data-ttu-id="2898e-192">`Version`은 복원할 패키지 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-192">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="2898e-193">이 특성은 [NuGet 버전 지정](/nuget/create-packages/dependency-versions#version-ranges) 체계의 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-193">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="2898e-194">기본 동작은 정확한 버전 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-194">The default behavior is an exact version match.</span></span> <span data-ttu-id="2898e-195">예를 들어 `Version="1.2.3"`을 지정하는 것은 정확한 1.2.3 버전의 패키지에 대한 NuGet 표기법 `[1.2.3]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-195">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="2898e-196">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2898e-196">RuntimeIdentifiers</span></span>
<span data-ttu-id="2898e-197">`<RuntimeIdentifiers>` 속성 요소를 사용하면 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-197">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="2898e-198">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-198">RIDs enable publishing self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="2898e-199">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="2898e-199">RuntimeIdentifier</span></span>
<span data-ttu-id="2898e-200">`<RuntimeIdentifier>` 속성 요소를 사용하면 프로젝트의 [RID(런타임 식별자)](../rid-catalog.md)를 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-200">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="2898e-201">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-201">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="2898e-202">여러 런타임에 게시해야 하는 경우 `<RuntimeIdentifiers>`(복수)를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2898e-202">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="2898e-203">단일 런타임만 필요한 경우에는 `<RuntimeIdentifier>`를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-203">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="2898e-204">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="2898e-204">PackageTargetFallback</span></span> 
<span data-ttu-id="2898e-205">`<PackageTargetFallback>` 속성 요소를 사용하면 패키지를 복원할 때 사용할 호환 가능한 대상 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-205">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="2898e-206">이는 dotnet [TxM(대상 x 모니커)](/nuget/schema/target-frameworks)을 사용하는 패키지가 dotnet TxM을 선언하지 않은 패키지와 작동하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-206">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="2898e-207">프로젝트에서 dotnet TxM을 사용하는 경우 프로젝트에 `<PackageTargetFallback>`을 추가하여 dotnet이 아닌 플랫폼이 dotnet과 호환되도록 허용하지 않는 이상, 프로젝트에 사용하는 모든 패키지에도 dotnet TxM이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-207">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="2898e-208">다음 예제에서는 프로젝트의 모든 대상에 대한 대체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-208">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="2898e-209">다음 예제에서는 `netcoreapp2.1` 대상에 대해서만 대체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-209">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="2898e-210">NuGet 메타데이터 속성</span><span class="sxs-lookup"><span data-stu-id="2898e-210">NuGet metadata properties</span></span>
<span data-ttu-id="2898e-211">MSBuild로 전환하면서 NuGet 패키지를 압축할 때 사용되는 입력 메타데이터를 *project.json*에서 *.csproj* 파일로 전환했습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-211">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="2898e-212">이 입력은 MSBuild 속성이므로 `<PropertyGroup>` 그룹 내에서 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-212">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="2898e-213">다음은 `dotnet pack` 명령 또는 SDK의 일부인 `Pack` MSBuild 대상을 사용할 때 압축 프로세스의 입력으로 사용되는 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-213">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="2898e-214">IsPackable</span><span class="sxs-lookup"><span data-stu-id="2898e-214">IsPackable</span></span>
<span data-ttu-id="2898e-215">프로젝트를 압축할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-215">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="2898e-216">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-216">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="2898e-217">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="2898e-217">PackageVersion</span></span>
<span data-ttu-id="2898e-218">결과 패키지의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-218">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="2898e-219">모든 형식의 NuGet 버전 문자열을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-219">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="2898e-220">기본값은 `$(Version)`의 값입니다. 즉 프로젝트에서 `Version` 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-220">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="2898e-221">PackageId</span><span class="sxs-lookup"><span data-stu-id="2898e-221">PackageId</span></span>
<span data-ttu-id="2898e-222">결과 패키지의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-222">Specifies the name for the resulting package.</span></span> <span data-ttu-id="2898e-223">지정하지 않으면 `pack` 작업에서 기본값으로 `AssemblyName`을 사용하거나 패키지 이름으로 디렉터리 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-223">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="2898e-224">제목</span><span class="sxs-lookup"><span data-stu-id="2898e-224">Title</span></span>
<span data-ttu-id="2898e-225">사람들에게 친숙한 패키지 제목이며 보통 nuget.org 및 Visual Studio의 패키지 관리자에서 UI 표시에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-225">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="2898e-226">지정하지 않으면 패키지 ID가 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-226">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="2898e-227">만든 이</span><span class="sxs-lookup"><span data-stu-id="2898e-227">Authors</span></span>
<span data-ttu-id="2898e-228">nuget.org에서 프로필 이름과 일치하는, 세미콜론으로 구분된 패키지 작성자 목록입니다. 이러한 목록은 nuget.org의 NuGet 갤러리에 표시되고 동일한 작성자가 패키지를 상호 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-228">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="2898e-229">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="2898e-229">PackageDescription</span></span>

<span data-ttu-id="2898e-230">UI 표시를 위한 패키지에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-230">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="2898e-231">설명</span><span class="sxs-lookup"><span data-stu-id="2898e-231">Description</span></span>
<span data-ttu-id="2898e-232">어셈블리에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-232">A long description for the assembly.</span></span> <span data-ttu-id="2898e-233">`PackageDescription`을 지정하지 않으면 이 속성이 패키지 설명으로도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-233">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="2898e-234">Copyright</span><span class="sxs-lookup"><span data-stu-id="2898e-234">Copyright</span></span>
<span data-ttu-id="2898e-235">패키지에 대한 저작권 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-235">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="2898e-236">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="2898e-236">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="2898e-237">클라이언트에서, 소비자가 패키지를 설치하기 전에 패키지 라이선스에 동의하도록 물어야 할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-237">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="2898e-238">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-238">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="2898e-239">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="2898e-239">PackageLicenseUrl</span></span>
<span data-ttu-id="2898e-240">패키지에 적용되는 라이선스에 대한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-240">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="2898e-241">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="2898e-241">PackageProjectUrl</span></span>
<span data-ttu-id="2898e-242">nuget.org뿐만 아니라 종종 UI 표시에 표시되는 패키지의 홈페이지에 대한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-242">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="2898e-243">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="2898e-243">PackageIconUrl</span></span>
<span data-ttu-id="2898e-244">UI 표시에서 패키지에 대한 아이콘으로 사용하는 투명한 배경의 64x64 이미지에 대한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-244">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="2898e-245">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="2898e-245">PackageReleaseNotes</span></span>
<span data-ttu-id="2898e-246">패키지에 대한 릴리스 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-246">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="2898e-247">PackageTags</span><span class="sxs-lookup"><span data-stu-id="2898e-247">PackageTags</span></span>
<span data-ttu-id="2898e-248">패키지를 지정하는 세미콜론으로 구분된 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-248">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="2898e-249">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="2898e-249">PackageOutputPath</span></span>
<span data-ttu-id="2898e-250">압축된 패키지가 삭제되는 출력 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-250">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="2898e-251">기본값은 `$(OutputPath)`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-251">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="2898e-252">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="2898e-252">IncludeSymbols</span></span>
<span data-ttu-id="2898e-253">이 부울 값은 프로젝트가 압축될 때 패키지에서 추가 기호 패키지를 만들어야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-253">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="2898e-254">이 패키지에는 *. symbols.nupkg* 확장이 있으며 DLL 및 기타 출력 파일과 함께 PDB 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-254">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="2898e-255">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="2898e-255">IncludeSource</span></span>
<span data-ttu-id="2898e-256">이 부울 값은 팩 프로세스에서 소스 패키지를 만들어야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-256">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="2898e-257">소스 패키지에는 PDB 파일뿐만 아니라 라이브러리의 소스 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-257">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="2898e-258">소스 파일은 결과 패키지 파일의 `src/ProjectName` 디렉터리 아래에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-258">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="2898e-259">IsTool</span><span class="sxs-lookup"><span data-stu-id="2898e-259">IsTool</span></span>
<span data-ttu-id="2898e-260">모든 출력 파일이 *lib* 폴더 대신 *tools* 폴더에 복사되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-260">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="2898e-261">이것은 *.csproj* 파일에서 `PackageType`을 설정하여 지정하는 `DotNetCliTool`과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-261">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="2898e-262">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="2898e-262">RepositoryUrl</span></span>
<span data-ttu-id="2898e-263">패키지에 대한 소스 코드 및/또는 빌드 중인 소스 코드가 있는 리포지토리의 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-263">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="2898e-264">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="2898e-264">RepositoryType</span></span>
<span data-ttu-id="2898e-265">리포지토리의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-265">Specifies the type of the repository.</span></span> <span data-ttu-id="2898e-266">기본값은 "git"입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-266">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="2898e-267">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="2898e-267">NoPackageAnalysis</span></span>
<span data-ttu-id="2898e-268">패키지를 빌드한 후 팩에서 패키지 분석을 실행하지 않아야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-268">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="2898e-269">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="2898e-269">MinClientVersion</span></span>
<span data-ttu-id="2898e-270">nuget.exe 및 Visual Studio 패키지 관리자에 의해 적용되는, 이 패키지를 설치할 수 있는 NuGet 클라이언트의 최소 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-270">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="2898e-271">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="2898e-271">IncludeBuildOutput</span></span>
<span data-ttu-id="2898e-272">이 부울 값은 빌드 출력 어셈블리를 *.nupkg* 파일에 압축해야 할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-272">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="2898e-273">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="2898e-273">IncludeContentInPack</span></span>
<span data-ttu-id="2898e-274">이 부울 값은 `Content` 형식이 있는 항목이 결과 패키지에 자동으로 포함될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-274">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="2898e-275">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-275">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="2898e-276">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="2898e-276">BuildOutputTargetFolder</span></span>
<span data-ttu-id="2898e-277">출력 어셈블리를 배치할 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-277">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="2898e-278">출력 어셈블리(및 기타 출력 파일)는 해당 프레임워크 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-278">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="2898e-279">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="2898e-279">ContentTargetFolders</span></span>
<span data-ttu-id="2898e-280">이 속성은 `PackagePath`가 지정되지 않은 경우 모든 콘텐츠 파일의 기본 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-280">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="2898e-281">기본값은 "content;contentFiles"입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-281">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="2898e-282">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="2898e-282">NuspecFile</span></span>
<span data-ttu-id="2898e-283">압축에 사용되는 *.nuspec* 파일에 대한 상대 또는 절대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-283">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="2898e-284">*.nuspec* 파일이 지정된 경우 패키징 정보에 대해 **단독으로** 사용되며 프로젝트의 모든 정보는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-284">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="2898e-285">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="2898e-285">NuspecBasePath</span></span>
<span data-ttu-id="2898e-286">*.nuspec* 파일에 대한 기본 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-286">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="2898e-287">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="2898e-287">NuspecProperties</span></span>
<span data-ttu-id="2898e-288">key=value 쌍의 세미콜론으로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-288">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="2898e-289">AssemblyInfo 속성</span><span class="sxs-lookup"><span data-stu-id="2898e-289">AssemblyInfo properties</span></span>
<span data-ttu-id="2898e-290">일반적으로 *AssemblyInfo* 파일에 있는 [어셈블리 특성](../../framework/app-domains/set-assembly-attributes.md)은 이제 속성에서 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-290">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="2898e-291">특성별 속성</span><span class="sxs-lookup"><span data-stu-id="2898e-291">Properties per attribute</span></span>

<span data-ttu-id="2898e-292">각 특성에는 해당 콘텐츠를 제어하는 속성과 다음 표에 표시된 대로 생성을 사용하지 않도록 설정하는 또 다른 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-292">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="2898e-293">특성</span><span class="sxs-lookup"><span data-stu-id="2898e-293">Attribute</span></span>                                                      | <span data-ttu-id="2898e-294">속성</span><span class="sxs-lookup"><span data-stu-id="2898e-294">Property</span></span>               | <span data-ttu-id="2898e-295">사용하지 않도록 설정할 속성</span><span class="sxs-lookup"><span data-stu-id="2898e-295">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="2898e-296">메모:</span><span class="sxs-lookup"><span data-stu-id="2898e-296">Notes:</span></span>

* <span data-ttu-id="2898e-297">`AssemblyVersion` 및 `FileVersion` 기본값은 접미사 없이 `$(Version)` 값을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-297">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="2898e-298">예를 들어 `$(Version)`가 `1.2.3-beta.4`인 경우 값은 `1.2.3`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-298">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="2898e-299">`InformationalVersion`은 기본적으로 `$(Version)` 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-299">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="2898e-300">속성이 있는 경우 `InformationalVersion`에 `$(SourceRevisionId)`가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-300">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="2898e-301">`IncludeSourceRevisionInInformationalVersion`을 사용하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-301">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="2898e-302">`Copyright` 및 `Description` 속성도 NuGet 메타데이터에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-302">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="2898e-303">`Configuration`은 모든 빌드 프로세스와 공유되고 `dotnet` 명령의 `--configuration` 매개 변수를 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-303">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="2898e-304">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="2898e-304">GenerateAssemblyInfo</span></span> 
<span data-ttu-id="2898e-305">모든 AssemblyInfo 생성을 사용하거나 사용하지 않도록 설정하는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-305">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="2898e-306">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-306">The default value is `true`.</span></span> 

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="2898e-307">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="2898e-307">GeneratedAssemblyInfoFile</span></span> 
<span data-ttu-id="2898e-308">생성된 어셈블리 정보 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-308">The path of the generated assembly info file.</span></span> <span data-ttu-id="2898e-309">기본적으로 `$(IntermediateOutputPath)`(obj) 디렉터리의 파일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2898e-309">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
