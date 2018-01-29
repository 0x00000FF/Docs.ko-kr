---
title: "dotnet 명령 - .NET Core CLI"
description: "dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2eea7d13994bfddc89d8f3513308a6620c53c88c
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="c8297-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="c8297-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c8297-104">name</span><span class="sxs-lookup"><span data-stu-id="c8297-104">Name</span></span>

<span data-ttu-id="c8297-105">`dotnet` - 명령줄 명령을 실행하기 위한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c8297-106">개요</span><span class="sxs-lookup"><span data-stu-id="c8297-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c8297-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c8297-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c8297-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c8297-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="c8297-109">설명</span><span class="sxs-lookup"><span data-stu-id="c8297-109">Description</span></span>

<span data-ttu-id="c8297-110">`dotnet`은 CLI(명령줄 인터페이스) 도구 체인에 대한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="c8297-111">자체적으로 호출되어 간단한 사용 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="c8297-112">각 특정 기능은 명령으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="c8297-113">기능을 사용하려면 [`dotnet build`](dotnet-build.md)와 같이 `dotnet`뒤에 명령을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="c8297-114">명령 다음에 오는 모든 인수는 고유한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="c8297-115">`dotnet` 자체가 명령으로 사용되는 유일한 경우는 [프레임워크 종속 앱](../deploying/index.md)을 실행하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="c8297-116">`dotnet` 동사 뒤에 응용 프로그램 DLL을 지정하여 응용 프로그램을 실행합니다(예: `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="c8297-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="c8297-117">옵션</span><span class="sxs-lookup"><span data-stu-id="c8297-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c8297-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c8297-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="c8297-119">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c8297-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c8297-121">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c8297-122">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c8297-123">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-123">Prints out a short help for the command.</span></span> <span data-ttu-id="c8297-124">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c8297-125">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c8297-126">후보 공유 프레임워크에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="c8297-127">자세한 정보 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c8297-128">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c8297-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c8297-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c8297-130">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c8297-131">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c8297-132">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c8297-133">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-133">Prints out a short help for the command.</span></span> <span data-ttu-id="c8297-134">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c8297-135">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="c8297-136">자세한 정보 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c8297-137">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c8297-138">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="c8297-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c8297-139">일반</span><span class="sxs-lookup"><span data-stu-id="c8297-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c8297-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c8297-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="c8297-141">명령</span><span class="sxs-lookup"><span data-stu-id="c8297-141">Command</span></span>                             | <span data-ttu-id="c8297-142">함수</span><span class="sxs-lookup"><span data-stu-id="c8297-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c8297-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c8297-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c8297-144">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c8297-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c8297-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c8297-146">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c8297-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c8297-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c8297-148">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c8297-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c8297-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c8297-150">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c8297-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c8297-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c8297-152">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c8297-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c8297-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c8297-154">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c8297-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c8297-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c8297-156">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c8297-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c8297-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c8297-158">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c8297-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c8297-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c8297-160">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c8297-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c8297-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c8297-162">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c8297-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c8297-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c8297-164">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c8297-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c8297-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c8297-166">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c8297-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c8297-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c8297-168">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c8297-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c8297-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c8297-170">명령</span><span class="sxs-lookup"><span data-stu-id="c8297-170">Command</span></span>                             | <span data-ttu-id="c8297-171">함수</span><span class="sxs-lookup"><span data-stu-id="c8297-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c8297-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c8297-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c8297-173">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c8297-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c8297-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c8297-175">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c8297-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c8297-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c8297-177">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c8297-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c8297-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c8297-179">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c8297-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c8297-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c8297-181">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c8297-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c8297-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c8297-183">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c8297-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c8297-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c8297-185">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c8297-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c8297-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c8297-187">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c8297-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c8297-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c8297-189">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c8297-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c8297-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c8297-191">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c8297-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c8297-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c8297-193">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c8297-194">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="c8297-194">Project references</span></span>

<span data-ttu-id="c8297-195">명령</span><span class="sxs-lookup"><span data-stu-id="c8297-195">Command</span></span> | <span data-ttu-id="c8297-196">함수</span><span class="sxs-lookup"><span data-stu-id="c8297-196">Function</span></span>
--- | ---
[<span data-ttu-id="c8297-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c8297-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c8297-198">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-198">Add a project reference.</span></span>
[<span data-ttu-id="c8297-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c8297-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c8297-200">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-200">List project references.</span></span>
[<span data-ttu-id="c8297-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c8297-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c8297-202">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c8297-203">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="c8297-203">NuGet packages</span></span>

<span data-ttu-id="c8297-204">명령</span><span class="sxs-lookup"><span data-stu-id="c8297-204">Command</span></span> | <span data-ttu-id="c8297-205">함수</span><span class="sxs-lookup"><span data-stu-id="c8297-205">Function</span></span>
--- | ---
[<span data-ttu-id="c8297-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c8297-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c8297-207">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-207">Add a NuGet package.</span></span>
[<span data-ttu-id="c8297-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c8297-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c8297-209">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c8297-210">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="c8297-210">NuGet commands</span></span>

<span data-ttu-id="c8297-211">명령</span><span class="sxs-lookup"><span data-stu-id="c8297-211">Command</span></span> | <span data-ttu-id="c8297-212">함수</span><span class="sxs-lookup"><span data-stu-id="c8297-212">Function</span></span>
--- | ---
[<span data-ttu-id="c8297-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c8297-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c8297-214">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c8297-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c8297-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c8297-216">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c8297-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c8297-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c8297-218">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="c8297-219">예제</span><span class="sxs-lookup"><span data-stu-id="c8297-219">Examples</span></span>

<span data-ttu-id="c8297-220">컴파일하고 실행할 수 있는 샘플 .NET Core 콘솔 응용 프로그램을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="c8297-221">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c8297-222">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c8297-223">이름이 `myapp.dll`인 프레임워크 종속형 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c8297-224">환경 변수</span><span class="sxs-lookup"><span data-stu-id="c8297-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="c8297-225">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-225">The primary package cache.</span></span> <span data-ttu-id="c8297-226">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c8297-227">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c8297-228">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c8297-229">원격 분석 기능을 옵트아웃하려면 `true`(값 `true`, `1` 또는 `yes` 허용)로 설정하고, 원격 분석 기능을 옵트인하려면 `false`(값 `false`, `0` 또는 `no` 허용)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c8297-230">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8297-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>
