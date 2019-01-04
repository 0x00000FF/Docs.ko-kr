---
title: dotnet nuget push 명령
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 4f0d127d8b9f37b1c381d8981f54035a2fc3b0e5
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169354"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="4fc2d-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4fc2d-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4fc2d-104">name</span><span class="sxs-lookup"><span data-stu-id="4fc2d-104">Name</span></span>

<span data-ttu-id="4fc2d-105">`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4fc2d-106">개요</span><span class="sxs-lookup"><span data-stu-id="4fc2d-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4fc2d-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4fc2d-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4fc2d-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4fc2d-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="4fc2d-109">설명</span><span class="sxs-lookup"><span data-stu-id="4fc2d-109">Description</span></span>

<span data-ttu-id="4fc2d-110">`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="4fc2d-111">push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="4fc2d-112">구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="4fc2d-113">NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="4fc2d-114">인수</span><span class="sxs-lookup"><span data-stu-id="4fc2d-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="4fc2d-115">푸시되는 패키지에 대한 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="4fc2d-116">옵션</span><span class="sxs-lookup"><span data-stu-id="4fc2d-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4fc2d-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4fc2d-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="4fc2d-118">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="4fc2d-119">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="4fc2d-120">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="4fc2d-121">명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="4fc2d-122">.NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4fc2d-123">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="4fc2d-124">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="4fc2d-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="4fc2d-125">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="4fc2d-126">.NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4fc2d-127">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-127">Specifies the server URL.</span></span> <span data-ttu-id="4fc2d-128">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="4fc2d-129">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="4fc2d-130">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="4fc2d-131">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="4fc2d-132">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="4fc2d-133">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4fc2d-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4fc2d-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="4fc2d-135">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="4fc2d-136">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4fc2d-137">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4fc2d-138">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="4fc2d-139">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="4fc2d-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4fc2d-140">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-140">Specifies the server URL.</span></span> <span data-ttu-id="4fc2d-141">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="4fc2d-142">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="4fc2d-143">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="4fc2d-144">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="4fc2d-145">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="4fc2d-146">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4fc2d-147">예제</span><span class="sxs-lookup"><span data-stu-id="4fc2d-147">Examples</span></span>

* <span data-ttu-id="4fc2d-148">기본 푸시 소스에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="4fc2d-149">사용자 지정 푸시 소스 `https://customsource`에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="4fc2d-150">기본 푸시 소스 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="4fc2d-151">기본 기호 소스에 *foo.symbols.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="4fc2d-152">360초 시간 제한을 지정하여 기본 푸시 소스에 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="4fc2d-153">기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```