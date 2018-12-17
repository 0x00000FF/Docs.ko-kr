---
title: .NET Core 런타임 및 SDK 제거
description: 이 문서에서는 현재 설치된 .NET Core 런타임 및 SDK 버전을 확인하는 방법 및 Windows, Mac 및 Linux에서 제거하는 방법을 설명합니다.
ms.date: 07/28/2018
author: billwagner
ms.author: wiwagn
ms.custom: seodec18
ms.openlocfilehash: 6204a28200f1db6350e695a9ab29502c46c25590
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129703"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="1c7dd-103">.NET Core 런타임 및 SDK를 제거하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c7dd-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="1c7dd-104">시간이 지남에 따라 .NET Core 런타임 및 SDK의 업데이트된 버전을 설치할 때 머신에서 .NET Core의 오래된 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="1c7dd-105">이전 버전의 런타임을 제거하면 [.NET Core 버전 선택](selection.md)의 문서에서 설명한 대로 공유 프레임워크 응용 프로그램을 실행하기 위해 선택한 런타임이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="1c7dd-106">버전을 제거해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="1c7dd-106">Should I remove a version?</span></span>

<span data-ttu-id="1c7dd-107">[.NET Core 버전 선택](selection.md) 동작 및 .NET Core의 런타임 호환성을 업데이트하여 이전 버전을 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="1c7dd-108">.NET Core 런타임 업데이트는 1.x 및 2.x와 같은 주 버전 '대역' 내에서 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="1c7dd-109">또한 .NET Core SDK의 최신 릴리스는 호환 가능한 방식으로 이전 버전의 런타임을 대상으로 하는 응용 프로그램을 빌드하는 기능을 일반적으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="1c7dd-110">일반적으로 응용 프로그램에 필요한 최신 SDK 및 런타임의 최신 패치 버전만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="1c7dd-111">이전 SDK 또는 런타임 버전을 유지하는 인스턴스에는 **project.json** 기반 애플리케이션 유지 관리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-111">Instances where retaining older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="1c7dd-112">응용 프로그램에 이전 SDK 또는 런타임에 대한 특정 이유가 없는 경우 이전 버전을 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="1c7dd-113">설치된 버전 확인</span><span class="sxs-lookup"><span data-stu-id="1c7dd-113">Determine what is installed</span></span>

<span data-ttu-id="1c7dd-114">.NET Core 2.1부터 .NET CLI에는 머신에 설치된 SDK 및 런타임 버전을 나열하는 데 사용할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="1c7dd-115">[`dotnet --list-sdks`](../tools/dotnet.md#options)를 사용하여 머신에 설치된 SDK의 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="1c7dd-116">[`dotnet --list-runtimes`](../tools/dotnet.md#options)을 사용하여 머신에 설치된 런타임의 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="1c7dd-117">다음 텍스트는 Windows, macOS 또는 Linux의 일반적인 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="1c7dd-118">Windows</span><span class="sxs-lookup"><span data-stu-id="1c7dd-118">Windows</span></span>](#tab/windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="1c7dd-119">Linux</span><span class="sxs-lookup"><span data-stu-id="1c7dd-119">Linux</span></span>](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="1c7dd-120">macOS</span><span class="sxs-lookup"><span data-stu-id="1c7dd-120">macOS</span></span>](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

***

## <a name="uninstalling-net-core"></a><span data-ttu-id="1c7dd-121">.NET Core 제거</span><span class="sxs-lookup"><span data-stu-id="1c7dd-121">Uninstalling .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="1c7dd-122">Windows</span><span class="sxs-lookup"><span data-stu-id="1c7dd-122">Windows</span></span>](#tab/windows)

<span data-ttu-id="1c7dd-123">.NET core는 Windows **프로그램 추가/제거** 대화 상자를 사용하여 .NET Core 런타임 및 SDK의 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-123">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="1c7dd-124">다음 그림에서는 여러 버전의 .NET 런타임 및 SDK가 설치된 **프로그램 추가/제거** 대화 상자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-124">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![.NET Core 제거를 위한 프로그램 추가/제거](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="1c7dd-126">머신에서 제거할 버전을 선택하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-126">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="1c7dd-127">Linux</span><span class="sxs-lookup"><span data-stu-id="1c7dd-127">Linux</span></span>](#tab/linux)

<span data-ttu-id="1c7dd-128">Linux에서 .NET Core(SDK 또는 런타임)를 제거하는 옵션이 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-128">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="1c7dd-129">.NET Core를 제거하는 가장 좋은 방법은 .NET Core 설치에 사용한 작업을 미러링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-129">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="1c7dd-130">세부 정보는 선택한 배포 및 설치 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-130">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c7dd-131">Red Hat 설치의 경우 .NET Core 설치 및 제거에 대한 정보는 [Red Hat 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-131">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="1c7dd-132">.NET Core 2.1부터 패키지 관리자를 사용하여 업그레이드할 때 .NET Core SDK를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-132">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="1c7dd-133">패키지 관리자 `update` 또는 `refresh` 명령은 최신 버전을 성공적으로 설치하면 이전 버전을 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-133">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="1c7dd-134">패키지 관리자를 사용하여 .NET Core를 설치한 경우 동일한 패키지 관리자를 사용하여 .NET SDK 또는 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-134">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="1c7dd-135">.NET core 설치는 가장 인기 있는 패키지 관리자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-135">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="1c7dd-136">환경의 정확한 구문은 배포의 패키지 관리자에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-136">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="1c7dd-137">[apt-get(8)](https://linux.die.net/man/8/apt-get)은 Debian 기반 시스템(Ubuntu 포함)에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="1c7dd-138">[yum(8)](https://linux.die.net/man/8/yum)은 Fedora, CentOS 및 Oracle Linux에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-138">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="1c7dd-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain))는 openSUSE 및 SLES(SUSE Linux Enterprise 시스템)에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="1c7dd-140">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html)는 Fedora에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-140">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="1c7dd-141">대부분의 경우 패키지를 제거하는 명령은 `remove`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-141">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="1c7dd-142">대부분의 패키지 관리자에 대한 .NET Core SDK 설치의 패키지 이름은 `dotnet-sdk`이며, 그 뒤에 버전 번호가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-142">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="1c7dd-143">.NET Core SDK의 버전 2.1.300 및 런타임의 버전 `2.1`부터는 주 및 부 버전 번호만 필요합니다. 예를 들어 .NET Core SDK 버전 2.1.300은 `dotnet-sdk-2.1` 패키지로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-143">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="1c7dd-144">이전 버전에는 전체 버전 문자열이 필요합니다. 예를 들어 .NET Core SDK의 버전 2.1.200에는 `dotnet-sdk-2.1.200`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-144">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="1c7dd-145">SDK가 아닌 런타임만 설치한 머신의 경우, 패키지 이름은 .NET Core 런타임의 경우에는 `dotnet-runtime-<version>`이고 전체 런타임 스택의 경우에는 `aspnetcore-runtime-<version>`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-145">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="1c7dd-146">2.0 이전의 .NET Core 설치는 패키지 관리자를 사용하여 SDK를 제거할 때 호스트 응용 프로그램을 제거하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-146">.NET Core installations prior to 2.0 did not uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="1c7dd-147">`apt-get`을 사용하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-147">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="1c7dd-148">`dotnet-host`에 연결된 버전이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-148">Note that there is no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="1c7dd-149">tarball을 사용하여 설치한 경우 수동 메서드를 사용하여 .NET Core를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-149">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="1c7dd-150">해당 버전을 포함하는 디렉터리를 제거하여 SDK와 런타임을 별도로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-150">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="1c7dd-151">예는 들어 1.0.1 SDK 및 런타임을 제거하려면 다음 bash 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-151">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="1c7dd-152">SDK 및 런타임에 대한 부모 디렉터리는 이전 표에 표시된 것처럼 `dotnet --list-sdks` 및 `dotnet --list-runtimes` 명령의 출력에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-152">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="1c7dd-153">macOS</span><span class="sxs-lookup"><span data-stu-id="1c7dd-153">macOS</span></span>](#tab/macos)

<span data-ttu-id="1c7dd-154">Mac에서는 해당 버전을 포함하는 디렉터리를 제거하여 SDK와 런타임을 별도로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-154">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="1c7dd-155">예는 들어 1.0.1 SDK 및 런타임을 제거하려면 다음 bash 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-155">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="1c7dd-156">SDK 및 런타임에 대한 부모 디렉터리는 이전 표에 표시된 것처럼 `dotnet --list-sdks` 및 `dotnet --list-runtimes` 명령의 출력에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7dd-156">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---
