---
title: dotnet nuget delete 명령
description: dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 70316a0baa2cf9923738a53af561b5c77014c3ff
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202577"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="117c8-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="117c8-103">dotnet nuget delete</span></span>

<span data-ttu-id="117c8-104">**이 항목 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="117c8-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="117c8-105">name</span><span class="sxs-lookup"><span data-stu-id="117c8-105">Name</span></span>

<span data-ttu-id="117c8-106">`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="117c8-107">개요</span><span class="sxs-lookup"><span data-stu-id="117c8-107">Synopsis</span></span>

```console
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="117c8-108">설명</span><span class="sxs-lookup"><span data-stu-id="117c8-108">Description</span></span>

<span data-ttu-id="117c8-109">`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="117c8-110">[nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="117c8-111">인수</span><span class="sxs-lookup"><span data-stu-id="117c8-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="117c8-112">삭제할 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="117c8-113">삭제할 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="117c8-114">옵션</span><span class="sxs-lookup"><span data-stu-id="117c8-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="117c8-115">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="117c8-116">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="117c8-117">명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="117c8-118">.NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="117c8-119">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="117c8-120">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="117c8-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="117c8-121">.NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="117c8-122">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="117c8-123">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-123">Specifies the server URL.</span></span> <span data-ttu-id="117c8-124">nuget.org에 대해 지원되는 URL에는 `https://www.nuget.org`, `https://www.nuget.org/api/v3` 및 `https://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="117c8-125">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="117c8-126">예제</span><span class="sxs-lookup"><span data-stu-id="117c8-126">Examples</span></span>

* <span data-ttu-id="117c8-127">`Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="117c8-128">사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="117c8-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
