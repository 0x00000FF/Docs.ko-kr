---
title: <appDomainResourceMonitoring> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154378"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="d2998-102">\<앱도메인리소스 모니터링> 요소</span><span class="sxs-lookup"><span data-stu-id="d2998-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="d2998-103">프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="d2998-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2998-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2998-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2998-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d2998-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<앱도메인리소스 모니터링>**</span><span class="sxs-lookup"><span data-stu-id="d2998-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2998-107">구문</span><span class="sxs-lookup"><span data-stu-id="d2998-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2998-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2998-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d2998-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2998-110">특성</span><span class="sxs-lookup"><span data-stu-id="d2998-110">Attributes</span></span>  
  
|<span data-ttu-id="d2998-111">attribute</span><span class="sxs-lookup"><span data-stu-id="d2998-111">Attribute</span></span>|<span data-ttu-id="d2998-112">Description</span><span class="sxs-lookup"><span data-stu-id="d2998-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d2998-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d2998-114">런타임이 응용 프로그램 도메인 리소스 모니터링에 대한 통계를 수집하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d2998-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="d2998-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d2998-116">값</span><span class="sxs-lookup"><span data-stu-id="d2998-116">Value</span></span>|<span data-ttu-id="d2998-117">Description</span><span class="sxs-lookup"><span data-stu-id="d2998-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="d2998-118">응용 프로그램 도메인 리소스 모니터링에 대한 통계가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="d2998-119">응용 프로그램 도메인 리소스 모니터링에 대한 통계는 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2998-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2998-120">Child Elements</span></span>  
 <span data-ttu-id="d2998-121">없음</span><span class="sxs-lookup"><span data-stu-id="d2998-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2998-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2998-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d2998-123">요소</span><span class="sxs-lookup"><span data-stu-id="d2998-123">Element</span></span>|<span data-ttu-id="d2998-124">Description</span><span class="sxs-lookup"><span data-stu-id="d2998-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d2998-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d2998-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2998-127">설명</span><span class="sxs-lookup"><span data-stu-id="d2998-127">Remarks</span></span>  
 <span data-ttu-id="d2998-128">응용 프로그램 도메인 리소스 모니터링은 관리되는 응용 프로그램 도메인 클래스, 호스팅 [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 WINDOWS용 이벤트 추적(ETW)을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="d2998-129">모니터링을 사용하도록 설정하면 프로세스의 수명 동안 프로세스의 모든 응용 프로그램 도메인에 대한 통계가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="d2998-130">관리 코드에서 모니터링을 사용하려면 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="d2998-131">이 구성 요소는 .NET Framework 4 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2998-132">예제</span><span class="sxs-lookup"><span data-stu-id="d2998-132">Example</span></span>  
 <span data-ttu-id="d2998-133">다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용하도록 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2998-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2998-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2998-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d2998-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d2998-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d2998-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d2998-136">Configuration File Schema</span></span>](../index.md)
