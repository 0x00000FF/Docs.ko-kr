---
title: <appDomainResourceMonitoring> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1395ee64d94e33693344b678c7a949665f994079
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252818"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="0de87-102">\<appDomainResourceMonitoring > 요소</span><span class="sxs-lookup"><span data-stu-id="0de87-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="0de87-103">프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="0de87-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0de87-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0de87-105">&nbsp;&nbsp;[ **\<런타임 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0de87-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0de87-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainResourceMonitoring>**</span><span class="sxs-lookup"><span data-stu-id="0de87-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de87-107">구문</span><span class="sxs-lookup"><span data-stu-id="0de87-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0de87-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0de87-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0de87-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0de87-110">특성</span><span class="sxs-lookup"><span data-stu-id="0de87-110">Attributes</span></span>  
  
|<span data-ttu-id="0de87-111">특성</span><span class="sxs-lookup"><span data-stu-id="0de87-111">Attribute</span></span>|<span data-ttu-id="0de87-112">설명</span><span class="sxs-lookup"><span data-stu-id="0de87-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0de87-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0de87-114">런타임이 응용 프로그램 도메인 리소스 모니터링에 대 한 통계를 수집 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0de87-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="0de87-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0de87-116">값</span><span class="sxs-lookup"><span data-stu-id="0de87-116">Value</span></span>|<span data-ttu-id="0de87-117">설명</span><span class="sxs-lookup"><span data-stu-id="0de87-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="0de87-118">응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="0de87-119">응용 프로그램 도메인 리소스 모니터링에 대 한 통계는 수집 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0de87-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0de87-120">Child Elements</span></span>  
 <span data-ttu-id="0de87-121">없음</span><span class="sxs-lookup"><span data-stu-id="0de87-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0de87-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0de87-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0de87-123">요소</span><span class="sxs-lookup"><span data-stu-id="0de87-123">Element</span></span>|<span data-ttu-id="0de87-124">설명</span><span class="sxs-lookup"><span data-stu-id="0de87-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0de87-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0de87-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0de87-127">설명</span><span class="sxs-lookup"><span data-stu-id="0de87-127">Remarks</span></span>  
 <span data-ttu-id="0de87-128">응용 프로그램 도메인 리소스 모니터링은 관리 되는 응용 프로그램 도메인 클래스, 호스팅 [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 ETW (Windows 용 이벤트 추적)를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="0de87-129">모니터링을 사용 하는 경우 프로세스의 수명 동안 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="0de87-130">관리 코드에서 모니터링을 사용 하도록 설정 하려면 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="0de87-131">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de87-132">예제</span><span class="sxs-lookup"><span data-stu-id="0de87-132">Example</span></span>  
 <span data-ttu-id="0de87-133">다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0de87-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0de87-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="0de87-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0de87-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0de87-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0de87-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0de87-136">Configuration File Schema</span></span>](../index.md)
