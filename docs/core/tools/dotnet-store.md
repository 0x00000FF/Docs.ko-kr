---
title: "dotnet store 명령"
description: "'dotnet store' 명령은 지정된 어셈블리를 런타임 패키지 저장소에 저장합니다."
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: fcf1eeba0709e05cff124bc3ae7bb93f4ca57128
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-store"></a><span data-ttu-id="14801-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="14801-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="14801-104">이름</span><span class="sxs-lookup"><span data-stu-id="14801-104">Name</span></span>

<span data-ttu-id="14801-105">`dotnet store` - 지정된 어셈블리를 [런타임 패키지 저장소](../deploying/runtime-store.md)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="14801-106">개요</span><span class="sxs-lookup"><span data-stu-id="14801-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="14801-107">설명</span><span class="sxs-lookup"><span data-stu-id="14801-107">Description</span></span>

<span data-ttu-id="14801-108">`dotnet store`는 지정된 어셈블리를 [런타임 패키지 저장소](../deploying/runtime-store.md)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="14801-109">기본적으로 어셈블리는 대상 런타임 및 프레임워크에 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="14801-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="14801-110">자세한 내용은 [런타임 패키지 저장소](../deploying/runtime-store.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14801-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="14801-111">필수 옵션</span><span class="sxs-lookup"><span data-stu-id="14801-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="14801-112">[대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="14801-113">*패키지 저장소 매니페스트 파일*은 저장할 패키지 목록이 포함된 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="14801-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="14801-114">매니페스트 파일 형식은 *csproj* 형식과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="14801-114">The format of the manifest file is compatible with the *csproj* format.</span></span> <span data-ttu-id="14801-115">따라서 원하는 패키지를 참조하는 *csproj* 프로젝트 파일을 `-m|--manifest` 옵션과 함께 사용하여 런타임 패키지 저장소에 어셈블리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14801-115">So, a *csproj* project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="14801-116">여러 매니페스트 파일을 지정하려면 각 파일에 대해 옵션 및 경로를 반복합니다. `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="14801-116">To specify multiple manifest files, repeat the option and path for each file: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="14801-117">대상으로 지정할 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="14801-117">The runtime identifier to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="14801-118">선택적 옵션</span><span class="sxs-lookup"><span data-stu-id="14801-118">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="14801-119">.NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-119">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="14801-120">이 옵션을 사용하여 `-f|--framework` 옵션을 통해 지정된 프레임워크가 아닌 특정 프레임워크 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14801-120">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="14801-121">도움말 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-121">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="14801-122">런타임 패키지 저장소의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-122">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="14801-123">지정하지 않으면 기본적으로 사용자 프로필 .NET Core 설치 디렉터리의 *store* 하위 디렉터리가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14801-123">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="14801-124">최적화 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="14801-124">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="14801-125">기호 생성을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="14801-125">Skips symbol generation.</span></span> <span data-ttu-id="14801-126">현재 Windows 및 Linux에서만 기호를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-126">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="14801-127">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14801-128">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="14801-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="14801-129">명령에서 사용되는 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="14801-129">The working directory used by the command.</span></span> <span data-ttu-id="14801-130">지정하지 않으면 현재 디렉터리의 *obj* 하위 디렉터리가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14801-130">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="14801-131">예제</span><span class="sxs-lookup"><span data-stu-id="14801-131">Examples</span></span>

<span data-ttu-id="14801-132">지정된 패키지를 .NET Core 2.0.0에 대한 *packages.csproj* 프로젝트 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-132">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="14801-133">지정된 패키지를 최적화 없이 *packages.csproj*에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14801-133">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="14801-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14801-134">See also</span></span>

[<span data-ttu-id="14801-135">런타임 패키지 저장소</span><span class="sxs-lookup"><span data-stu-id="14801-135">Runtime package store</span></span>](../deploying/runtime-store.md)   
