---
title: ML.NET CLI(명령줄 인터페이스) 도구를 설치하는 방법
description: ML.NET CLI(명령줄 인터페이스) 도구 개요 및 설치
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 869c443d519557c9d3976676047e63a4a072d2d3
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065806"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="14c52-103">ML.NET CLI(명령줄 인터페이스) 도구를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="14c52-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="14c52-104">모든 명령 프롬프트(Windows, Mac 또는 Linux)에서 ML.NET CLI를 실행하여 제공한 학습 데이터 세트를 기초로 품질 높은 ML.NET 모델과 소스 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-104">The ML.NET CLI (command-line interface) is a tool you can run on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on training datasets you provide.</span></span>

> [!NOTE]
> <span data-ttu-id="14c52-105">이 항목은 현재 미리 보기로 제공되는 ML.NET CLI 및 ML.NET AutoML을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-105">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="14c52-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="14c52-106">Pre-requisites</span></span>

- [<span data-ttu-id="14c52-107">.NET Core 2.2 SDK</span><span class="sxs-lookup"><span data-stu-id="14c52-107">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="14c52-108">(선택 사항) [Visual Studio 2017 또는 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="14c52-108">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="14c52-109">생성된 C# 코드 프로젝트를 Visual Studio F5 또는 `dotnet run`(.NET Core CLI)으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-109">You can either run the generated C# code projects with Visual Studio F5 or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="14c52-110">참고: [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) 설치 후 `dotnet tool` 명령이 작동하지 않는 경우 Windows에서 로그아웃했다가 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-110">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="14c52-111">설치</span><span class="sxs-lookup"><span data-stu-id="14c52-111">Install</span></span>

<span data-ttu-id="14c52-112">ML.NET CLI는 다른 DotNet Global Tool처럼 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-112">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="14c52-113">`dotnet tool install` .NET Core CLI 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-113">You use the `dotnet tool install` .NET Core CLI command.</span></span> 

<span data-ttu-id="14c52-114">다음 예제에서는 기본 NuGet 피드 위치에 ML.NET CLI를 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-114">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```console
> dotnet tool install -g mlnet
```

<span data-ttu-id="14c52-115">도구를 설치할 수 없는 경우(즉 기본 NuGet 피드에서 사용할 수 없는 경우) 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-115">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="14c52-116">예상한 피드가 확인되고 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-116">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="14c52-117">설치에 성공하면 다음 예와 같이 도구와 설치된 버전을 호출하는 데 사용되는 명령을 보여 주는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-117">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="14c52-118">다음 명령을 입력하여 설치가 완료되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-118">You can confirm the installation was successful by typing the following command:</span></span>

```console
> mlnet
```

<span data-ttu-id="14c52-119">'auto-train' 명령처럼 mlnet 도구에 대해 사용 가능한 명령의 도움말을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-119">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="14c52-120">특정 릴리스 버전 설치</span><span class="sxs-lookup"><span data-stu-id="14c52-120">Install a specific release version</span></span>

<span data-ttu-id="14c52-121">이전 릴리스 버전 또는 특정 버전의 도구를 설치하려는 경우 다음 형식을 사용하여 버전 번호를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-121">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```console
> dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="14c52-122">다음 명령을 입력하여 패키지가 올바르게 설치되었는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-122">You can also check if the package is properly installed by typing the following command:</span></span>

```console
> dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="14c52-123">CLI 패키지 제거</span><span class="sxs-lookup"><span data-stu-id="14c52-123">Uninstall the CLI package</span></span>

<span data-ttu-id="14c52-124">로컬 컴퓨터에서 패키지를 제거하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-124">Type the following command to uninstall the package from your local machine:</span></span>

```console
> dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="14c52-125">CLI 패키지 업데이트</span><span class="sxs-lookup"><span data-stu-id="14c52-125">Update the CLI package</span></span>

<span data-ttu-id="14c52-126">로컬 컴퓨터에서 패키지를 업데이트하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-126">Type the following command to update the package from your local machine:</span></span>

```console
> dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="14c52-127">CLI 제안(탭 기반 자동 완성) 설정</span><span class="sxs-lookup"><span data-stu-id="14c52-127">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="14c52-128">ML.NET CLI는 `System.CommandLine`을 기반으로 하므로 탭 완성을 기본 제공으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-128">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="14c52-129">탭 자동 완성이 작동하는 예제는 다음 애니메이션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-129">An example of how tab auto completion works is shown in the following animation:</span></span>

![이미지](./media/cli-tab-completion.gif)

<span data-ttu-id="14c52-131">'탭 기반 자동 완성'(매개 변수 제안)은 *Windows PowerShell* 및 *macOS/Linux bash*에서 실행되나 *Windows CMD*에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-131">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="14c52-132">현재 미리 보기 버전에서 이를 사용하려면 최종 사용자가 아래에서 설명한 대로 셸마다 한 번씩 몇 가지 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-132">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="14c52-133">이 후에는 ML.NET CLI처럼 `System.CommandLine`을 사용하여 작성된 모든 앱에 완성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-133">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="14c52-134">완성을 사용하려는 컴퓨터에서 다음 두 가지를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-134">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="14c52-135">다음 명령을 실행하여 `dotnet-suggest` 글로벌 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-135">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```console
    > dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="14c52-136">셸 프로필에 적합한 Shim 스크립트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-136">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="14c52-137">셸 프로필 파일을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-137">You may have to create a shell profile file.</span></span> <span data-ttu-id="14c52-138">Shim 스크립트는 셸의 완성 요청을 `dotnet-suggest` 도구로 전달하며 적합한 `System.CommandLine` 기반 앱에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-138">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    * <span data-ttu-id="14c52-139">Bash의 경우 [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash)의 콘텐츠를 `~/.bash_profile`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-139">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    * <span data-ttu-id="14c52-140">PowerShell의 경우 [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1)의 콘텐츠를 PowerShell 프로필에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-140">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="14c52-141">콘솔에서 다음 명령을 실행하여 PowerShell 프로필의 예상 경로를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-141">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    > echo $profile
    ``` 

<span data-ttu-id="14c52-142">(다른 셸의 경우 [검색](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) 또는 [문제](https://github.com/dotnet/System.CommandLine/issues) 열기)</span><span class="sxs-lookup"><span data-stu-id="14c52-142">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="14c52-143">설치 디렉터리</span><span class="sxs-lookup"><span data-stu-id="14c52-143">Installation directory</span></span>

<span data-ttu-id="14c52-144">ML.NET CLI는 기본 디렉터리 또는 특정 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-144">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="14c52-145">기본 디렉터리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-145">The default directories are:</span></span>

| <span data-ttu-id="14c52-146">OS</span><span class="sxs-lookup"><span data-stu-id="14c52-146">OS</span></span>          | <span data-ttu-id="14c52-147">경로</span><span class="sxs-lookup"><span data-stu-id="14c52-147">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="14c52-148">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="14c52-148">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="14c52-149">Windows</span><span class="sxs-lookup"><span data-stu-id="14c52-149">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="14c52-150">이러한 위치는 SDK를 처음 실행할 때 사용자 경로에 추가되므로 설치된 Global Tool을 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-150">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="14c52-151">참고: Global Tool은 컴퓨터 전체가 아닌 사용자 특정입니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-151">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="14c52-152">사용자별 도구라는 것은 컴퓨터의 모든 사용자가 사용할 수 있는 Global Tool을 설치할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-152">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="14c52-153">이 도구는 도구가 설치된 각 사용자 프로필에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-153">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="14c52-154">Global Tool을 특정 디렉터리에 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-154">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="14c52-155">특정 디렉터리에 설치된 경우 사용자는 경로에 해당 디렉터리를 포함하거나, 지정된 디렉터리로 명령을 호출하거나, 지정된 디렉터리 내에서 도구를 호출하여 명령을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-155">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="14c52-156">이 경우 .NET Core CLI는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c52-156">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="14c52-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14c52-157">See also</span></span>

- [<span data-ttu-id="14c52-158">‘ML.NET CLI 도구 시작' 자습서</span><span class="sxs-lookup"><span data-stu-id="14c52-158">Tutorial on 'Getting Started with ML.NET CLI tool'</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="14c52-159">ML.NET CLI 도구를 사용하여 자동으로 모델을 학습하는 방법</span><span class="sxs-lookup"><span data-stu-id="14c52-159">How to automatically train models with the ML.NET CLI tool</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="14c52-160">ML.NET CLI auto-train 명령 참조 가이드</span><span class="sxs-lookup"><span data-stu-id="14c52-160">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md) 
- [<span data-ttu-id="14c52-161">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="14c52-161">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
