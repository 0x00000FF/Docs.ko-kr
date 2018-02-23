---
title: ".NET 컨테이너에서 대상으로 지정할 OS"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | .NET 컨테이너에서 대상으로 지정할 OS"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="c2324-104">.NET 컨테이너에서 대상으로 지정할 OS</span><span class="sxs-lookup"><span data-stu-id="c2324-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="c2324-105">Docker에서 지원하는 운영 체제의 다양함과 .NET Framework 및 .NET Core 간 차이를 고려해 보면 사용하는 프레임워크에 따라 특정 OS와 특정 버전을 목표로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="c2324-106">Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c2324-107">이러한 Windows 버전은 각각 .NET Framework나 .NET Core에서 필요할 수 있는 다양한 특성(Windows Server Core의 IIS와 Nano Server의 Kestrel 같은 자체 호스팅 웹 서버)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="c2324-108">Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="c2324-109">그림 3-1에서는 사용하는 .NET 프레임워크에 따라 가능한 OS 버전을 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="c2324-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="c2324-110">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="c2324-110">**Figure 3-1.**</span></span> <span data-ttu-id="c2324-111">.NET framework의 버전에 따라 대상으로 하는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="c2324-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="c2324-112">다른 Linux 배포판을 사용하려 하거나 Microsoft에서 제공하지 않는 버전 이미지가 필요한 경우 자체 Docker 이미지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="c2324-113">예를 들어 .NET Framework 및Windows Server Core에서 실행되는 기존 ASP.NET Core를 통해 이미지를 만들 수 있으나 Docker에는 그렇게 일반적인 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="c2324-114">Dockerfile 파일에 이미지 이름을 추가할 때는 다음 예제에서처럼 사용하는 태그에 따라 운영 체제와 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2324-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="c2324-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="c2324-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="c2324-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="c2324-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="c2324-117">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="c2324-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="c2324-118">[이전] (container-framework-choice-factors.md) [다음] (official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="c2324-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
