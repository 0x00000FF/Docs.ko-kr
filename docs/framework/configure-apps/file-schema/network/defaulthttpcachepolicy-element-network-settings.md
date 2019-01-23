---
title: '&lt;defaultHttpCachePolicy&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 8b71942380b750cd654c2d4c248bf5c93d82112e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555095"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="50eec-102">&lt;defaultHttpCachePolicy&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="50eec-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="50eec-103">HTTP 캐싱을 활성화 되어 있는지 여부를 나타내고 기본 캐싱 정책은 설명 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="50eec-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="50eec-104">\<configuration></span></span>  
<span data-ttu-id="50eec-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="50eec-105">\<system.net></span></span>  
<span data-ttu-id="50eec-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="50eec-106">\<requestCaching></span></span>  
<span data-ttu-id="50eec-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="50eec-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50eec-108">구문</span><span class="sxs-lookup"><span data-stu-id="50eec-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50eec-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="50eec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="50eec-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50eec-111">특성</span><span class="sxs-lookup"><span data-stu-id="50eec-111">Attributes</span></span>  
  
|<span data-ttu-id="50eec-112">특성</span><span class="sxs-lookup"><span data-stu-id="50eec-112">Attribute</span></span>|<span data-ttu-id="50eec-113">설명</span><span class="sxs-lookup"><span data-stu-id="50eec-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="50eec-114">캐시 된 개체는 만료 됨으로 표시 되기 전까지 최대 시간 간격을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="50eec-115">캐시 된 개체는 만료 됨으로 표시 되기 전까지 계산 된 새로 고침 이후의 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="50eec-116">새 것으로 간주 하는 캐시 된 개체에 대 한 최소 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="50eec-117">캐싱 정책을 자동으로 인지 또는 캐시를 바이패스 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="50eec-118">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50eec-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="50eec-119">Child Elements</span></span>  
 <span data-ttu-id="50eec-120">없음</span><span class="sxs-lookup"><span data-stu-id="50eec-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50eec-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="50eec-121">Parent Elements</span></span>  
  
|<span data-ttu-id="50eec-122">요소</span><span class="sxs-lookup"><span data-stu-id="50eec-122">Element</span></span>|<span data-ttu-id="50eec-123">설명</span><span class="sxs-lookup"><span data-stu-id="50eec-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50eec-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="50eec-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="50eec-125">네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50eec-126">설명</span><span class="sxs-lookup"><span data-stu-id="50eec-126">Remarks</span></span>  
 <span data-ttu-id="50eec-127">에 대 한 값을 `policyLevel` 특성은 `BypassCache` 또는 `Default`합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="50eec-128">에 대 한 값을 `maximumAge`, `maximumStale`, 및 `minimumFresh` 요소가 형식의 명시적 시간 간격 *d*. *hh*:*mm*:*ss* (일, 시간, 분 및 초) 또는 상수 `minValue` 또는 `maxValue`를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="50eec-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="50eec-129">Configuration Files</span></span>  
 <span data-ttu-id="50eec-130">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50eec-131">예제</span><span class="sxs-lookup"><span data-stu-id="50eec-131">Example</span></span>  
 <span data-ttu-id="50eec-132">다음 예제에서는 6 시간, 2 일의 최대 사용 기간 및 최대 부실 시간의 4 시간 최소 새로 고침 시간을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50eec-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50eec-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="50eec-133">See also</span></span>
- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="50eec-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="50eec-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
