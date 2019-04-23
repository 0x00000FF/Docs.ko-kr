---
title: project.json에서 .NET Core 마이그레이션
description: project.json을 사용하여 이전 .NET Core 프로젝트를 마이그레이션하는 방법 알아보기
ms.date: 07/19/2017
ms.custom: seodec18
ms.openlocfilehash: f48728e647b57a8c5796bdc2119f72b58a49d80f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663342"
---
# <a name="migrating-net-core-projects-from-projectjson"></a><span data-ttu-id="7c56b-103">project.json에서 .NET Core 프로젝트 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-103">Migrating .NET Core projects from project.json</span></span>

<span data-ttu-id="7c56b-104">이 문서에서는 .NET Core 프로젝트에 대한 마이그레이션 시나리오를 설명하고 다음 세 가지 마이그레이션 시나리오를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-104">This document will cover migration scenarios for .NET Core projects and will go over the following three migration scenarios:</span></span>

1. [<span data-ttu-id="7c56b-105">*project.json*의 유효한 스키마에서 *csproj*로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-105">Migration from a valid latest schema of *project.json* to *csproj*</span></span>](#migration-from-projectjson-to-csproj)
2. [<span data-ttu-id="7c56b-106">DNX에서 csproj로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-106">Migration from DNX to csproj</span></span>](#migration-from-dnx-to-csproj)
3. [<span data-ttu-id="7c56b-107">RC3 및 이전 .NET Core csproj 프로젝트에서 최종 형식으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-107">Migration from RC3 and previous .NET Core csproj projects to the final format</span></span>](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

<span data-ttu-id="7c56b-108">이 문서는 여전히 project.json을 사용하는 이전 .NET Core 프로젝트에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-108">This document is only applicable to older .NET Core projects that still use project.json.</span></span> <span data-ttu-id="7c56b-109">.NET Framework에서 .NET Core로 마이그레이션하는 경우에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-109">It is not applicable for migrating from .NET Framework to .NET Core.</span></span>

## <a name="migration-from-projectjson-to-csproj"></a><span data-ttu-id="7c56b-110">project.json에서 csproj로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-110">Migration from project.json to csproj</span></span>

<span data-ttu-id="7c56b-111">*project.json*에서 *.csproj*로 마이그레이션하려면 다음 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-111">Migration from *project.json* to *.csproj* can be done using one of the following methods:</span></span>

- [<span data-ttu-id="7c56b-112">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7c56b-112">Visual Studio 2017</span></span>](#visual-studio-2017)
- [<span data-ttu-id="7c56b-113">dotnet 마이그레이션 명령줄 도구</span><span class="sxs-lookup"><span data-stu-id="7c56b-113">dotnet migrate command-line tool</span></span>](#dotnet-migrate)

<span data-ttu-id="7c56b-114">두 방법 모두 동일한 기본 엔진을 사용하여 프로젝트를 마이그레이션하므로 결과가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-114">Both methods use the same underlying engine to migrate the projects, so the results will be the same for both.</span></span> <span data-ttu-id="7c56b-115">대부분의 경우 이러한 두 가지 방법 중 하나를 사용하여 *project.json*을 *csproj*로 마이그레이션하기만 하면 되며 프로젝트 파일을 추가로 수동 편집할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-115">In most cases, using one of these two ways to migrate the *project.json* to *csproj* is the only thing that is needed and no further manual editing of the project file is necessary.</span></span> <span data-ttu-id="7c56b-116">결과로 얻는 *.csproj* 파일의 이름은 포함되는 디렉터리 이름과 동일하게 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-116">The resulting *.csproj* file will be named the same as the containing directory name.</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="7c56b-117">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7c56b-117">Visual Studio 2017</span></span>

<span data-ttu-id="7c56b-118">*.xproj* 파일이나 *.xproj* 파일을 참조하는 솔루션 파일을 열면 **단방향 업그레이드** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-118">When you open a *.xproj* file or a solution file which references *.xproj* files, the **One-way upgrade** dialog appears.</span></span> <span data-ttu-id="7c56b-119">이 대화 상자에 마이그레이션할 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-119">The dialog displays the projects to be migrated.</span></span>
<span data-ttu-id="7c56b-120">솔루션 파일을 여는 경우에는 솔루션 파일에 지정된 모든 프로젝트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-120">If you open a solution file, all the projects specified in the solution file will be listed.</span></span> <span data-ttu-id="7c56b-121">마이그레이션할 프로젝트 목록을 검토하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-121">Review the list of projects to be migrated and select **OK**.</span></span>

![마이그레이션할 프로젝트 목록을 표시하는 단방향 업그레이드 대화 상자](media/one-way-upgrade.jpg)

<span data-ttu-id="7c56b-123">Visual Studio는 선택된 프로젝트를 자동으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-123">Visual Studio will migrate the projects chosen automatically.</span></span> <span data-ttu-id="7c56b-124">솔루션을 마이그레이션할 때 모든 프로젝트를 선택하지 않는 경우에는 동일한 대화 상자에 해당 솔루션의 나머지 솔루션을 업그레이드할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-124">When migrating a solution, if you don't choose all projects, the same dialog will appear asking you to upgrade the remaining projects from that solution.</span></span> <span data-ttu-id="7c56b-125">프로젝트를 마이그레이션한 후 **솔루션 탐색기** 창의 프로젝트를 마우스 오른쪽 단추로 클릭하고 **\<project name>.csproj 편집**을 선택하여 콘텐츠를 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-125">After the project is migrated, you can see and modify its contents by right-clicking the project in the **Solution Explorer** window and selecting **Edit \<project name>.csproj**.</span></span>

<span data-ttu-id="7c56b-126">마이그레이션된 파일(*project.json*, *global.json*, *.xproj* 및 솔루션 파일)은 *Backup* 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-126">Files that were migrated (*project.json*, *global.json*, *.xproj* and solution file) will be moved to a *Backup* folder.</span></span> <span data-ttu-id="7c56b-127">마이그레이션된 솔루션 파일은 Visual Studio 2017로 업그레이드되며 이전 버전의 Visual Studio에서 해당 솔루션 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-127">The solution file that is migrated will be upgraded to Visual Studio 2017 and you won't be able to open that solution file in previous versions of Visual Studio.</span></span>
<span data-ttu-id="7c56b-128">마이그레이션 보고서를 포함하는 *UpgradeLog.htm*이라는 파일도 저장되고 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-128">A file named *UpgradeLog.htm* is also saved and automatically opened that contains a migration report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c56b-129">Visual Studio 2015에서는 새로운 도구를 사용할 수 없으므로, 해당 버전의 Visual Studio를 사용하여 프로젝트를 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-129">The new tooling is not available in Visual Studio 2015, so you cannot migrate your projects using that version of Visual Studio.</span></span>

### <a name="dotnet-migrate"></a><span data-ttu-id="7c56b-130">dotnet 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-130">dotnet migrate</span></span>

<span data-ttu-id="7c56b-131">명령줄 시나리오에서는 [`dotnet migrate`](../tools/dotnet-migrate.md) 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-131">In the command-line scenario, you can use the [`dotnet migrate`](../tools/dotnet-migrate.md) command.</span></span> <span data-ttu-id="7c56b-132">이 경우 프로젝트, 솔루션 또는 폴더 집합을 발견된 순서에 따라 차례로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-132">It will migrate a project, a solution or a set of folders in that order, depending on which ones were found.</span></span>
<span data-ttu-id="7c56b-133">프로젝트를 마이그레이션하면 프로젝트 및 프로젝트의 모든 종속 항목이 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-133">When you migrate a project, the project and all its dependencies are migrated.</span></span>

<span data-ttu-id="7c56b-134">마이그레이션된 파일(*project.json*, *global.json* 및 *.xproj*)은 *backup* 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-134">Files that were migrated (*project.json*, *global.json* and *.xproj*) will be moved to a *backup* folder.</span></span>

> [!NOTE]
> <span data-ttu-id="7c56b-135">Visual Studio Code를 사용 중인 경우 `dotnet migrate` 명령은 `tasks.json`과 같은 Visual Studio Code 관련 파일을 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-135">If you are using Visual Studio Code, the `dotnet migrate` command will not modify Visual Studio Code-specific files such as `tasks.json`.</span></span> <span data-ttu-id="7c56b-136">이러한 파일은 수동으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-136">These files need to be changed manually.</span></span>
> <span data-ttu-id="7c56b-137">Project Ryder나 다른 편집기 또는 Visual Studio 이외의 IDE(통합 개발 환경)를 사용 중인 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-137">This is also true if you are using Project Ryder or any editor or Integrated Development Environment (IDE) other than Visual Studio.</span></span>

<span data-ttu-id="7c56b-138">project.json 및 csproj 형식 간을 비교하려면 [project.json 및 csproj 속성 간 매핑](../tools/project-json-to-csproj.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c56b-138">See [A mapping between project.json and csproj properties](../tools/project-json-to-csproj.md) for a comparison of project.json and csproj formats.</span></span>

### <a name="common-issues"></a><span data-ttu-id="7c56b-139">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="7c56b-139">Common issues</span></span>

- <span data-ttu-id="7c56b-140">“No executable found matching command dotnet-migrate”(dotnet-migrate 명령과 일치하는 실행 파일을 찾을 수 없습니다.) 오류가 발생하는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-140">If you get an error: "No executable found matching command dotnet-migrate":</span></span>

<span data-ttu-id="7c56b-141">`dotnet --version`을 실행하여 사용 중인 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-141">Run `dotnet --version` to see which version you are using.</span></span> <span data-ttu-id="7c56b-142">[`dotnet migrate`](../tools/dotnet-migrate.md)을 사용하려면 .NET Core CLI RC3 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-142">[`dotnet migrate`](../tools/dotnet-migrate.md) requires .NET Core CLI RC3 or higher.</span></span>
<span data-ttu-id="7c56b-143">*global.json* 파일이 현재 또는 상위 디렉터리에 있고 `sdk` 버전이 이전 버전으로 설정된 경우 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-143">You’ll get this error if you have a *global.json* file in the current or parent directory and the `sdk` version is set to an older version.</span></span>

## <a name="migration-from-dnx-to-csproj"></a><span data-ttu-id="7c56b-144">DNX에서 csproj로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-144">Migration from DNX to csproj</span></span>

<span data-ttu-id="7c56b-145">.NET Core 개발에 DNX를 여전히 사용 중인 경우 다음 두 단계로 마이그레이션 프로세스를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-145">If you are still using DNX for .NET Core development, your migration process should be done in two stages:</span></span>

1. <span data-ttu-id="7c56b-146">[기존 DNX 마이그레이션 지침](from-dnx.md)에 따라 DNX에서 project-json 사용 CLI로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-146">Use the [existing DNX migration guidance](from-dnx.md) to migrate from DNX to project-json enabled CLI.</span></span>
2. <span data-ttu-id="7c56b-147">이전 섹션의 단계에 따라 *project.json*에서 *.csproj*로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-147">Follow the steps from the previous section to migrate from *project.json* to *.csproj*.</span></span>  

> [!NOTE]
> <span data-ttu-id="7c56b-148">DNX는 .NET Core CLI의 Preview 1 릴리스부터 공식적으로 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-148">DNX has become officially deprecated during the Preview 1 release of the .NET Core CLI.</span></span>

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a><span data-ttu-id="7c56b-149">이전 .NET Core csproj 형식에서 RTM csproj로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7c56b-149">Migration from earlier .NET Core csproj formats to RTM csproj</span></span>

<span data-ttu-id="7c56b-150">.NET Core csproj 형식은 새 시험판 버전의 도구가 나올 때마다 변경되고 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-150">The .NET Core csproj format has been changing and evolving with each new pre-release version of the tooling.</span></span> <span data-ttu-id="7c56b-151">csproj의 이전 버전에서 최신 버전으로 프로젝트 파일을 마이그레이션하는 도구는 없으므로 프로젝트 파일을 수동으로 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-151">There is no tool that will migrate your project file from earlier versions of csproj to the latest, so you need to manually edit the project file.</span></span> <span data-ttu-id="7c56b-152">실제 단계는 마이그레이션하는 프로젝트 파일의 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-152">The actual steps depend on the version of the project file you are migrating.</span></span> <span data-ttu-id="7c56b-153">다음은 버전 간에 수행된 변경 사항에 따라 고려할 몇 가지 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-153">The following is some guidance to consider based on the changes that happened between versions:</span></span>

* <span data-ttu-id="7c56b-154">`<Project>` 요소에 도구 버전 속성이 있는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-154">Remove the tools version property from the `<Project>` element, if it exists.</span></span>
* <span data-ttu-id="7c56b-155">`<Project>` 요소에서 XML 네임스페이스(`xmlns`)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-155">Remove the XML namespace (`xmlns`) from the `<Project>` element.</span></span>
* <span data-ttu-id="7c56b-156">`Sdk` 특성이 없는 경우 `<Project>` 요소에 추가하고 `Microsoft.NET.Sdk` 또는 `Microsoft.NET.Sdk.Web`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-156">If it doesn't exist, add the `Sdk` attribute to the `<Project>` element and set it to `Microsoft.NET.Sdk` or `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="7c56b-157">이 특성은 프로젝트에서 사용할 SDK를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-157">This attribute specifies that the project uses the SDK to be used.</span></span> <span data-ttu-id="7c56b-158">웹앱에는 `Microsoft.NET.Sdk.Web`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-158">`Microsoft.NET.Sdk.Web` is used for web apps.</span></span>
* <span data-ttu-id="7c56b-159">프로젝트의 맨 위와 맨 아래에서 `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` 및 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` 문을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-159">Remove the `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` and `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` statements from the top and bottom of the project.</span></span> <span data-ttu-id="7c56b-160">이러한 import 문은 SDK에 포함되므로, 프로젝트에 있을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-160">These import statements are implied by the SDK, so there is no need for them to be in the project.</span></span>
* <span data-ttu-id="7c56b-161">프로젝트에 `Microsoft.NETCore.App` 또는 `NETStandard.Library` `<PackageReference>` 항목이 있으면 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-161">If you have `Microsoft.NETCore.App` or `NETStandard.Library` `<PackageReference>` items in your project, you should remove them.</span></span> <span data-ttu-id="7c56b-162">이러한 패키지 참조는 [SDK에 포함](https://aka.ms/sdkimplicitrefs)되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-162">These package references are [implied by the SDK](https://aka.ms/sdkimplicitrefs).</span></span>
* <span data-ttu-id="7c56b-163">`Microsoft.NET.Sdk` `<PackageReference>` 요소가 있는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-163">Remove the `Microsoft.NET.Sdk` `<PackageReference>` element, if it exists.</span></span> <span data-ttu-id="7c56b-164">SDK 참조는 `<Project>` 요소의 `Sdk` 특성을 통해 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-164">The SDK reference comes through the `Sdk` attribute on the `<Project>` element.</span></span>
* <span data-ttu-id="7c56b-165">[SDK에 포함](../tools/csproj.md#default-compilation-includes-in-net-core-projects)된 [glob](https://en.wikipedia.org/wiki/Glob_(programming))을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-165">Remove the [globs](https://en.wikipedia.org/wiki/Glob_(programming)) that are [implied by the SDK](../tools/csproj.md#default-compilation-includes-in-net-core-projects).</span></span> <span data-ttu-id="7c56b-166">프로젝트에 이러한 GLOB를 남겨 두면 컴파일 항목이 중복되므로 빌드 시 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-166">Leaving these globs in your project will cause an error on build because compile items will be duplicated.</span></span>

<span data-ttu-id="7c56b-167">이러한 단계를 수행하면 프로젝트가 RTM .NET Core csproj 형식과 완벽히 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c56b-167">After these steps your project should be fully compatible with the RTM .NET Core csproj format.</span></span>

<span data-ttu-id="7c56b-168">이전 csproj 형식에서 새 형식으로 마이그레이션하기 전후의 예는 .NET 블로그에서 [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/)(Visual Studio 2017 RC 업데이트 – .NET Core 도구 개선 사항) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c56b-168">For examples of before and after the migration from old csproj format to the new one, see the [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) article on the .NET blog.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c56b-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c56b-169">See also</span></span>

- [<span data-ttu-id="7c56b-170">Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7c56b-170">Port, Migrate, and Upgrade Visual Studio Projects</span></span>](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
