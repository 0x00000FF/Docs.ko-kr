---
title: .NET Core RID(런타임 식별자) 카탈로그
description: RID(런타임 식별자) 및 .NET Core에서 RID의 사용 방법에 관해 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 42707d96744ff765c2ea6ae2298da3e8b27f912f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="d31cb-103">.NET Core RID 카탈로그</span><span class="sxs-lookup"><span data-stu-id="d31cb-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="d31cb-104">RID는 *Runtime IDentifier(런타임 식별자)* 의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="d31cb-105">RID 값은 응용 프로그램을 실행하는 대상 플랫폼을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="d31cb-106">NuGet 패키지에서 .NET 패키지의 플랫폼 관련 자산을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="d31cb-107">RID 값의 예로 `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, `osx.10.12-x64` 등을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="d31cb-108">기본 종속성이 있는 패키지의 경우 RID는 패키지를 복원할 수 있는 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="d31cb-109">단일 RID는 프로젝트 파일의 `<RuntimeIdentifier>` 요소에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="d31cb-110">여러 RID는 프로젝트 파일의 `<RuntimeIdentifiers>` 요소에서 세미콜론으로 구분된 목록으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="d31cb-111">다음과 같은 [.NET Core CLI 명령](./tools/index.md)을 사용하여 `--runtime` 옵션을 통해서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="d31cb-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="d31cb-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="d31cb-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="d31cb-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="d31cb-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="d31cb-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="d31cb-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="d31cb-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="d31cb-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="d31cb-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="d31cb-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="d31cb-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="d31cb-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="d31cb-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="d31cb-119">구체적인 운영 체제를 나타내는 RID는 일반적으로 `[os].[version]-[architecture]-[additional qualifiers]`의 패턴을 따릅니다. 각각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="d31cb-120">`[os]` - 운영 체제/플랫폼 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="d31cb-121">예를 들어, `ubuntu`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="d31cb-122">`[version]` - 점으로 구분된(`.`) 버전 번호 형식의 운영 체제 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="d31cb-123">예를 들어, `15.10`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="d31cb-124">버전은 마케팅 버전이어서는 **안 됩니다**. 마케팅 버전은 종종 다양한 플랫폼 API 노출 영역이 있는 운영 체제의 여러 개별 버전을 나타내기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="d31cb-125">`[architecture]` - 프로세서 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="d31cb-126">예를 들면 `x86`, `x64`, `arm`, `arm64` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="d31cb-127">`[additional qualifiers]` - 다른 플랫폼을 추가로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="d31cb-128">예를 들면 `aot` 또는 `corert` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-128">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="d31cb-129">RID 그래프</span><span class="sxs-lookup"><span data-stu-id="d31cb-129">RID graph</span></span>

<span data-ttu-id="d31cb-130">RID 그래프 또는 런타임 Fallback 그래프는 서로 호환되는 RID 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="d31cb-131">RID는 [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 패키지에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="d31cb-132">지원되는 RID 및 RID 그래프 목록은 CoreFX 리포지토리에 있는 [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="d31cb-133">이 파일에서 기본 RID를 제외하고 모든 RID에 `"#import"` 문이 포함되어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="d31cb-134">이러한 문은 호환되는 RID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="d31cb-135">NuGet에서 패키지를 복원할 때 지정된 런타임에 대한 정확한 일치를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="d31cb-136">정확한 일치를 찾을 수 없는 경우 NuGet은 RID 그래프에 따라 가장 가까운 호환 시스템을 찾을 때까지 그래프를 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="d31cb-137">다음 예제는 `osx.10.12-x64` RID의 실제 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="d31cb-138">위의 RID는 `osx.10.12-x64`가 `osx.10.11-x64`를 가져오도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="d31cb-139">따라서 NuGet에서 패키지를 복원할 때 패키지에서 `osx.10.12-x64`와 정확히 일치하는 값을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="d31cb-140">NuGet이 특정 런타임을 찾을 수 없는 경우 예를 들어 `osx.10.11-x64` 런타임을 지정하는 패키지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="d31cb-141">다음 예제에서는 마찬가지로 *runtime.json* 파일에 정의된 약간 더 큰 RID 그래프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="d31cb-142">모든 RID는 결국 루트 `any` RID에 다시 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="d31cb-143">RID를 사용할 때는 RID에 대한 다음과 같은 몇 가지 고려 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="d31cb-144">RID는 **불투명 문자열**이며 블랙 박스로 취급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="d31cb-145">RID를 프로그래밍 방식으로 빌드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="d31cb-146">플랫폼에 대해 이미 정의된 RID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="d31cb-147">RID는 구체적이어야 하므로 실제 RID 값에서 어느 것도 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="d31cb-148">RID 사용</span><span class="sxs-lookup"><span data-stu-id="d31cb-148">Using RIDs</span></span>

<span data-ttu-id="d31cb-149">RID를 사용할 수 있으려면 어떤 RID가 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="d31cb-150">새 값이 플랫폼에 정기적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="d31cb-151">최신의 완전한 버전을 보려면 CoreFX 리포지토리에서 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="d31cb-152">.NET Core 2.0 SDK에서는 이식 가능 RID라는 개념을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="d31cb-153">이식 가능 RID란 RID 그래프에 추가된 새 값인데 아직 특정 버전 또는 OS 배포에 연결되지 않은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="d31cb-154">이 값은 여러 Linux 배포를 다룰 때 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-154">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="d31cb-155">다음 목록에서는 각 OS에 사용되는 일반적인 RID를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-155">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="d31cb-156">`arm` 또는 `corert` 값은 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-156">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="d31cb-157">Windows RID</span><span class="sxs-lookup"><span data-stu-id="d31cb-157">Windows RIDs</span></span>

- <span data-ttu-id="d31cb-158">이식 가능</span><span class="sxs-lookup"><span data-stu-id="d31cb-158">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="d31cb-159">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d31cb-159">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="d31cb-160">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d31cb-160">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="d31cb-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d31cb-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="d31cb-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d31cb-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="d31cb-163">자세한 내용은 [Windows에서 .NET Core의 필수 구성 요소](windows-prerequisites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="d31cb-164">Linux RID</span><span class="sxs-lookup"><span data-stu-id="d31cb-164">Linux RIDs</span></span>

- <span data-ttu-id="d31cb-165">이식 가능</span><span class="sxs-lookup"><span data-stu-id="d31cb-165">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="d31cb-166">CentOS</span><span class="sxs-lookup"><span data-stu-id="d31cb-166">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="d31cb-167">Debian</span><span class="sxs-lookup"><span data-stu-id="d31cb-167">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="d31cb-168">Fedora</span><span class="sxs-lookup"><span data-stu-id="d31cb-168">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="d31cb-169">`fedora.25-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-169">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="d31cb-170">`fedora.26-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-170">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="d31cb-171">Gentoo(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-171">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="d31cb-172">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d31cb-172">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="d31cb-173">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d31cb-173">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="d31cb-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d31cb-174">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="d31cb-175">`rhel.6-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="d31cb-176">`rhel.7.3-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-176">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="d31cb-177">`rhel.7.4-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-177">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="d31cb-178">Tizen(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-178">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="d31cb-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d31cb-179">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="d31cb-180">Ubuntu 파생 제품</span><span class="sxs-lookup"><span data-stu-id="d31cb-180">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="d31cb-181">`linuxmint.18.1-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-181">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="d31cb-182">자세한 내용은 [Linux에서 .NET Core의 필수 구성 요소](linux-prerequisites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-182">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="d31cb-183">macOS RID</span><span class="sxs-lookup"><span data-stu-id="d31cb-183">macOS RIDs</span></span>

<span data-ttu-id="d31cb-184">macOS RID는 이전 "OSX" 브랜딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d31cb-184">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="d31cb-185">`osx-x64`(.NET Core 2.0 이상 버전, 최소 버전은 `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="d31cb-185">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="d31cb-186">`osx.10.12-x64`(.NET Core 1.1 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-186">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="d31cb-187">자세한 내용은 [macOS에서 .NET Core의 필수 구성 요소](macos-prerequisites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d31cb-187">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="d31cb-188">Android RID(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="d31cb-188">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="d31cb-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d31cb-189">See also</span></span>

[<span data-ttu-id="d31cb-190">런타임 ID</span><span class="sxs-lookup"><span data-stu-id="d31cb-190">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
