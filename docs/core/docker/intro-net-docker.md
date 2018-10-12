---
title: .NET 및 Docker 소개
description: Docker 및 .NET Core 이해
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.custom: mvc
ms.openlocfilehash: d578ec5a25dbb5de3c88386e212e68cf3b267749
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45970645"
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="b4831-103">.NET 및 Docker 소개</span><span class="sxs-lookup"><span data-stu-id="b4831-103">Introduction to .NET and Docker</span></span>

<span data-ttu-id="b4831-104">이 문서에서는 Docker에서의 .NET 작업을 소개하고 관련 개념적 배경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-104">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span>

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="b4831-105">Docker: 앱을 패키지하여 어디서나 배포 및 실행</span><span class="sxs-lookup"><span data-stu-id="b4831-105">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="b4831-106">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md)는 개발자 및 관리자가 [컨테이너](https://www.docker.com/what-container)라는 느슨하게 격리된 환경에서 [이미지](https://docs.docker.com/glossary/?term=image)를 빌드하고, 분산 응용 프로그램을 제공 및 실행할 수 있게 해주는 개방형 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-106">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="b4831-107">이 접근 방식을 통해 개발, QA 및 프로덕션 환경 간에 효율적으로 응용 프로그램 수명 주기를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-107">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="b4831-108">[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform)에서는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine)을 사용하여 신속하게 앱을 만들고 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식으로 작성된 다음 [계층화된 컨테이너](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)에서 배포 및 실행되는 파일을 사용하여 만들어진 [Docker 이미지](https://docs.docker.com/glossary/?term=image)로 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-108">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="b4831-109">고유한 [계층화된 이미지](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)를 dockerfile로 만들거나 [레지스트리](https://docs.docker.com/glossary/?term=registry)의 기존 dockerfile(예: [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub))을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-109">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="b4831-110">[Docker 컨테이너, 이미지 및 레지스트리 간의 관계](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md)는 [컨테이너화된 응용 프로그램이나 마이크로 서비스를 설계 및 빌드](../../standard/microservices-architecture/architect-microservice-container-applications/index.md)할 때 중요한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-110">The [relationship between Docker containers, images, and registries](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) is an important concept when [architecting and building containerized applications or microservices](../../standard/microservices-architecture/architect-microservice-container-applications/index.md).</span></span> <span data-ttu-id="b4831-111">이 접근 방식은 개발과 배포 간의 시간을 크게 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-111">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="b4831-112">추가 읽기(및 보기) 정보</span><span class="sxs-lookup"><span data-stu-id="b4831-112">Further reading (and watching)</span></span>

* <span data-ttu-id="b4831-113">[Windows-based containers: Modern app development with enterprise-grade control](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)(Windows 기반 컨테이너: 엔터프라이즈급 제어 기능을 통한 최신 앱 개발)</span><span class="sxs-lookup"><span data-stu-id="b4831-113">[Windows-based containers: Modern app development with enterprise-grade control.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)</span></span>
* <span data-ttu-id="b4831-114">[Docker overview](https://docs.docker.com/engine/docker-overview/)(Docker 개요)</span><span class="sxs-lookup"><span data-stu-id="b4831-114">[Docker overview](https://docs.docker.com/engine/docker-overview/)</span></span>
* [<span data-ttu-id="b4831-115">Windows 컨테이너의 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="b4831-115">Dockerfile on Windows Containers</span></span>](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* <span data-ttu-id="b4831-116">[Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)(Dockerfile 작성에 대한 모범 사례)</span><span class="sxs-lookup"><span data-stu-id="b4831-116">[Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)</span></span>
* [<span data-ttu-id="b4831-117">.NET Core 응용 프로그램에 대한 Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="b4831-117">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="b4831-118">.NET Docker 이미지 가져오기</span><span class="sxs-lookup"><span data-stu-id="b4831-118">Getting .NET Docker images</span></span>

<span data-ttu-id="b4831-119">공식 .NET Docker 이미지는 Microsoft에서 만들고 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-119">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="b4831-120">이러한 이미지는 Docker Hub의 Microsoft 리포지토리에서 공개적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-120">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="b4831-121">각 리포지토리에는 .NET 버전 및 OS 버전에 따라 여러 이미지가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-121">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="b4831-122">이미지 리포지토리 대부분은 특정 프레임워크 버전과 OS(Linux 배포 또는 Windows 버전)를 모두 선택하는 데 도움이 되는 광범위한 태그 지정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-122">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="b4831-123">시나리오 기반 지침</span><span class="sxs-lookup"><span data-stu-id="b4831-123">Scenario based guidance</span></span>

<span data-ttu-id="b4831-124">.NET 리포지토리에 대한 Microsoft의 의도는 특정 시나리오나 워크로드를 나타내는 세분화되고 집중된 리포지토리를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-124">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="b4831-125">`microsoft/aspnetcore` 이미지는 Docker의 ASP.NET Core 앱에 최적화되어 있으므로 컨테이너를 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-125">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="b4831-126">.NET Core 이미지(`microsoft/dotnet`)는 .NET Core를 기반으로 하는 콘솔 앱을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-126">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="b4831-127">예를 들어 일괄 처리 프로세스, Azure WebJobs 및 기타 콘솔 시나리오는 최적화된 .NET Core 이미지를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-127">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="b4831-128">Docker 및 .NET 응용 프로그램 사용에 대한 가장 명확한 수평적 시나리오는 프로덕션 배포 및 호스팅에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-128">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="b4831-129">프로덕션은 한 가지 시나리오일 뿐이며, 다른 시나리오도 동일하게 유용한 것으로 판명되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-129">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="b4831-130">이러한 시나리오는 .NET에만 국한된 것이 아니라, 대부분의 개발자 플랫폼에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-130">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="b4831-131">**저마찰 설치** - 로컬 설치 없이 .NET을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-131">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="b4831-132">.NET이 포함된 Docker 이미지를 다운로드하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-132">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="b4831-133">**컨테이너에서 개발** - 일관된 환경에서 개발하여 개발 환경과 프로덕션 환경을 유사하게 만들 수 있습니다(개발자 컴퓨터의 전역 상태와 같은 문제 방지).</span><span class="sxs-lookup"><span data-stu-id="b4831-133">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="b4831-134">Visual Studio Tools for Docker를 통해 Visual Studio에서 직접 컨테이너를 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-134">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="b4831-135">**컨테이너에서 테스트** - 컨테이너에서 테스트하여 잘못 구성된 환경이나 마지막 테스트에서 남겨진 기타 변경 내용으로 인한 실패를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-135">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="b4831-136">**컨테이너에서 빌드** - 컨테이너에서 코드를 빌드하여 여러 환경에 대해 공유 빌드 컴퓨터를 올바르게 구성할 필요 없이, 대신 “BYOC”(Bring Your Own Container) 접근 방식으로 넘어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-136">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="b4831-137">**모든 환경에서 배포** - 모든 환경을 통해 이미지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-137">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="b4831-138">이 접근 방식을 사용하면 구성 차이로 인한 실패가 줄어듭니다(일반적으로 외부 구성을 통해 이미지 동작 변경(예: 삽입된 환경 변수)).</span><span class="sxs-lookup"><span data-stu-id="b4831-138">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="b4831-139">Docker 컨테이너 개발을 위해 .NET Core와 .NET Framework 중에서 결정하는 데 대한 [일반적인 지침](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-139">[General guidance](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="b4831-140">일반적인 Docker 개발 시나리오</span><span class="sxs-lookup"><span data-stu-id="b4831-140">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="b4831-141">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b4831-141">.NET Core</span></span>

<span data-ttu-id="b4831-142">**.NET Core 리소스**</span><span class="sxs-lookup"><span data-stu-id="b4831-142">**.NET Core resources**</span></span>

 <span data-ttu-id="b4831-143">관심 있는 시나리오에 맞는 .NET Core 샘플을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="b4831-143">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="b4831-144">모든 샘플 지침은 Windows, Linux 또는 macOS 호스트에서 Windows 또는 Linux Docker 이미지를 대상으로 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-144">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="b4831-145">샘플에서는 .NET Core 2.0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-145">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="b4831-146">이러한 샘플에서는 해당하는 경우 Docker [다단계 빌드](https://github.com/dotnet/announcements/issues/18) 및 [다중 아키텍처 태그](https://github.com/dotnet/announcements/issues/14)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-146">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="b4831-147">DockerHub의 .NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-147">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* <span data-ttu-id="b4831-148">[Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/)(.NET Core 응용 프로그램 Docker화)</span><span class="sxs-lookup"><span data-stu-id="b4831-148">[Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/)</span></span>

* <span data-ttu-id="b4831-149">이 .NET Core Docker 샘플은 [.NET Core 개발 프로세스에서 Docker를 사용](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-149">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="b4831-150">샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-150">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="b4831-151">이 .NET Core Docker 샘플은 [프로덕션용 .NET Core 앱에 대한 Docker 이미지를 빌드](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-151">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="b4831-152">샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-152">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="b4831-153">이 [.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)은 [자체 포함된 .NET Core 응용 프로그램](../deploying/index.md)에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-153">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](../deploying/index.md).</span></span> <span data-ttu-id="b4831-154">[컨테이너 간에 기본 이미지 공유](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)의 이점이 없는 가장 작은 프로덕션 컨테이너에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-154">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="b4831-155">그러나 하위 Docker 계층은 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-155">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="b4831-156">ARM32/Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="b4831-156">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="b4831-157">.NET Core 런타임 ARM32 빌드 공지 사항</span><span class="sxs-lookup"><span data-stu-id="b4831-157">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="b4831-158">DockerHub의 ARM32/Raspberry Pi .NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-158">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="b4831-159">GitHub의 ARM32/Raspberry Pi .NET Core Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="b4831-159">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="b4831-160">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4831-160">.NET Framework</span></span>

* [<span data-ttu-id="b4831-161">DockerHub의 .NET Framework 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-161">.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet-framework/)

<span data-ttu-id="b4831-162">이 리포지토리에는 다양한 .NET Framework Docker 구성을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-162">This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="b4831-163">이러한 이미지를 고유한 Docker 이미지의 기반으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="b4831-164">**.NET Framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="b4831-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="b4831-165">[dotnet-framework:4.7 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)은 [.NET Framework 4.7](../../framework/whats-new/index.md#v47)의 기본 “Hello World” 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-165">The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](../../framework/whats-new/index.md#v47).</span></span> <span data-ttu-id="b4831-166">이 샘플은 [.NET Framework 4.7 Docker 이미지](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile)를 사용하여 앱을 빌드하고 배포하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).</span></span>

<span data-ttu-id="b4831-167">**.NET Framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="b4831-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="b4831-168">[dotnet-framework:4.6.2 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)은 [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462)의 기본 “Hello World” 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462).</span></span> <span data-ttu-id="b4831-169">이 샘플은 [.NET Framework 4.6.2 Docker 이미지](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile)를 사용하여 앱을 빌드하고 배포하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile).</span></span>

<span data-ttu-id="b4831-170">**.NET Framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="b4831-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="b4831-171">[dotnet-framework:3.5 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)은 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile)의 기본 “Hello World” 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile).</span></span> <span data-ttu-id="b4831-172">이 샘플은 Docker에서 .NET Framework 3.5를 사용하여 프로젝트를 빌드하고 배포하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="b4831-173">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b4831-173">ASP.NET Core</span></span>

* <span data-ttu-id="b4831-174">[이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="b4831-175">샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="b4831-176">DockerHub의 ASP.NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="b4831-177">GitHub의 ASP.NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="b4831-178">ASP.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4831-178">ASP.NET Framework</span></span>

* [<span data-ttu-id="b4831-179">DockerHub의 ASP.NET Framework 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="b4831-180">.NET Framework 4.6.2의 ASP.NET Web Forms 앱 샘플</span><span class="sxs-lookup"><span data-stu-id="b4831-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="b4831-181">WCF(Windows Communication Framework)</span><span class="sxs-lookup"><span data-stu-id="b4831-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="b4831-182">DockerHub의 WCF(Windows Communication Framework) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="b4831-183">GitHub의 WCF(Windows Communication Framework) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

* [<span data-ttu-id="b4831-184">.NET Framework 4.6.2를 사용하는 WCF(Windows Communication Framework) Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="b4831-184">Windows Communication Framework (WCF) Docker samples using .NET Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="b4831-185">IIS(Internet Information Server)</span><span class="sxs-lookup"><span data-stu-id="b4831-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="b4831-186">DockerHub의 IIS(Internet Information Server) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="b4831-187">GitHub의 IIS(Internet Information Server) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="b4831-188">다른 Microsoft 스택 컨테이너 이미지와 상호 작용</span><span class="sxs-lookup"><span data-stu-id="b4831-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="b4831-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4831-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="b4831-190">Docker 빠른 시작을 통해 Linux 2017용 Microsoft SQL Server 컨테이너 이미지 실행</span><span class="sxs-lookup"><span data-stu-id="b4831-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="b4831-191">DockerHub의 Linux용 Microsoft SQL Server 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [<span data-ttu-id="b4831-192">DockerHub의 Windows 컨테이너용 Microsoft SQL Server Express Edition 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-192">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="b4831-193">DockerHub의 Windows 컨테이너용 Microsoft SQL Server Developer Edition 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-193">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="azure-devops-services-agent"></a><span data-ttu-id="b4831-194">Azure DevOps Services 에이전트</span><span class="sxs-lookup"><span data-stu-id="b4831-194">Azure DevOps Services agent</span></span>

* [<span data-ttu-id="b4831-195">DockerHub에 있는 Azure DevOps Services 에이전트 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-195">Azure DevOps Services agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="b4831-196">GitHub에 있는 Azure DevOps Services 에이전트 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-196">Azure DevOps Services agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="b4831-197">OMS(Operations Management Suite) Linux 에이전트</span><span class="sxs-lookup"><span data-stu-id="b4831-197">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="b4831-198">OMS(Operations Management Suite) Linux 에이전트 개요</span><span class="sxs-lookup"><span data-stu-id="b4831-198">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [<span data-ttu-id="b4831-199">DockerHub의 OMS(Operations Management Suite) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-199">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/oms/)

* [<span data-ttu-id="b4831-200">GitHub의 OMS(Operations Management Suite) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-200">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="b4831-201">Microsoft Azure CLI(명령줄 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="b4831-201">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="b4831-202">DockerHub의 Microsoft Azure CLI(명령줄 인터페이스) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-202">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cli/) 

* [<span data-ttu-id="b4831-203">GitHub의 Microsoft Azure CLI(명령줄 인터페이스) 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-203">Microsoft Azure Command-Line Interface (CLI) images on GitHub</span></span>](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> <span data-ttu-id="b4831-204">Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b4831-204">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="b4831-205">Microsoft Azure Cosmos DB 에뮬레이터(Windows 컨테이너만 해당)</span><span class="sxs-lookup"><span data-stu-id="b4831-205">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="b4831-206">DockerHub의 Microsoft Azure Cosmos DB 에뮬레이터 이미지</span><span class="sxs-lookup"><span data-stu-id="b4831-206">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="b4831-207">로컬 개발 및 테스트에 Azure Cosmos DB 에뮬레이터 사용</span><span class="sxs-lookup"><span data-stu-id="b4831-207">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="b4831-208">풍부한 Docker 개발 에코시스템 살펴보기</span><span class="sxs-lookup"><span data-stu-id="b4831-208">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="b4831-209">Docker 플랫폼 및 다양한 Docker 이미지에 대해 알아보았으므로, 다음 단계는 풍부한 Docker 에코시스템을 살펴보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-209">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="b4831-210">다음 링크는 Microsoft 도구가 컨테이너 개발을 보완하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4831-210">The following links show you how the Microsoft tools complement container development.</span></span>

* <span data-ttu-id="b4831-211">[Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)(.NET 및 Docker 함께 사용)</span><span class="sxs-lookup"><span data-stu-id="b4831-211">[Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)</span></span>
* [<span data-ttu-id="b4831-212">다중 컨테이너 및 마이크로 서비스 기반 .NET 응용 프로그램 디자인 및 개발</span><span class="sxs-lookup"><span data-stu-id="b4831-212">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [<span data-ttu-id="b4831-213">Visual Studio Code Docker 확장</span><span class="sxs-lookup"><span data-stu-id="b4831-213">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile)
* [<span data-ttu-id="b4831-214">Azure Service Fabric 사용 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="b4831-214">Learn how to use Azure Service Fabric</span></span>](/azure/service-fabric/index)
* <span data-ttu-id="b4831-215">[Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)(Service Fabric 시작 샘플)</span><span class="sxs-lookup"><span data-stu-id="b4831-215">[Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)</span></span>
* [<span data-ttu-id="b4831-216">Windows 컨테이너의 혜택</span><span class="sxs-lookup"><span data-stu-id="b4831-216">Benefits of Windows Containers</span></span>](/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="b4831-217">Visual Studio Docker 도구로 작업</span><span class="sxs-lookup"><span data-stu-id="b4831-217">Working with Visual Studio Docker Tools</span></span>](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* [<span data-ttu-id="b4831-218">Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포</span><span class="sxs-lookup"><span data-stu-id="b4831-218">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* <span data-ttu-id="b4831-219">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)(Visual Studio Code를 사용한 디버깅)</span><span class="sxs-lookup"><span data-stu-id="b4831-219">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)</span></span>
* [<span data-ttu-id="b4831-220">클라우드에서 Mac용 Visual Studio, 컨테이너 및 서버리스 코드에 익숙해지기</span><span class="sxs-lookup"><span data-stu-id="b4831-220">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* <span data-ttu-id="b4831-221">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)(Docker 및 Mac용 Visual Studio 랩 시작)</span><span class="sxs-lookup"><span data-stu-id="b4831-221">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4831-222">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b4831-222">Next steps</span></span>

* [<span data-ttu-id="b4831-223">.NET Core와 Docker 기본 사항 알아보기</span><span class="sxs-lookup"><span data-stu-id="b4831-223">Learn Docker Basics with .NET Core</span></span>](docker-basics-dotnet-core.md)
* [<span data-ttu-id="b4831-224">.NET Core Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="b4831-224">Building .NET Core Docker Images</span></span>](building-net-docker-images.md)
