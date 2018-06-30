---
title: 컨테이너 및 Docker 소개
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: e9f81c5fecc06b19ebd84cc4b2cc232686768a90
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106634"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="ca9e9-103">컨테이너 및 Docker 소개</span><span class="sxs-lookup"><span data-stu-id="ca9e9-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="ca9e9-104">컨테이너화는 응용 프로그램 또는 서비스, 이에 해당하는 종속성 및 (배포 매니페스트 파일로 일반화된) 구성이 컨테이너 이미지로 패키지되는 소프트웨어 개발 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="ca9e9-105">그런 다음 컨테이너화된 응용 프로그램을 하나의 단위로 테스트하고 컨테이너 이미지 인스턴스로 호스트 운영 체제에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="ca9e9-106">배송 업계에서 표준화된 컨테이너를 사용하여 컨테이너 안에 들어있는 화물에 상관없이 상품을 배, 기차 또는 트럭으로 운반하듯이 소프트웨어 컨테이너도 다양한 코드 및 종속성을 포함할 수 있는 소프트웨어의 표준 단위 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="ca9e9-107">컨테이너에 소프트웨어를 포함하면 개발자와 IT 전문가가 수정 과정을 거의 거치지 않고 모든 환경에서 이러한 컨테이너를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="ca9e9-108">또한 컨테이너는 공유 OS(운영 체제)에서 응용 프로그램을 서로 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="ca9e9-109">컨테이너화된 응용 프로그램은 OS(Linux 또는 Windows)에서 차례대로 실행되는 컨테이너 호스트의 맨 위에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="ca9e9-110">따라서 컨테이너의 공간은 VM(가상 머신) 이미지보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="ca9e9-111">그림 1-1에 표시된 것처럼 각 컨테이너는 전체 웹 응용 프로그램 또는 서비스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="ca9e9-112">그림 1-1: 컨테이너 호스트에서 실행되는 여러 컨테이너</span><span class="sxs-lookup"><span data-stu-id="ca9e9-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="ca9e9-113">이 예제에서는 Docker 호스트가 컨테이너 호스트이며 앱 1, 앱 2, Svc 1, Svc 2가 컨테이너화된 응용 프로그램 또는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="ca9e9-114">컨테이너화로 얻을 수 있는 또 다른 이점은 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="ca9e9-115">단기 작업에 대한 새 컨테이너를 만들어 신속하게 스케일 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="ca9e9-116">응용 프로그램의 관점에서 볼 때 *이미지 인스턴스화*(컨테이너 생성)는 서비스 또는 웹앱과 같은 프로세스 인스턴스화와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="ca9e9-117">그러나 안정성을 생각한다면, 동일한 이미지의 여러 인스턴스를 여러 호스트 서버에서 실행할 경우 일반적으로 기본 도메인이 다른 다양한 호스트 서버 또는 VM에서 각 컨테이너(이미지 인스턴스)를 실행하려 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="ca9e9-118">즉, 컨테이너는 전체 응용 프로그램 수명 주기 워크플로에서 격리, 이식성, 민첩성, 확장성, 제어에 대한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="ca9e9-119">가장 중요한 이점은 개발 및 작업 사이에서 격리를 제공한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9e9-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
[<span data-ttu-id="ca9e9-120">다음</span><span class="sxs-lookup"><span data-stu-id="ca9e9-120">Next</span></span>](what-is-docker.md)
