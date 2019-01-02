---
title: .NET Framework 및 .NET Core용 프로젝트 구성
description: .NET Framework 및 .NET Core에 대해 솔루션을 나란히 컴파일하려는 프로젝트 소유자를 위한 도움말입니다.
author: conniey
ms.date: 04/06/2017
ms.custom: seodec18
ms.openlocfilehash: 97673e1ccaeb094bf8c7cb835a84ae9389fac502
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169133"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="ea202-103">.NET Framework 및 .NET Core를 둘 다 지원하도록 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="ea202-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="ea202-104">.NET Framework와 .NET Core 둘 다에 대해 나란히 컴파일되는 솔루션을 만드는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="ea202-105">이러한 목표를 달성할 수 있도록 프로젝트를 구성하는 여러 가지 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea202-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="ea202-106">.NET Core를 사용하여 프로젝트 레이아웃을 설정하는 방법을 결정할 때 고려해야 할 몇 가지 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="ea202-107">여기에서 모든 것을 다루지는 못할 수 있습니다. 프로젝트 요구에 따라 우선 순위를 정하세요.</span><span class="sxs-lookup"><span data-stu-id="ea202-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="ea202-108">[**기존 프로젝트와 .NET Core 프로젝트를 단일 프로젝트로 결합**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="ea202-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="ea202-109">*좋은 점:*</span><span class="sxs-lookup"><span data-stu-id="ea202-109">*What this is good for:*</span></span>
  * <span data-ttu-id="ea202-110">각각 다른 .NET Framework 버전 또는 플랫폼을 대상으로 하는 여러 프로젝트를 컴파일하는 것이 아니라 단일 프로젝트를 컴파일함으로써 빌드 프로세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="ea202-111">단일 프로젝트 파일을 관리해야 하므로 멀티 타기팅 프로젝트에 대한 소스 파일 관리를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="ea202-112">소스 파일을 추가/제거할 때 대체 방법에서는 이를 다른 프로젝트와 수동으로 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="ea202-113">사용할 NuGet 패키지를 쉽게 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="ea202-114">컴파일러 지시문을 사용하여 라이브러리에서 특정 .NET Framework 버전에 대한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="ea202-115">*지원되지 않는 시나리오:*</span><span class="sxs-lookup"><span data-stu-id="ea202-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="ea202-116">개발자가 기존 프로젝트를 열려면 Visual Studio 2017을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="ea202-117">Visual Studio의 이전 버전을 지원하려면 [프로젝트 파일을 서로 다른 폴더에 유지](#support-vs)하는 것이 더 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="ea202-118">[**기존 프로젝트와 새로운 .NET Core 프로젝트를 별도로 유지**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="ea202-118">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="ea202-119">*좋은 점:*</span><span class="sxs-lookup"><span data-stu-id="ea202-119">*What this is good for:*</span></span>
  * <span data-ttu-id="ea202-120">Visual Studio 2017이 없는 개발자/참가자의 경우 업그레이드하지 않고 기존 프로젝트에 대한 개발을 계속 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="ea202-121">기존 프로젝트에서 코드 변동이 필요하지 않으므로 새 버그가 발생할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="ea202-122">예제</span><span class="sxs-lookup"><span data-stu-id="ea202-122">Example</span></span>

<span data-ttu-id="ea202-123">아래 리포지토리를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ea202-123">Consider the repository below:</span></span>

<span data-ttu-id="ea202-124">![기존 프로젝트][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="ea202-124">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="ea202-125">[**소스 코드**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="ea202-125">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="ea202-126">아래에서는 기존 프로젝트의 제약 조건 및 복잡성에 따라 이 리포지토리에 대한 .NET Core 지원을 추가하는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="ea202-127">기존 프로젝트를 멀티 타기팅 .NET Core 프로젝트로 교체</span><span class="sxs-lookup"><span data-stu-id="ea202-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="ea202-128">기존 *\*.csproj* 파일을 제거하고 여러 프레임워크를 대상으로 하는 단일 *\*.csproj* 파일을 만들도록 리포지토리를 재구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="ea202-129">서로 다른 프레임워크에 대해 단일 프로젝트를 컴파일할 수 있으므로 이는 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="ea202-130">대상 프레임워크별로 서로 다른 컴파일 옵션 및 종속성을 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="ea202-131">![여러 프레임워크를 대상으로 하는 csproj 만들기][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="ea202-131">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="ea202-132">[**소스 코드**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="ea202-132">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="ea202-133">주목할 변경 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-133">Changes to note are:</span></span>

* <span data-ttu-id="ea202-134">*packages.config* 및 *\*.csproj*가 새로운 [.NET Core *\*.csproj*][example-csproj-netcore]로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="ea202-135">NuGet 패키지가 `<PackageReference> ItemGroup`을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="ea202-136">기존 프로젝트를 유지하고 .NET Core 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea202-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="ea202-137">이전 프레임워크를 대상으로 하는 기존 프로젝트가 있는 경우, 이러한 프로젝트는 그대로 두고 이후 프레임워크를 대상으로 하는 .NET Core를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="ea202-138">![다른 폴더에 기존 프로젝트가 있는 .NET Core 프로젝트][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="ea202-138">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="ea202-139">[**소스 코드**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="ea202-139">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="ea202-140">주목할 변경 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-140">Changes to note are:</span></span>

* <span data-ttu-id="ea202-141">.NET Core와 기존 프로젝트가 별도의 폴더에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  * <span data-ttu-id="ea202-142">프로젝트를 별도의 폴더에 유지하면 Visual Studio 2017이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="ea202-143">이전 프로젝트만 여는 별도 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea202-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea202-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea202-144">See Also</span></span>

* <span data-ttu-id="ea202-145">.NET Core로의 마이그레이션에 대한 자세한 지침은 [.NET Core 이식 문서][porting-doc]를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea202-145">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "기존 프로젝트"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "여러 프레임워크를 대상으로 하는 csproj 만들기"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "다른 폴더에 기존 PCL이 있는 .NET Core 프로젝트"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
