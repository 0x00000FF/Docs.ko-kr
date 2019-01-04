---
title: dotnet tool uninstall 명령
description: dotnet tool uninstall 명령은 컴퓨터에서 지정한 .NET Core Global Tool을 제거합니다.
ms.date: 05/29/2018
ms.openlocfilehash: 2ac0046d012fcf4a4be1c9bfa2e942e35b2c7290
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168353"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="f7516-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="f7516-103">dotnet tool uninstall</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="f7516-104">name</span><span class="sxs-lookup"><span data-stu-id="f7516-104">Name</span></span>

<span data-ttu-id="f7516-105">`dotnet tool uninstall` - 컴퓨터에서 지정된 [.NET Core Global Tool](global-tools.md)을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-105">`dotnet tool uninstall` - Uninstalls the specified [.NET Core Global Tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f7516-106">개요</span><span class="sxs-lookup"><span data-stu-id="f7516-106">Synopsis</span></span>

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="f7516-107">설명</span><span class="sxs-lookup"><span data-stu-id="f7516-107">Description</span></span>

<span data-ttu-id="f7516-108">`dotnet tool uninstall` 명령은 컴퓨터에서 .NET Core Global Tool을 제거하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-108">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core Global Tools from your machine.</span></span> <span data-ttu-id="f7516-109">이 명령을 사용하려면 `--global` 옵션을 사용하여 사용자 수준 도구를 제거하거나 `--tool-path` 옵션을 사용하여 도구를 설치할 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-109">To use the command, you either have to specify that you want to remove a user-wide tool using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="f7516-110">인수</span><span class="sxs-lookup"><span data-stu-id="f7516-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="f7516-111">제거할 .NET Core Global Tool을 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-111">Name/ID of the NuGet package that contains the .NET Core Global Tool to uninstall.</span></span> <span data-ttu-id="f7516-112">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-112">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="f7516-113">옵션</span><span class="sxs-lookup"><span data-stu-id="f7516-113">Options</span></span>

`-g|--global`

<span data-ttu-id="f7516-114">사용자 수준 설치에서 제거할 도구임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-114">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="f7516-115">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-115">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f7516-116">이 옵션을 지정하지 않으면 `--tool-path` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-116">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="f7516-117">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-117">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="f7516-118">Global Tool을 제거할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-118">Specifies the location where to uninstall the Global Tool.</span></span> <span data-ttu-id="f7516-119">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-119">PATH can be absolute or relative.</span></span> <span data-ttu-id="f7516-120">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-120">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f7516-121">이 옵션을 지정하지 않으면 `--global` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-121">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="f7516-122">예제</span><span class="sxs-lookup"><span data-stu-id="f7516-122">Examples</span></span>

<span data-ttu-id="f7516-123">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-123">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool uninstall -g dotnetsay`

<span data-ttu-id="f7516-124">특정 Windows 폴더에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-124">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Windows folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="f7516-125">특정 Linux/macOS 폴더에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7516-125">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Linux/macOS folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="f7516-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7516-126">See also</span></span>

* [<span data-ttu-id="f7516-127">.NET Core Global Tool</span><span class="sxs-lookup"><span data-stu-id="f7516-127">.NET Core Global Tools</span></span>](global-tools.md)