---
title: dotnet add package 명령
description: ‘dotnet add package’ 명령은 NuGet 패키지 참조를 프로젝트에 추가하는 편리한 옵션을 제공합니다.
ms.date: 04/24/2019
ms.openlocfilehash: 82f178026b46eb0237243b8ae49d17fbcc1af6ec
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959247"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="6e449-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="6e449-103">dotnet add package</span></span>

<span data-ttu-id="6e449-104">**이 문서 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="6e449-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="6e449-105">name</span><span class="sxs-lookup"><span data-stu-id="6e449-105">Name</span></span>

<span data-ttu-id="6e449-106">`dotnet add package` - 패키지 참조를 프로젝트 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6e449-107">개요</span><span class="sxs-lookup"><span data-stu-id="6e449-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="6e449-108">설명</span><span class="sxs-lookup"><span data-stu-id="6e449-108">Description</span></span>

<span data-ttu-id="6e449-109">`dotnet add package` 명령은 패키지 참조를 프로젝트 파일에 추가하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="6e449-110">명령을 실행한 후 패키지가 프로젝트의 프레임워크와 호환되는지 확인하는 호환성 검사가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="6e449-111">검사를 통과하면 `<PackageReference>` 요소가 프로젝트 파일에 추가되고 [dotnet restore](dotnet-restore.md)가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="6e449-112">예를 들어 `Newtonsoft.Json`를 *ToDo.csproj*에 추가하면 다음 예제와 유사한 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

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

<span data-ttu-id="6e449-113">이제 *ToDo.csproj* 파일에 참조되는 패키지에 대한 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="6e449-114">인수</span><span class="sxs-lookup"><span data-stu-id="6e449-114">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="6e449-115">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-115">Specifies the project file.</span></span> <span data-ttu-id="6e449-116">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-116">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="6e449-117">추가할 패키지 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="6e449-118">옵션</span><span class="sxs-lookup"><span data-stu-id="6e449-118">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6e449-119">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 패키지 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="6e449-120">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="6e449-121">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="6e449-121">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="6e449-122">.NET Core 2.1 SDK 버전 2.1.400 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="6e449-123">복원 미리 보기 및 호환성 검사를 수행하지 않고 패키지 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="6e449-124">패키지를 복원할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-124">The directory where to restore the packages.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="6e449-125">복원 작업 중에 사용할 NuGet 패키지 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-125">The NuGet package source to use during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="6e449-126">패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-126">Version of the package.</span></span> <span data-ttu-id="6e449-127">[NuGet 패키지 버전 관리](https://docs.microsoft.com/nuget/reference/package-versioning)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e449-127">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="6e449-128">예제</span><span class="sxs-lookup"><span data-stu-id="6e449-128">Examples</span></span>

* <span data-ttu-id="6e449-129">`Newtonsoft.Json` NuGet 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-129">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="6e449-130">특정 버전의 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-130">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="6e449-131">특정 NuGet 소스를 사용하여 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e449-131">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```
