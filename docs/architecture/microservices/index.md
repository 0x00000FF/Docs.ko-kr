---
title: .NET 마이크로 서비스. 컨테이너화된 .NET 애플리케이션을 위한 아키텍처
description: 컨테이너화된 .NET 애플리케이션에 대한 .NET 마이크로 서비스 아키텍처 | 마이크로 서비스는 독립적으로 배포 가능한 모듈 형식 서비스입니다. (Linux 및 Windows용) Docker 컨테이너는서비스 및 해당 종속성을 단일 단위로 묶어서 배포 및 테스트를 간소화합니다. 그러면 격리된 환경에서 실행됩니다.
ms.date: 01/07/2019
ms.openlocfilehash: dcfff8b06dc77b47e6586ea82c82acc30a5cf3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848871"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="65da3-105">.NET 마이크로 서비스: 컨테이너화된 .NET 애플리케이션을 위한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="65da3-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![책 표지](./media/cover-small.png)

<span data-ttu-id="65da3-107">**EDITION v2.2** - ASP.NET Core 2.2로 업데이트되었습니다</span><span class="sxs-lookup"><span data-stu-id="65da3-107">**EDITION v2.2** - Updated to ASP.NET Core 2.2</span></span>

<span data-ttu-id="65da3-108">이 가이드는 마이크로 서비스 기반 애플리케이션을 개발하고 컨테이너를 사용하여 해당 애플리케이션을 관리하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="65da3-109">또한 .NET Core 및 Docker 컨테이너를 사용하여 아키텍처를 설계 및 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> 

<span data-ttu-id="65da3-110">더 쉽게 ​​시작할 수 있도록 이 가이드는 탐색 가능한 참조 컨테이너화된 애플리케이션 및 마이크로 서비스 기반 애플리케이션에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="65da3-111">참조 애플리케이션은 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub 리포지토리에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="65da3-112">작업 링크</span><span class="sxs-lookup"><span data-stu-id="65da3-112">Action links</span></span>

- <span data-ttu-id="65da3-113">다음 중 원하는 형식으로 이 전자책 다운로드: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-epub) |</span><span class="sxs-lookup"><span data-stu-id="65da3-113">Download this eBook in your format of choice: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-epub) |</span></span>

- <span data-ttu-id="65da3-114">참조 애플리케이션인 [GitHub의 eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 클론/포크</span><span class="sxs-lookup"><span data-stu-id="65da3-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>
 
- <span data-ttu-id="65da3-115">[Channel 9의 소개 비디오](https://aka.ms/microservices-video) 보기</span><span class="sxs-lookup"><span data-stu-id="65da3-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="65da3-116">지금 바로 [마이크로 서비스 아키텍처](https://aka.ms/MicroservicesArchitecture) 알아보기</span><span class="sxs-lookup"><span data-stu-id="65da3-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="65da3-117">소개</span><span class="sxs-lookup"><span data-stu-id="65da3-117">Introduction</span></span>

<span data-ttu-id="65da3-118">기업은 컨테이너를 사용함으로써 점점 더 비용 절감을 실현하고, 배포 문제를 해결하며, DevOps 및 프로덕션 작업을 개선하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="65da3-119">Microsoft는 Azure Kubernetes Service 및 Azure Service Fabric과 같은 제품을 만들고 Docker, Mesosphere 및 Kubernetes와 같은 업계 선두 업체와 협력하여 Windows 및 Linux를 위한 컨테이너 혁신 제품을 출시해왔습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="65da3-120">이러한 제품은 기업이 선택한 플랫폼이나 도구와 상관없이 클라우드의 속도 및 규모로 애플리케이션을 빌드 및 배포할 수 있도록 하는 컨테이너 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="65da3-121">Windows 및 Linux 에코시스템에서 가장 중요한 공급업체가 지원하는 Docker는 컨테이너 업계의 사실상 표준이 되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="65da3-122">(Microsoft는 Docker를 지원하는 주요 클라우드 공급업체 중 하나입니다.) 향후에는 아마도 클라우드 또는 온-프레미스의 어떤 데이터 센터에서나 Docker를 아주 흔히 볼 수 있게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="65da3-123">또한 [마이크로 서비스](https://martinfowler.com/articles/microservices.html) 아키텍처는 중요 업무용 분산 애플리케이션을 위한 중요한 접근 방식으로 부상하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="65da3-124">마이크로 서비스 기반 아키텍처에서 애플리케이션은 독립적으로 개발, 테스트, 배포 및 버전 지정할 수 있는 서비스 컬렉션을 기반으로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="65da3-125">이 가이드의 내용</span><span class="sxs-lookup"><span data-stu-id="65da3-125">About this guide</span></span>

<span data-ttu-id="65da3-126">이 가이드는 마이크로 서비스 기반 애플리케이션을 개발하고 컨테이너를 사용하여 해당 애플리케이션을 관리하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="65da3-127">또한 .NET Core 및 Docker 컨테이너를 사용하여 아키텍처를 설계 및 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="65da3-128">컨테이너 및 마이크로 서비스를 더 쉽게 ​​시작할 수 있도록 이 가이드는 탐색 가능한 참조 컨테이너화된 애플리케이션 및 마이크로 서비스 기반 애플리케이션에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="65da3-129">애플리케이션 예제는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub 리포지토리에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="65da3-130">이 가이드는 두 가지 기술 즉, Docker 및 .NET Core에 중점을 둔 개발 환경 수준에서 주로 기본적인 개발 및 아키텍처 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="65da3-131">이 가이드의 목적은 프로덕션 환경의 인프라(클라우드 또는 온-프레미스)에 집중하지 않고 애플리케이션 디자인을 고려할 때 정보를 제공하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="65da3-132">인프라에 대한 결정은 나중에 프로덕션이 준비된 애플리케이션을 만들 때 내립니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="65da3-133">따라서 이 가이드는 인프라와 관계없이 개발 환경 중심적으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="65da3-134">이 가이드를 살펴본 후에는 다음 단계로 Microsoft Azure에서 프로덕션이 준비된 마이크로 서비스에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="65da3-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="65da3-135">버전</span><span class="sxs-lookup"><span data-stu-id="65da3-135">Version</span></span>

<span data-ttu-id="65da3-136">이 가이드는 **.NET Core 2.2** 버전 및 .NET Core 2.2와 동시에 제공되는 동일한 기술 “웨이브”(즉,</span><span class="sxs-lookup"><span data-stu-id="65da3-136">This guide has been revised to cover **.NET Core 2.2** version plus many additional updates related to the same “wave” of technologies (that is.</span></span> <span data-ttu-id="65da3-137">Azure 기술 및 타사의 추가 기술)에 관련된 여러 추가 업데이트를 다루도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-137">Azure and additional 3rd party technologies) coinciding in time with .NET Core 2.2.</span></span> <span data-ttu-id="65da3-138">이런 이유로 책 버전도 버전 **2.2**로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-138">That’s why the book version has also been updated to version **2.2**.</span></span> 

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="65da3-139">이 가이드에서 다루지 않는 내용</span><span class="sxs-lookup"><span data-stu-id="65da3-139">What this guide does not cover</span></span>

<span data-ttu-id="65da3-140">이 가이드는 애플리케이션 수명 주기, DevOps, CI/CD 파이프라인 또는 팀 작업에 중점을 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-140">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="65da3-141">이러한 주제는 상호 보완적인 가이드인 [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook)에서 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-141">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="65da3-142">또한 현재 이 가이드는 특정 Orchestrator에 대한 정보와 같은 Azure 인프라에 대한 구현 세부 정보도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-142">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="65da3-143">추가 자료</span><span class="sxs-lookup"><span data-stu-id="65da3-143">Additional resources</span></span>

- <span data-ttu-id="65da3-144">**Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기**(다운로드 가능한 eBook)</span><span class="sxs-lookup"><span data-stu-id="65da3-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="65da3-145">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="65da3-145">Who should use this guide</span></span>

<span data-ttu-id="65da3-146">이 가이드는 Docker 기반 애플리케이션 개발 및 마이크로 서비스 기반 아키텍처를 처음 접하는 개발자 및 솔루션 설계자를 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-146">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="65da3-147">이 가이드는 Microsoft 개발 기술(특히 .NET Core에 중점을 둠) 및 Docker 컨테이너를 사용하여 개념 증명 애플리케이션을 설계, 디자인 및 구현하는 방법을 알아보려는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-147">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="65da3-148">또한 이 가이드는 새로운 최신 분산 애플리케이션을 위해 어떤 접근 방식을 선택할지 결정하기 전에 먼저 아키텍처 및 기술에 대해 간략히 알아보려는 기술 의사 결정자(예: 엔터프라이즈 설계자)에게도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-148">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="65da3-149">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="65da3-149">How to use this guide</span></span>

<span data-ttu-id="65da3-150">이 가이드의 첫 번째 부분에서는 Docker 컨테이너를 소개하고, .NET Core와 .NET Framework 중에서 하나를 개발 프레임워크로 선택하는 방법에 대해 설명하고, 마이크로 서비스에 대해 간략하게 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-150">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="65da3-151">이 콘텐츠는 개요만 알면 되고 코드 구현 세부 정보에 집중할 필요가 없는 설계자 및 기술 의사 결정자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-151">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="65da3-152">이 가이드의 두 번째 부분은 [Docker 기반 애플리케이션의 개발 프로세스](./docker-application-development-process/index.md) 섹션으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-152">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="65da3-153">이 섹션은 .NET Core 및 Docker를 사용하여 애플리케이션을 구현하기 위한 개발 및 마이크로 서비스 패턴에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-153">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="65da3-154">이 섹션은 코드와 패턴 및 구현 세부 정보에 중점을 두려는 개발자 및 설계자에게 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-154">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="65da3-155">관련 마이크로 서비스 및 컨테이너 기반 참조 애플리케이션: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="65da3-155">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="65da3-156">eShopOnContainers 애플리케이션은 Docker 컨테이너를 사용하여 배포되도록 설계된 .NET Core 및 마이크로 서비스용 오픈 소스 참조 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-156">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="65da3-157">이 애플리케이션은 몇 가지 온라인 스토어 UI 프런트 엔드(Web MVC 앱, Web SPA 및 네이티브 모바일 앱)를 비롯한 여러 하위 시스템으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-157">The application consists of multiple subsystems, including several e-store UI front ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="65da3-158">또한 필요한 모든 서버 쪽 작업을 위한 백 엔드 마이크로 서비스 및 컨테이너를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-158">It also includes the back-end microservices and containers for all required server-side operations.</span></span> 

<span data-ttu-id="65da3-159">이 애플리케이션의 목적은 아키텍처 패턴을 소개하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-159">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="65da3-160">실제 애플리케이션을 시작하기 위한 **즉시 사용 가능한 템플릿은 아닙니다**.</span><span class="sxs-lookup"><span data-stu-id="65da3-160">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="65da3-161">사실상, 이 애플리케이션은 잠재적으로 흥미로운 새 기술이 등장할 때 이 기술을 테스트하는 데에도 사용되므로 영구적인 베타 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-161">In fact, the application is in a permanent beta state, as it’s also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="65da3-162">피드백을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="65da3-162">Send us your feedback!</span></span>

<span data-ttu-id="65da3-163">이 가이드는 .NET에서 컨테이너화된 애플리케이션 및 마이크로 서비스의 아키텍처를 쉽게 이해할 수 있도록 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-163">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="65da3-164">가이드 및 관련 참조 애플리케이션은 계속 발전할 예정이므로, 피드백이 있으시면 언제든지 보내주세요!</span><span class="sxs-lookup"><span data-stu-id="65da3-164">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="65da3-165">이 가이드의 개선 방안에 대한 의견이 있으시면 다음 주소로 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="65da3-165">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

## <a name="credits"></a><span data-ttu-id="65da3-166">크레딧</span><span class="sxs-lookup"><span data-stu-id="65da3-166">Credits</span></span>

<span data-ttu-id="65da3-167">공동 작성자:</span><span class="sxs-lookup"><span data-stu-id="65da3-167">Co-Authors:</span></span>

> <span data-ttu-id="65da3-168">**Cesar de la Torre**, 선임 PM, .NET 제품 팀, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="65da3-168">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="65da3-169">**Bill Wagner**, 선임 콘텐츠 개발자, C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="65da3-169">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="65da3-170">**Mike Rousos**, 수석 소프트웨어 엔지니어, Microsoft DevDiv CAT 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-170">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="65da3-171">편집자:</span><span class="sxs-lookup"><span data-stu-id="65da3-171">Editors:</span></span>

> <span data-ttu-id="65da3-172">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="65da3-172">**Mike Pope**</span></span>
>
> <span data-ttu-id="65da3-173">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="65da3-173">**Steve Hoag**</span></span>

<span data-ttu-id="65da3-174">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="65da3-174">Participants and reviewers:</span></span>

> <span data-ttu-id="65da3-175">**Jeffrey Richter**, 파트너 소프트웨어 엔지니어, Microsoft Azure 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-175">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-176">**Jimmy Bogard**, 최고 설계자, Headspring</span><span class="sxs-lookup"><span data-stu-id="65da3-176">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="65da3-177">**Udi Dahan**, 창립자 겸 CEO, Particular Software</span><span class="sxs-lookup"><span data-stu-id="65da3-177">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="65da3-178">**Jimmy Nilsson**, 공동 창립자 겸 CEO, Factor10</span><span class="sxs-lookup"><span data-stu-id="65da3-178">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="65da3-179">**Glenn Condron**, 선임 프로그램 관리자, ASP.NET 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-179">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="65da3-180">**Mark Fussell**, 수석 PM 리더, Microsoft Azure Service Fabric 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-180">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-181">**Diego Vega**, PM 리더, Microsoft Entity Framework 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-181">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-182">**Barry Dorrans**, 선임 보안 프로그램 관리자</span><span class="sxs-lookup"><span data-stu-id="65da3-182">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="65da3-183">**Rowan Miller**, 선임 프로그램 관리자, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65da3-183">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="65da3-184">**Ankit Asthana**, 수석 PM 관리자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-184">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-185">**Scott Hunter**, 파트너 PM 책임자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-185">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-186">**Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65da3-186">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-187">**Dylan Reisenberger**, 설계자 겸 개발자 리더, Polly</span><span class="sxs-lookup"><span data-stu-id="65da3-187">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="65da3-188">**Steve "ardalis" Smith** - 소프트웨어 설계자이자 강사 - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="65da3-188">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="65da3-189">**Ian Cooper**, 코딩 설계자, Brighter</span><span class="sxs-lookup"><span data-stu-id="65da3-189">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="65da3-190">**Unai Zorrilla**, 설계자 겸 개발자 리더, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65da3-190">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="65da3-191">**Eduard Tomas**, 개발자 리더, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65da3-191">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="65da3-192">**Ramon Tomas**, 개발자, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65da3-192">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="65da3-193">**David Sanz**, 개발자, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65da3-193">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="65da3-194">**Javier Valero**, 최고 운영 책임자, Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="65da3-194">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="65da3-195">**Pierre Millet**, 선임 컨설턴트, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65da3-195">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="65da3-196">**Michael Friis**, 제품 관리자, Docker Inc</span><span class="sxs-lookup"><span data-stu-id="65da3-196">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="65da3-197">**Charles Lowell**, 소프트웨어 엔지니어, Microsoft VS CAT 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-197">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="65da3-198">**Miguel Veloso**, 선임 컨설턴트, Turing Challenge</span><span class="sxs-lookup"><span data-stu-id="65da3-198">**Miguel Veloso**, Sr. Consultant at Turing Challenge</span></span>

## <a name="copyright"></a><span data-ttu-id="65da3-199">Copyright</span><span class="sxs-lookup"><span data-stu-id="65da3-199">Copyright</span></span>

<span data-ttu-id="65da3-200">다운로드 위치: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="65da3-200">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="65da3-201">게시자:</span><span class="sxs-lookup"><span data-stu-id="65da3-201">PUBLISHED BY</span></span>

<span data-ttu-id="65da3-202">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="65da3-202">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="65da3-203">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="65da3-203">A division of Microsoft Corporation</span></span>

<span data-ttu-id="65da3-204">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="65da3-204">One Microsoft Way</span></span>

<span data-ttu-id="65da3-205">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="65da3-205">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="65da3-206">Copyright © 2019 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="65da3-206">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="65da3-207">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="65da3-207">All rights reserved.</span></span> <span data-ttu-id="65da3-208">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-208">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="65da3-209">이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-209">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="65da3-210">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-210">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="65da3-211">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-211">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="65da3-212">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-212">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="65da3-213">“상표” 웹 페이지의 <https://www.microsoft.com> 에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-213">Microsoft and the trademarks listed at <https://www.microsoft.com> on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="65da3-214">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-214">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="65da3-215">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-215">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="65da3-216">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="65da3-216">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="65da3-217">다음</span><span class="sxs-lookup"><span data-stu-id="65da3-217">Next</span></span>](container-docker-introduction/index.md)
