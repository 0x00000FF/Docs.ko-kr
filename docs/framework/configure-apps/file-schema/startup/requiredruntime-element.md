---
title: '&lt;requiredRuntime&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 66de3e30ce862cd317e80ea267bf22ce728aca82
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222131"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="78bea-102">&lt;requiredRuntime&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="78bea-102">&lt;requiredRuntime&gt; element</span></span>

<span data-ttu-id="78bea-103">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="78bea-104">이 요소는 사용 되지 않으며 더 이상 사용 되지 않음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="78bea-105">합니다 [ `supportedRuntime` ](supportedruntime-element.md) 요소를 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="78bea-106">\<구성 > \<시작 > \<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="78bea-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="78bea-107">구문</span><span class="sxs-lookup"><span data-stu-id="78bea-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78bea-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78bea-108">Attributes and elements</span></span>

<span data-ttu-id="78bea-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="78bea-110">특성</span><span class="sxs-lookup"><span data-stu-id="78bea-110">Attributes</span></span>

|<span data-ttu-id="78bea-111">특성</span><span class="sxs-lookup"><span data-stu-id="78bea-111">Attribute</span></span>|<span data-ttu-id="78bea-112">설명</span><span class="sxs-lookup"><span data-stu-id="78bea-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="78bea-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="78bea-114">이 응용 프로그램이 지 원하는.NET Framework의 버전을 지정 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="78bea-115">문자열 값에는.NET Framework 설치 루트 아래의 있는 디렉터리 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="78bea-116">문자열 값의 내용은 구문 분석 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="78bea-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="78bea-118">런타임 시작 코드가 런타임 버전을 확인 하려면 레지스트리를 검색 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="78bea-119">안전 모드 특성</span><span class="sxs-lookup"><span data-stu-id="78bea-119">safemode attribute</span></span>

|<span data-ttu-id="78bea-120">값</span><span class="sxs-lookup"><span data-stu-id="78bea-120">Value</span></span>|<span data-ttu-id="78bea-121">설명</span><span class="sxs-lookup"><span data-stu-id="78bea-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="78bea-122">레지스트리는 런타임 시작 코드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="78bea-123">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="78bea-124">레지스트리에서 런타임 시작 코드를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="78bea-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78bea-125">Child elements</span></span>

<span data-ttu-id="78bea-126">없음</span><span class="sxs-lookup"><span data-stu-id="78bea-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78bea-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78bea-127">Parent elements</span></span>

|<span data-ttu-id="78bea-128">요소</span><span class="sxs-lookup"><span data-stu-id="78bea-128">Element</span></span>|<span data-ttu-id="78bea-129">설명</span><span class="sxs-lookup"><span data-stu-id="78bea-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="78bea-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="78bea-131">포함 된 `<requiredRuntime>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78bea-132">설명</span><span class="sxs-lookup"><span data-stu-id="78bea-132">Remarks</span></span>
 <span data-ttu-id="78bea-133">런타임이 버전 1.0만을 지원 하도록 빌드된 응용 프로그램을 사용 해야 합니다는 `<requiredRuntime>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="78bea-134">런타임의 1.1 이상 버전을 사용 하 여 빌드된 응용 프로그램을 사용 해야 합니다는 `<supportedRuntime>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="78bea-135">사용 하는 경우는 [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 구성 파일을 지정 하려면 함수를 사용 해야 합니다는 `<requiredRuntime>` 런타임의 모든 버전에 대 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="78bea-136">합니다 `<supportedRuntime>` 사용 하는 경우 요소는 무시 됩니다 [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="78bea-137">`version` 특성 문자열에 지정된 된 버전의.NET Framework에 대 한 설치 폴더 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="78bea-138">이 문자열 해석 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-138">This string is not interpreted.</span></span> <span data-ttu-id="78bea-139">런타임 시작 코드에서 일치 하는 폴더를 찾지 못하면 런타임이 로드 되지 않습니다. 시작 코드는 오류 메시지를 표시 하 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="78bea-140">Microsoft Internet Explorer에서 호스팅되는 응용 프로그램 시작 코드를 무시 합니다 `<requiredRuntime>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="78bea-141">예제</span><span class="sxs-lookup"><span data-stu-id="78bea-141">Example</span></span>

<span data-ttu-id="78bea-142">다음 예제에서는 구성 파일에서 런타임 버전을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78bea-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="78bea-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="78bea-143">See also</span></span>

- [<span data-ttu-id="78bea-144">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="78bea-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="78bea-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="78bea-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="78bea-146">방법: .NET Framework 4 또는 이상 버전을 지원 하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="78bea-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)