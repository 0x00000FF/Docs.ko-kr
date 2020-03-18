---
title: 런타임 패키지 저장소
description: 런타임 패키지 저장소를 사용하여 .NET Core에서 사용되는 매니페스트를 대상으로 지정하는 방법을 알아봅니다.
ms.date: 08/12/2017
ms.openlocfilehash: 7a833ed95147608c6fb403f8f0dec179d2a73833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77448960"
---
# <a name="runtime-package-store"></a><span data-ttu-id="9d09e-103">런타임 패키지 저장소</span><span class="sxs-lookup"><span data-stu-id="9d09e-103">Runtime package store</span></span>

<span data-ttu-id="9d09e-104">.NET Core 2.0부터는 대상 환경의 알려진 패키지 집합을 대상으로 앱을 패키지하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="9d09e-105">경우에 따라 더 빠르게 배포하고, 디스크 공간을 더 적게 사용하고, 시작 성능이 향상되는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-105">The benefits are faster deployments, lower disk space usage, and improved startup performance in some cases.</span></span>

<span data-ttu-id="9d09e-106">이 기능은 패키지가 저장된 디스크의 디렉터리(일반적으로 macOS/Linux의 */usr/local/share/dotnet/store* 및 Windows의 *C:/Program Files/dotnet/store*)에 해당하는 *런타임 패키지 저장소*로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="9d09e-107">이 디렉터리 아래에는 아키텍처 및 [대상 프레임워크](../../standard/frameworks.md)의 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="9d09e-108">파일 레이아웃은 [NuGet 자산이 디스크에 배치](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure)되는 방식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

<span data-ttu-id="9d09e-109">*대상 매니페스트* 파일에는 런타임 패키지 저장소의 패키지가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-109">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="9d09e-110">개발자는 앱을 게시할 때 이 매니페스트를 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-110">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="9d09e-111">일반적으로 대상 프로덕션 환경의 소유자가 대상 매니페스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-111">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="9d09e-112">런타임 환경 준비</span><span class="sxs-lookup"><span data-stu-id="9d09e-112">Preparing a runtime environment</span></span>

<span data-ttu-id="9d09e-113">런타임 환경의 관리자는 런타임 패키지 저장소 및 해당하는 대상 매니페스트를 빌드하여 더 빠르게 배포하고 디스크 공간을 더 적게 사용하도록 앱을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-113">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="9d09e-114">첫 번째 단계는 런타임 패키지 저장소를 작성하는 패키지가 나열되는 *패키지 저장소 매니페스트*를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-114">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="9d09e-115">이 파일 형식은 프로젝트 파일 형식(*csproj*)과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-115">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="9d09e-116">**예제**</span><span class="sxs-lookup"><span data-stu-id="9d09e-116">**Example**</span></span>

<span data-ttu-id="9d09e-117">다음 패키지 저장소 매니페스트(*packages.csproj*) 예제는 [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) 및 [`Moq`](https://www.nuget.org/packages/moq/)를 런타임 패키지 저장소에 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-117">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="9d09e-118">패키지 저장소 매니페스트, 런타임 및 프레임워크에서 `dotnet store`를 실행하여 런타임 패키지 저장소를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-118">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="9d09e-119">**예제**</span><span class="sxs-lookup"><span data-stu-id="9d09e-119">**Example**</span></span>

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="9d09e-120">명령에서 옵션과 경로를 반복해서 단일 [`dotnet store`](../tools/dotnet-store.md) 명령에 여러 대상 패키지 저장소 매니페스트의 경로를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-120">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="9d09e-121">기본적으로 명령의 출력은 사용자 프로필의 *.dotnet/store* 하위 디렉터리 아래에 있는 패키지 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-121">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="9d09e-122">`--output <OUTPUT_DIRECTORY>` 옵션을 사용하여 다른 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-122">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="9d09e-123">저장소의 루트 디렉터리에는 대상 매니페스트 *artifact.xml* 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-123">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="9d09e-124">게시할 때 이 저장소를 대상으로 지정하고자 하는 앱 작성자가 이 파일을 다운로드하도록 제공하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-124">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="9d09e-125">**예제**</span><span class="sxs-lookup"><span data-stu-id="9d09e-125">**Example**</span></span>

<span data-ttu-id="9d09e-126">이전 예제를 실행한 후 다음 *artifact.xml* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-126">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="9d09e-127">[`Castle.Core`](https://www.nuget.org/packages/Castle.Core/)는 `Moq`의 종속성이므로 *artifacts.xml* 매니페스트 파일에 자동으로 포함되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-127">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="9d09e-128">대상 매니페스트에 앱 게시</span><span class="sxs-lookup"><span data-stu-id="9d09e-128">Publishing an app against a target manifest</span></span>

<span data-ttu-id="9d09e-129">디스크에 대상 매니페스트 파일이 있는 경우 앱을 게시할 때 [`dotnet publish`](../tools/dotnet-publish.md) 명령을 사용하여 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-129">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="9d09e-130">**예제**</span><span class="sxs-lookup"><span data-stu-id="9d09e-130">**Example**</span></span>

```dotnetcli
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="9d09e-131">대상 매니페스트에 설명된 패키지가 있는 환경에 게시된 결과 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-131">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="9d09e-132">배포하지 못하면 앱이 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-132">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="9d09e-133">앱을 게시할 때 옵션과 경로를 반복하여 여러 대상 매니페스트를 지정합니다(예: `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="9d09e-133">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="9d09e-134">이렇게 하면 명령에 제공되는 대상 매니페스트 파일에 지정된 패키지의 합집합을 기준으로 앱이 트리밍됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-134">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="9d09e-135">프로젝트 파일에서 대상 매니페스트 지정</span><span class="sxs-lookup"><span data-stu-id="9d09e-135">Specifying target manifests in the project file</span></span>

<span data-ttu-id="9d09e-136">[`dotnet publish`](../tools/dotnet-publish.md) 명령을 사용하여 대상 매니페스트를 지정하는 대신, 프로젝트 파일에서 **\<TargetManifestFiles>** 태그 아래에 세미콜론으로 구분된 경로 목록으로 대상 매니페스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-136">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="9d09e-137">.NET Core 프로젝트와 같이 앱의 대상 환경이 잘 알려진 경우에만 프로젝트 파일에서 대상 매니페스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-137">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="9d09e-138">오픈 소스 프로젝트에는 이 방법을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-138">This isn't the case for open-source projects.</span></span> <span data-ttu-id="9d09e-139">오픈 소스 프로젝트의 사용자는 일반적으로 앱을 다양한 프로덕션 환경에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-139">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="9d09e-140">이러한 프로덕션 환경에는 대개 여러 가지 패키지 집합이 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-140">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="9d09e-141">이런 환경에서는 대상 매니페스트에 대한 가정을 세울 수 없으므로 `--manifest`[`dotnet publish`의 ](../tools/dotnet-publish.md) 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-141">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="9d09e-142">ASP.NET Core 암시적 저장소</span><span class="sxs-lookup"><span data-stu-id="9d09e-142">ASP.NET Core implicit store</span></span>

<span data-ttu-id="9d09e-143">ASP.NET Core 암시적 저장소는 ASP.NET Core 2.0에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-143">The ASP.NET Core implicit store applies only to ASP.NET Core 2.0.</span></span> <span data-ttu-id="9d09e-144">암시적 저장소를 사용하지 **않는** ASP.NET Core 2.1 이상을 사용하는 애플리케이션을 강력히 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-144">We strongly recommend applications use ASP.NET Core 2.1 and later, which does **not** use the implicit store.</span></span> <span data-ttu-id="9d09e-145">ASP.NET Core 2.1 이상에서는 공유 프레임워크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-145">ASP.NET Core 2.1 and later use the shared framework.</span></span>

<span data-ttu-id="9d09e-146">런타임 패키지 저장소 기능은 앱이 [FDD(프레임워크 종속 배포)](index.md#publish-runtime-dependent) 앱으로 배포될 경우 ASP.NET Core 앱에서 암시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-146">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#publish-runtime-dependent) app.</span></span> <span data-ttu-id="9d09e-147">[`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk)의 대상에는 대상 시스템의 암시적 패키지 저장소를 참조하는 매니페스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-147">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="9d09e-148">또한 `Microsoft.AspNetCore.All` 패키지를 사용하는 FDD 앱은 앱과 자산만 포함되고 `Microsoft.AspNetCore.All` 메타패키지에 나열된 패키지가 포함되지 않은 게시된 앱이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-148">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="9d09e-149">해당 패키지는 대상 시스템에 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-149">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="9d09e-150">런타임 패키지 저장소는 .NET Core SDK가 설치될 때 호스트에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-150">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="9d09e-151">다른 설치 관리자에서는 .NET Core SDK, `apt-get`, Red Hat Yum, .NET Core Windows Server 호스팅 번들의 Zip/tarball 설치와 수동 런타임 패키지 저장소 설치를 포함한 런타임 패키지 저장소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-151">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="9d09e-152">[FDD(프레임워크 종속 배포)](index.md#publish-runtime-dependent) 앱을 배포할 경우 대상 환경에 .NET Core SDK가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-152">When deploying a [framework-dependent deployment (FDD)](index.md#publish-runtime-dependent) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="9d09e-153">ASP.NET Core가 포함되지 않은 환경에 앱을 배포할 경우 다음 예제와 같이 프로젝트 파일에서 **\<PublishWithAspNetCoreTargetManifest>** 를 `false`로 지정하여 암시적 저장소를 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-153">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="9d09e-154">[SCD(자체 포함된 배포)](index.md#publish-self-contained) 앱의 경우 대상 시스템에 필수 매니페스트 패키지가 없어도 되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-154">For [self-contained deployment (SCD)](index.md#publish-self-contained) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="9d09e-155">따라서 SCD 앱의 경우 **\<PublishWithAspNetCoreTargetManifest>** 는 `true`로 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-155">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="9d09e-156">배포에 포함되지 않은 매니페스트 종속성을 사용하여 애플리케이션을 배포할 경우(어셈블리가 *bin* 폴더에 있음) 해당 어셈블리의 호스트에서 런타임 패키지 저장소가 *사용되지 않습니다*.</span><span class="sxs-lookup"><span data-stu-id="9d09e-156">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="9d09e-157">*bin* 폴더 어셈블리는 호스트의 런타임 패키지 저장소에 어셈블리가 있는지에 관계없이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-157">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="9d09e-158">매니페스트에 지정된 종속성 버전은 런타임 패키지 저장소의 종속성 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-158">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="9d09e-159">대상 매니페스트의 종속성과 런타임 패키지 저장소에 있는 버전 간에 버전이 일치하지 않고 앱 배포에 필수 패키지 버전이 없는 경우에는 앱이 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-159">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="9d09e-160">런타임 패키지 저장소 어셈블리에 대해 호출되는 대상 매니페스트의 이름은 예외에 포함되므로 불일치 문제를 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-160">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="9d09e-161">게시할 때 배포가 *트리밍*될 경우에는 게시된 출력에서 지정한 매니페스트 패키지의 특정 버전만 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-161">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="9d09e-162">앱을 시작하려면 지정된 버전의 패키지가 호스트에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d09e-162">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d09e-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d09e-163">See also</span></span>

- [<span data-ttu-id="9d09e-164">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="9d09e-164">dotnet-publish</span></span>](../tools/dotnet-publish.md)
- [<span data-ttu-id="9d09e-165">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="9d09e-165">dotnet-store</span></span>](../tools/dotnet-store.md)
