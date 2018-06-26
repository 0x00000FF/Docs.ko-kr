---
title: Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작
description: 이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: dd8262a7d2fa03ab06f9f85e91c298f52e3c0849
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315149"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="96a91-103">Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="96a91-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="96a91-104">Visual Studio for Mac은 .NET Core 응용 프로그램 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="96a91-105">이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="96a91-106">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-106">Your feedback is highly valued.</span></span> <span data-ttu-id="96a91-107">두 가지가 Visual Studio for Mac의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-107">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="96a91-108">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="96a91-109">[Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="96a91-110">제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio UserVoice 웹 페이지](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96a91-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="96a91-111">Prerequisites</span></span>

<span data-ttu-id="96a91-112">[Mac에서 .NET Core의 필수 구성 요소](../../core/macos-prerequisites.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96a91-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="96a91-113">시작</span><span class="sxs-lookup"><span data-stu-id="96a91-113">Getting started</span></span>

<span data-ttu-id="96a91-114">필수 구성 요소와 Visual Studio for Mac을 이미 설치한 경우 이 섹션을 건너뛰고 [프로젝트 만들기](#creating-a-project)를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="96a91-115">다음 단계에 따라 필수 구성 요소 및 Visual Studio for Mac을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="96a91-116">[Visual Studio for Mac 설치 관리자](https://visualstudio.microsoft.com/vs/visual-studio-mac/)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="96a91-117">설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-117">Run the installer.</span></span> <span data-ttu-id="96a91-118">사용권 계약을 읽은 다음 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-118">Read and accept the license agreement.</span></span> <span data-ttu-id="96a91-119">설치하는 동안 플랫폼 간 모바일 앱 개발 기술인 Xamarin을 설치할 기회가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="96a91-120">Xamarin 및 관련된 구성 요소의 설치는 .NET Core 개발에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="96a91-121">Visual Studio for Mac 설치 프로세스에 대한 연습을 진행하려면 [Visual Studio for Mac 소개](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96a91-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="96a91-122">설치가 완료되면 Visual Studio for Mac IDE를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="96a91-123">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="96a91-123">Creating a project</span></span>

1. <span data-ttu-id="96a91-124">시작 화면에서 **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-124">Select **New Project** on the Welcome screen.</span></span>

   ![Visual Studio for Mac 시작 화면의 새 프로젝트 단추](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="96a91-126">**새 프로젝트** 대화 상자에서 **.NET Core** 노드 아래에서 **앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="96a91-127">**콘솔 응용 프로그램** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![새 프로젝트 템플릿 목록](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="96a91-129">**프로젝트 이름**으로 "HelloWorld"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="96a91-130">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-130">Select **Create**.</span></span>

   ![새 콘솔 응용 프로그램 대화 상자 구성](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="96a91-132">프로젝트의 종속성이 복원되는 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="96a91-133">프로젝트에는 `Main` 메서드가 있는 `Program` 클래스를 포함하는 C# 파일 *Program.cs*가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="96a91-134">앱이 실행되면 `Console.WriteLine` 문은 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="96a91-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="96a91-135">콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-135">to the console when the app is run.</span></span>

   ![Program.cs 파일이 열려 있는 주 창](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="96a91-137">응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="96a91-137">Run the application</span></span>

<span data-ttu-id="96a91-138"><kbd>F5</kbd> 키를 사용하여 디버그 모드에서 또는 <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 사용하여 릴리스 모드에서 이 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![응용 프로그램 출력 창에 Hello World!가 표시됩니다.](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="96a91-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="96a91-140">Next step</span></span>

<span data-ttu-id="96a91-141">[Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드](using-on-mac-vs-full-solution.md) 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 전체 .NET Core 솔루션을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96a91-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
