---
title: .NET Core 3.0의 새로운 기능
description: .NET Core 3.0에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: 5f9d7026b270a010d2ba5d4b1165728a100ab6ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922557"
---
# <a name="whats-new-in-net-core-30-preview-8"></a><span data-ttu-id="28f27-103">.NET Core 3.0(Preview 8)의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="28f27-103">What's new in .NET Core 3.0 (Preview 8)</span></span>

<span data-ttu-id="28f27-104">이 문서는 .NET Core 3.0(Preview 8)의 새로운 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-104">This article describes what is new in .NET Core 3.0 (through preview 8).</span></span> <span data-ttu-id="28f27-105">가장 중요한 개선 사항 중 하나는 Windows 데스크톱 애플리케이션에 대한 지원(Windows만 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="28f27-106">.NET Core 3.0 SDK 구성 요소 Windows 데스크톱을 사용하여 Windows Forms 및 Windows Presentation Foundation(WPF) 애플리케이션을 포트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="28f27-107">분명히 말하지만, Windows 데스크톱 구성 요소는 Windows에서만 지원되고 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="28f27-108">자세한 내용은 이 문서 후반부의 [Windows 데스크톱](#windows-desktop) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="28f27-109">.NET Core 3.0에서는 C# 8.0에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="28f27-110">[Visual Studio 미리 보기 최신 릴리스](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview) 또는 OmniSharp 확장이 지원되는 Visual Studio Code를 사용하는 것이 매우 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-110">It's highly recommended that you use the [latest release of Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), or Visual Studio Code with the OmniSharp extension.</span></span>

<span data-ttu-id="28f27-111">Windows, macOS 또는 Linux에서 지금 바로 [.NET Core 3.0 Preview 8을 다운로드하여 시작](https://aka.ms/netcore3download)하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-111">[Download and get started with .NET Core 3.0 preview 8](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="28f27-112">각 미리 보기 릴리스에 대한 자세한 내용은 다음 공지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="28f27-113">.NET Core 3.0 Preview 8 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-113">.NET Core 3.0 Preview 8 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)
- [<span data-ttu-id="28f27-114">.NET Core 3.0 Preview 7 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-114">.NET Core 3.0 Preview 7 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)
- [<span data-ttu-id="28f27-115">.NET Core 3.0 Preview 6 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-115">.NET Core 3.0 Preview 6 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-6/)
- [<span data-ttu-id="28f27-116">.NET Core 3.0 Preview 5 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-116">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="28f27-117">.NET Core 3.0 Preview 4 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-117">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="28f27-118">.NET Core 3.0 Preview 3 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-118">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="28f27-119">.NET Core 3.0 Preview 2 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-119">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="28f27-120">.NET Core 3.0 Preview 1 공지 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-120">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="production-supported-preview"></a><span data-ttu-id="28f27-121">프로덕션 지원 미리 보기</span><span class="sxs-lookup"><span data-stu-id="28f27-121">Production supported preview</span></span>

<span data-ttu-id="28f27-122">.NET Core Preview 8은 Microsoft에서 준비하는 프로덕션으로 간주되며 완벽하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-122">.NET Core Preview 8 is considered production ready by Microsoft and is fully supported.</span></span> <span data-ttu-id="28f27-123">Preview 7부터 릴리스는 새 기능을 추가하는 대신 .NET Core 3.0을 개선하는 데 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-123">Starting with preview 7, releases will focus on polishing .NET Core 3.0 instead of adding new features.</span></span> <span data-ttu-id="28f27-124">Preview 8에서 변경된 내용에 관한 자세한 내용은 [Preview 8 공지 사항](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-124">For more information about what has changed in preview 8, see the [preview 8 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/).</span></span>

<span data-ttu-id="28f27-125">이전 미리 보기 릴리스를 사용하는 경우 “Go Live” 지원을 계속하려면 Preview 8로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-125">If you're using a previous preview release, you must move to Preview 8 for continued "Go Live" support.</span></span>

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="28f27-126">.NET Core SDK Windows Installer</span><span class="sxs-lookup"><span data-stu-id="28f27-126">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="28f27-127">Windows용 MSI 설치 관리자는 .NET Core 3.0부터 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-127">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="28f27-128">이제 SDK 설치 관리자는 준비된 SDK 기반 밴드 릴리스를 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-128">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="28f27-129">기능 밴드는 번호 버전의 *패치* 섹션에서 *수백 개*의 그룹에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-129">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="28f27-130">예를 들어, **3.0._101_** 및 **3.0._201_** 은 두 가지 기능 밴드의 버전이며, **3.0._101_** 및 **3.0._199_** 는 동일한 기능 밴드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-130">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="28f27-131">그리고 .NET Core SDK **3.0._101_** 이 설치되어 있는 경우 .NET Core SDK**3.0._100_** 은 머신에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-131">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="28f27-132">.NET Core SDK **3.0._200_** 이 동일한 머신에 설치되어 있는 경우 .NET Core SDK **3.0._101_** 은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-132">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="28f27-133">버전 관리에 대한 자세한 내용은 [.NET Core의 버전 관리 방법](../versions/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-133">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="28f27-134">C# 8.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="28f27-134">C# 8.0 preview</span></span>

<span data-ttu-id="28f27-135">.NET Core 3.0은 C# 8 미리 보기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-135">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="28f27-136">C# 8.0 기능에 대한 자세한 내용은 [C# 8.0의 새로운 기능](../../csharp/whats-new/csharp-8.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-136">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="28f27-137">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="28f27-137">.NET Standard 2.1</span></span>

<span data-ttu-id="28f27-138">.NET Core 3.0이 **.NET 표준 2.1**을 지원하는 경우에도 기본 `dotnet new classlib` 템플릿은 **.NET 표준 2.0**을 대상으로 지정하는 프로젝트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-138">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="28f27-139">**.NET 표준 2.1**을 대상으로 지정하려면 프로젝트 파일을 편집하고 `TargetFramework` 속성을 `netstandard2.1`로 변경하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-139">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="28f27-140">Visual Studio를 사용하고 있는 경우 Visual Studio 2017은 **.NET Standard 2.1** 또는 **.NET Core 3.0**을 지원하지 않으므로 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-140">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="28f27-141">향상된 .NET Core Version API</span><span class="sxs-lookup"><span data-stu-id="28f27-141">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="28f27-142">.NET Core 3.0부터 .NET Core에 제공된 버전 API가 이제 사용자가 예상하는 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-142">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="28f27-143">예:</span><span class="sxs-lookup"><span data-stu-id="28f27-143">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="28f27-144">주요 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="28f27-144">Breaking change.</span></span> <span data-ttu-id="28f27-145">버전 관리 체계 변경되었기 때문에 엄밀히 따지면 주요 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-145">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="28f27-146">.NET 플랫폼 종속 내장 함수</span><span class="sxs-lookup"><span data-stu-id="28f27-146">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="28f27-147">**SIMD** 또는 **비트 조작 명령어** 세트와 같은 특정 perf-oriented CPU 명령어에 대한 액세스를 허용하는 API가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-147">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="28f27-148">이러한 명령어를 사용하면 특정 시나리오(효율적인 데이터 병렬 처리)에서 성능을 크게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-148">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="28f27-149">적절한 경우 .NET 라이브러리는 성능을 개선하기 위해 이러한 명령을 사용하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-149">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="28f27-150">자세한 내용은 [.NET 플랫폼 종속 내장 함수](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-150">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="28f27-151">기본 실행 파일</span><span class="sxs-lookup"><span data-stu-id="28f27-151">Default executables</span></span>

<span data-ttu-id="28f27-152">이제 .NET Core에서 기본적으로 [프레임워크 종속 실행 파일](../deploying/index.md#framework-dependent-executables-fde)을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-152">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="28f27-153">이는 전역적으로 설치된 .NET Core 버전을 사용하는 애플리케이션을 위한 새로운 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-153">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="28f27-154">지금까지는 [자체 포함 배포](../deploying/index.md#self-contained-deployments-scd)만 실행 파일을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-154">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="28f27-155">사용 중인 SDK의 환경 및 플랫폼과 일치하는 경우 `dotnet build` 또는 `dotnet publish` 중에 실행 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-155">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="28f27-156">다른 네이티브 실행 파일과 마찬가지로 이러한 실행 파일에서도 다음과 같은 동일한 기능을 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-156">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="28f27-157">실행 파일을 두 번 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-157">You can double-click on the executable.</span></span>
- <span data-ttu-id="28f27-158">Windows의 `myapp.exe`, Linux 및 macOS의 `./myapp`과 같은 애플리케이션을 명령 프롬프트에서 직접 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-158">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="28f27-159">단일 실행 파일</span><span class="sxs-lookup"><span data-stu-id="28f27-159">Single-file executables</span></span>

<span data-ttu-id="28f27-160">`dotnet publish` 명령은 플랫폼별 단일 실행 파일로 앱 패키징을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-160">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="28f27-161">실행 파일은 자동 압축 풀기 파일이며 앱을 실행하는 데 필요한 모든 종속 항목(네이티브 포함)을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-161">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="28f27-162">앱을 처음 실행하면 애플리케이션은 앱 이름과 빌드 식별자에 기반하여 디렉터리로 압축이 풀립니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-162">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="28f27-163">해당 애플리케이션을 다시 실행하면 시작이 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-163">Startup is faster when the application is run again.</span></span> <span data-ttu-id="28f27-164">새 버전을 사용한 경우가 아니라면 두 번째에는 애플리케이션의 압축을 풀 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-164">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="28f27-165">단일 실행 파일을 게시하려면 `dotnet publish` 명령을 사용하여 프로젝트 또는 명령줄에 `PublishSingleFile`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-165">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="28f27-166">또는</span><span class="sxs-lookup"><span data-stu-id="28f27-166">-or-</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="28f27-167">단일 파일 게시에 대한 자세한 내용은 [단일 파일 번들러 설계 문서](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-167">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="assembly-linking"></a><span data-ttu-id="28f27-168">어셈블리 연결</span><span class="sxs-lookup"><span data-stu-id="28f27-168">Assembly linking</span></span>

<span data-ttu-id="28f27-169">.NET Core SDK 3.0에는 IL을 분석하고 사용되지 않는 어셈블리를 잘라내어 앱의 크기를 줄일 수 있는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-169">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="28f27-170">자체 포함 앱에는 호스트 컴퓨터에 .NET을 설치하지 않고도 코드를 실행하는 데 필요한 모든 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-170">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="28f27-171">그러나 앱을 실행하는 데 프레임워크의 작은 하위 집합만 필요한 경우가 많으므로 사용되지 않는 다른 라이브러리를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-171">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="28f27-172">이제 .NET Core에 [IL 링커](https://github.com/mono/linker) 도구를 사용하여 앱의 IL을 검사하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-172">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="28f27-173">이 도구는 필요한 코드를 검색한 다음, 사용되지 않는 라이브러리를 잘라냅니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-173">this tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="28f27-174">이 도구를 통해 일부 앱의 배포 크기를 훨씬 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-174">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="28f27-175">이 도구를 사용하려면 프로젝트에서 `<PublishTrimmed>` 설정을 추가하고 자체 포함 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-175">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```console
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="28f27-176">예를 들어 포함된 기본 “hello world” 새 콘솔 프로젝트 템플릿은 게시될 때 크기가 약 70MB입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-176">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="28f27-177">`<PublishTrimmed>`를 사용하면 크기가 약 30MB로 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-177">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="28f27-178">잘라낼 때 리플렉션이나 관련된 동적 기능을 사용하는 애플리케이션 또는 프레임워크 (ASP.NET Core, WPF 등)가 중단되는 경우가 많다는 것을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-178">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="28f27-179">이러한 중단은 링커에서 이 동적 동작을 알지 못하고 리플렉션에 필요한 프레임워크 유형을 확인할 수 없기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-179">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="28f27-180">이 시나리오를 인식하도록 IL 링커 도구를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-180">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="28f27-181">무엇보다도, 잘라낸 후 앱을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-181">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="28f27-182">IL 링커 도구에 대한 자세한 내용은 [문서](https://aka.ms/dotnet-illink)또는 [mono/linker]( https://github.com/mono/linker) 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-182">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="28f27-183">계층화된 컴파일</span><span class="sxs-lookup"><span data-stu-id="28f27-183">Tiered compilation</span></span>

<span data-ttu-id="28f27-184">[계층화된 컴파일](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/)(TC)은 .NET Core 3.0에서 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-184">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="28f27-185">런타임 시 JIT(Just-In-Time) 컴파일러를 보다 유연하게 사용해서 성능을 선할 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-185">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="28f27-186">TC의 주요 혜택은 품질은 낮지만 빠른 계층의 (재)JIT 메서드 또는 품질은 높지만 느린 계층의 (재)JIT 메서드를 활성화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-186">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="28f27-187">이렇게 하면 시작에서 정적인 상태까지 다양한 실행 단계를 거치므로 애플리케이션의 성능을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-187">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="28f27-188">이점은 모든 메서드가 단일 방식으로 컴파일링되어(고품질 계층과 동일) 시작 성능에 있어 정적인 상태로 편중되는 비-TC 방법과는 대비됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-188">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="28f27-189">빠른 JIT(계층 0 JIT 처리된 코드)를 활성화하려면 프로젝트 파일에서 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-189">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="28f27-190">TC를 완전히 비활성화하려면 프로젝트 파일에서 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-190">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="readytorun-images"></a><span data-ttu-id="28f27-191">ReadyToRun 이미지</span><span class="sxs-lookup"><span data-stu-id="28f27-191">ReadyToRun images</span></span>

<span data-ttu-id="28f27-192">R2R(ReadyToRun) 형식으로 애플리케이션 어셈블리를 컴파일하면 .NET Core 애플리케이의 시작 시간을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-192">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="28f27-193">R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-193">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="28f27-194">R2R 이진 파일은 애플리케이션이 로드될 때 JIT(Just-In-Time) 컴파일러에서 수행해야 하는 작업량을 줄여 시작 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-194">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="28f27-195">이진 파일에는 JIT에서 생성되는 코드와 비슷한 네이티브 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-195">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="28f27-196">그러나 R2R 이진 파일은 일부 시나리오에서 필요한 IL(중간 언어) 코드와 동일한 코드의 네이티브 버전을 모두 포함하므로 크기가 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-196">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="28f27-197">R2R은 Linux x64 또는 Windows x64와 같은 특정 런타임 환경(RID)을 대상으로 하는 자체 포함 앱을 게시하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-197">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="28f27-198">프로젝트를 ReadyToRun으로 컴파일하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-198">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="28f27-199">프로젝트에 `<PublishReadyToRun>` 설정 추가</span><span class="sxs-lookup"><span data-stu-id="28f27-199">Add the `<PublishReadyToRun>` setting to your project</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="28f27-200">자체 포함 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-200">Publish a self-contained app.</span></span> <span data-ttu-id="28f27-201">예를 들어 이 명령은 Windows 64비트 버전용 자체 포함 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-201">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```console
    dotnet publish -c Release -r win-x64 --self-contained true
    ```

### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="28f27-202">교차 플랫폼/아키텍처 제한 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-202">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="28f27-203">현재 ReadyToRun 컴파일러는 교차 대상 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-203">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="28f27-204">지정된 대상에서 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-204">You must compile on a given target.</span></span> <span data-ttu-id="28f27-205">예를 들어 Windows x64용 R2R 이미지를 만들려는 경우 해당 환경에서 게시 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-205">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="28f27-206">교차 대상 지정 예외:</span><span class="sxs-lookup"><span data-stu-id="28f27-206">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="28f27-207">Windows x64를 사용하여 Windows ARM32, ARM64 및 x86 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-207">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="28f27-208">Windows x86을 사용하여 Windows ARM32 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-208">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="28f27-209">Linux X64를 사용하여 Linux ARM32 및 ARM64 이미지를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-209">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="28f27-210">빌드 복사본 종속성</span><span class="sxs-lookup"><span data-stu-id="28f27-210">Build copies dependencies</span></span>

<span data-ttu-id="28f27-211">`dotnet build` 명령은 이제 애플리케이션에 대한 NuGet 종속성을 NuGet 캐시에서 빌드 출력 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-211">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="28f27-212">이전에는 종속성이 `dotnet publish` 중에만 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-212">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="28f27-213">연결, Razor 페이지 게시 등 여전히 게시해야 하는 일부 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-213">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="28f27-214">로컬 도구</span><span class="sxs-lookup"><span data-stu-id="28f27-214">Local tools</span></span>

<span data-ttu-id="28f27-215">.NET core 3.0에서는 로컬 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-215">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="28f27-216">로컬 도구는 [전역 도구](../tools/global-tools.md)와 유사하지만 디스크의 특정 위치와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-216">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="28f27-217">로컬 도구는 전역적으로 사용할 수 없으며 NuGet 패키지로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-217">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="28f27-218">.NET Core 3.0 미리 보기 1에서 `dotnet tool restore` 또는 `dotnet tool install` 삭제와 같은 현지 도구를 사용했다면 로컬 도구 캐시 폴더를 삭제하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-218">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="28f27-219">그렇지 않으면 로컬 도구는 모든 최신 릴리스에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-219">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="28f27-220">이 폴더의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-220">This folder is located at:</span></span>
>
> <span data-ttu-id="28f27-221">macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="28f27-221">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="28f27-222">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="28f27-222">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="28f27-223">로컬 도구는 현재 디렉터리에 있는 매니페스트 파일 이름 `dotnet-tools.json`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-223">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="28f27-224">이 매니페스트 파일은 해당 폴더 및 그 아래에서 사용할 수 있는 도구를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-224">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="28f27-225">코드를 사용하는 누구나 동일한 도구를 복구하고 사용할 수 있도록 코드로 매니페스트 파일을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-225">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="28f27-226">전역 도구와 로컬 도구 둘 다, 호환되는 버전의 런타임이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-226">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="28f27-227">현재 NuGet.org의 많은 도구는 .NET Core 런타임 2.1을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-227">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="28f27-228">이러한 도구를 전역 또는 로컬로 설치하려면 여전히 [NET Core 2.1 런타임](https://dotnet.microsoft.com/download/dotnet-core/2.1)을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-228">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="28f27-229">주 버전 롤포워드</span><span class="sxs-lookup"><span data-stu-id="28f27-229">Major-version Roll Forward</span></span>

<span data-ttu-id="28f27-230">.NET Core 3.0은 애플리케이션을 .NET Core의 최신 주 버전으로 롤포워드할 수 있는 옵트인(opt-in) 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-230">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="28f27-231">또한, 롤포워드가 애플리케이션에 적용되는 방식을 제어하기 위해 새 설정이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-231">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="28f27-232">이 설정은 다음과 같은 방법으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-232">This can be configured in the following ways:</span></span>

- <span data-ttu-id="28f27-233">프로젝트 파일 속성: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="28f27-233">Project file property: `RollForward`</span></span>
- <span data-ttu-id="28f27-234">런타임 구성 파일 속성: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="28f27-234">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="28f27-235">환경 변수: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="28f27-235">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="28f27-236">명령줄 인수: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="28f27-236">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="28f27-237">다음 값 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-237">One of the following values must be specified.</span></span> <span data-ttu-id="28f27-238">설정을 생략하면 **Minor**가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-238">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="28f27-239">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="28f27-239">**LatestPatch**</span></span>\
<span data-ttu-id="28f27-240">가장 높은 패치 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-240">Roll forward to the highest patch version.</span></span> <span data-ttu-id="28f27-241">부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-241">This disables minor version roll forward.</span></span>
- <span data-ttu-id="28f27-242">**Minor**</span><span class="sxs-lookup"><span data-stu-id="28f27-242">**Minor**</span></span>\
<span data-ttu-id="28f27-243">요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-243">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="28f27-244">요청된 부 버전이 있다면 **LatestPatch** 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-244">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="28f27-245">**Major**</span><span class="sxs-lookup"><span data-stu-id="28f27-245">**Major**</span></span>\
<span data-ttu-id="28f27-246">요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-246">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="28f27-247">요청된 주 버전이 있다면 **Minor** 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-247">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="28f27-248">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="28f27-248">**LatestMinor**</span></span>\
<span data-ttu-id="28f27-249">요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-249">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="28f27-250">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-250">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="28f27-251">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="28f27-251">**LatestMajor**</span></span>\
<span data-ttu-id="28f27-252">요청된 주 버전이 있는 경우에도 가장 높은 주, 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-252">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="28f27-253">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-253">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="28f27-254">**Disable**</span><span class="sxs-lookup"><span data-stu-id="28f27-254">**Disable**</span></span>\
<span data-ttu-id="28f27-255">롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-255">Don't roll forward.</span></span> <span data-ttu-id="28f27-256">지정된 버전에만 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-256">Only bind to specified version.</span></span> <span data-ttu-id="28f27-257">이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-257">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="28f27-258">이 값은 테스트용으로만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-258">This value is only recommended for testing.</span></span>

<span data-ttu-id="28f27-259">**Disable** 설정 이외에도 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-259">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="28f27-260">Windows 바탕 화면</span><span class="sxs-lookup"><span data-stu-id="28f27-260">Windows desktop</span></span>

<span data-ttu-id="28f27-261">.NET Core 3.0은 Windows Presentation Foundation(WPF) 및 Windows Forms를 사용하여 Windows 데스크톱 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-261">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="28f27-262">이러한 프레임워크는 [XAML 아일랜드](/windows/uwp/xaml-platform/xaml-host-controls)를 통해 Windows UI XAML 라이브러리(WinUI)의 최신 컨트롤 및 Fluent 스타일을 사용하는 것도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-262">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="28f27-263">Windows 데스크톱 구성 요소는 Windows .NET Core 3.0 SDK의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-263">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="28f27-264">다음 `dotnet` 명령을 사용하여 새 WPF 또는 Windows Forms 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-264">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="28f27-265">Visual Studio 2019에는 .NET Core 3.0 Windows Forms 및 WPF용 **새 프로젝트** 템플릿이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-265">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="28f27-266">기존 .NET Framework 애플리케이션을 포트하는 방법에 대한 자세한 내용은 [WPF 프로젝트 포트](../porting/wpf.md) 및 [Windows Forms 프로젝트 포트](../porting/winforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-266">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="28f27-267">COM 호출 가능 구성 요소 - Windows 데스크톱</span><span class="sxs-lookup"><span data-stu-id="28f27-267">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="28f27-268">Windows에서 이제는 COM 호출 가능 관리형 구성 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-268">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="28f27-269">이 기능은 COM 추가 기능 모델을 통해 .NET Core를 사용할 뿐만 아니라 .NET Framework에 패리티를 제공하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-269">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="28f27-270">*mscoree.dll*이 COM 서버처럼 사용되는 .NET Framework와는 달리, .NET Core는 COM 구성 요소 빌드 시 네이티브 시작 관리자 dll을 *bin* 디렉터리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-270">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="28f27-271">COM 구성 요소를 만들고 사용하는 방법에 대한 예는 [COM 데모](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-271">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="28f27-272">MSIX 배포 - Windows 데스크톱</span><span class="sxs-lookup"><span data-stu-id="28f27-272">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="28f27-273">[MSIX](https://docs.microsoft.com/windows/msix/)는 새로운 Windows 애플리케이션 패키지 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-273">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="28f27-274">Windows 10에 .NET Core 3.0 데스크톱 애플리케이션을 배포하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-274">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="28f27-275">Visual Studio 2019에 제공되는 [Windows 애플리케이션 패키징 프로젝트](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)를 사용하면 [자체 포함](../deploying/index.md#self-contained-deployments-scd) .NET Core 애플리케이션을 사용하여 MSIX 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-275">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="28f27-276">NET Core 프로젝트 파일은 `<RuntimeIdentifiers>` 속성에 지원되는 런타임을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-276">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-high-dpi"></a><span data-ttu-id="28f27-277">WinForms의 높은 DPI</span><span class="sxs-lookup"><span data-stu-id="28f27-277">WinForms high DPI</span></span>

<span data-ttu-id="28f27-278">.NET Core Windows Forms 애플리케이션은 <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>을(를) 사용하여 높은 DPI 모드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-278">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28f27-279">`SetHighDpiMode` 메서드는 해당 설정이 `Application.Run` 전에 `App.Manifest` 또는 P/Invoke와 같은 다른 수단으로 설정된 경우가 아니라면 해당하는 높은 DPI 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-279">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="28f27-280"><xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 열거형으로 표현되는 가능한 `highDpiMode` 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-280">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="28f27-281">높은 DPI 모드에 대한 자세한 내용은 [Windows에서 높은 DPI 데스크톱 애플리케이션 개발](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-281">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="28f27-282">범위 및 인덱스</span><span class="sxs-lookup"><span data-stu-id="28f27-282">Ranges and indices</span></span>

<span data-ttu-id="28f27-283">새 <xref:System.Index?displayProperty=nameWithType> 형식을 인덱싱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-283">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="28f27-284">시작부터 계산되는 `int`의 인덱스를 만들거나, 접두사 `^` 연산자(C#)를 사용하여 끝부터 계산되는 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-284">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="28f27-285">시작 인덱스와 끝 인덱스의 두 `Index` 값으로 구성되고 `x..y` 범위 식(C#)으로 작성할 수 있는 <xref:System.Range?displayProperty=nameWithType> 유형도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-285">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="28f27-286">그런 다음, 조각을 생성하는 `Range`로 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-286">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="28f27-287">자세한 내용은 [범위 및 인덱스 자습서](../../csharp/tutorials/ranges-indexes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-287">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

## <a name="async-streams"></a><span data-ttu-id="28f27-288">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="28f27-288">Async streams</span></span>

<span data-ttu-id="28f27-289"><xref:System.Collections.Generic.IAsyncEnumerable%601> 형식은 <xref:System.Collections.Generic.IEnumerable%601>의 새로운 비동기 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-289">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="28f27-290">이 언어를 사용하면 `IAsyncEnumerable<T>`을 통해 `await foreach`를 수행하여 요소를 사용하고 `yield return`을 사용하여 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-290">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="28f27-291">다음 예제에서는 비동기 스트림의 생성 및 사용을 둘 다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-291">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="28f27-292">`foreach` 문은 비동기이며, `yield return`을 사용하여 호출자에 대한 비동기 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-292">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="28f27-293">이 패턴(`yield return` 사용)은 비동기 스트림 생성을 위한 권장 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-293">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="28f27-294">`await foreach`를 수행할 수 있을 뿐 아니라, 비동기 반복기(예: `await` 및 `yield`가 둘 다 가능한 `IAsyncEnumerable/IAsyncEnumerator`를 반환하는 반복기)를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-294">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="28f27-295">삭제해야 하는 개체의 경우 `Stream` 및 `Timer`와 같은 다양한 BCL 유형이 구현하는 `IAsyncDisposable`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-295">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="28f27-296">자세한 내용은 [비동기 스트림 자습서](../../csharp/tutorials/generate-consume-asynchronous-stream.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-296">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="28f27-297">IEEE 부동 소수점 개선 사항</span><span class="sxs-lookup"><span data-stu-id="28f27-297">IEEE Floating-point improvements</span></span>

<span data-ttu-id="28f27-298">부동 소수점 API는 [IEEE 754-2008 개정판](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)을 준수하도록 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-298">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="28f27-299">이러한 변경의 목표는 **필요한** 모든 작업을 노출하고 이 작업이 IEEE 사양을 준수하는지 확인하는 것입니다. 부동 소수점 개선 사항에 대한 자세한 내용은 [.NET Core 3.0에서 부동 소수점 구문 분석 및 서식 지정 개선 사항](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-299">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="28f27-300">구문 분석 및 서식 지정 개선 사항:</span><span class="sxs-lookup"><span data-stu-id="28f27-300">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="28f27-301">모든 길이의 입력을 올바르게 구문 분석하고 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-301">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="28f27-302">음수 0을 올바르게 구문 분석하고 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-302">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="28f27-303">대/소문자를 구분하지 않는 검사를 수행하여 `Infinity`와 `NaN`을 올바르게 구문 분석하고, 적용 가능한 경우 선행 `+` 옵션을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-303">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="28f27-304">새 <xref:System.Math?displayProperty=nameWithType> API의 구성 내용:</span><span class="sxs-lookup"><span data-stu-id="28f27-304">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="28f27-305"><xref:System.Math.BitIncrement(System.Double)> 및 <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="28f27-305"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="28f27-306">`nextUp` 및 `nextDown` IEEE 연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-306">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="28f27-307">입력보다 크거나 작은 값을 각각 비교하는 최소 부동 소수점 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-307">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="28f27-308">예를 들어 `Math.BitIncrement(0.0)`는 `double.Epsilon`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-308">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="28f27-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> 및 <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="28f27-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="28f27-310">`maxNumMag` 및 `minNumMag` IEEE 연산에 해당하며 두 입력의 규모 중 더 크거나 작은 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-310">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="28f27-311">예를 들어 `Math.MaxMagnitude(2.0, -3.0)`는 `-3.0`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-311">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="28f27-312">`logB` IEEE 연산에 해당하며 정수값을 반환하고, 입력 매개 변수의 정수 이진 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-312">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="28f27-313">이 메서드는 `floor(log2(x))`와 사실상 동일하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-313">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="28f27-314">정수 값을 취하는 `scaleB` IEEE 연산에 해당하며 사실상 `x * pow(2, n)`을 반환하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-314">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="28f27-315">`log2` IEEE 연산에 해당하며, 기본-2 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-315">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="28f27-316">반올림 오류를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-316">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="28f27-317">`fma` IEEE 연산에 해당하며, 단일 곱셈 누산기(fused multiply add) 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-317">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="28f27-318">다시 말해, `(x * y) + z`을(를) 단일 연산으로 수행하기 때문에 반올림 오류가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-318">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="28f27-319">예를 들어 `FusedMultiplyAdd(1e308, 2.0, -1e308)`는 `1e308`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-319">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="28f27-320">일반 `(1e308 * 2.0) - 1e308`은 `double.PositiveInfinity`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-320">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="28f27-321">`copySign` IEEE 연산에 해당하며, `x`의 값을 반환하지만 `y`의 부호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-321">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="28f27-322">빠른 기본 제공 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="28f27-322">Fast built-in JSON support</span></span>

<span data-ttu-id="28f27-323">.NET 사용자는 [**Json.NET**](https://www.newtonsoft.com/json) 및 여전히 유용한 기타 인기 있는 JSON 라이브러리를 많이 사용해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-323">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="28f27-324">**Json.NET**은 내부적으로 UTF-16인 .NET 문자열을 기본 데이터 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-324">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="28f27-325">새로 기본 제공되는 JSON 지원은 성능이 높고, 할당이 낮으며 `Span<byte>`를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-325">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="28f27-326">.NET Core 3.0 <xref:System.Text.Json?displayProperty=nameWithType> 네임스페이스에 세 가지 주요 JSON 관련 형식이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-326">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="28f27-327">이러한 형식은 *아직* 일반 이전 CLR 개체(POCO) Serialization 및 Deserialization를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-327">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="28f27-328">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="28f27-328">Utf8JsonReader</span></span>

<span data-ttu-id="28f27-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType>는 `ReadOnlySpan<byte>`에서 읽어온 UTF-8 인코드된 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="28f27-330">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준의 기초 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-330">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="28f27-331">새 `Utf8JsonReader`를 사용하여 JSON 페이로드를 읽을 경우 **Json.NET**의 판독기를 사용하는 것에 비해 2배 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-331">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="28f27-332">JSON 토큰을 (UTF-16) 문자열로 실현해야 할 때까지 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-332">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="28f27-333">다음은 Visual Studio Code로 생성된 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 파일을 읽는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-333">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="28f27-334">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="28f27-334">Utf8JsonWriter</span></span>

<span data-ttu-id="28f27-335"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>는 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓰는 캐시를 사용하지 않고 앞으로만 이동 가능한 고성능의 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-335"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="28f27-336">reader와 마찬가지로 writer는 사용자 지정 serializer를 빌드하는 데 활용될 수 있는 기초적인 하위 수준 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-336">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="28f27-337">새로운 `Utf8JsonWriter`를 사용하여 JSON 페이로드를 작성하면**Json.NET**의 writer를 사용하는 것보다 30-80% 빠르며 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-337">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="28f27-338">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="28f27-338">JsonDocument</span></span>

<span data-ttu-id="28f27-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType>는 `Utf8JsonReader`를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="28f27-340">`JsonDocument`는 JSON 데이터를 구문 분석하고 임의 액세스 및 열거를 지원하기 위해 쿼리할 수 있는 읽기 전용 DOM(문서 개체 모델)을 작성하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-340">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="28f27-341">데이터를 구성하는 JSON 요소는 `JsonDocument`에 의해 `RootElement`라는 속성으로 노출되는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-341">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="28f27-342">`JsonElement`는 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API와 함께 개체 열거자와 JSON 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-342">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="28f27-343">`JsonDocument`를 사용하여 일반적인 JSON 페이로드를 구분 분석하고 모든 멤버에 액세스하면 **Json.NET**보다 2-3배 빠르고, 합리적인 크기(예 : 1MB 미만)의 데이터가 거의 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-343">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="28f27-344">다음은 시작점으로 사용할 수 있는 `JsonDocument` 및 `JsonElement`의 샘플 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-344">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

<span data-ttu-id="28f27-345">다음은 Visual Studio Code로 생성된 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 파일을 읽는 C# 8.0 예입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-345">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="28f27-346">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="28f27-346">JsonSerializer</span></span>

<span data-ttu-id="28f27-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType>은(는) <xref:System.Text.Json.Utf8JsonReader> 및 <xref:System.Text.Json.Utf8JsonWriter>의 위에 빌드되어 JSON 문서 및 조각과 작동 시 빠른 저메모리 Serialization을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast, low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="28f27-348">다음은 개체를 JSON으로 serialize하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-348">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="28f27-349">다음은 JSON 문자열을 개체로 deserialize하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-349">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="28f27-350">이전 예에서 생성된 JSON 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-350">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="28f27-351">Interop 개선</span><span class="sxs-lookup"><span data-stu-id="28f27-351">Interop improvements</span></span>

<span data-ttu-id="28f27-352">.NET Core 3.0은 네이티브 API Interop을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-352">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="28f27-353">유형: NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="28f27-353">Type: NativeLibrary</span></span>

<span data-ttu-id="28f27-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType>는 네이티브 라이브러리(.NET Core P/Invoke와 동일한 로드 논리 사용)를 로드하고 `getSymbol`과 같은 관련 있는 도우미 함수를 제공하는 데 캡슐화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="28f27-355">코드 예제는 [DLLMap 데모](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-355">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="28f27-356">Windows 네이티브 Interop</span><span class="sxs-lookup"><span data-stu-id="28f27-356">Windows Native Interop</span></span>

<span data-ttu-id="28f27-357">Windows는 플랫 C API, COM 및 WinRT의 형태로 다양한 네이티브 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-357">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="28f27-358">.NET Core에서는 **P/Invoke**를 지원하지만, .NET Core 3.0은 **CoCreate COM API** 및 **Activate WinRT API**에 대한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-358">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="28f27-359">코드 예제는 [Excel 데모](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-359">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="28f27-360">HTTP/2 지원</span><span class="sxs-lookup"><span data-stu-id="28f27-360">HTTP/2 support</span></span>

<span data-ttu-id="28f27-361"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 HTTP/2 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-361">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="28f27-362">HTTP/2를 사용할 수 있는 경우 TLS/ALPN을 통해 HTTP 프로토콜 버전이 협상되며, 서버에서 사용하기로 선택하면 HTTP/2가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-362">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="28f27-363">기본 프로토콜은 여전히 HTTP/1.1이지만, 두 가지 방법으로 HTTP/2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-363">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="28f27-364">첫째, HTTP/2를 사용하도록 HTTP 요청 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-364">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!CODE-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="28f27-365">둘째, 기본적으로 HTTP/2를 사용하도록 <xref:System.Net.Http.HttpClient>를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-365">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!CODE-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="28f27-366">애플리케이션 개발 중에 암호화되지 않은 연결을 사용하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-366">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="28f27-367">대상 엔드포인트에서 HTTP/2를 사용할 것을 알고 있으면, HTTP/2에 대해 암호화되지 않은 연결을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-367">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="28f27-368">`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 환경 변수를 `1` 로 설정하거나 앱 컨텍스트에서 사용하도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-368">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!CODE-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="28f27-369">Linux의 TLS 1.3 및 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="28f27-369">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="28f27-370">이제 .NET Core는 지정된 환경에서 사용 가능한 경우 [OpenSSL 1.1.1의 TLS 1.3 지원](https://www.openssl.org/blog/blog/2018/09/11/release111/)을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-370">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="28f27-371">TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="28f27-371">With TLS 1.3:</span></span>

- <span data-ttu-id="28f27-372">클라이언트와 서버 간에 필요한 왕복 횟수가 감소하여 연결 시간이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-372">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="28f27-373">더 이상 사용하지 않고 안전하지 않은 암호화 알고리즘을 제거하므로 보안이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-373">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="28f27-374">사용 가능한 경우 .NET Core 3.0은 Linux 시스템에서 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** 또는 **OpenSSL 1.0.2**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-374">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="28f27-375">**OpenSSL 1.1.1**이 사용 가능한 경우 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 **TLS 1.3**을 사용합니다(클라이언트와 서버 둘 다 **TLS 1.3**을 지원한다고 가정).</span><span class="sxs-lookup"><span data-stu-id="28f27-375">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="28f27-376">Windows 및 macOS에서는 아직 **TLS 1.3**을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-376">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="28f27-377">지원이 제공되면 .NET Core 3.0은 이러한 운영 체제에서 **TLS 1.3**을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-377">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="28f27-378">다음 C# 8.0 예제는 <https://www.cloudflare.com>에 연결하는 Ubuntu 18.10의 .NET Core 3.0을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-378">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="28f27-379">암호화 암호</span><span class="sxs-lookup"><span data-stu-id="28f27-379">Cryptography ciphers</span></span>

<span data-ttu-id="28f27-380">.NET 3.0은 각각 <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>으로 구현된 **AES-GCM** 및 **AES-CCM** 암호에 대한 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-380">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="28f27-381">이러한 알고리즘은 둘 다 [AEAD(Authenticated Encryption with Association Data) 알고리즘](https://en.wikipedia.org/wiki/Authenticated_encryption)입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-381">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="28f27-382">다음 코드는 `AesGcm` 암호를 사용하여 임의 데이터를 암호화하고 암호를 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-382">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="28f27-383">암호화 키 가져오기/내보내기</span><span class="sxs-lookup"><span data-stu-id="28f27-383">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="28f27-384">.NET Core 3.0은 표준 형식에서 비대칭 공개 키와 개인 키를 가져오고 내보낼 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-384">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="28f27-385">X.509 인증서를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-385">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="28f27-386">모든 키 형식(*RSA*, *DSA*, *ECDsa* 및 *ECDiffieHellman*)에서 다음 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-386">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="28f27-387">**공개 키**</span><span class="sxs-lookup"><span data-stu-id="28f27-387">**Public Key**</span></span>
  - <span data-ttu-id="28f27-388">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="28f27-388">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="28f27-389">**개인 키**</span><span class="sxs-lookup"><span data-stu-id="28f27-389">**Private key**</span></span>
  - <span data-ttu-id="28f27-390">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="28f27-390">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="28f27-391">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="28f27-391">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="28f27-392">RSA 키는 다음도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-392">RSA keys also support:</span></span>

- <span data-ttu-id="28f27-393">**공개 키**</span><span class="sxs-lookup"><span data-stu-id="28f27-393">**Public Key**</span></span>
  - <span data-ttu-id="28f27-394">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="28f27-394">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="28f27-395">**개인 키**</span><span class="sxs-lookup"><span data-stu-id="28f27-395">**Private key**</span></span>
  - <span data-ttu-id="28f27-396">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="28f27-396">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="28f27-397">내보내기 메서드는 DER로 인코드된 이진 데이터를 생성하고, 가져오기 메서드도 동일한 동작을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-397">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="28f27-398">키가 텍스트에 편리한 PEM 형식으로 저장된 경우 호출자는 가져오기 메서드를 호출하기 전에 콘텐츠를 base64로 디코드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-398">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="28f27-399">**PKCS#8** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType>로 검사하고 **PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>로 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-399">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28f27-400">**PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-400">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="28f27-401">Linux용 SerialPort</span><span class="sxs-lookup"><span data-stu-id="28f27-401">SerialPort for Linux</span></span>

<span data-ttu-id="28f27-402">.NET Core 3.0은 Linux에서 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>에 대한 기본 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-402">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="28f27-403">이전에는 .NET Core가 Windows에서만 `SerialPort` 사용을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-403">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="28f27-404">Linux의 제한적 직렬 포트 지원에 대한 자세한 내용은 [GitHub 이슈 #33146](https://github.com/dotnet/corefx/issues/33146)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-404">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="28f27-405">Docker 및 cgroup 메모리 한도</span><span class="sxs-lookup"><span data-stu-id="28f27-405">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="28f27-406">Preview 3부터, Docker를 사용하여 Linux에서 .NET Core 3.0을 실행하면 cgroup 메모리 한도에 훨씬 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-406">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="28f27-407">메모리 한도가 있는 Docker 컨테이너를 실행하면(`docker run -m` 사용) .NET Core 동작 방식이 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-407">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="28f27-408">기본 가비지 수집기(GC) 힙 크기: 최대 20mb 또는 컨테이너에서 75%의 메모리 한도</span><span class="sxs-lookup"><span data-stu-id="28f27-408">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="28f27-409">명시적 크기는 절대수 또는 cgroup 한도의 비율로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-409">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="28f27-410">GC 힙당 최소 예약된 세그먼트 크기는 16mb입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-410">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="28f27-411">이 크기는 머신에서 생성된 힙 수를 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-411">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="28f27-412">더 작은 가비지 수집 힙 크기</span><span class="sxs-lookup"><span data-stu-id="28f27-412">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="28f27-413">가비지 수집기의 기본 힙 크기가 감소되어 .NET Core에서 사용되는 메모리가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-413">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="28f27-414">이러한 변화는 최신 프로세서 캐시 크기의 생성 0 할당 예산과 부합됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-414">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="28f27-415">가비지 수집 Large Page 지원</span><span class="sxs-lookup"><span data-stu-id="28f27-415">Garbage Collection Large Page support</span></span>

<span data-ttu-id="28f27-416">Large Page(또는 Linux Huge Page)는 운영 체제가 이러한 큰 페이지를 요청하는 애플리케이션의 성능을 개선하기 위해 네이티브 페이지 크기(보통 4K)보다 더 큰 메모리 영역을 구축할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-416">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="28f27-417">이제 가비지 수집기는 Windows에서 큰 페이지를 할당하기 위해 선택할 수 있는 옵트인(opt-in) 기능으로 **GCLargePages** 설정을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-417">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="28f27-418">Raspberry Pi에 대한 GPIO 지원</span><span class="sxs-lookup"><span data-stu-id="28f27-418">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="28f27-419">GPIO 프로그래밍에 사용할 수 있는 두 개의 패키지가 NuGet에 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-419">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="28f27-420">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="28f27-420">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="28f27-421">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="28f27-421">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="28f27-422">GPIO 패키지에는 *GPIO*, *SPI*, *I2C* 및 *PWM*디바이스용 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-422">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="28f27-423">IoT 바인딩 패키지에 디바이스 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-423">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="28f27-424">자세한 내용은 [디바이스 GitHub 리포지토리](https://github.com/dotnet/iot/blob/master/src/devices/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-424">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="28f27-425">ARM64 Linux 지원</span><span class="sxs-lookup"><span data-stu-id="28f27-425">ARM64 Linux support</span></span>

<span data-ttu-id="28f27-426">.NET Core 3.0에서는 Linux용 ARM64에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-426">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="28f27-427">ARM64는 현재 IoT 시나리오에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-427">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="28f27-428">자세한 내용은 [.NET Core ARM64 상태](https://github.com/dotnet/announcements/issues/82)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28f27-428">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="28f27-429">[ARM64의 .NET Core에 대한 Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/)를 Alpine, Debian 및 Ubuntu에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-429">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="28f27-430">**ARM64** Windows 지원은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28f27-430">**ARM64** Windows support isn't yet available.</span></span>
