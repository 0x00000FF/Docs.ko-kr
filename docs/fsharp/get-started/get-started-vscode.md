---
title: 'Visual Studio Code에서 F #으로 시작.'
description: 'Visual Studio Code 및 Ionide 플러그 인 suite F #을 사용 하는 방법에 알아봅니다.'
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728630"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="4d9df-103">Visual Studio Code에서 F #으로 시작.</span><span class="sxs-lookup"><span data-stu-id="4d9df-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="4d9df-104">작성할 수 있습니다 F # [Visual Studio Code](https://code.visualstudio.com) 와 [Ionide 플러그 인](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)는 뛰어난 플랫폼, 간단한 통합 개발 환경 (IDE) 경험을 얻을 수 IntelliSense 및 기본 코드 리팩터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="4d9df-105">방문 [Ionide.io](http://ionide.io) 플러그 인 집합에 대 한 자세한 내용을 보려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d9df-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4d9df-106">Prerequisites</span></span>

<span data-ttu-id="4d9df-107">있어야 [git 설치](https://git-scm.com/download) 및 사용할 수 있도록 경로에 Ionide 프로젝트 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="4d9df-108">입력 하 여 올바르게 설치 되었는지 확인할 수 `git --version` 고 키를 눌러 명령 프롬프트에서 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="4d9df-109">macOS</span><span class="sxs-lookup"><span data-stu-id="4d9df-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="4d9df-110">사용 하 여 Ionide [모노](http://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-110">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="4d9df-111">Homebrew를 통해 모노 macOS에 설치 하는 가장 쉬운 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-111">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="4d9df-112">단순히 터미널에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="4d9df-113">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="4d9df-114">Linux</span><span class="sxs-lookup"><span data-stu-id="4d9df-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="4d9df-115">Linux에서 Ionide 또한 사용 하 여 [모노](https://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="4d9df-116">Debian 또는 Ubuntu 인 경우 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="4d9df-117">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="4d9df-118">Windows</span><span class="sxs-lookup"><span data-stu-id="4d9df-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="4d9df-119">Windows를 사용 하는 경우 해야 [F #를 지 원하는 Visual Studio 설치](get-started-visual-studio.md#installing-f)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="4d9df-120">작성, 컴파일 및 F # 코드를 실행 하는 데 필요한 모든 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="4d9df-121">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="4d9df-122">Visual Studio Code 및 Ionide 플러그 인 설치</span><span class="sxs-lookup"><span data-stu-id="4d9df-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="4d9df-123">Visual Studio Code에서 설치할 수는 [code.visualstudio.com](https://code.visualstudio.com) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>

<span data-ttu-id="4d9df-124">확장명 아이콘 및 "Ionide"에 대 한 검색을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-124">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="4d9df-125">Visual Studio 코드에서 지원 되는 F #에 필요한 유일한 플러그 인 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-125">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="4d9df-126">그러나 설치할 수도 있습니다 [Ionide 모조](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 가져오려는 [가짜](https://fsharp.github.io/FAKE/) 지원 및 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 가져오려는 [Paket](https://fsprojects.github.io/Paket/) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-126">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="4d9df-127">가짜 Paket F # 커뮤니티 하기 위한 추가 도구 프로젝트를 빌드 및 종속성을 각각 관리 되며 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-127">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="4d9df-128">Ionide를 사용 하 여 첫 번째 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4d9df-128">Creating your first project with Ionide</span></span>

<span data-ttu-id="4d9df-129">새 F # 프로젝트를 만들려면 (수 이름을 바꾸는) 인 새 폴더에 Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-129">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="4d9df-130">명령 팔레트를 열고 (**보기 > 명령 팔레트**) 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-130">Next, open the command pallette (**View > Command Pallette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="4d9df-131">연결 된 값이 고 [FORGE](https://github.com/fsharp-editing/Forge) 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="4d9df-131">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="4d9df-132">템플릿 옵션 보이지 않으면 명령 팔레트에서 다음 명령을 실행 하 여 서식 파일을 새로 고쳐 보세요: `>F#: Refresh Project Templates`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-132">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="4d9df-133">F #:: "새 프로젝트"를 클릭 하 여 선택 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-133">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="4d9df-134">이 위한 프로젝트 템플릿을 선택 하는 다음 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-134">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="4d9df-135">선택 된 `classlib` 템플릿과 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-135">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="4d9df-136">다음으로 프로젝트를 만들 수 있는 디렉터리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-136">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="4d9df-137">두면 빈, 현재 디렉터리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-137">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="4d9df-138">마지막으로, 마지막 단계에서 프로젝트를 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-138">Finally, name your project in the final step.</span></span> <span data-ttu-id="4d9df-139">사용 하 여 F # [파스칼식 대 / 소문자로](http://c2.com/cgi/wiki?PascalCase) 프로젝트 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-139">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="4d9df-140">이 문서에서는 `ClassLibraryDemo` 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-140">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="4d9df-141">프로젝트에 사용할 이름을 입력 하 여, 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-141">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="4d9df-142">이전 단계를 따른 경우 Visual Studio 코드 작업 영역 왼쪽에는 다음에 표시 될을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-142">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="4d9df-143">F # 프로젝트 자체를 아래에서 `ClassLibraryDemo` 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-143">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="4d9df-144">통해 패키지를 추가 하기 위한 올바른 디렉터리 구조 [ `Paket` ](https://fsprojects.github.io/Paket/)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-144">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="4d9df-145">플랫폼 간 빌드 스크립트와 [ `FAKE` ](https://fsharp.github.io/FAKE/)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-145">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="4d9df-146">`paket.exe` 패키지를 인출 하 고 있습니다에 대 한 종속성을 확인할 수 있는 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-146">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="4d9df-147">A `.gitignore` Git 기반 소스 제어에이 프로젝트를 추가 하려는 경우 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-147">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="4d9df-148">일부 코드 작성</span><span class="sxs-lookup"><span data-stu-id="4d9df-148">Writing some code</span></span>

<span data-ttu-id="4d9df-149">열기는 *ClassLibraryDemo* 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-149">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="4d9df-150">다음 파일이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-150">You should see the following files:</span></span>

1. <span data-ttu-id="4d9df-151">`ClassLibraryDemo.fs`를 정의 하는 클래스와 F # 구현 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-151">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="4d9df-152">`ClassLibraryDemo.fsproj`를이 프로젝트를 빌드하는 데는 F # 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-152">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="4d9df-153">`Script.fsx`는 F # 스크립트 파일을 소스 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-153">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="4d9df-154">`paket.references`프로젝트 종속성을 지정 하는 Paket 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-154">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="4d9df-155">열기 `Script.fsx`, 그 후에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-155">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="4d9df-156">이 함수는 형태의 단어 변환 [Pig 라틴](https://en.wikipedia.org/wiki/Pig_Latin)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-156">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="4d9df-157">다음 단계에서는 F # 대화형 (FSI)를 사용 하 여 평가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-157">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="4d9df-158">전체 함수 (11 줄 이어야 함)를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-158">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="4d9df-159">강조 표시 되 면 보유는 **Alt** 키 및 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-159">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="4d9df-160">아래 팝업 창을 보면 하 고 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-160">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ionide 사용 하 여 F # Interactive 출력의 예](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="4d9df-162">이 세 가지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-162">This did three things:</span></span>

1. <span data-ttu-id="4d9df-163">FSI 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-163">It started the FSI process.</span></span>
2. <span data-ttu-id="4d9df-164">FSI 프로세스를 통해 강조 표시 된 코드를 전송.</span><span class="sxs-lookup"><span data-stu-id="4d9df-164">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="4d9df-165">FSI 프로세스를 통해 전송 된 코드를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-165">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="4d9df-166">통해 보낸 되었으므로 [함수](../language-reference/functions/index.md), 이제 FSI 해당 함수를 호출할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="4d9df-166">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="4d9df-167">대화형 창에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-167">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="4d9df-168">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-168">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="4d9df-169">이제 첫 번째 문자로 함께 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-169">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="4d9df-170">다음을 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="4d9df-170">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="4d9df-171">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-171">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="4d9df-172">예상 대로 작동 하는 함수 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-172">The function appears to be working as expected.</span></span> <span data-ttu-id="4d9df-173">축 하 합니다, 방금 Visual Studio 코드에서 첫 번째 F # 함수를 작성 하 고 FSI를 사용 하 여 확인!</span><span class="sxs-lookup"><span data-stu-id="4d9df-173">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="4d9df-174">FSI에서 줄 종결 되는지 알 수 있습니다, 처럼 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-174">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="4d9df-175">즉, FSI를 사용 하면 여러 줄을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-175">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="4d9df-176">`;;` 끝 FSI 코드가 완료 되었을 때를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-176">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="4d9df-177">코드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-177">Explaining the code</span></span>

<span data-ttu-id="4d9df-178">코드 실제로 수행 하는 방법에 대 한 잘 모르는 경우 다음 단계별 마법사은입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-178">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="4d9df-179">볼 수 있듯이 `toPigLatin` 단어 입력으로 사용 하 고 단어의 Pig 라틴 문자 표현으로 변환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-179">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="4d9df-180">이 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-180">The rules for this are as follows:</span></span>

<span data-ttu-id="4d9df-181">단어의 첫 번째 문자는 함께 시작 되 면 ""이 얼 간 단어의 끝에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-181">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="4d9df-182">함께 시작 되지 않는다면 해당 첫 번째 문자는 단어의 끝으로 이동 합니다. 및 "집니다"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-182">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="4d9df-183">FSI에서 다음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-183">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="4d9df-184">이 나타내는 `toPigLatin` 에서 사용 되는 함수는 `string` 입력으로 (호출 `word`)를 반환 하는 값 및 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-184">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="4d9df-185">로 알려져는 [함수의 형식 서명이](https://fsharpforfunandprofit.com/posts/function-signatures/), F # 코드를 이해 하는 F #의 기본적인 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-185">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="4d9df-186">Visual Studio 코드의 함수 위로 가져가면에 다음이 표시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-186">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="4d9df-187">함수 본문에서 두 가지 부분을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-187">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="4d9df-188">호출 하는 내부 함수 `isVowel`를 결정 하는 경우 지정 된 문자 (`c`)를 통해 제공 된 패턴 중 하 나와 일치 하는 경우를 확인 하 여이 모음인 [패턴 일치](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="4d9df-188">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="4d9df-189">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) 인지 확인 하는 경우 첫 번째 문자에 모음이 구문에서 입력된 된 문자는 반환 값 인지에 따라 첫 번째 문자 식에 모음이 되었거나:</span><span class="sxs-lookup"><span data-stu-id="4d9df-189">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="4d9df-190">흐름 `toPigLatin` 있으므로:</span><span class="sxs-lookup"><span data-stu-id="4d9df-190">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="4d9df-191">입력된 단어의 첫 번째 문자에 모음이 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d9df-191">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="4d9df-192">인 경우 단어의 끝에 ""이 얼 간을 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-192">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="4d9df-193">그렇지 않으면 첫 번째 문자가 단어의 끝으로 이동 및 "집니다"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-193">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="4d9df-194">이 대 한 확인 해야 할 사항이 하나는:는 많은 다른 언어와 달리 하셨습니까 함수에서 반환할 수 없는 명시적 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-194">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="4d9df-195">F #은 식 기반 이며 함수의 본문에서 반환 값 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-195">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="4d9df-196">때문에 `if..then..else` 은 자체는 식의 본문은 `then` 블록 또는 본문에는 `else` 블록 입력된 값에 따라 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-196">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="4d9df-197">구현 파일에 스크립트 코드를 이동</span><span class="sxs-lookup"><span data-stu-id="4d9df-197">Moving your script code into the implementation file</span></span>

<span data-ttu-id="4d9df-198">이 문서의 이전 섹션에는 F # 코드를 작성 합니다. 일반적인 첫 번째 단계는 설명: FSI를 대화형으로 실행 하는 초기 함수를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-198">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="4d9df-199">복제 기반 개발으로도 알려져 있는 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 는 "읽기 평가 인쇄 루프"를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-199">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="4d9df-200">작업 결과가 있는 될 때까지 기능을 시험해 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-200">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="4d9df-201">복제 기반 개발의 다음 단계는 F # 구현 파일에 작업 코드를 옮기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-201">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="4d9df-202">그런 다음 컴파일될 수 F # 컴파일러에 의해 실행 될 수 있는 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-202">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="4d9df-203">를 시작 하려면 열기 `ClassLibraryDemo.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-203">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="4d9df-204">일부 코드는 이미에 있는 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-204">You'll notice that some code is already in there.</span></span> <span data-ttu-id="4d9df-205">계속 진행 하 고 클래스 정의 삭제 하지만을 남겨 두어야는 [ `namespace` ](../language-reference/namespaces.md) 위쪽에 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-205">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="4d9df-206">다음으로 새 만듭니다 [ `module` ](../language-reference/modules.md) 호출 `PigLatin` 복사는 `toPigLatin` 따라서 함수에:</span><span class="sxs-lookup"><span data-stu-id="4d9df-206">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="4d9df-207">을 열고는 `Script.fsx` 다시 파일을 전체 삭제 `toPigLatin` 작동할 수 있지만 파일에 다음 두 줄을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-207">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="4d9df-208">첫 번째 줄에 로드 하는 데 스크립팅을 FSI 필요한 `ClassLibraryDemo.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-208">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="4d9df-209">두 번째 줄은 편의 위해: 생략 하는 것은 선택 사항 이지만 입력할 필요가 `open ClassLibraryDemo` FSI 창 상태로 전환 하려는 경우에 `ToPigLatin` 범위로 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-209">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="4d9df-210">그런 다음 FSI 창에서 사용 하 여 함수 호출의 `PigLatin` 앞에서 정의한 모듈:</span><span class="sxs-lookup"><span data-stu-id="4d9df-210">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="4d9df-211">성공</span><span class="sxs-lookup"><span data-stu-id="4d9df-211">Success!</span></span> <span data-ttu-id="4d9df-212">이전에 동일한 결과를 가져오지만 이제 F # 구현 파일에서 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-212">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="4d9df-213">주요 차이점은 FSI에서 뿐 아니라 어디서 나 실행할 수 있는 어셈블리에 F # 소스 파일 파일은 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-213">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="4d9df-214">요약</span><span class="sxs-lookup"><span data-stu-id="4d9df-214">Summary</span></span>

<span data-ttu-id="4d9df-215">이 문서에서는 지금까지 학습:</span><span class="sxs-lookup"><span data-stu-id="4d9df-215">In this article, you've learned:</span></span>

1. <span data-ttu-id="4d9df-216">Ionide와 Visual Studio 코드를 설정 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="4d9df-216">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="4d9df-217">Ionide와 첫 번째 F # 프로젝트를 만드는 방법.</span><span class="sxs-lookup"><span data-stu-id="4d9df-217">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="4d9df-218">Ionide에서 첫 번째 F # 함수를 작성 한 후 FSI에서 실행 F # 스크립트를 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-218">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="4d9df-219">F # 소스를 스크립트 코드를 마이그레이션하고 FSI에서 해당 코드를 호출 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="4d9df-219">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="4d9df-220">코드를 작성할 훨씬 더 많은 F # Visual Studio Code 및 Ionide 사용 하 여 이제 정답입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-220">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4d9df-221">문제 해결</span><span class="sxs-lookup"><span data-stu-id="4d9df-221">Troubleshooting</span></span>

<span data-ttu-id="4d9df-222">여기 몇 가지 방법으로 충돌할 수 있는 특정 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-222">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="4d9df-223">코드 편집 Ionide의는 기능을 가져오려면 F # 파일 Visual Studio Code 작업 영역에서 열려 있는 폴더 내에서 디스크에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-223">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="4d9df-224">시스템에 변경 작업을 수행 하거나 Visual Studio 코드 열려 Ionide 필수 구성 요소를 설치, Visual Studio 코드를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-224">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="4d9df-225">F # 컴파일러 및 F # interactive 정식 경로 사용 하지 않고 명령줄에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-225">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="4d9df-226">입력 하 여 그렇게 할 수 `fsc` F # 컴파일러에 대 한 명령줄의 및 `fsi` 또는 `fsharpi` 에 대 한 Visual F # 도구 창 및 linux/Mac에서 모노에 각각.</span><span class="sxs-lookup"><span data-stu-id="4d9df-226">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="4d9df-227">프로젝트 디렉터리에 잘못 된 문자가 있으면 Ionide 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-227">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="4d9df-228">이 경우 프로젝트 디렉터리를 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-228">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="4d9df-229">작업 Ionide 명령 중 없음, 확인 프로그램 [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) 경우 재정의 중인에 실수로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-229">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="4d9df-230">컴퓨터에 Ionide 나뉘어집니다 위에 해당는 문제를 해결 하는 경우를 제거해 보세요는 `ionide-fsharp` 컴퓨터에 디렉터리 플러그 인 도구 모음을 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-230">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="4d9df-231">Ionide는 오픈 소스 프로젝트 작성 및 F # 커뮤니티의 회원이 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-231">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="4d9df-232">문제를 보고 하 고에 참가할 수 정도 하십시오는 [Ionide VSCode: FSharp GitHub 리포지토리](https://github.com/ionide/ionide-vscode-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-232">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="4d9df-233">보고서에 문제가 있는 경우 따르십시오 [문제를 보고할 때 사용 하는 로그를 가져오기 위한 지침은](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-233">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="4d9df-234">Ionide 개발자 및 F #에서 커뮤니티에서 도움을 요청할 수도 있습니다는 [Ionide Gitter 채널](https://gitter.im/ionide/ionide-project)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-234">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d9df-235">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4d9df-235">Next steps</span></span>

<span data-ttu-id="4d9df-236">F # 및 언어의 기능에 대 한 자세한 내용은 체크 아웃 [둘러보기의 F #](../tour.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9df-236">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
