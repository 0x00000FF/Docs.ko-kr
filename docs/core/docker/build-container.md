---
title: Docker를 사용하여 앱 컨테이너화 자습서
description: 이 자습서에서는 Docker를 사용하여 .NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: f0e0fad9bde4c35fb5c5b0b505b9fa8441e432ba
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926312"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="1e974-103">자습서: .NET Core 앱 컨테이너화</span><span class="sxs-lookup"><span data-stu-id="1e974-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="1e974-104">이 자습서에서는 .NET Core 애플리케이션을 포함하는 Docker 이미지를 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="1e974-105">이미지를 사용하여 로컬 개발 환경이나 프라이빗 클라우드 또는 퍼블릭 클라우드용 컨테이너를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="1e974-106">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="1e974-107">간단한 .NET Core 앱 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="1e974-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="1e974-108">.NET Core용 Dockerfile 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="1e974-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="1e974-109">Docker 이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="1e974-109">Build a Docker image</span></span>
> * <span data-ttu-id="1e974-110">Docker 컨테이너 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="1e974-110">Create and run a Docker container</span></span>

<span data-ttu-id="1e974-111">.NET Core 애플리케이션용 Docker 컨테이너 빌드 및 배포 작업을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="1e974-112">Docker 플랫폼은 Docker 엔진을 사용하여 Docker 이미지로 앱을 신속하게 빌드하고 패키지합니다.   </span><span class="sxs-lookup"><span data-stu-id="1e974-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="1e974-113">이 이미지는 계층화된 컨테이너에서 배포되고 실행되도록 *Dockerfile* 형식으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e974-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="1e974-114">Prerequisites</span></span>

<span data-ttu-id="1e974-115">다음 필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-115">Install the following prerequisites:</span></span>

* <span data-ttu-id="1e974-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="1e974-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="1e974-117">.NET Core가 설치되어 있는 경우 `dotnet --info` 명령을 사용하여 사용 중인 SDK를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

* [<span data-ttu-id="1e974-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="1e974-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

* <span data-ttu-id="1e974-119">*Dockerfile* 및 .NET Core 예제 앱의 임시 작업 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-119">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="1e974-120">이 자습서에서는 이름 `docker-working`이 작업 폴더로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-120">In this tutorial, the name `docker-working` is used as the working folder.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="1e974-121">SDK 버전 2.2 사용</span><span class="sxs-lookup"><span data-stu-id="1e974-121">Use SDK version 2.2</span></span>

<span data-ttu-id="1e974-122">3\.0 같은 최신 SDK를 사용하는 경우 앱에서 2.2 SDK를 사용해야 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-122">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="1e974-123">작업 폴더에 `global.json`이라는 파일을 만들고 다음 json 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-123">Create a file named `global.json` in your working folder and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="1e974-124">이 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-124">Save this file.</span></span> <span data-ttu-id="1e974-125">파일이 존재하면 .NET Core에서는 이 폴더 및 아래에서 호출된 모든 `dotnet` 명령에 버전 2.2를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-125">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this folder and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="1e974-126">.NET Core 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="1e974-126">Create .NET Core app</span></span>

<span data-ttu-id="1e974-127">Docker 컨테이너가 실행되는 .NET Core 앱이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-127">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="1e974-128">아직 없는 경우, 터미널을 열고 작업 폴더를 만든 후 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-128">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="1e974-129">작업 폴더에서 다음 명령을 실행하여 app이라는 하위 디렉터리에서 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-129">In the working folder, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="1e974-130">폴더 트리는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-130">Your folder tree will look like the following:</span></span>

```
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="1e974-131">`dotnet new` 명령은 *app*이라는 새 폴더를 만들고 “Hello World” 앱을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-131">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="1e974-132">*app* 폴더를 입력하고 `dotnet run` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-132">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="1e974-133">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-133">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="1e974-134">기본 템플릿은 터미널에 인쇄한 후 종료되는 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-134">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="1e974-135">이 자습서에서는 무한 반복되는 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-135">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="1e974-136">텍스트 편집기에서 **Program.cs** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-136">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="1e974-137">현재는 다음 코드와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-137">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="1e974-138">1초마다 숫자를 계산하는 다음 코드로 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-138">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="1e974-139">파일을 저장하고 `dotnet run`을 사용하여 프로그램을 다시 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-139">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="1e974-140">이 앱은 무한 실행된다는 점을 명심하세요.</span><span class="sxs-lookup"><span data-stu-id="1e974-140">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="1e974-141">취소 명령 <kbd>CTRL+C</kbd>를 사용하여 앱을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-141">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="1e974-142">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-142">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="1e974-143">명령줄의 숫자를 앱에 전달하면 해당 양까지만 계산되고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-143">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="1e974-144">앱에서 `dotnet run -- 5`를 사용하여 5까지 계산해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1e974-144">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="1e974-145">`--` 이후 매개 변수는 `dotnet run` 명령에 전달되지 않고 대신 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-145">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="1e974-146">.NET Core 앱 게시</span><span class="sxs-lookup"><span data-stu-id="1e974-146">Publish .NET Core app</span></span>

<span data-ttu-id="1e974-147">Docker 이미지에 .NET Core 앱을 추가하기 전에 해당 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-147">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="1e974-148">앱이 시작될 때 컨테이너가 게시된 버전의 앱을 실행하는지 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-148">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="1e974-149">작업 폴더에서 예제 소스 코드가 있는 **app** 폴더를 입력하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-149">From the working folder, enter the **app** folder with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="1e974-150">이 명령은 앱을 **publish** 폴더로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-150">This command compiles your app to the **publish** folder.</span></span> <span data-ttu-id="1e974-151">작업 폴더에서 **publish** 폴더의 경로는 `.\app\bin\Release\netcoreapp2.2\publish\`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-151">The path to the **publish** folder from the working folder should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="1e974-152">publish 폴더의 디렉터리 목록을 가져오고 **myapp.dll**이 생성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-152">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="1e974-153">**app** 폴더에서 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-153">From the **app** folder, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="1e974-154">Dockerfile 만들기</span><span class="sxs-lookup"><span data-stu-id="1e974-154">Create the Dockerfile</span></span>

<span data-ttu-id="1e974-155">*Dockerfile* 파일은 `docker build` 명령에서 컨테이너 이미지를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="1e974-156">이 파일은 확장명이 없는 *Dockerfile*이라는 일반 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span>

<span data-ttu-id="1e974-157">터미널에서 시작 시에 생성한 작업 폴더로 디렉터리를 위쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-157">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="1e974-158">작업 폴더에 *Dockerfile*이라는 파일을 만들고 텍스트 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-158">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="1e974-159">다음 명령을 파일의 첫 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-159">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="1e974-160">`FROM` 명령은 **mcr.microsoft.com/dotnet/core/runtime** 리포지토리에서 **2.2** 태그가 지정된 이미지를 풀하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-160">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="1e974-161">SDK에서 대상으로 지정된 런타임과 일치하는 .NET Core 런타임을 풀해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-161">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="1e974-162">예를 들어 이전 섹션에서 만든 앱은 .NET Core 2.2 SDK를 사용하고 .NET Core 2.2를 대상으로 하는 앱을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-162">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="1e974-163">따라서 *Dockerfile*에서 참조되는 기본 이미지에는 **2.2** 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-163">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="1e974-164">*Dockerfile* 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="1e974-165">작업 폴더의 디렉터리 구조는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="1e974-166">문서에서 공간을 절약하기 위해 더 깊은 수준의 파일과 폴더의 일부가 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="1e974-167">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="1e974-168">Docker가 *Dockerfile*에서 각 줄을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="1e974-169">`docker build` 명령의 `.`는 *Dockerfile*을 찾는 데 현재 폴더를 사용하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="1e974-170">이 명령은 이미지를 빌드하고 해당 이미지를 가리키는 **myimage**라는 로컬 리포지토리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="1e974-171">이 명령이 완료된 후 `docker images`를 실행하여 설치된 이미지 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="1e974-172">두 이미지가 동일한 **IMAGE ID** 값을 공유함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="1e974-173">*Dockerfile*의 유일한 명령은 기존 이미지를 기반으로 새 이미지를 만드는 것이므로 두 이미지에서 해당 값이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="1e974-174">*Dockerfile*에 두 개의 명령을 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="1e974-175">각 명령은 **myimage** 리포지토리가 가리키는 이미지를 나타내는 마지막 명령으로 새 이미지 계층을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-175">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="1e974-176">`COPY` 명령은 컴퓨터의 지정된 폴더를 컨테이너의 폴더에 복사하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="1e974-177">이 예제에서 **publish** 폴더는 컨테이너의 **app** 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-177">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="1e974-178">다음 명령인 `ENTRYPOINT`는 컨테이너가 실행 파일로 실행되게 컨테이너를 구성하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="1e974-179">컨테이너가 시작되면 `ENTRYPOINT` 명령이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="1e974-180">이 명령이 종료되면 컨테이너가 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="1e974-181">터미널에서 `docker build -t myimage -f Dockerfile .`를 실행하고 명령이 완료되면 `docker images`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="1e974-182">*Dockerfile*의 각 명령이 계층을 생성하고 **IMAGE ID**를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="1e974-183">마지막 **IMAGE ID**(사용자에 따라 다름)는 **ddcc6646461b**이고 다음에 이 이미지를 기반으로 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="1e974-184">컨테이너 만들기</span><span class="sxs-lookup"><span data-stu-id="1e974-184">Create a container</span></span>

<span data-ttu-id="1e974-185">이제 앱을 포함하는 이미지가 있으므로 컨테이너를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="1e974-186">두 가지 방법으로 컨테이너를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-186">You can create a container in two ways.</span></span> <span data-ttu-id="1e974-187">먼저 중지된 새 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="1e974-188">위에서 `docker create` 명령은 **myimage** 이미지를 기반으로 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="1e974-189">해당 명령의 출력은 생성된 컨테이너의 **CONTAINER ID**(사용자에 따라 다름)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="1e974-190">모든 컨테이너 목록을 보려면 `docker ps -a` 명령을 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="1e974-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="1e974-191">컨테이너 관리</span><span class="sxs-lookup"><span data-stu-id="1e974-191">Manage the container</span></span>

<span data-ttu-id="1e974-192">각 컨테이너에는 해당 컨테이너 인스턴스를 참조하는 데 사용할 수 있는 임의 이름이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="1e974-193">예를 들어 자동으로 생성된 컨테이너에 **boring_matsumoto**(사용자에 따라 다름) 이름이 선택되면 해당 이름을 사용하여 컨테이너를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-193">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="1e974-194">`docker create --name` 매개 변수를 사용하여 특정 이름으로 자동 이름을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="1e974-195">다음 예제에서는 `docker start` 명령을 사용하여 컨테이너를 시작한 후 `docker ps` 명령을 사용하여 실행 중인 컨테이너만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="1e974-196">마찬가지로 `docker stop` 명령은 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="1e974-197">다음 예제에서는 `docker stop` 명령을 사용하여 컨테이너를 중지한 후 `docker ps` 명령을 사용하여 컨테이너가 실행 중이지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="1e974-198">컨테이너에 연결</span><span class="sxs-lookup"><span data-stu-id="1e974-198">Connect to a container</span></span>

<span data-ttu-id="1e974-199">컨테이너가 실행된 후 컨테이너에 연결하여 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="1e974-200">`docker start` 및 `docker attach` 명령을 사용하여 컨테이너를 시작하고 출력 스트림을 피킹합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="1e974-201">이 예제에서는 <kbd>CTRL+C</kbd> 명령을 사용하여 실행 중인 컨테이너에서 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-201">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="1e974-202">이렇게 하면 실제로 컨테이너에서 프로세스가 종료되어 컨테이너가 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-202">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="1e974-203">`--sig-proxy=false` 매개 변수는 <kbd>CTRL + C</kbd>가 컨테이너에서 프로세스를 중지하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="1e974-204">컨테이너에서 분리한 후 다시 연결하여 계속 실행 및 계산 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="1e974-205">컨테이너 삭제</span><span class="sxs-lookup"><span data-stu-id="1e974-205">Delete a container</span></span>

<span data-ttu-id="1e974-206">이 문서의 목적이 아무 작업도 수행하지 않는 컨테이너를 만드는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="1e974-207">이전에 만든 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-207">Delete the container you previously created.</span></span> <span data-ttu-id="1e974-208">컨테이너가 실행 중이면 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-208">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="1e974-209">다음 예제에는 모든 컨테이너가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-209">The following example lists all containers.</span></span> <span data-ttu-id="1e974-210">`docker rm` 명령을 사용하여 컨테이너를 삭제한 후 실행 중인 컨테이너가 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="1e974-211">단일 실행</span><span class="sxs-lookup"><span data-stu-id="1e974-211">Single run</span></span>

<span data-ttu-id="1e974-212">Docker는 단일 명령으로 컨테이너를 만들고 실행할 수 있는 `docker run` 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="1e974-213">이 명령을 사용하면 `docker create`를 실행한 후 `docker start`를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="1e974-214">컨테이너가 중지될 때 컨테이너를 자동으로 삭제하도록 이 명령을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="1e974-215">예를 들어 `docker run -it --rm`을 사용하여 두 가지 작업을 수행합니다. 먼저 현재 터미널을 사용하여 컨테이너에 연결한 후 컨테이너가 완료되면 컨테이너를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="1e974-216">`docker run -it`을 사용하면 <kbd>CTRL+C</kbd> 명령이 컨테이너에서 실행 중인 프로세스를 중지하고, 이에 따라 컨테이너가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="1e974-217">`--rm` 매개 변수가 제공되었으므로 프로세스가 중지되면 컨테이너가 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="1e974-218">컨테이너가 존재하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-218">Verify that it does not exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="1e974-219">ENTRYPOINT 변경</span><span class="sxs-lookup"><span data-stu-id="1e974-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="1e974-220">`docker run` 명령을 사용하면 *Dockerfile*에서 `ENTRYPOINT` 명령을 수정하고 해당 컨테이너에만 해당하는 다른 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="1e974-221">예를 들어 다음 명령을 사용하여 `bash` 또는 `cmd.exe`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="1e974-222">필요에 따라 명령을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="1e974-223">Windows</span><span class="sxs-lookup"><span data-stu-id="1e974-223">Windows</span></span>
<span data-ttu-id="1e974-224">이 예제에서 `ENTRYPOINT`는 `cmd.exe`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="1e974-225"><kbd>Ctrl+C</kbd>를 눌러 프로세스를 종료하고 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-225"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a><span data-ttu-id="1e974-226">Linux</span><span class="sxs-lookup"><span data-stu-id="1e974-226">Linux</span></span>

<span data-ttu-id="1e974-227">이 예제에서 `ENTRYPOINT`는 `bash`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="1e974-228">`quit` 명령이 실행되면 프로세스가 종료되고 컨테이너가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="1e974-229">필수 명령</span><span class="sxs-lookup"><span data-stu-id="1e974-229">Essential commands</span></span>

<span data-ttu-id="1e974-230">Docker에는 컨테이너 및 이미지로 수행할 작업을 다루는 다른 명령이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="1e974-231">이 Docker 명령은 컨테이너 관리에 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-231">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="1e974-232">docker build</span><span class="sxs-lookup"><span data-stu-id="1e974-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="1e974-233">docker run</span><span class="sxs-lookup"><span data-stu-id="1e974-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="1e974-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="1e974-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="1e974-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="1e974-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="1e974-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="1e974-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="1e974-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="1e974-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="1e974-238">docker image</span><span class="sxs-lookup"><span data-stu-id="1e974-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="1e974-239">리소스 정리</span><span class="sxs-lookup"><span data-stu-id="1e974-239">Clean up resources</span></span>

<span data-ttu-id="1e974-240">이 자습서에서는 컨테이너 및 이미지를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-240">During this tutorial you created containers and images.</span></span> <span data-ttu-id="1e974-241">원하는 경우 이 리소스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-241">If you want, delete these resources.</span></span> <span data-ttu-id="1e974-242">다음 명령을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-242">Use the following commands to</span></span>

01. <span data-ttu-id="1e974-243">모든 컨테이너 나열</span><span class="sxs-lookup"><span data-stu-id="1e974-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="1e974-244">실행 중인 컨테이너 중지</span><span class="sxs-lookup"><span data-stu-id="1e974-244">Stop containers that are running.</span></span> <span data-ttu-id="1e974-245">`CONTAINER_NAME`은 컨테이너에 자동으로 할당된 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="1e974-246">컨테이너 삭제</span><span class="sxs-lookup"><span data-stu-id="1e974-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="1e974-247">그런 다음, 머신에서 더 이상 사용하지 않을 이미지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="1e974-248">*Dockerfile*에서 만든 이미지를 삭제한 후 *Dockerfile*이 기반으로 하는 .NET Core 이미지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="1e974-249">**IMAGE ID** 또는 **REPOSITORY:TAG** 형식 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="1e974-250">`docker images` 명령을 사용하여 설치된 이미지 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="1e974-251">이미지 파일이 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-251">Image files can be large.</span></span> <span data-ttu-id="1e974-252">일반적으로 앱을 테스트하고 개발하는 동안 만든 임시 컨테이너를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="1e974-253">일반적으로 해당 런타임을 기반으로 다른 이미지를 빌드할 계획인 경우에는 설치된 런타임과 함께 기본 이미지를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e974-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e974-254">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1e974-254">Next steps</span></span>

* [<span data-ttu-id="1e974-255">ASP.NET Core 마이크로 서비스 자습서 확인 보기</span><span class="sxs-lookup"><span data-stu-id="1e974-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="1e974-256">컨테이너를 지원하는 Azure 서비스 검토</span><span class="sxs-lookup"><span data-stu-id="1e974-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
* [<span data-ttu-id="1e974-257">Dockerfile 명령에 대해 읽어 보기</span><span class="sxs-lookup"><span data-stu-id="1e974-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
* [<span data-ttu-id="1e974-258">Visual studio용 컨테이너 도구 살펴보기</span><span class="sxs-lookup"><span data-stu-id="1e974-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
