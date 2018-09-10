---
title: dotnet tool update 명령 - .NET Core CLI
description: dotnet tool update 명령은 컴퓨터에 지정된 .NET Core Global Tool을 업데이트합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 90b0dc91f74d890420dc7185642aa89100cadba8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44069395"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="97353-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="97353-103">dotnet tool update</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="97353-104">name</span><span class="sxs-lookup"><span data-stu-id="97353-104">Name</span></span>

<span data-ttu-id="97353-105">`dotnet tool update` - 컴퓨터에서 지정된 [.NET Core Global Tool](global-tools.md)을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-105">`dotnet tool update` - Updates the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="97353-106">개요</span><span class="sxs-lookup"><span data-stu-id="97353-106">Synopsis</span></span>

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="97353-107">설명</span><span class="sxs-lookup"><span data-stu-id="97353-107">Description</span></span>

<span data-ttu-id="97353-108">`dotnet tool update` 명령은 컴퓨터의 .NET Core Global Tool을 패키지의 안정적인 최신 버전으로 업데이트하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-108">The `dotnet tool update` command provides a way for you to update .NET Core Global Tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="97353-109">이 명령은 도구를 제거하고 다시 설치하여 효과적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-109">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="97353-110">이 명령을 사용하려면 `--global` 옵션을 사용하여 사용자 수준 설치에서 도구를 업데이트하거나 `--tool-path` 옵션을 사용하여 도구를 설치할 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-110">To use the command, you either have to specify that you want to update a tool from a user-wide installation using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="97353-111">인수</span><span class="sxs-lookup"><span data-stu-id="97353-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="97353-112">업데이트할 .NET Core Global Tool을 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="97353-112">Name/ID of the NuGet package that contains the .NET Core Global Tool to update.</span></span> <span data-ttu-id="97353-113">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97353-113">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="97353-114">옵션</span><span class="sxs-lookup"><span data-stu-id="97353-114">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="97353-115">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-115">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="97353-116">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="97353-116">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="97353-117">도구를 업데이트할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-117">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

`-g|--global`

<span data-ttu-id="97353-118">업데이트가 사용자 수준 도구에 대한 것임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-118">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="97353-119">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97353-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="97353-120">이 옵션을 지정하지 않으면 `--tool-path` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-120">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="97353-121">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-121">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="97353-122">Global Tool이 설치되는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-122">Specifies the location where the Global Tool is installed.</span></span> <span data-ttu-id="97353-123">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97353-123">PATH can be absolute or relative.</span></span> <span data-ttu-id="97353-124">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97353-124">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="97353-125">이 옵션을 지정하지 않으면 `--global` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-125">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="97353-126">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="97353-127">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="97353-127">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="97353-128">예제</span><span class="sxs-lookup"><span data-stu-id="97353-128">Examples</span></span>

<span data-ttu-id="97353-129">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-129">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool update -g dotnetsay`

<span data-ttu-id="97353-130">특정 Windows 폴더에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-130">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Windows folder:</span></span>

`dotnet tool update dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="97353-131">특정 Linux/macOS 폴더에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="97353-131">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Linux/macOS folder:</span></span>

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="97353-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97353-132">See also</span></span>

* [<span data-ttu-id="97353-133">.NET Core Global Tool</span><span class="sxs-lookup"><span data-stu-id="97353-133">.NET Core Global Tools</span></span>](global-tools.md)