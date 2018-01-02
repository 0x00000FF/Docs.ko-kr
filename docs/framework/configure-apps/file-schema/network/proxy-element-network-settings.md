---
title: "&lt;프록시&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b0b397e66e0f73d10f482bc9151a6fbacf3e774d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="2e989-102">&lt;프록시&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="2e989-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2e989-103">프록시 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="2e989-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2e989-104">\<configuration></span></span>  
<span data-ttu-id="2e989-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="2e989-105">\<system.net></span></span>  
<span data-ttu-id="2e989-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="2e989-106">\<defaultProxy></span></span>  
<span data-ttu-id="2e989-107">\<프록시 ></span><span class="sxs-lookup"><span data-stu-id="2e989-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e989-108">구문</span><span class="sxs-lookup"><span data-stu-id="2e989-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e989-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2e989-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e989-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e989-111">특성</span><span class="sxs-lookup"><span data-stu-id="2e989-111">Attributes</span></span>  
  
|<span data-ttu-id="2e989-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="2e989-112">**Attribute**</span></span>|<span data-ttu-id="2e989-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="2e989-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="2e989-114">프록시를 자동으로 검색할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="2e989-115">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="2e989-116">로컬 리소스에 대 한 프록시를 바이패스 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="2e989-117">로컬 리소스는 로컬 서버 (http://localhost, http://loopback, 또는 http://127.0.0.1) 및 마침표 (http://webserver) 없이 URI를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="2e989-118">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="2e989-119">프록시 사용 하는 URI를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="2e989-120">구성 스크립트의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="2e989-121">Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="2e989-122">경우 설정 `true`, 후속 특성에는 Internet Explorer 프록시 설정은 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="2e989-123">기본값은 `unspecified`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e989-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2e989-124">Child Elements</span></span>  
 <span data-ttu-id="2e989-125">없음</span><span class="sxs-lookup"><span data-stu-id="2e989-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e989-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2e989-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2e989-127">**요소**</span><span class="sxs-lookup"><span data-stu-id="2e989-127">**Element**</span></span>|<span data-ttu-id="2e989-128">**설명**</span><span class="sxs-lookup"><span data-stu-id="2e989-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2e989-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2e989-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="2e989-130">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="2e989-131">텍스트 값</span><span class="sxs-lookup"><span data-stu-id="2e989-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e989-132">설명</span><span class="sxs-lookup"><span data-stu-id="2e989-132">Remarks</span></span>  
 <span data-ttu-id="2e989-133">`proxy` 요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="2e989-134">이 요소는 구성 파일에서 누락,.NET Framework Internet Explorer에서 프록시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2e989-135">에 대 한 값은 `proxyaddress` 특성에는 올바른 형식의 표시기 URI (Uniform Resource) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="2e989-136">`scriptLocation` 특성이 프록시 구성 스크립트의 자동 검색을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="2e989-137"><xref:System.Net.WebProxy> 클래스는 구성 스크립트 (일반적으로 명명 된 Wpad.dat) 경우 찾으려고 시도 **자동 구성 스크립트를 사용 하 여** Internet Explorer에서 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2e989-138">사용 하 여 `usesystemdefault` 버전 2.0으로 마이그레이션하는.NET Framework 버전 1.1 응용 프로그램에 대 한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="2e989-139">예외가 발생 하는 경우는 `proxyaddress` 특성 잘못 된 기본 프록시를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="2e989-140">예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2e989-141">구성 파일</span><span class="sxs-lookup"><span data-stu-id="2e989-141">Configuration Files</span></span>  
 <span data-ttu-id="2e989-142">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e989-143">예</span><span class="sxs-lookup"><span data-stu-id="2e989-143">Example</span></span>  
 <span data-ttu-id="2e989-144">다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 여, 프록시 주소를 지정 및 로컬 액세스에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e989-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e989-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e989-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="2e989-146">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2e989-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
