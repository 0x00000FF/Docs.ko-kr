---
title: "Windows에서 .NET Core의 필수 구성 요소"
description: "Windows 컴퓨터에서 .NET Core 응용프로그램을 개발 및 실행하기 위해 필요한 종속성이 무엇인지 살펴보세요."
author: JRAlexander
ms.author: johalex
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 16a72edde39e4857dbdfb400f195deb9975f993c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="88030-103">Windows에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="88030-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="88030-104">이 문서에서는 Windows에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88030-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="88030-105">다음에 나오는 지원되는 OS 버전 및 종속성은 Windows에서 .NET Core 앱을 개발하기 위한 세 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="88030-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="88030-106">명령줄</span><span class="sxs-lookup"><span data-stu-id="88030-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="88030-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="88030-107">Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)
* [<span data-ttu-id="88030-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="88030-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="88030-109">.NET Core가 지원되는 Windows 버전</span><span class="sxs-lookup"><span data-stu-id="88030-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="88030-110">.NET Core는 다음 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="88030-110">.NET Core is supported on the following versions of :</span></span>

* <span data-ttu-id="88030-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="88030-111">Windows 7 SP1</span></span>
* <span data-ttu-id="88030-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="88030-112">Windows 8.1</span></span>
* <span data-ttu-id="88030-113">Windows 10, Windows 10 1주년 업데이트(버전 1607) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="88030-113">Windows 10, Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="88030-114">Windows Server 2008 R2 SP1(전체 서버 또는 Server Core)</span><span class="sxs-lookup"><span data-stu-id="88030-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="88030-115">Windows Server 2012 SP1(전체 서버 또는 Server Core)</span><span class="sxs-lookup"><span data-stu-id="88030-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="88030-116">Windows Server 2012 R2(전체 서버 또는 Server Core)</span><span class="sxs-lookup"><span data-stu-id="88030-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="88030-117">Windows Server 2016(전체 서버, Server Core 또는 Nano Server)</span><span class="sxs-lookup"><span data-stu-id="88030-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="88030-118">.NET Core 2.x가 지원되는 운영 체제의 전체 목록은 [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x - 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88030-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="88030-119">.NET Core 1.x가 지원되는 운영 체제의 전체 목록은 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88030-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="88030-120">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="88030-120">.NET Core dependencies</span></span>

<span data-ttu-id="88030-121">이전 Windows 10 및 Windows Server 2016 버전의 Windows 버전에서 실행 하는 경우.NET core 1.1 및 이전 버전에서 Visual c + + 재배포 가능 패키지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-121">.NET Core 1.1 and earlier requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="88030-122">이 종속성은 .NET Core 설치 관리자에 의해 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="88030-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="88030-123">다음과 같은 경우에는 [Microsoft Visual C++ 2015 재배포 가능 패키지 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685)을 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

   * <span data-ttu-id="88030-124">[설치 관리자 스크립트](./tools/dotnet-install-script.md)를 사용하여 .NET Core 설치.</span><span class="sxs-lookup"><span data-stu-id="88030-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
   * <span data-ttu-id="88030-125">자체 포함된 .NET Core 응용 프로그램 배포.</span><span class="sxs-lookup"><span data-stu-id="88030-125">Deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="88030-126"><em>Windows 7 및 Windows Server 2008용 컴퓨터만 해당:</em></span><span class="sxs-lookup"><span data-stu-id="88030-126"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="88030-127">설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치된 핫픽스 [KB2533623](https://support.microsoft.com/help/2533623)이 포함되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="88030-127">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="88030-128">Visual Studio 2017 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="88030-128">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="88030-129">.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발하기 위해 원하는 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88030-129">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span>  <span data-ttu-id="88030-130">[Visual Studio 2017](#visual-studio-2017)에서는 Windows 기반 .NET Core 앱에 대한 통합 개발 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-130">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="88030-131">[릴리스 정보](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes)에서 Visual Studio 2017의 변경 내용에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88030-131">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>
# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="88030-132">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="88030-132">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="88030-133">Visual Studio 2017에서 .NET Core 2.x 앱을 개발하려면:</span><span class="sxs-lookup"><span data-stu-id="88030-133">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="88030-134">**기타 도구 집합** 섹션에서 **.NET Core 플랫폼 간 개발** 워크로드를 선택하고 [Visual Studio 2017 버전 15.3.0 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-134">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="88030-135">![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="88030-135">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span></span>

<span data-ttu-id="88030-136">**.NET Core 플랫폼 간 개발** 도구 집합이 설치된 후 Visual Studio 2017에서는 기본적으로 .NET Core 1.x를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-136">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="88030-137">.NET Core 2.x SDK를 설치하여 Visual Studio 2017에 .NET Core 2.x 지원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88030-137">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="88030-138">[.NET Core 2.x SDK](https://www.microsoft.com/net/download/core)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-138">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="88030-139">다음 지침에 따라 기존 또는 새로운 .NET Core 1.x 프로젝트의 대상을 .NET Core 2.x로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-139">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="88030-140">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-140">On the **Project** menu, Choose **Properties**.</span></span> 
    * <span data-ttu-id="88030-141">**대상 프레임워크** 선택 메뉴에서 값을 **.NET Core 2.0**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-141">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![“.NET Core 2.0” 대상 프레임워크 메뉴 항목을 선택한 Visual Studio 2017 응용 프로그램 프로젝트 속성의 스크린샷](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="88030-143">.NET Core 2.x SDK가 설치된 후 Visual Studio 2017에서는 기본적으로 .NET Core SDK 2.x를 사용하고 다음 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-143">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

  * <span data-ttu-id="88030-144">기존 .NET Core 1.x 프로젝트를 열고, 빌드하고, 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-144">Open, build, and run existing .NET Core 1.x projects.</span></span>
  * <span data-ttu-id="88030-145">.NET Core 1.x 프로젝트의 대상을 .NET Core 2.x로 변경하고 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-145">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
  * <span data-ttu-id="88030-146">새로운 .NET Core 2.x 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88030-146">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="88030-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="88030-147">.NET Core 1.x</span></span>](#tab/netcore1x)
<span data-ttu-id="88030-148">Visual Studio에서 .NET Core 1.x 앱을 개발하려면 **기타 도구 집합** 섹션에서 **“.NET Core 플랫폼 간 개발”** 워크로드를 선택하고 [Visual Studio 2017 RTM(버전 15.0.26228.4) 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-148">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="88030-149">![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="88030-149">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="88030-150">.NET Core 1.x 개발에 Visual Studio 2015를 사용할 수 있지만 다음 이유로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88030-150">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="88030-151">.NET Core 도구는 지원되지 않는 미리 보기 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="88030-151">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="88030-152">프로젝트는 더 이상 사용되지 않는 project.json을 기반으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88030-152">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="88030-153">프로젝트 형식 변경에 대한 자세한 내용은 [변경 내용에 대한 대략적인 개요](./tools/cli-msbuild-architecture.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88030-153">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

>[!TIP]
  > <span data-ttu-id="88030-154">Visual Studio 2017 버전을 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="88030-154">To verify your Visual Studio 2017 version:</span></span>
>
     > * <span data-ttu-id="88030-155">**도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-155">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
     > * <span data-ttu-id="88030-156">**Microsoft Visual Studio 정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88030-156">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>     * <span data-ttu-id="88030-157">.NET Core 2.x 앱의 경우 Visual Studio 2017 버전 15.3(26730.01) 이상.</span><span class="sxs-lookup"><span data-stu-id="88030-157">For .NET Core 2.x apps, Visual Studio 2017 version 15.3 (26730.01) or higher.</span></span>
>     * <span data-ttu-id="88030-158">.NET Core 1.x 앱의 경우 Visual Studio 2017 버전 15.0(26228.04) 이상.</span><span class="sxs-lookup"><span data-stu-id="88030-158">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 (26228.04) or higher.</span></span>
