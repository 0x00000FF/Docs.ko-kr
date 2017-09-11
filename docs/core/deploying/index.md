---
title: ".NET Core 응용 프로그램 배포"
description: ".NET Core 응용 프로그램 배포."
keywords: ".NET, .NET Core, .NET Core 배포"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 199bb132df201175dbdbdd19634de5c3551b5f3b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-application-deployment"></a><span data-ttu-id="e3c64-104">.NET Core 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="e3c64-104">.NET Core application deployment</span></span>

<span data-ttu-id="e3c64-105">.NET Core 응용 프로그램에 대해 두 가지 유형을 배포를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-105">You can create two types of deployments for .NET Core applications:</span></span>

- <span data-ttu-id="e3c64-106">프레임워크 종속 배포.</span><span class="sxs-lookup"><span data-stu-id="e3c64-106">Framework-dependent deployment.</span></span> <span data-ttu-id="e3c64-107">이름에서 알 수 있듯이 FDD(프레임워크 종속 배포)에서는 대상 시스템에 .NET Core의 공유 시스템 차원 버전이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-107">As the name implies, framework-dependent deployment (FDD) relies on the presence of a shared system-wide version of .NET Core on the target system.</span></span> <span data-ttu-id="e3c64-108">.NET Core가 이미 존재하기 때문에 .NET Core 설치 간에 앱을 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-108">Because .NET Core is already present, your app is also portable between installations of .NET Core.</span></span> <span data-ttu-id="e3c64-109">앱은 고유한 코드와 .NET Core 라이브러리 외부에 있는 타사 종속성만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-109">Your app contains only its own code and any third-party dependencies that are outside of the .NET Core libraries.</span></span> <span data-ttu-id="e3c64-110">FDD는 명령줄에서 [dotnet 유틸리티](../tools/dotnet.md)를 사용하여 시작할 수 있는 *.dll* 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-110">FDDs contain *.dll* files that can be launched by using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span> <span data-ttu-id="e3c64-111">예를 들어 `dotnet app.dll`은 `app`이라는 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-111">For example, `dotnet app.dll` runs an application named `app`.</span></span>

- <span data-ttu-id="e3c64-112">자체 포함 배포.</span><span class="sxs-lookup"><span data-stu-id="e3c64-112">Self-contained deployment.</span></span> <span data-ttu-id="e3c64-113">FDD와 달리 SCD(자체 포함 배포)에서는 대상 시스템에 공유 구성 요소가 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-113">Unlike FDD, a self-contained deployment (SCD) doesn't rely on the presence of shared components on the target system.</span></span> <span data-ttu-id="e3c64-114">.NET Core 라이브러리 및 .NET Core 런타임을 비롯한 모든 구성 요소가 응용 프로그램에 포함되며 다른 .NET Core 응용 프로그램에서는 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-114">All components, including both the .NET Core libraries and the .NET Core runtime, are included with the application and are isolated from other .NET Core applications.</span></span> <span data-ttu-id="e3c64-115">SCD는 플랫폼별 .NET Core 호스트의 이름이 변경된 버전인 실행 파일(예: Windows 플랫폼에서 `app`이라는 응용 프로그램에 대한 *app.exe*)과 실제 응용 프로그램인 *.dll* 파일(예: *app.dll*)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-115">SCDs include an executable (such as *app.exe* on Windows platforms for an application named `app`), which is  a renamed version of the platform-specific .NET Core host, and a *.dll* file (such as *app.dll*), which is the actual application.</span></span>

## <a name="framework-dependent-deployments-fdd"></a><span data-ttu-id="e3c64-116">프레임워크 종속 배포(FDD)</span><span class="sxs-lookup"><span data-stu-id="e3c64-116">Framework-dependent deployments (FDD)</span></span>

<span data-ttu-id="e3c64-117">FDD에서는 앱과 타사 종속성만 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-117">For an FDD, you deploy only your app and any third-party dependencies.</span></span> <span data-ttu-id="e3c64-118">앱에서 대상 시스템에 있는 .NET Core 버전을 사용하므로 .NET Core를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-118">You don't have to deploy .NET Core, since your app will use the version of .NET Core that's present on the target system.</span></span> <span data-ttu-id="e3c64-119">이 배포는 .NET Core 앱의 기본 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-119">This is the default deployment model for .NET Core apps.</span></span>

### <a name="why-create-a-framework-dependent-deployment"></a><span data-ttu-id="e3c64-120">프레임워크 종속 배포를 만드는 이유</span><span class="sxs-lookup"><span data-stu-id="e3c64-120">Why create a framework-dependent deployment?</span></span>

<span data-ttu-id="e3c64-121">FDD 배포에는 다음과 같은 여러 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-121">Deploying an FDD has a number of advantages:</span></span>

- <span data-ttu-id="e3c64-122">.NET Core 앱이 실행될 대상 운영 체제를 미리 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-122">You don't have to define the target operating systems that your .NET Core app will run on in advance.</span></span> <span data-ttu-id="e3c64-123">.NET Core는 운영 체제에 관계없이 실행 파일 및 라이브러리에 공용 PE 파일 형식을 사용하므로 기본 운영 체제에 관계없이 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-123">Because .NET Core uses a common PE file format for executables and libraries regardless of operating system, .NET Core can execute your app regardless of the underlying operating system.</span></span> <span data-ttu-id="e3c64-124">PE 파일 형식에 대한 자세한 내용은 [.NET 어셈블리 파일 형식](../../standard/assembly-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c64-124">For more information on the PE file format, see [.NET Assembly File Format](../../standard/assembly-format.md).</span></span>

- <span data-ttu-id="e3c64-125">배포 패키지의 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-125">The size of your deployment package is small.</span></span> <span data-ttu-id="e3c64-126">앱과 앱의 종속성만 배포하고 .NET Core 자체는 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-126">You only deploy your app and its dependencies, not .NET Core itself.</span></span>

- <span data-ttu-id="e3c64-127">여러 앱에서 동일한 .NET Core 설치를 사용하여 호스트 시스템에서 디스크 공간 및 메모리 사용량을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-127">Multiple apps use the same .NET Core installation, which reduces both disk space and memory usage on host systems.</span></span>

<span data-ttu-id="e3c64-128">다음과 같은 몇 가지 단점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-128">There are also a few disadvantages:</span></span>

- <span data-ttu-id="e3c64-129">대상으로 지정한 .NET Core의 버전이나 그 이상 버전이 호스트 시스템에 이미 설치된 경우에만 앱이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-129">Your app can run only if the version of .NET Core that you target, or a later version, is already installed on the host system.</span></span>

- <span data-ttu-id="e3c64-130">.NET Core 런타임 및 라이브러리가 향후 릴리스에서 사용자 모르게 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-130">It's possible for the .NET Core runtime and libraries to change without your knowledge in future releases.</span></span> <span data-ttu-id="e3c64-131">드문 경우지만 이로 인해 앱의 동작이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-131">In rare cases, this may change the behavior of your app.</span></span>

## <a name="self-contained-deployments-scd"></a><span data-ttu-id="e3c64-132">자체 포함 배포(SCD)</span><span class="sxs-lookup"><span data-stu-id="e3c64-132">Self-contained deployments (SCD)</span></span>

<span data-ttu-id="e3c64-133">자체 포함 배포에서는 앱과 필요한 타사 종속성 외에도 앱을 빌드하는 데 사용한 .NET Core 버전도 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-133">For a self-contained deployment, you deploy your app and any required third-party dependencies along with the version of .NET Core that you used to build the app.</span></span> <span data-ttu-id="e3c64-134">SCD를 만들 때 다양한 플랫폼의 [.NET Core에 대한 기본 종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 포함하지 않으므로 앱을 실행하려면 이러한 종속성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-134">Creating an SCD doesn't include the [native dependencies of .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) on various platforms, so these must be present before the app runs.</span></span>

<span data-ttu-id="e3c64-135">FDD 및 SCD 배포는 별도의 호스트 실행 파일을 사용하므로 게시자 서명이 있는 SCD에 대해 호스트 실행 파일에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-135">FDD and SCD deployments use separate host executables, so you can sign a host executable for an SCD with your publisher signature.</span></span>

### <a name="why-deploy-a-self-contained-deployment"></a><span data-ttu-id="e3c64-136">자체 포함 배포를 배포하는 이유</span><span class="sxs-lookup"><span data-stu-id="e3c64-136">Why deploy a self-contained deployment?</span></span>

<span data-ttu-id="e3c64-137">자체 포함 배포를 배포하면 다음과 같은 두 가지 주요 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-137">Deploying a Self-contained deployment has two major advantages:</span></span>

- <span data-ttu-id="e3c64-138">앱과 함께 배포되는 .NET Core 버전을 유일하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-138">You have sole control of the version of .NET Core that is deployed with your app.</span></span> <span data-ttu-id="e3c64-139">.NET Core만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-139">.NET Core can be serviced only by you.</span></span>

- <span data-ttu-id="e3c64-140">앱이 실행될 .NET Core 버전을 제공하므로 대상 시스템에서 .NET Core 앱을 실행할 수 있다고 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-140">You can be assured that the target system can run your .NET Core app, since you're providing the version of .NET Core that it will run on.</span></span>

<span data-ttu-id="e3c64-141">다음과 같은 여러 가지 단점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-141">It also has a number of disadvantages:</span></span>

- <span data-ttu-id="e3c64-142">.NET Core가 배포 패키지에 포함되므로 배포 패키지를 빌드할 대상 플랫폼을 미리 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-142">Because .NET Core is included in your deployment package, you must select the target platforms for which you build deployment packages in advance.</span></span>

- <span data-ttu-id="e3c64-143">.NET Core뿐만 아니라 앱과 해당 타사 종속성도 포함해야 하므로 배포 패키지의 크기가 상대적으로 큽니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-143">The size of your deployment package is relatively large, since you have to include .NET Core as well as your app and its third-party dependencies.</span></span>

- <span data-ttu-id="e3c64-144">다양한 자체 포함 .NET Core 앱을 시스템에 배포하면 각 앱에서 .NET Core 파일을 중복하므로 엄청나게 많은 디스크 공간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-144">Deploying numerous self-contained .NET Core apps to a system can consume significant amounts of disk space, since each app duplicates .NET Core files.</span></span>

## <a name="step-by-step-examples"></a><span data-ttu-id="e3c64-145">단계별 예제</span><span class="sxs-lookup"><span data-stu-id="e3c64-145">Step-by-step examples</span></span>

<span data-ttu-id="e3c64-146">CLI 도구를 사용하여 .NET Core 앱을 배포하는 방법을 보여 주는 단계별 예제는 [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md)(CLI 도구를 사용하여 .NET Core 앱 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c64-146">For step-by-step examples of deploying .NET Core apps with CLI tools, see [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md).</span></span> <span data-ttu-id="e3c64-147">Visual Studio를 사용하여 .NET Core 앱을 배포하는 방법을 보여 주는 단계별 예제는 [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md)(Visual Studio를 사용하여 .NET Core 앱 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c64-147">For step-by-step examples of deploying .NET Core apps with Visual Studio, see [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md).</span></span> <span data-ttu-id="e3c64-148">각 항목에는 다음 배포에 대한 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3c64-148">Each topic includes examples of the following deployments:</span></span>

- <span data-ttu-id="e3c64-149">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="e3c64-149">Framework-dependent deployment</span></span>
- <span data-ttu-id="e3c64-150">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="e3c64-150">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="e3c64-151">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="e3c64-151">Self-contained deployment</span></span>
- <span data-ttu-id="e3c64-152">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="e3c64-152">Self-contained deployment with third-party dependencies</span></span>

# <a name="see-also"></a><span data-ttu-id="e3c64-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3c64-153">See also</span></span>

<span data-ttu-id="e3c64-154">[Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (CLI 도구를 사용하여 .NET Core 앱 배포)</span><span class="sxs-lookup"><span data-stu-id="e3c64-154">[Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) </span></span>  
<span data-ttu-id="e3c64-155">[Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Visual Studio를 사용하여 .NET Core 앱 배포)</span><span class="sxs-lookup"><span data-stu-id="e3c64-155">[Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) </span></span>  
<span data-ttu-id="e3c64-156">[패키지, 메타패키지 및 프레임워크](../packages.md) </span><span class="sxs-lookup"><span data-stu-id="e3c64-156">[Packages, Metapackages and Frameworks](../packages.md) </span></span>  
[<span data-ttu-id="e3c64-157">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="e3c64-157">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

