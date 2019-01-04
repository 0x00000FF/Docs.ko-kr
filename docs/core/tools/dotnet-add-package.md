---
title: dotnet add package 명령
description: ‘dotnet add package’ 명령은 NuGet 패키지 참조를 프로젝트에 추가하는 편리한 옵션을 제공합니다.
ms.date: 12/04/2018
ms.openlocfilehash: 159b208feafb82e267629ea47dcef02d6b575055
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170004"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="e4777-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="e4777-103">dotnet add package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e4777-104">name</span><span class="sxs-lookup"><span data-stu-id="e4777-104">Name</span></span>

<span data-ttu-id="e4777-105">`dotnet add package` - 패키지 참조를 프로젝트 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-105">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e4777-106">개요</span><span class="sxs-lookup"><span data-stu-id="e4777-106">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="e4777-107">설명</span><span class="sxs-lookup"><span data-stu-id="e4777-107">Description</span></span>

<span data-ttu-id="e4777-108">`dotnet add package` 명령은 패키지 참조를 프로젝트 파일에 추가하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-108">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="e4777-109">명령을 실행한 후 패키지가 프로젝트의 프레임워크와 호환되는지 확인하는 호환성 검사가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-109">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="e4777-110">검사를 통과하면 `<PackageReference>` 요소가 프로젝트 파일에 추가되고 [dotnet restore](dotnet-restore.md)가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-110">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="e4777-111">예를 들어 `Newtonsoft.Json`를 *ToDo.csproj*에 추가하면 다음 예제와 유사한 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-111">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="e4777-112">이제 *ToDo.csproj* 파일에 참조되는 패키지에 대한 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-112">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="e4777-113">인수</span><span class="sxs-lookup"><span data-stu-id="e4777-113">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="e4777-114">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-114">Specifies the project file.</span></span> <span data-ttu-id="e4777-115">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-115">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="e4777-116">추가할 패키지 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-116">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="e4777-117">옵션</span><span class="sxs-lookup"><span data-stu-id="e4777-117">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e4777-118">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 패키지 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-118">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="e4777-119">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-119">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="e4777-120">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="e4777-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="e4777-121">.NET Core 2.1 SDK 버전 2.1.400 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-121">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="e4777-122">복원 미리 보기 및 호환성 검사를 수행하지 않고 패키지 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="e4777-123">지정된 디렉터리에 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-123">Restores the package to the specified directory.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="e4777-124">복원 작업 중 특정 NuGet 패키지 소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-124">Uses a specific NuGet package source during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="e4777-125">패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-125">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="e4777-126">예제</span><span class="sxs-lookup"><span data-stu-id="e4777-126">Examples</span></span>

* <span data-ttu-id="e4777-127">`Newtonsoft.Json` NuGet 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-127">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="e4777-128">특정 버전의 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-128">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="e4777-129">특정 NuGet 소스를 사용하여 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4777-129">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```