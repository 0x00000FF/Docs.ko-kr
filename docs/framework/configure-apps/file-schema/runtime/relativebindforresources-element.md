---
title: '&lt;relativeBindForResources&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1933fad8ea87351a56fcc7dd4a4fd67e890b58f5
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613897"
---
# <a name="ltrelativebindforresourcesgt-element"></a><span data-ttu-id="e0fb1-102">&lt;relativeBindForResources&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-102">&lt;relativeBindForResources&gt; Element</span></span>
<span data-ttu-id="e0fb1-103">위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="e0fb1-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-104">\<configuration> Element</span></span>  
<span data-ttu-id="e0fb1-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-105">\<runtime> Element</span></span>  
<span data-ttu-id="e0fb1-106">\<relativeBindForResources > 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fb1-107">구문</span><span class="sxs-lookup"><span data-stu-id="e0fb1-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0fb1-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e0fb1-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0fb1-110">특성</span><span class="sxs-lookup"><span data-stu-id="e0fb1-110">Attributes</span></span>  
  
|<span data-ttu-id="e0fb1-111">특성</span><span class="sxs-lookup"><span data-stu-id="e0fb1-111">Attribute</span></span>|<span data-ttu-id="e0fb1-112">설명</span><span class="sxs-lookup"><span data-stu-id="e0fb1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e0fb1-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e0fb1-114">공용 언어 런타임은 위성 어셈블리에 대 한 프로브를 최적화 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e0fb1-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="e0fb1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e0fb1-116">값</span><span class="sxs-lookup"><span data-stu-id="e0fb1-116">Value</span></span>|<span data-ttu-id="e0fb1-117">설명</span><span class="sxs-lookup"><span data-stu-id="e0fb1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e0fb1-118">런타임은 위성 어셈블리에 대 한 프로브를 최적화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="e0fb1-119">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="e0fb1-120">런타임은 위성 어셈블리에 대 한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0fb1-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-121">Child Elements</span></span>  
 <span data-ttu-id="e0fb1-122">없음</span><span class="sxs-lookup"><span data-stu-id="e0fb1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0fb1-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e0fb1-124">요소</span><span class="sxs-lookup"><span data-stu-id="e0fb1-124">Element</span></span>|<span data-ttu-id="e0fb1-125">설명</span><span class="sxs-lookup"><span data-stu-id="e0fb1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e0fb1-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e0fb1-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0fb1-128">설명</span><span class="sxs-lookup"><span data-stu-id="e0fb1-128">Remarks</span></span>  
 <span data-ttu-id="e0fb1-129">에 설명 된 대로 Resource Manager 리소스에 대 한 프로브 일반적으로 [리소스 패키징 및 배포](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="e0fb1-130">즉, Resource Manager 리소스의 지역화 된 특정 버전에 대 한 검색을 하는 경우이 수 전역 어셈블리 캐시 확인, 위성 어셈블리를 검색할 Windows Installer 응용 프로그램의 코드 베이스를 쿼리의 문화권별 폴더에 발생 합니다 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="e0fb1-131">`<relativeBindForResources>` 요소는 Resource Manager 위성 어셈블리에 대 한 검색 하는 방식을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="e0fb1-132">다음 조건에서 리소스를 검색 하는 경우에 성능 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="e0fb1-133">경우 위성 어셈블리는 코드 어셈블리와 동일한 위치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="e0fb1-134">즉, 코드 어셈블리는 전역 어셈블리 캐시에 설치 하는 경우 위성 어셈블리를 설치 해야 합니다도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="e0fb1-135">응용 프로그램의 코드 베이스에서 코드 어셈블리가 설치 되어 있으면 위성 어셈블리를 코드 베이스의 문화권별 폴더에도 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="e0fb1-136">Windows Installer를 사용 하지 않거나 드물게 사용 되 면 요청 시 위성 어셈블리 설치에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="e0fb1-137">응용 프로그램 코드를 처리 하지 않습니다 경우는 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="e0fb1-138">설정 합니다 `enabled` 특성을 `<relativeBindForResources>` 요소를 `true` 위성 어셈블리에 대 한 다음과 같은 Resource Manager의 프로브를 최적화:</span><span class="sxs-lookup"><span data-stu-id="e0fb1-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="e0fb1-139">부모 코드 어셈블리의 위치를 사용 하 여 위성 어셈블리에 대 한 프로브.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="e0fb1-140">위성 어셈블리에 대 한 Windows Installer 쿼리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="e0fb1-141">발생 하지 않습니다는 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e0fb1-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fb1-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0fb1-142">See Also</span></span>  
- [<span data-ttu-id="e0fb1-143">리소스 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="e0fb1-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
- [<span data-ttu-id="e0fb1-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e0fb1-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="e0fb1-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e0fb1-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
