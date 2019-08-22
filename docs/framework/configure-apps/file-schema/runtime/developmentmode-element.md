---
title: <developmentMode> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7c7f866cdbcd39194d61a3db821bf973b4e057e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663814"
---
# <a name="developmentmode-element"></a><span data-ttu-id="6e3c5-102">\<developmentMode > 요소</span><span class="sxs-lookup"><span data-stu-id="6e3c5-102">\<developmentMode> Element</span></span>
<span data-ttu-id="6e3c5-103">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="6e3c5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6e3c5-104">\<configuration></span></span>  
<span data-ttu-id="6e3c5-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6e3c5-105">\<runtime></span></span>  
<span data-ttu-id="6e3c5-106">\<developmentMode></span><span class="sxs-lookup"><span data-stu-id="6e3c5-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3c5-107">구문</span><span class="sxs-lookup"><span data-stu-id="6e3c5-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e3c5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6e3c5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e3c5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e3c5-110">특성</span><span class="sxs-lookup"><span data-stu-id="6e3c5-110">Attributes</span></span>  
  
|<span data-ttu-id="6e3c5-111">특성</span><span class="sxs-lookup"><span data-stu-id="6e3c5-111">Attribute</span></span>|<span data-ttu-id="6e3c5-112">설명</span><span class="sxs-lookup"><span data-stu-id="6e3c5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e3c5-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="6e3c5-113">**developerInstallation**</span></span>|<span data-ttu-id="6e3c5-114">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="6e3c5-115">developerInstallation 특성</span><span class="sxs-lookup"><span data-stu-id="6e3c5-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="6e3c5-116">값</span><span class="sxs-lookup"><span data-stu-id="6e3c5-116">Value</span></span>|<span data-ttu-id="6e3c5-117">설명</span><span class="sxs-lookup"><span data-stu-id="6e3c5-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e3c5-118">**true**</span><span class="sxs-lookup"><span data-stu-id="6e3c5-118">**true**</span></span>|<span data-ttu-id="6e3c5-119">DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="6e3c5-120">**false**</span><span class="sxs-lookup"><span data-stu-id="6e3c5-120">**false**</span></span>|<span data-ttu-id="6e3c5-121">는 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="6e3c5-122">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e3c5-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6e3c5-123">Child Elements</span></span>  
 <span data-ttu-id="6e3c5-124">없음</span><span class="sxs-lookup"><span data-stu-id="6e3c5-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e3c5-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6e3c5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6e3c5-126">요소</span><span class="sxs-lookup"><span data-stu-id="6e3c5-126">Element</span></span>|<span data-ttu-id="6e3c5-127">설명</span><span class="sxs-lookup"><span data-stu-id="6e3c5-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e3c5-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6e3c5-129">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e3c5-130">설명</span><span class="sxs-lookup"><span data-stu-id="6e3c5-130">Remarks</span></span>  
 <span data-ttu-id="6e3c5-131">이 설정은 개발 시에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-131">Use this setting only at development time.</span></span> <span data-ttu-id="6e3c5-132">런타임은 DEVPATH에서 찾은 강력한 이름의 어셈블리에 대 한 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="6e3c5-133">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3c5-134">예제</span><span class="sxs-lookup"><span data-stu-id="6e3c5-134">Example</span></span>  
 <span data-ttu-id="6e3c5-135">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e3c5-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e3c5-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e3c5-136">See also</span></span>

- [<span data-ttu-id="6e3c5-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6e3c5-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6e3c5-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6e3c5-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6e3c5-139">방법: DEVPATH를 사용 하 여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="6e3c5-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
