---
title: Docker를 사용하여 앱 컨테이너화 - .NET Core
description: 이 자습서에서는 기본 .NET Core 애플리케이션을 만들고 Docker를 사용하여 컨테이너화하는 방법을 설명합니다.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8f08936142b0cc44baf268f100e228f68920b69d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126370"
---
# <a name="how-to-containerize-a-net-core-application"></a><span data-ttu-id="c8886-103">.NET Core 애플리케이션을 컨테이너화하는 방법</span><span class="sxs-lookup"><span data-stu-id="c8886-103">How to containerize a .NET Core application</span></span>

<span data-ttu-id="c8886-104">이 자습서에서는 Docker 컨테이너 빌드 및 .NET Core 응용 프로그램에 대한 배포 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-104">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="c8886-105">[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform)은 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine)을 사용하여 [Docker 이미지](https://docs.docker.com/glossary/?term=image)로 앱을 신속하게 빌드하고 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-105">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="c8886-106">이러한 이미지는 [계층화된 컨테이너](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)에서 배포되고 실행되도록 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-106">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="c8886-107">이 자습서를 진행하면서 다음을 익히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-107">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="c8886-108">Dockerfile 파일을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="c8886-108">How to create a Dockerfile</span></span>
> * <span data-ttu-id="c8886-109">.NET Core 앱을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="c8886-109">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="c8886-110">앱을 Docker 컨테이너에 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="c8886-110">How to deploy your app into a Docker container.</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="c8886-111">.NET Core: 시작하는 가장 쉬운 방법</span><span class="sxs-lookup"><span data-stu-id="c8886-111">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="c8886-112">Docker 이미지를 만들기 전에 컨테이너화할 응용 프로그램이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-112">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="c8886-113">Linux, MacOS 또는 Windows에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-113">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="c8886-114">작업을 수행하는 가장 빠르고 쉬운 방법은 .NET Core를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-114">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="c8886-115">.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/index.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="c8886-115">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="c8886-116">[다중 아키텍처 기반 태그](https://github.com/dotnet/announcements/issues/14)를 사용하여 Windows와 Linux 컨테이너 모두를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-116">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="c8886-117">첫 번째 .NET Core Docker 앱</span><span class="sxs-lookup"><span data-stu-id="c8886-117">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c8886-118">전제 조건</span><span class="sxs-lookup"><span data-stu-id="c8886-118">Prerequisites</span></span>

<span data-ttu-id="c8886-119">이 자습서를 완료하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-119">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="c8886-120">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="c8886-120">.NET Core SDK</span></span>

* <span data-ttu-id="c8886-121">[.NET Core 2.1 SDK](https://www.microsoft.com/net/download) 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-121">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="c8886-122">.NET Core 2.1이 지원되는 운영 체제, 지원되지 않는 OS 버전 및 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8886-122">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="c8886-123">아직 없는 경우 즐겨 찾는 코드 편집기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-123">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="c8886-124">코드 편집기를 설치해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c8886-124">Need to install a code editor?</span></span> <span data-ttu-id="c8886-125">[Visual Studio Code](https://code.visualstudio.com/download)를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c8886-125">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="c8886-126">Docker 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="c8886-126">Installing Docker Client</span></span>

<span data-ttu-id="c8886-127">[Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) 이상의 Docker 클라이언트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-127">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="c8886-128">Docker 클라이언트를 다음에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-128">The Docker client can be installed in:</span></span>

* <span data-ttu-id="c8886-129">Linux 배포</span><span class="sxs-lookup"><span data-stu-id="c8886-129">Linux distributions</span></span>

   * [<span data-ttu-id="c8886-130">CentOS</span><span class="sxs-lookup"><span data-stu-id="c8886-130">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="c8886-131">Debian</span><span class="sxs-lookup"><span data-stu-id="c8886-131">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="c8886-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="c8886-132">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="c8886-133">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8886-133">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="c8886-134">macOS</span><span class="sxs-lookup"><span data-stu-id="c8886-134">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="c8886-135">[Windows](https://docs.docker.com/docker-for-windows/install/)</span><span class="sxs-lookup"><span data-stu-id="c8886-135">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="c8886-136">Dockerization에 대한 .NET Core 2.1 콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="c8886-136">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="c8886-137">명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-137">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="c8886-138">만든 폴더로 이동하고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-138">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="c8886-139">이제 간단한 연습을 해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-139">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="c8886-140">[`dotnet new`](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 `Hello.csproj` 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-140">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="c8886-141">응용 프로그램에 대한 진입점을 포함하는 기본 파일인 `Program.cs`도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-141">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="c8886-142">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="c8886-142">`Hello.csproj`:</span></span>

   <span data-ttu-id="c8886-143">프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-143">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="c8886-144">`OutputType` 태그에서는 실행 파일, 즉 콘솔 응용 프로그램을 빌드하고 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-144">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="c8886-145">`TargetFramework` 태그에서는 대상으로 하는 .NET 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-145">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="c8886-146">고급 시나리오에서는 여러 대상 프레임워크를 지정하고 단일 작업에서 지정된 프레임워크로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-146">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="c8886-147">이 자습서에서는 .NET Core 2.1용으로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-147">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="c8886-148">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="c8886-148">`Program.cs`:</span></span>

   <span data-ttu-id="c8886-149">프로그램은 `using System`으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-149">The program starts by `using System`.</span></span> <span data-ttu-id="c8886-150">즉, "`System` 네임스페이스의 모든 항목을 이 파일 범위로 가져옵니다".</span><span class="sxs-lookup"><span data-stu-id="c8886-150">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="c8886-151">`System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-151">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="c8886-152">그런 다음 `Hello`라는 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-152">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="c8886-153">네임스페이스를 원하는 값으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-153">You can change namespace to anything you want.</span></span> <span data-ttu-id="c8886-154">`Program`이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-154">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="c8886-155">이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-155">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="c8886-156">예제에서 프로그램은 콘솔에 "Hello World!"만</span><span class="sxs-lookup"><span data-stu-id="c8886-156">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="c8886-157">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-157">to the console.</span></span>

   <span data-ttu-id="c8886-158">**dotnet new**는 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-158">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="c8886-159">**Dotnet restore**는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자) 호출로 종속성 트리를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-159">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="c8886-160">NuGet은 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-160">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="c8886-161">*Hello.csproj* 파일을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-161">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="c8886-162">파일 종속성을 다운로드하거나 머신 캐시에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-162">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="c8886-163">*obj/project.assets.json* 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-163">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="c8886-164">*project.assets.json* 파일은 NuGet 종속성 그래프, 바인딩 해상도 및 다른 앱 메타데이터의 전체 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-164">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="c8886-165">이 필수 파일은 소스 코드를 올바르게 처리하도록 [`dotnet build`](../tools/dotnet-build.md) 및 [`dotnet run`](../tools/dotnet-run.md) 등의 다른 도구에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-165">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="c8886-166">[`dotnet run`](../tools/dotnet-run.md)는 성공적인 필드를 확인하기 위해 [`dotnet build`](../tools/dotnet-build.md)를 호출한 다음 응용 프로그램을 실행하기 위해 `dotnet <assembly.dll>`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-166">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="c8886-167">고급 시나리오의 경우 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8886-167">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="c8886-168">.NET Core 응용 프로그램 Docker화</span><span class="sxs-lookup"><span data-stu-id="c8886-168">Dockerize the .NET Core application</span></span>

<span data-ttu-id="c8886-169">Hello .NET Core 콘솔 앱은 성공적으로 로컬로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-169">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="c8886-170">이제 한 단계 나아가서 Docker에서 앱을 빌드하고 실행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-170">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="c8886-171">첫 번째 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="c8886-171">Your first Dockerfile</span></span>

<span data-ttu-id="c8886-172">텍스트 편집기를 열고 시작해 보겠습니다!</span><span class="sxs-lookup"><span data-stu-id="c8886-172">Open your text editor and let's get started!</span></span> <span data-ttu-id="c8886-173">앱을 빌드한 Hello 디렉터리에서 계속 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-173">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="c8886-174">Linux 또는 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/)용 다음 Docker 명령을 새 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-174">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="c8886-175">완료되면 확장명 없이 Hello 디렉터리의 루트에 **Dockerfile**로 저장합니다(파일 형식을 `All types (*.*)` 또는 유사한 것으로 설정해야 할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="c8886-175">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="c8886-176">Dockerfile은 순서대로 실행되는 Docker 빌드 명령을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-176">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="c8886-177">첫 번째 명령은 [**FROM**](https://docs.docker.com/engine/reference/builder/#from)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-177">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="c8886-178">이 명령은 새 빌드 단계를 초기화하고 나머지 명령에 대한 기본 이미지를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-178">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="c8886-179">다중 아키텍처 태그는 Windows [컨테이너 모드](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)용 Docker에 따라 Windows 또는 Linux 컨테이너를 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-179">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="c8886-180">샘플에 대한 기본 이미지는 microsoft/dotnet 리포지토리에 있는 2.1-sdk 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-180">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="c8886-181">[**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) 명령은 나머지 RUN, CMD, ENTRYPOINT, COPY 및 ADD Dockerfile 명령에 대해 작업 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-181">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="c8886-182">디렉터리가 없을 경우 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-182">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="c8886-183">이 경우 WORKDIR은 앱 디렉터리로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-183">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="c8886-184">[**COPY**](https://docs.docker.com/engine/reference/builder/#copy) 명령은 원본 경로에서 새 파일 또는 디렉터리를 복사하고 대상 컨테이너 파일 시스템에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-184">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="c8886-185">이 명령으로 C# 프로젝트 파일을 컨테이너에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-185">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="c8886-186">[**RUN**](https://docs.docker.com/engine/reference/builder/#run) 명령은 현재 이미지를 기반으로 새 계층의 모든 명령을 실행하고 결과를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-186">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="c8886-187">커밋된 결과 이미지는 Dockerfile의 다음 단계에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-187">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="c8886-188">C# 프로젝트 파일의 필요한 종속성을 가져오기 위해 **dotnet restore**를 실행하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-188">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="c8886-189">이 **COPY** 명령은 파일의 나머지 부분을 새 [계층](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)의 컨테이너로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-189">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="c8886-190">이 **RUN** 명령으로 앱을 게시하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-190">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="c8886-191">[**dotnet publish**](../tools/dotnet-publish.md) 명령은 응용 프로그램을 컴파일하고, 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-191">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="c8886-192">앱은 **릴리스** 구성과 함께 게시되며 기본 디렉터리에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-192">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="c8886-193">[**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) 명령을 통해 컨테이너는 실행 파일로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-193">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="c8886-194">이제 다음을 수행하는 Dockerfile이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-194">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="c8886-195">앱을 이미지에 복사</span><span class="sxs-lookup"><span data-stu-id="c8886-195">copies your app to the image</span></span>
* <span data-ttu-id="c8886-196">이미지에 대한 앱의 종속성</span><span class="sxs-lookup"><span data-stu-id="c8886-196">your app's dependencies to the image</span></span>
* <span data-ttu-id="c8886-197">앱이 실행 파일로 실행되도록 빌드</span><span class="sxs-lookup"><span data-stu-id="c8886-197">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="c8886-198">Hello .NET Core 앱 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="c8886-198">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="c8886-199">필수 Docker 명령</span><span class="sxs-lookup"><span data-stu-id="c8886-199">Essential Docker commands</span></span>

<span data-ttu-id="c8886-200">필수 Docker 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-200">These Docker commands are essential:</span></span>

* [<span data-ttu-id="c8886-201">docker build</span><span class="sxs-lookup"><span data-stu-id="c8886-201">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="c8886-202">docker run</span><span class="sxs-lookup"><span data-stu-id="c8886-202">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="c8886-203">docker ps</span><span class="sxs-lookup"><span data-stu-id="c8886-203">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="c8886-204">docker stop</span><span class="sxs-lookup"><span data-stu-id="c8886-204">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="c8886-205">docker rm</span><span class="sxs-lookup"><span data-stu-id="c8886-205">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="c8886-206">docker rmi</span><span class="sxs-lookup"><span data-stu-id="c8886-206">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="c8886-207">docker image</span><span class="sxs-lookup"><span data-stu-id="c8886-207">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="c8886-208">빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="c8886-208">Build and run</span></span>

<span data-ttu-id="c8886-209">dockerfile을 작성했습니다. 이제 Docker는 앱을 빌드한 다음 컨테이너를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-209">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="c8886-210">`docker build` 명령의 출력은 다음 콘솔 출력과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-210">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="c8886-211">출력에서 볼 수 있듯이 Docker 엔진은 컨테이너를 빌드하는 데 Dockerfile을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-211">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="c8886-212">`docker run` 명령의 출력은 다음 콘솔 출력과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-212">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="c8886-213">지금까지</span><span class="sxs-lookup"><span data-stu-id="c8886-213">Congratulations!</span></span> <span data-ttu-id="c8886-214">다음 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-214">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="c8886-215">로컬 .NET Core 앱 생성</span><span class="sxs-lookup"><span data-stu-id="c8886-215">Created a local .NET Core app</span></span>
> * <span data-ttu-id="c8886-216">첫 번째 컨테이너를 빌드하도록 Dockerfile 생성</span><span class="sxs-lookup"><span data-stu-id="c8886-216">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="c8886-217">Docker화된 앱 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="c8886-217">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8886-218">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c8886-218">Next steps</span></span>

<span data-ttu-id="c8886-219">수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8886-219">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="c8886-220">.NET Docker 이미지 비디오 소개</span><span class="sxs-lookup"><span data-stu-id="c8886-220">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="c8886-221">Visual Studio, Docker 및 Azure Container Instances의 시너지 효과!</span><span class="sxs-lookup"><span data-stu-id="c8886-221">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [<span data-ttu-id="c8886-222">Azure 빠른 시작용 Docker</span><span class="sxs-lookup"><span data-stu-id="c8886-222">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="c8886-223">Azure용 Docker에서 앱 배포</span><span class="sxs-lookup"><span data-stu-id="c8886-223">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="c8886-224">Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c8886-224">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="c8886-225">이 샘플에 사용된 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="c8886-225">Docker Images used in this sample</span></span>

<span data-ttu-id="c8886-226">이 샘플에서는 다음 Docker 이미지가 사용됨</span><span class="sxs-lookup"><span data-stu-id="c8886-226">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="c8886-227">관련 참고 자료</span><span class="sxs-lookup"><span data-stu-id="c8886-227">Related resources</span></span>

* [<span data-ttu-id="c8886-228">.NET Core Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="c8886-228">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [<span data-ttu-id="c8886-229">Windows 컨테이너의 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="c8886-229">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="c8886-230">.NET Framework Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="c8886-230">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="c8886-231">DockerHub의 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c8886-231">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="c8886-232">.NET Core 응용 프로그램 Docker화 - Docker 자습서</span><span class="sxs-lookup"><span data-stu-id="c8886-232">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="c8886-233">Visual Studio Docker 도구로 작업</span><span class="sxs-lookup"><span data-stu-id="c8886-233">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="c8886-234">Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포</span><span class="sxs-lookup"><span data-stu-id="c8886-234">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)