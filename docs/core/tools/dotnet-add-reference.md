---
title: dotnet-add reference 명령 - .NET Core CLI
description: dotnet add reference 명령은 프로젝트 간 참조를 추가하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: c82696eee2fbe4bbad86e59cf5de1c2e74d048f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="7df36-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="7df36-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7df36-104">name</span><span class="sxs-lookup"><span data-stu-id="7df36-104">Name</span></span>

<span data-ttu-id="7df36-105">`dotnet add reference` - 프로젝트 간(P2P) 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7df36-106">개요</span><span class="sxs-lookup"><span data-stu-id="7df36-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="7df36-107">설명</span><span class="sxs-lookup"><span data-stu-id="7df36-107">Description</span></span>

<span data-ttu-id="7df36-108">`dotnet add reference` 명령은 프로젝트에 프로젝트 참조를 추가하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="7df36-109">명령을 실행한 후 [ `<ProjectReference>` ](/visualstudio/msbuild/common-msbuild-project-items) 요소가 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="7df36-110">인수</span><span class="sxs-lookup"><span data-stu-id="7df36-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="7df36-111">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-111">Specifies the project file.</span></span> <span data-ttu-id="7df36-112">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="7df36-113">추가할 프로젝트 간(P2P) 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="7df36-114">하나 이상의 프로젝트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-114">Specify one or more projects.</span></span> <span data-ttu-id="7df36-115">Unix/Linux 기반 시스템에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="7df36-116">옵션</span><span class="sxs-lookup"><span data-stu-id="7df36-116">Options</span></span>

`-h|--help`

<span data-ttu-id="7df36-117">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7df36-118">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="7df36-119">예제</span><span class="sxs-lookup"><span data-stu-id="7df36-119">Examples</span></span>

<span data-ttu-id="7df36-120">프로젝트 참조 추가:</span><span class="sxs-lookup"><span data-stu-id="7df36-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="7df36-121">현재 디렉터리의 프로젝트에 여러 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7df36-121">Add multiple project references to the project in the current directory:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="7df36-122">Linux/Unix에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조 추가:</span><span class="sxs-lookup"><span data-stu-id="7df36-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
