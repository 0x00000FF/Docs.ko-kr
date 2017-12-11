---
title: ".NET Core 2.0의 새로운 기능"
description: ".NET Core에서 볼 수 있는 새로운 기능에 대해 알아봅니다."
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: e54cabe67558300b5c5fb9552d78397850d4c782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="ed7ae-104">.NET Core의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="ed7ae-104">What's new in .NET Core</span></span>

<span data-ttu-id="ed7ae-105">.NET Core 2.0은 다음 영역에서 향상된 기능 및 새로운 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="ed7ae-106">도구</span><span class="sxs-lookup"><span data-stu-id="ed7ae-106">Tooling</span></span>](#tooling)
- [<span data-ttu-id="ed7ae-107">언어 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-107">Language support</span></span>](#language-support)
- [<span data-ttu-id="ed7ae-108">플랫폼 개선</span><span class="sxs-lookup"><span data-stu-id="ed7ae-108">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="ed7ae-109">API 변경 내용</span><span class="sxs-lookup"><span data-stu-id="ed7ae-109">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="ed7ae-110">Visual Studio 통합</span><span class="sxs-lookup"><span data-stu-id="ed7ae-110">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="ed7ae-111">설명서 개선</span><span class="sxs-lookup"><span data-stu-id="ed7ae-111">Documentation improvements</span></span>](#documentation-improvements)

## <a name="tooling"></a><span data-ttu-id="ed7ae-112">도구</span><span class="sxs-lookup"><span data-stu-id="ed7ae-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="ed7ae-113">dotnet restore runs implicitly</span><span class="sxs-lookup"><span data-stu-id="ed7ae-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="ed7ae-114">이전 버전의 .NET Core에서 [dotnet new](../tools/dotnet-new.md) 명령을 사용하여 새 프로젝트를 만든 이후뿐만 아니라 프로젝트에 새 종속성을 추가할 때마다 [dotnet restore](../tools/dotnet-restore.md) 명령을 실행하여 즉시 종속성을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ed7ae-115">`--no-restore` 스위치를 `new`, `run`, `build`, `publish`, `pack` 및 `test` 명령으로 전달하여 `dotnet restore` 자동 호출을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-115">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="ed7ae-116">.NET Core 2.0로 대상 다시 지정</span><span class="sxs-lookup"><span data-stu-id="ed7ae-116">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="ed7ae-117">.NET Core 2.0 SDK가 설치되면 .NET Core 1.x을 대상으로 지정하는 프로젝트는 .NET Core 2.0의 대상으로 다시 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-117">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="ed7ae-118">.NET Core 2.0을 대상으로 지정하려면 1.x에서 2.0까지 `<TargetFramework>` 요소(또는 프로젝트 파일에서 대상이 둘 이상 있는 경우 `<TargetFrameworks>` 요소)의 값을 변경하여 프로젝트 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-118">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="ed7ae-119">또한 같은 방식으로 .NET 표준 2.0으로 .NET 표준 라이브러리의 대상을 다시 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-119">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="ed7ae-120">프로젝트를 .NET Core 2.0으로 마이그레이션하는 방법에 대한 자세한 정보는 [ASP.NET Core 1.x에서 ASP.NET Core 2.0으로 마이그레이션](/aspnet/core/migration/1x-to-2x/index)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-120">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="ed7ae-121">언어 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-121">Language support</span></span>

<span data-ttu-id="ed7ae-122">C# 및 F #를 지원할 뿐만 아니라 .NET Core 2.0도 Visual Basic을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-122">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="ed7ae-123">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed7ae-123">Visual Basic</span></span>

<span data-ttu-id="ed7ae-124">이제 버전 2.0,.NET Core는 Visual Basic 2017을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-124">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="ed7ae-125">Visual Basic을 사용하여 다음과 같은 프로젝트 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-125">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="ed7ae-126">.NET Core 콘솔 앱</span><span class="sxs-lookup"><span data-stu-id="ed7ae-126">.NET Core console apps</span></span>
- <span data-ttu-id="ed7ae-127">.NET Core 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed7ae-127">.NET Core class libraries</span></span>
- <span data-ttu-id="ed7ae-128">.NET 표준 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed7ae-128">.NET Standard class libraries</span></span>
- <span data-ttu-id="ed7ae-129">.NET Core 단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed7ae-129">.NET Core unit test projects</span></span>
- <span data-ttu-id="ed7ae-130">.NET Core xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed7ae-130">.NET Core xUnit test projects</span></span>

<span data-ttu-id="ed7ae-131">예를 들어 Visual Basic "Hello World" 응용 프로그램을 만들려면 명령줄에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-131">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="ed7ae-132">콘솔 창을 열고 프로젝트에 대한 디렉터리를 만들고 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-132">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="ed7ae-133">`dotnet new console -lang vb` 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-133">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="ed7ae-134">이 명령은 *Program.vb*라는 Visual Basic 소스 코드와 함께 `.vbproj` 파일 확장인 프로젝트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-134">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="ed7ae-135">이 파일은 문자열 "Hello World!"를 작성하는 소스 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-135">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="ed7ae-136">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-136">to the console window.</span></span>

1.  <span data-ttu-id="ed7ae-137">`dotnet run` 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-137">Enter the command `dotnet run`.</span></span> <span data-ttu-id="ed7ae-138">[.NET Core CLI 도구](../tools/index.md)는 응용 프로그램을 자동으로 컴파일하고 실행합니다. 그러면 "Hello World!" 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-138">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="ed7ae-139">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-139">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="ed7ae-140">C# 7.1에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-140">Support for C# 7.1</span></span>

<span data-ttu-id="ed7ae-141">.NET Core 2.0은 다음을 비롯하여 다양하고 새로운 기능을 추가하는 C# 7.1을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-141">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="ed7ae-142">응용 프로그램 진입점인 `Main` 메서드는 [비동기](../../csharp/language-reference/keywords/async.md) 키워드로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-142">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="ed7ae-143">유추된 튜플 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-143">Inferred tuple names.</span></span>
- <span data-ttu-id="ed7ae-144">기본 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-144">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="ed7ae-145">플랫폼 개선</span><span class="sxs-lookup"><span data-stu-id="ed7ae-145">Platform improvements</span></span>

<span data-ttu-id="ed7ae-146">.NET Core 2.0은 .NET Core를 쉽게 설치하고 지원되는 운영 체제에서 사용할 수 있는 다양한 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-146">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="ed7ae-147">Linux용 .NET core는 단일 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-147">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="ed7ae-148">.NET Core 2.0은 여러 Linux 배포에서 작동하는 단일 Linux 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-148">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="ed7ae-149">.NET Core 1.x은 배포 관련 Linux 구현을 다운로드하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-149">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="ed7ae-150">또한 단일 운영 체제로 Linux를 대상으로 하는 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-150">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="ed7ae-151">.NET Core 1.x는 별도로 각 Linux 배포를 대상으로 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-151">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="ed7ae-152">Apple 암호화 라이브러리에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-152">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="ed7ae-153">.NET Core 1.x는 OpenSSL 도구 키트의 암호화 라이브러리에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-153">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="ed7ae-154">.NET Core 2.0은 Apple 암호화 라이브러리를 사용하고 OpenSSL을 필요로 하지 않으므로 더 이상 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-154">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="ed7ae-155">API 변경 내용 및 라이브러리 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-155">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="ed7ae-156">.NET 표준 2.0에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-156">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="ed7ae-157">.NET 표준은 해당 버전의 표준에 부합하는 .NET 구현에서 사용할 수 있어야 하는 버전이 지정된 API 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-157">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="ed7ae-158">.NET 표준은 라이브러리 개발자에서 대상으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-158">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="ed7ae-159">각 .NET 구현에 .NET 표준의 버전을 대상으로 지정하는 라이브러리에 사용할 수 있는 기능을 보장하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-159">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="ed7ae-160">.NET Core 1.x는 .NET 표준 버전 1.6을 지원하고 .NET Core 2.0은 최신 버전인 .NET 표준 2.0을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-160">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="ed7ae-161">자세한 내용은 [.NET 표준](../../standard/net-standard.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-161">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="ed7ae-162">.NET 표준 2.0에는 .NET 표준 1.6에서 사용할 수 있었던 20,000개가 넘는 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-162">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="ed7ae-163">이 확장된 노출 영역 중 상당 부분은 .NET Framework 및 Xamarin에 공통되는 API를 .NET 표준에 통합한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-163">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="ed7ae-164">.NET 표준 2.0 클래스 라이브러리는 .NET Framework 클래스 라이브러리를 참조할 수도 있고 .NET 표준 2.0에서 표시되는 API를 호출하도록 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-164">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="ed7ae-165">.NET Framework 라이브러리를 다시 컴파일하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-165">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="ed7ae-166">마지막 버전인 .NET 표준 1.6 이후 .NET 표준에 추가된 API 목록은 [.NET 표준 2.0 및 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-166">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="ed7ae-167">확장된 노출 영역</span><span class="sxs-lookup"><span data-stu-id="ed7ae-167">Expanded surface area</span></span>

<span data-ttu-id="ed7ae-168">.NET Core 2.0에서는 사용할 수 있는 API의 총수는 .NET Core 1.1에 비교하여 두 배 이상 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-168">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="ed7ae-169">그리고 [Windows 호환 기능 팩](../porting/windows-compat-pack.md) 덕분에 .NET Framework에서 이식하는 작업이 훨씬 더 간편해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-169">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="ed7ae-170">.NET Framework 라이브러리에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-170">Support for .NET Framework libraries</span></span>

<span data-ttu-id="ed7ae-171">.NET Core 코드는 기존 NuGet 패키지를 비롯한 기존 .NET Framework 라이브러리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-171">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="ed7ae-172">라이브러리는 표준.NET에서 발견되는 API를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-172">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="ed7ae-173">Visual Studio 통합</span><span class="sxs-lookup"><span data-stu-id="ed7ae-173">Visual Studio integration</span></span>

<span data-ttu-id="ed7ae-174">Visual Studio 2017 버전 15.3 및 경우에 따라 Mac용 Visual Studio는 .NET Core 개발자를 위해 다양한 주요 기능 향상을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-174">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="ed7ae-175">.NET Core 앱 및 .NET 표준 라이브러리를 대상으로 다시 지정</span><span class="sxs-lookup"><span data-stu-id="ed7ae-175">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="ed7ae-176">.NET Core 2.0 SDK가 설치되는 경우 .NET Core 1.x 프로젝트를 .NET Core 2.0으로, .NET 표준 1.x 라이브러리를 .NET 표준 2.0으로 대상을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-176">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="ed7ae-177">Visual Studio에서 프로젝트의 대상을 변경하려면 프로젝트 속성 대화 상자의 **응용 프로그램** 탭을 열고 **대상 프레임 워크** 값을 **.NET Core 2.0** 또는 **.NET 표준 2.0**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-177">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="ed7ae-178">또한 프로젝트를 마우스 오른쪽 단추로 클릭하고 **\*.csproj 파일 편집** 옵션을 선택하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-178">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="ed7ae-179">자세한 내용은 이 항목 앞 부분의 [도구](#tooling) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-179">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="ed7ae-180">.NET Core에 대한 Live Unit Testing 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-180">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="ed7ae-181">Live Unit Testing이 코드를 수정하려면 언제든지 자동으로 백그라운드에서 영향을 받는 단위 테스트를 실행하고 Visual Studio 환경에서 결과 및 코드 검사 라이브를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-181">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="ed7ae-182">이제 .NET Core 2.0은 Live Unit Testing을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-182">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="ed7ae-183">이전에 Live Unit Testing은 .NET Framework 응용 프로그램에만 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-183">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="ed7ae-184">자세한 내용은 [Visual Studio 2017에서 Live Unit Testing](/visualstudio/test/live-unit-testing) 및 [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-184">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="ed7ae-185">다양한 대상 프레임워크에 대한 지원 향상</span><span class="sxs-lookup"><span data-stu-id="ed7ae-185">Better support for multiple target frameworks</span></span>

<span data-ttu-id="ed7ae-186">다양한 대상 프레임워크에 대한 프로젝트를 빌드하는 경우 이제 최상위 메뉴에서 대상 플랫폼을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-186">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="ed7ae-187">다음 그림에서 SCD1이라는 프로젝트는 64비트 Mac OS X 10.11(`osx.10.11-x64`) 및 64비트 Windows 10/Windows Server 2016(`win10-x64`)을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-187">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="ed7ae-188">디버그 빌드를 실행하는 경우에 프로젝트 단추를 선택하기 전에 대상 프레임워크를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-188">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![프로젝트를 빌드할 때 대상 프레임워크 선택](media/multitarget.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="ed7ae-190">.NET Core SDK에 대한 병렬 지원</span><span class="sxs-lookup"><span data-stu-id="ed7ae-190">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="ed7ae-191">이제 Visual Studio와 독립적으로 .NET Core SDK를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-191">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="ed7ae-192">따라서 단일 버전의 Visual Studio에서 다른 버전의 .NET Core를 대상으로 지정하는 프로젝트를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-192">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="ed7ae-193">이전에 Visual Studio 및 .NET Core SDK는 밀접하게 연결되어 있었습니다. 특정 버전의 SDK는 특정 버전의 Visual Studio와 함께 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-193">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="ed7ae-194">설명서 개선</span><span class="sxs-lookup"><span data-stu-id="ed7ae-194">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="ed7ae-195">.NET 응용 프로그램 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ed7ae-195">.NET Application Architecture</span></span>

<span data-ttu-id="ed7ae-196">빌드하는 데 .NET을 사용하는 경우 [.NET 응용 프로그램 아키텍처](https://www.microsoft.com/net/learn/architecture)는 지침, 모범 사례 및 응용 프로그램 예제를 제공하는 전자책 집합에 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ed7ae-196">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="ed7ae-197">마이크로 서비스 및 Docker 컨테이너</span><span class="sxs-lookup"><span data-stu-id="ed7ae-197">Microservices and Docker containers.</span></span>
- <span data-ttu-id="ed7ae-198">ASP.NET을 사용하는 웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed7ae-198">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="ed7ae-199">Xamarin을 사용하는 모바일 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed7ae-199">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="ed7ae-200">Azure에서 클라우드에 배포되는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed7ae-200">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed7ae-201">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed7ae-201">See also</span></span>
 [<span data-ttu-id="ed7ae-202">ASP.NET Core 2.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="ed7ae-202">What's new in ASP.NET Core 2.0</span></span>](/aspnet/core/aspnetcore-2.0)
