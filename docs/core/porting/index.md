---
title: .NET Framework에서 .NET Core로 코드 포팅
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요.
author: cartermp
ms.date: 12/04/2018
ms.custom: seodec18
ms.openlocfilehash: e29750340cf272c2e05287482bcbeca703d8720a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266574"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a><span data-ttu-id="ac377-103">.NET Framework에서 .NET Core로 코드 포팅</span><span class="sxs-lookup"><span data-stu-id="ac377-103">Port your code from .NET Framework to .NET Core</span></span>

<span data-ttu-id="ac377-104">.NET Framework에서 실행되는 코드를 사용한 적이 있다면 .NET Core에서 코드를 실행하는 것에도 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-104">If you've got code that runs on the .NET Framework, you may be interested in running your code on .NET Core, too.</span></span> <span data-ttu-id="ac377-105">여기서는 포팅 프로세스 및 코드를 .NET Core로 포팅할 때 유용할 수 있는 도구 목록을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-105">Here's an overview of the porting process and a list of the tools you may find helpful when porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="ac377-106">포팅 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="ac377-106">Overview of the porting process</span></span>

<span data-ttu-id="ac377-107">프로젝트를 .NET Core로 포팅할 때 권장되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-107">This is the process we recommend you take when porting your project to .NET Core.</span></span> <span data-ttu-id="ac377-108">프로세스의 각 단계는 향후 문서에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-108">Each step of the process is covered in more detail in further articles.</span></span>

1. <span data-ttu-id="ac377-109">타사 종속성을 식별하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-109">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="ac377-110">이 단계에서는 타사 종속성의 개념, 사용 방법, .NET Core에서도 실행되는지 확인하는 방법 및 실행되지 않을 경우 수행할 수 있는 단계를 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-110">This step involves understanding what your third-party dependencies are, how you depend on them, how to check if they also run on .NET Core, and steps you can take if they don't.</span></span> <span data-ttu-id="ac377-111">.NET Core에 사용되는 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 형식으로 종속성을 마이그레이션하는 방법에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-111">It also covers how you can migrate your dependencies over to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format that is used in .NET Core.</span></span>

2. <span data-ttu-id="ac377-112">포팅하려는 모든 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-112">Retarget all projects you wish to port to target the .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="ac377-113">이 단계에서는 .NET Core에서 특정 API를 지원하지 않는 경우 .NET Framework 특정 대상에 대한 API 대안을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-113">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

3. <span data-ttu-id="ac377-114">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)를 사용하여 어셈블리를 분석하고 결과에 따라 이식 계획을 수립합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-114">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="ac377-115">API 이식성 분석기 도구는 컴파일된 어셈블리를 분석하고 개괄적인 이식성 요약 및 .NET Core에서 사용할 수 없는 사용 중인 각 API에 대한 분석 결과를 보여 주는 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-115">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report that shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span> <span data-ttu-id="ac377-116">코드베이스에 대한 분석과 함께 이 보고서를 사용하여 코드를 이식할 방법에 대한 계획을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>

4. <span data-ttu-id="ac377-117">테스트 코드를 이식합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-117">Port your tests code.</span></span>

   <span data-ttu-id="ac377-118">.NET Core로 포팅하면 코드베이스가 많이 변경되기 때문에 코드를 포팅할 때 테스트를 실행할 수 있도록 테스트를 포팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-118">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to get your tests ported, so that you can run tests as you port your code over.</span></span> <span data-ttu-id="ac377-119">MSTest, xUnit 및 NUnit는 모두 .NET Core를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-119">MSTest, xUnit, and NUnit all support .NET Core.</span></span>

5. <span data-ttu-id="ac377-120">이식에 대한 계획을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="ac377-121">유용한 도구</span><span class="sxs-lookup"><span data-stu-id="ac377-121">Tools to help</span></span>

<span data-ttu-id="ac377-122">다음 목록은 포팅 프로세스 중에 사용하면 도움이 되는 도구를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-122">The following list shows tools you might find helpful to use during the porting process:</span></span>

* <span data-ttu-id="ac377-123">.NET 이식성 분석기 - [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases) 또는 [Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)으로, 문제에 대한 어셈블리 단위 분석 결과를 사용하여 .NET Framework와 .NET Core 간에 코드를 포팅할 수 있는 정도에 대한 보고서를 생성할 수 있는 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-123">.NET Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span> <span data-ttu-id="ac377-124">자세한 내용은 [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac377-124">For more information, see [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md).</span></span>
* <span data-ttu-id="ac377-125">.NET API 분석기 - 여러 플랫폼에서 C# API에 대한 잠재적 호환성 위험을 검색하고 사용되지 않는 API 호출을 탐지하는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-125">.NET API analyzer - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="ac377-126">자세한 내용은 [.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac377-126">For more information, see [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>
* <span data-ttu-id="ac377-127">역방향 패키지 검색 - 형식을 검색하고 해당 형식을 포함하는 패키지를 찾을 수 있는 [유용한 웹 서비스](https://packagesearch.azurewebsites.net)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-127">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

<span data-ttu-id="ac377-128">또한 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 도구를 사용하여 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 포팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-128">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="ac377-129">CsprojToVs2017은 타사 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-129">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="ac377-130">모든 프로젝트에서 작동한다는 보장은 없으며, 사용하는 동작이 미묘하게 변경될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-130">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="ac377-131">CsprojToVs2017은 자동화할 수 있는 기본 사항을 자동화하는 _시작점_으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-131">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="ac377-132">프로젝트 파일 형식을 마이그레이션하는 보장된 솔루션은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ac377-132">It is not a guaranteed solution to migrating project file formats.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="ac377-133">다음</span><span class="sxs-lookup"><span data-stu-id="ac377-133">Next</span></span>](third-party-deps.md)
