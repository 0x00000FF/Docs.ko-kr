---
title: <disableCachingBindingFailures> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c99eb6b77a969a1c5003743b0407821e2537b683
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289720"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="ac7a5-102">\<disableCachingBindingFailures> Element</span><span class="sxs-lookup"><span data-stu-id="ac7a5-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="ac7a5-103">검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 비활성화할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="ac7a5-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-104">\<configuration> Element</span></span>  
<span data-ttu-id="ac7a5-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-105">\<runtime> Element</span></span>  
<span data-ttu-id="ac7a5-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="ac7a5-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac7a5-107">구문</span><span class="sxs-lookup"><span data-stu-id="ac7a5-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac7a5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ac7a5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac7a5-110">특성</span><span class="sxs-lookup"><span data-stu-id="ac7a5-110">Attributes</span></span>  
  
|<span data-ttu-id="ac7a5-111">특성</span><span class="sxs-lookup"><span data-stu-id="ac7a5-111">Attribute</span></span>|<span data-ttu-id="ac7a5-112">설명</span><span class="sxs-lookup"><span data-stu-id="ac7a5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac7a5-113">사용</span><span class="sxs-lookup"><span data-stu-id="ac7a5-113">enabled</span></span>|<span data-ttu-id="ac7a5-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac7a5-115">검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 비활성화할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ac7a5-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ac7a5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="ac7a5-117">값</span><span class="sxs-lookup"><span data-stu-id="ac7a5-117">Value</span></span>|<span data-ttu-id="ac7a5-118">설명</span><span class="sxs-lookup"><span data-stu-id="ac7a5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ac7a5-119">0</span><span class="sxs-lookup"><span data-stu-id="ac7a5-119">0</span></span>|<span data-ttu-id="ac7a5-120">검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="ac7a5-121">이.NET Framework 버전 2.0부터 기본 바인딩 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="ac7a5-122">1</span><span class="sxs-lookup"><span data-stu-id="ac7a5-122">1</span></span>|<span data-ttu-id="ac7a5-123">검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패 캐싱을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="ac7a5-124">이 설정은.NET Framework 버전 1.1의 바인딩 동작으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac7a5-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-125">Child Elements</span></span>  
 <span data-ttu-id="ac7a5-126">없음</span><span class="sxs-lookup"><span data-stu-id="ac7a5-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac7a5-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ac7a5-128">요소</span><span class="sxs-lookup"><span data-stu-id="ac7a5-128">Element</span></span>|<span data-ttu-id="ac7a5-129">설명</span><span class="sxs-lookup"><span data-stu-id="ac7a5-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ac7a5-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ac7a5-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac7a5-132">설명</span><span class="sxs-lookup"><span data-stu-id="ac7a5-132">Remarks</span></span>  
 <span data-ttu-id="ac7a5-133">.NET Framework 버전 2.0부터 어셈블리 로드에 대 한 기본 동작 모든 바인딩 및 로드 실패를 캐시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="ac7a5-134">즉, 어셈블리를 로드 하려는 시도가 실패 하면 동일한 어셈블리를 로드 하는 후속 요청 즉시 없이 실패 어셈블리를 찾으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="ac7a5-135">이 요소는 검색 경로에서 어셈블리를 찾을 수 없습니다 때문에 발생 하는 바인딩 실패에 대 한 기본 동작을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="ac7a5-136">이러한 오류를 throw <xref:System.IO.FileNotFoundException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="ac7a5-137">일부 바인딩 및 오류를 로드 합니다.이 요소에 의해 영향을 받지 않습니다 하 고 항상 캐시 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="ac7a5-138">이러한 오류는 어셈블리를 찾았지만 로드할 수 없습니다 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="ac7a5-139">Throw <xref:System.BadImageFormatException> 또는 <xref:System.IO.FileLoadException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="ac7a5-140">다음 목록은 이러한 오류의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="ac7a5-141">로드 하려는 파일이 유효한 어셈블리가 아닙니다 경우 올바른 어셈블리를 사용 하 여 잘못 된 파일은 대체 하는 경우에 어셈블리를 로드 하는 후속 하려고 하면 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="ac7a5-142">파일 시스템에 의해 잠겨 있는 어셈블리를 로드 하려는 경우 파일 시스템에서 어셈블리를 해제 한 후에 이후에 어셈블리를 로드 하는 데 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="ac7a5-143">하나 또는 여러 버전 로드 하려고 하는 어셈블리의 검색 경로 있지만 요청 하는 특정 버전 없는 그중에서 경우 올바른 버전 검색 경로로 이동 하는 경우에 이후에 해당 버전을 로드 하는 데 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac7a5-144">예제</span><span class="sxs-lookup"><span data-stu-id="ac7a5-144">Example</span></span>  
 <span data-ttu-id="ac7a5-145">다음 예제에서는 검색 하 여 어셈블리를 찾을 수 없습니다 때문에 발생 하는 어셈블리 바인딩 실패 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac7a5-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac7a5-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac7a5-146">See also</span></span>
- [<span data-ttu-id="ac7a5-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ac7a5-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ac7a5-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ac7a5-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ac7a5-149">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="ac7a5-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
