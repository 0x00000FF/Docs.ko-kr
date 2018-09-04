---
title: .NET Core Docker 이미지 작성
description: Docker 이미지 및 .NET Core 이해
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e48a263334ebb93a5d281032336aeb4073d8467c
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "34827341"
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="d3a19-103">.NET Core 응용 프로그램에 대한 Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="d3a19-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="d3a19-104">이 자습서에서는 Docker에서 .NET Core를 사용하는 방법에 초점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="d3a19-105">먼저 Microsoft에서 제공되고 관리되는 서로 다른 Docker 이미지를 살펴보고 사례를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="d3a19-106">그런 다음 ASP.NET Core 앱을 빌드하고 Docker화하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="d3a19-107">이 자습서를 진행하면서 다음을 익히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d3a19-108">Microsoft .NET Core Docker 이미지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="d3a19-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="d3a19-109">Docker화할 ASP.NET Core 샘플 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="d3a19-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="d3a19-110">ASP.NET 샘플 앱을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="d3a19-111">Linux 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="d3a19-112">Windows 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="d3a19-113">Docker 이미지 최적화</span><span class="sxs-lookup"><span data-stu-id="d3a19-113">Docker Image Optimizations</span></span>

<span data-ttu-id="d3a19-114">개발자를 위한 Docker 이미지를 작성할 때 다음 세 가지 주요 시나리오를 중점적으로 고려했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="d3a19-115">.NET Core 앱을 개발하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="d3a19-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="d3a19-116">.NET Core 앱을 빌드하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="d3a19-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="d3a19-117">.NET Core 앱을 실행하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="d3a19-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="d3a19-118">왜 이 세 가지 이미지가 중요할까요?</span><span class="sxs-lookup"><span data-stu-id="d3a19-118">Why three images?</span></span>
<span data-ttu-id="d3a19-119">컨테이너화된 응용 프로그램을 개발, 빌드 및 실행할 때 서로 다른 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="d3a19-120">**개발:** 우선 순위는 신속하게 변경 내용을 반복하고 변경 내용을 디버그하는 기능에 초점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="d3a19-121">이미지의 크기는 중요하지 않으며 코드를 변경하고 변경 내용을 신속하게 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d3a19-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="d3a19-122">**빌드:** 이 이미지는 컴파일러 및 이진 파일을 최적화하는 다른 종속성을 포함하는 앱을 컴파일하는 데 필요한 모든 항목을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="d3a19-123">빌드 이미지를 사용하여 프로덕션 이미지로 배치하는 자산을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="d3a19-124">빌드 이미지는 연속 통합 또는 빌드 환경에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="d3a19-125">이 방법은 빌드 에이전트가 빌드 이미지 인스턴스에서 응용 프로그램(필요한 모든 종속성과 함께)을 컴파일하고 빌드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="d3a19-126">빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="d3a19-127">**프로덕션:** 이미지를 얼마나 빠르게 배포하고 시작할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d3a19-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="d3a19-128">이 이미지는 작기 때문에 Docker 레지스트리에서 Docker 호스트로 네트워크 성능이 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="d3a19-129">콘텐츠를 실행할 준비가 되면 Docker 실행부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="d3a19-130">동적 코드 컴파일은 Docker 모델에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="d3a19-131">이 이미지에 배치되는 콘텐츠는 이진 파일과 응용 프로그램을 실행하는 데 필요한 콘텐츠로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="d3a19-132">예를 들어 `dotnet publish` 출력은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="d3a19-133">컴파일된 이진 파일</span><span class="sxs-lookup"><span data-stu-id="d3a19-133">the compiled binaries</span></span>
    * <span data-ttu-id="d3a19-134">.js 및 .css 파일</span><span class="sxs-lookup"><span data-stu-id="d3a19-134">.js and .css files</span></span>


<span data-ttu-id="d3a19-135">프로덕션 이미지에 `dotnet publish` 명령 출력을 포함하는 이유는 크기를 최소로 유지하기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-135">The reason to include the `dotnet publish` command output in your production image is to keep its size to a minimum.</span></span>

<span data-ttu-id="d3a19-136">일부 .NET Core 이미지는 다른 태그 간의 계층을 공유하므로 최신 태그를 다운로드하는 것은 비교적 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="d3a19-137">컴퓨터에 이전 버전이 이미 있는 경우 이 아키텍처는 필요한 디스크 공간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="d3a19-138">동일한 컴퓨터에서 여러 응용 프로그램이 공용 이미지를 사용하는 경우 메모리는 공용 이미지 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="d3a19-139">이미지는 공유되도록 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="d3a19-140">Docker 이미지 변형</span><span class="sxs-lookup"><span data-stu-id="d3a19-140">Docker image variations</span></span>

<span data-ttu-id="d3a19-141">위의 목표를 달성하기 위해 [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/)에서 이미지 변형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="d3a19-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) 이 이미지는 .NET Core 및 CLI(명령줄 도구)가 포함된 .NET Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="d3a19-143">이 이미지는 **개발 시나리오**에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="d3a19-144">로컬 개발, 디버깅 및 단위 테스트에 이 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="d3a19-145">이 이미지는 **빌드** 시나리오에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="d3a19-146">`microsoft/dotnet:sdk`를 사용하면 항상 최신 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="d3a19-147">필요한 것이 확실하지 않은 경우 `microsoft/dotnet:<version>-sdk` 이미지를 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="d3a19-148">"de facto" 이미지로 삭제 컨테이너로 사용되도록 디자인되었으며(소스 코드 탑재 및 앱을 시작하도록 컨테이너 시작) 기본 이미지로 다른 이미지를 빌드하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="d3a19-149">`microsoft/dotnet:<version>-runtime`: 이 이미지는 .NET Core(런타임 및 라이브러리)를 포함하며 **프로덕션**에서 실행 중인 .NET Core 앱에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="d3a19-150">대체 이미지</span><span class="sxs-lookup"><span data-stu-id="d3a19-150">Alternative images</span></span>

<span data-ttu-id="d3a19-151">개발, 빌드 및 프로덕션에 최적화된 시나리오 외에도 추가 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="d3a19-152">`microsoft/dotnet:<version>-runtime-deps`: **runtime-deps** 이미지는 .NET Core에 필요한 모든 기본 종속성과 함께 운영 체제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="d3a19-153">이 이미지는 [자체 포함된 응용 프로그램](../deploying/index.md)을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="d3a19-154">각 변형의 최신 버전:</span><span class="sxs-lookup"><span data-stu-id="d3a19-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="d3a19-155">`microsoft/dotnet` 또는 `microsoft/dotnet:latest`(SDK 이미지에 대한 별칭)</span><span class="sxs-lookup"><span data-stu-id="d3a19-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="d3a19-156">탐색할 샘플</span><span class="sxs-lookup"><span data-stu-id="d3a19-156">Samples to explore</span></span>

* <span data-ttu-id="d3a19-157">[이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp)은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="d3a19-158">샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="d3a19-159">이 .NET Core Docker 샘플은 [프로덕션용 .NET Core 앱에 대한 Docker 이미지를 빌드](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span></span>

## <a name="forward-the-request-scheme-and-original-ip-address"></a><span data-ttu-id="d3a19-160">요청 스키마 및 원래 IP 주소 전달</span><span class="sxs-lookup"><span data-stu-id="d3a19-160">Forward the request scheme and original IP address</span></span>

<span data-ttu-id="d3a19-161">프록시 서버, 부하 분산 장치 및 기타 네트워크 어플라이언스는 종종 컨테이너화된 앱에 도달하기 전에 요청에 대한 정보를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-161">Proxy servers, load balancers, and other network appliances often obscure information about a request before it reaches the containerized app:</span></span>

* <span data-ttu-id="d3a19-162">HTTPS 요청이 HTTP를 통해 프록시된 경우 원래 스키마(HTTPS)가 손실되므로 헤더에서 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-162">When HTTPS requests are proxied over HTTP, the original scheme (HTTPS) is lost and must be forwarded in a header.</span></span>
* <span data-ttu-id="d3a19-163">앱은 프록시에서 요청을 수신하고 인터넷 또는 회사 네트워크의 실제 소스를 수신하는 것이 아니므로 원래 클라이언트 IP 주소도 헤더에서 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-163">Because an app receives a request from the proxy and not its true source on the Internet or corporate network, the original client IP address must also be forwarded in a header.</span></span>

<span data-ttu-id="d3a19-164">이 정보는 요청 처리 시 중요할 수 있습니다(예: 리디렉션, 인증, 링크 생성, 정책 평가 및 클라이언트 지리적 위치).</span><span class="sxs-lookup"><span data-stu-id="d3a19-164">This information may be important in request processing, for example in redirects, authentication, link generation, policy evaluation, and client geolocation.</span></span>

<span data-ttu-id="d3a19-165">컨테이너화된 ASP.NET Core 앱에 스키마 및 원래 IP 주소를 전달하려면 전달된 헤더 미들웨어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-165">To forward the scheme and original IP address to a containerized ASP.NET Core app, use Forwarded Headers Middleware.</span></span> <span data-ttu-id="d3a19-166">자세한 내용은 [프록시 서버 및 부하 분산 장치를 사용하도록 ASP.NET Core 구성](/aspnet/core/host-and-deploy/proxy-load-balancer)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-166">For more information, see [Configure ASP.NET Core to work with proxy servers and load balancers](/aspnet/core/host-and-deploy/proxy-load-balancer).</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="d3a19-167">첫 번째 ASP.NET Core Docker 앱</span><span class="sxs-lookup"><span data-stu-id="d3a19-167">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="d3a19-168">이 자습서의 경우 docker화하려는 앱에 대한 ASP.NET Core Docker 샘플 응용 프로그램을 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-168">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="d3a19-169">이 ASP.NET Core Docker 샘플 응용 프로그램은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-169">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="d3a19-170">샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-170">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="d3a19-171">샘플 Dockerfile은 ASP.NET Core 런타임 Docker 기본 이미지 기반의 ASP.NET Core 응용 프로그램 Docker 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-171">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="d3a19-172">다음 작업을 수행하는 데 [Docker 다단계 빌드 기능](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-172">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="d3a19-173">**더 큰** ASP.NET Core 빌드 Docker 기본 이미지에 따라 컨테이너에서 샘플 빌드</span><span class="sxs-lookup"><span data-stu-id="d3a19-173">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="d3a19-174">**더 작은** ASP.NET Core Docker 런타임 기본 이미지에 따라 최종 빌드 결과를 Docker 이미지로 복사</span><span class="sxs-lookup"><span data-stu-id="d3a19-174">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="d3a19-175">빌드 이미지는 응용 프로그램을 빌드하는 데 필요한 도구를 포함하는 반면 런타임 이미지는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-175">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d3a19-176">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d3a19-176">Prerequisites</span></span>

<span data-ttu-id="d3a19-177">빌드하고 실행하려면 다음 항목을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-177">To build and run, install the following items:</span></span>

#### <a name="net-core-21-sdk"></a><span data-ttu-id="d3a19-178">.NET Core 2.1 SDK</span><span class="sxs-lookup"><span data-stu-id="d3a19-178">.NET Core 2.1 SDK</span></span>

* <span data-ttu-id="d3a19-179">[.NET Core SDK 2.1](https://www.microsoft.com/net/core)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-179">Install [.NET Core SDK 2.1](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="d3a19-180">아직 없는 경우 즐겨 찾는 코드 편집기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-180">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="d3a19-181">코드 편집기를 설치해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d3a19-181">Need to install a code editor?</span></span> <span data-ttu-id="d3a19-182">[Visual Studio](https://visualstudio.com/downloads)를 체험해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-182">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="d3a19-183">Docker 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="d3a19-183">Installing Docker Client</span></span>

<span data-ttu-id="d3a19-184">[Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) 이상의 Docker 클라이언트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-184">Install [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="d3a19-185">Docker 클라이언트를 다음에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-185">The Docker client can be installed in:</span></span>

* <span data-ttu-id="d3a19-186">Linux 배포</span><span class="sxs-lookup"><span data-stu-id="d3a19-186">Linux distributions</span></span>

   * [<span data-ttu-id="d3a19-187">CentOS</span><span class="sxs-lookup"><span data-stu-id="d3a19-187">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="d3a19-188">Debian</span><span class="sxs-lookup"><span data-stu-id="d3a19-188">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="d3a19-189">Fedora</span><span class="sxs-lookup"><span data-stu-id="d3a19-189">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="d3a19-190">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d3a19-190">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="d3a19-191">macOS</span><span class="sxs-lookup"><span data-stu-id="d3a19-191">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="d3a19-192">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="d3a19-192">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="d3a19-193">샘플 리포지토리용 Git 설치</span><span class="sxs-lookup"><span data-stu-id="d3a19-193">Installing Git for sample repository</span></span>

* <span data-ttu-id="d3a19-194">리포지토리를 복제하려는 경우 [git](https://git-scm.com/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-194">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="d3a19-195">샘플 응용 프로그램 가져오기</span><span class="sxs-lookup"><span data-stu-id="d3a19-195">Getting the sample application</span></span>

<span data-ttu-id="d3a19-196">샘플을 가져오는 가장 쉬운 방법은 다음 지침을 사용하여 git로 [.NET Core Docker 리포지토리](https://github.com/dotnet/dotnet-docker)를 복제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-196">The easiest way to get the sample is by cloning the [.NET Core Docker repository](https://github.com/dotnet/dotnet-docker) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker
```

<span data-ttu-id="d3a19-197">.NET Core Docker 리포지토리에서 zip으로 리포지토리(작음)를 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-197">You can also download the repository (it is small) as a zip from the .NET Core Docker repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="d3a19-198">ASP.NET 앱을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-198">Run the ASP.NET app locally</span></span>

<span data-ttu-id="d3a19-199">참조 지점으로 응용 프로그램을 컨테이너화하기 전에 먼저 로컬로 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-199">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="d3a19-200">다음 명령을 사용하여 .NET Core 2.1 SDK와 함께 응용 프로그램을 로컬로 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).</span><span class="sxs-lookup"><span data-stu-id="d3a19-200">You can build and run the application locally with the .NET Core 2.1 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

<span data-ttu-id="d3a19-201">응용 프로그램이 시작된 후 웹 브라우저에서 **http://localhost:5000**을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-201">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="d3a19-202">Linux 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-202">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="d3a19-203">다음 명령을 사용하여 Linux 컨테이너를 사용하는 Docker에서 샘플을 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).</span><span class="sxs-lookup"><span data-stu-id="d3a19-203">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="d3a19-204">`docker run` '-p' 인수는 로컬 컴퓨터의 포트 5000을 컨테이너의 포트 80으로 매핑합니다(포트 매핑 형식은 `host:container`).</span><span class="sxs-lookup"><span data-stu-id="d3a19-204">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="d3a19-205">자세한 내용은 명령줄 매개 변수의 [docker run](https://docs.docker.com/engine/reference/commandline/exec/) 참조를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-205">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="d3a19-206">응용 프로그램이 시작된 후 웹 브라우저에서 **http://localhost:5000**을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-206">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="d3a19-207">Windows 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-207">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="d3a19-208">다음 명령을 사용하여 Windows 컨테이너를 사용하는 Docker에서 샘플을 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).</span><span class="sxs-lookup"><span data-stu-id="d3a19-208">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="d3a19-209">Windows 컨테이너를 사용하는 경우 브라우저에서 **컨테이너 IP 주소**(http://localhost) 와 반대로)로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-209">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="d3a19-210">다음 단계를 사용하여 컨테이너의 IP 주소를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-210">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="d3a19-211">다른 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-211">Open up another command prompt.</span></span>
* <span data-ttu-id="d3a19-212">`docker ps`를 실행하여 실행 중인 컨테이너를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-212">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="d3a19-213">"aspnetcore_sample" 컨테이너가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-213">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="d3a19-214">`docker exec aspnetcore_sample ipconfig`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-214">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="d3a19-215">컨테이너 IP 주소를 복사하고 브라우저로 붙여 넣습니다(예: 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="d3a19-215">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="d3a19-216">Docker exec는 이름 또는 해시로 컨테이너 식별을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-216">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="d3a19-217">예제에서는 이름(aspnetcore_sample)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-217">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="d3a19-218">실행 중인 Windows 컨테이너의 IP 주소를 가져오는 방법의 다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-218">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!NOTE]
> <span data-ttu-id="d3a19-219">Docker exec는 실행 중인 컨테이너에서 새 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-219">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="d3a19-220">자세한 내용은 명령줄 매개 변수의 [docker exec 참조](https://docs.docker.com/engine/reference/commandline/exec/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-220">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="d3a19-221">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 프로덕션에 로컬로 배포할 준비가 된 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-221">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> <span data-ttu-id="d3a19-222">-c 릴리스 인수는 릴리스 모드에서 응용 프로그램을 빌드합니다(기본값은 디버그 모드).</span><span class="sxs-lookup"><span data-stu-id="d3a19-222">The -c Release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="d3a19-223">자세한 내용은 명령줄 매개 변수의 [docker run 참조](../tools/dotnet-run.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-223">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="d3a19-224">다음 명령을 사용하여 **Windows**에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-224">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="d3a19-225">다음 명령을 사용하여 **Linux** 또는 **macOS**에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-225">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="d3a19-226">이 샘플에 사용된 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="d3a19-226">Docker Images used in this sample</span></span>

<span data-ttu-id="d3a19-227">이 샘플의 dockerfile에서는 다음 Docker 이미지가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-227">The following Docker images are used in this sample's dockerfile.</span></span>

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

<span data-ttu-id="d3a19-228">지금까지</span><span class="sxs-lookup"><span data-stu-id="d3a19-228">Congratulations!</span></span> <span data-ttu-id="d3a19-229">다음 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-229">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d3a19-230">Microsoft .NET Core Docker 이미지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="d3a19-230">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="d3a19-231">Docker화할 ASP.NET Core 샘플 앱 가져오기</span><span class="sxs-lookup"><span data-stu-id="d3a19-231">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="d3a19-232">ASP.NET 샘플 앱을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-232">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="d3a19-233">Linux 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-233">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="d3a19-234">Windows 컨테이너용 Docker로 샘플 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="d3a19-234">Built and ran the sample with Docker for Windows containers</span></span>

<span data-ttu-id="d3a19-235">**다음 단계**</span><span class="sxs-lookup"><span data-stu-id="d3a19-235">**Next Steps**</span></span>

<span data-ttu-id="d3a19-236">수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a19-236">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="d3a19-237">Visual Studio Docker 도구로 작업</span><span class="sxs-lookup"><span data-stu-id="d3a19-237">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="d3a19-238">Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포</span><span class="sxs-lookup"><span data-stu-id="d3a19-238">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* <span data-ttu-id="d3a19-239">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)(Visual Studio Code를 사용한 디버깅)</span><span class="sxs-lookup"><span data-stu-id="d3a19-239">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)</span></span> 
* [<span data-ttu-id="d3a19-240">클라우드에서 Mac용 Visual Studio, 컨테이너 및 서버리스 코드에 익숙해지기</span><span class="sxs-lookup"><span data-stu-id="d3a19-240">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* <span data-ttu-id="d3a19-241">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)(Docker 및 Mac용 Visual Studio 랩 시작)</span><span class="sxs-lookup"><span data-stu-id="d3a19-241">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!NOTE]
> <span data-ttu-id="d3a19-242">Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d3a19-242">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
