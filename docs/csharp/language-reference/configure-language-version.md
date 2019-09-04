---
title: C# 언어 버전 관리 - C# 가이드
description: 프로젝트에 따라 C# 언어 버전이 결정되는 방법과 수동으로 조정할 수 있는 다양한 값에 대해 알아봅니다.
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040343"
---
# <a name="c-language-versioning"></a><span data-ttu-id="ebaa8-103">C# 언어 버전 관리</span><span class="sxs-lookup"><span data-stu-id="ebaa8-103">C# language versioning</span></span>

<span data-ttu-id="ebaa8-104">최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="ebaa8-105">C# 언어는 모든 .NET 구현에서 사용할 수 없는 유형 또는 런타임 구성 요소를 사용하는 기능이 있을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="ebaa8-106">또한 프로젝트가 빌드된 대상에 상관없이 기본적으로 가장 호환성이 높은 언어 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="ebaa8-107">이 문서의 규칙은 Visual Studio 2019 또는 .NET Core 3.0 SDK와 함께 제공되는 컴파일러에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="ebaa8-108">Visual Studio 2017 설치 또는 이전 .NET Core SDK 버전의 일부인 C# 컴파일러는 기본적으로 C# 7.0을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="ebaa8-109">기본값</span><span class="sxs-lookup"><span data-stu-id="ebaa8-109">Defaults</span></span>

<span data-ttu-id="ebaa8-110">컴파일러는 다음 규칙에 따라 기본값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="ebaa8-111">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="ebaa8-111">Target framework</span></span>|<span data-ttu-id="ebaa8-112">버전</span><span class="sxs-lookup"><span data-stu-id="ebaa8-112">version</span></span>|<span data-ttu-id="ebaa8-113">C# 언어 버전 기본값</span><span class="sxs-lookup"><span data-stu-id="ebaa8-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="ebaa8-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="ebaa8-114">.NET Core</span></span>|<span data-ttu-id="ebaa8-115">3.x</span><span class="sxs-lookup"><span data-stu-id="ebaa8-115">3.x</span></span>|<span data-ttu-id="ebaa8-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="ebaa8-116">C# 8.0</span></span>|
|<span data-ttu-id="ebaa8-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="ebaa8-117">.NET Core</span></span>|<span data-ttu-id="ebaa8-118">2.x</span><span class="sxs-lookup"><span data-stu-id="ebaa8-118">2.x</span></span>|<span data-ttu-id="ebaa8-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="ebaa8-119">C# 7.3</span></span>|
|<span data-ttu-id="ebaa8-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="ebaa8-120">.NET Standard</span></span>|<span data-ttu-id="ebaa8-121">모두</span><span class="sxs-lookup"><span data-stu-id="ebaa8-121">all</span></span>|<span data-ttu-id="ebaa8-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="ebaa8-122">C# 7.3</span></span>|
|<span data-ttu-id="ebaa8-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ebaa8-123">.NET Framework</span></span>|<span data-ttu-id="ebaa8-124">모두</span><span class="sxs-lookup"><span data-stu-id="ebaa8-124">all</span></span>|<span data-ttu-id="ebaa8-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="ebaa8-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="ebaa8-126">미리 보기에 대한 기본값</span><span class="sxs-lookup"><span data-stu-id="ebaa8-126">Default for previews</span></span>

<span data-ttu-id="ebaa8-127">프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="ebaa8-128">이렇게 하면 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않고 모든 환경에서 해당 미리 보기로 작업할 수 있는 최신 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="ebaa8-129">기본값 재정의</span><span class="sxs-lookup"><span data-stu-id="ebaa8-129">Override a default</span></span>

<span data-ttu-id="ebaa8-130">C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="ebaa8-131">[프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="ebaa8-132">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="ebaa8-133">[`-langversion` 컴파일러 옵션](compiler-options/langversion-compiler-option.md) 구성</span><span class="sxs-lookup"><span data-stu-id="ebaa8-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="ebaa8-134">프로젝트 파일 편집</span><span class="sxs-lookup"><span data-stu-id="ebaa8-134">Edit the project file</span></span>

<span data-ttu-id="ebaa8-135">프로젝트 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-135">You can set the language version in your project file.</span></span> <span data-ttu-id="ebaa8-136">예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="ebaa8-137">값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="ebaa8-138">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="ebaa8-138">Configure multiple projects</span></span>

<span data-ttu-id="ebaa8-139">`<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들어 여러 디렉터리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="ebaa8-140">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="ebaa8-141">솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="ebaa8-142">이제 해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="ebaa8-143">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="ebaa8-144">C# 언어 버전 참조</span><span class="sxs-lookup"><span data-stu-id="ebaa8-144">C# language version reference</span></span>

<span data-ttu-id="ebaa8-145">모든 표는 현재 C# 언어 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="ebaa8-146">컴파일러가 오래된 것이라면 모든 값을 반드시 파악하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="ebaa8-147">.NET Core 3.0을 설치하면 나열된 모든 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="ebaa8-148">값</span><span class="sxs-lookup"><span data-stu-id="ebaa8-148">Value</span></span>|<span data-ttu-id="ebaa8-149">의미</span><span class="sxs-lookup"><span data-stu-id="ebaa8-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="ebaa8-150">미리 보기</span><span class="sxs-lookup"><span data-stu-id="ebaa8-150">preview</span></span>|<span data-ttu-id="ebaa8-151">컴파일러가 최신 미리 보기 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="ebaa8-152">latest</span><span class="sxs-lookup"><span data-stu-id="ebaa8-152">latest</span></span>|<span data-ttu-id="ebaa8-153">컴파일러가 최신 릴리스 버전(부 버전 포함)의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="ebaa8-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="ebaa8-154">latestMajor</span></span>|<span data-ttu-id="ebaa8-155">컴파일러가 최신 릴리스 주 버전의 구문을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="ebaa8-156">8.0</span><span class="sxs-lookup"><span data-stu-id="ebaa8-156">8.0</span></span>|<span data-ttu-id="ebaa8-157">컴파일러는 C# 8.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-158">7.3</span><span class="sxs-lookup"><span data-stu-id="ebaa8-158">7.3</span></span>|<span data-ttu-id="ebaa8-159">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="ebaa8-160">7.2</span><span class="sxs-lookup"><span data-stu-id="ebaa8-160">7.2</span></span>|<span data-ttu-id="ebaa8-161">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="ebaa8-162">7.1</span><span class="sxs-lookup"><span data-stu-id="ebaa8-162">7.1</span></span>|<span data-ttu-id="ebaa8-163">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="ebaa8-164">7</span><span class="sxs-lookup"><span data-stu-id="ebaa8-164">7</span></span>|<span data-ttu-id="ebaa8-165">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-166">6</span><span class="sxs-lookup"><span data-stu-id="ebaa8-166">6</span></span>|<span data-ttu-id="ebaa8-167">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-168">5</span><span class="sxs-lookup"><span data-stu-id="ebaa8-168">5</span></span>|<span data-ttu-id="ebaa8-169">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-170">4</span><span class="sxs-lookup"><span data-stu-id="ebaa8-170">4</span></span>|<span data-ttu-id="ebaa8-171">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-172">3</span><span class="sxs-lookup"><span data-stu-id="ebaa8-172">3</span></span>|<span data-ttu-id="ebaa8-173">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="ebaa8-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="ebaa8-174">ISO-2</span></span>|<span data-ttu-id="ebaa8-175">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="ebaa8-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="ebaa8-176">ISO-1</span></span>|<span data-ttu-id="ebaa8-177">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
