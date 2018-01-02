---
title: '&lt;cookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 302ccb3d95fc982ec7950dc7808dce61b263c481
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcookiehandlergt"></a><span data-ttu-id="5af6f-102">&lt;cookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="5af6f-102">&lt;cookieHandler&gt;</span></span>
<span data-ttu-id="5af6f-103">구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 / 쓰기 쿠키를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-103">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>  
  
 <span data-ttu-id="5af6f-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="5af6f-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="5af6f-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5af6f-105">\<federationConfiguration></span></span>  
<span data-ttu-id="5af6f-106">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="5af6f-106">\<cookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af6f-107">구문</span><span class="sxs-lookup"><span data-stu-id="5af6f-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5af6f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5af6f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5af6f-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5af6f-110">특성</span><span class="sxs-lookup"><span data-stu-id="5af6f-110">Attributes</span></span>  
  
|<span data-ttu-id="5af6f-111">특성</span><span class="sxs-lookup"><span data-stu-id="5af6f-111">Attribute</span></span>|<span data-ttu-id="5af6f-112">설명</span><span class="sxs-lookup"><span data-stu-id="5af6f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5af6f-113">name</span><span class="sxs-lookup"><span data-stu-id="5af6f-113">name</span></span>|<span data-ttu-id="5af6f-114">작성 된 쿠키에 대 한 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-114">Specifies the base name for any cookies written.</span></span> <span data-ttu-id="5af6f-115">기본값은 "FedAuth".</span><span class="sxs-lookup"><span data-stu-id="5af6f-115">The default is "FedAuth".</span></span>|  
|<span data-ttu-id="5af6f-116">path</span><span class="sxs-lookup"><span data-stu-id="5af6f-116">path</span></span>|<span data-ttu-id="5af6f-117">작성 된 쿠키에 대 한 경로 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-117">Specifies the path value for any cookies written.</span></span> <span data-ttu-id="5af6f-118">기본값은 "HttpRuntime.AppDomainAppVirtualPath".</span><span class="sxs-lookup"><span data-stu-id="5af6f-118">The default is "HttpRuntime.AppDomainAppVirtualPath".</span></span>|  
|<span data-ttu-id="5af6f-119">모드</span><span class="sxs-lookup"><span data-stu-id="5af6f-119">mode</span></span>|<span data-ttu-id="5af6f-120">중 하나는 <xref:System.IdentityModel.Services.CookieHandlerMode> SAM 사용 하는 쿠키 처리기의 종류를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-120">One of the <xref:System.IdentityModel.Services.CookieHandlerMode> values that specifies the kind of cookie handler used by the SAM.</span></span> <span data-ttu-id="5af6f-121">다음 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-121">The following values may be used:</span></span><br /><br /> <span data-ttu-id="5af6f-122">-"Default"-"Chunked"와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-122">-   "Default" — The same as "Chunked".</span></span><br /><span data-ttu-id="5af6f-123">-"청크 방식"-에서 사용 하는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-123">-   "Chunked" — Uses an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="5af6f-124">이 쿠키 처리기 개별 쿠키 설정 된 최대 크기를 초과 하지 않는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-124">This cookie handler ensures that individual cookies do not exceed a set maximum size.</span></span> <span data-ttu-id="5af6f-125">잠재적으로 "청크" 하나의 논리 쿠키 여러 개의 쿠키 실시간으로 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-125">It accomplishes this by potentially "chunking" one logical cookie into a number of cookies on-the-wire.</span></span><br /><span data-ttu-id="5af6f-126">-"Custom"-에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.CookieHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-126">-   "Custom" — Uses an instance of a custom class derived from <xref:System.IdentityModel.Services.CookieHandler>.</span></span> <span data-ttu-id="5af6f-127">파생된 클래스에서 참조 되는 `<customCookieHandler>` 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-127">The derived class is referenced by the `<customCookieHandler>` child element.</span></span><br /><br /> <span data-ttu-id="5af6f-128">기본값은 "Default"입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-128">The default is "Default".</span></span>|  
|<span data-ttu-id="5af6f-129">persistentSessionLifetime</span><span class="sxs-lookup"><span data-stu-id="5af6f-129">persistentSessionLifetime</span></span>|<span data-ttu-id="5af6f-130">영구 세션의 수명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-130">Specifies the lifetime of persistent sessions.</span></span> <span data-ttu-id="5af6f-131">0 이면 임시 세션 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-131">If zero, transient sessions are always used.</span></span> <span data-ttu-id="5af6f-132">기본값은 "0:0:0" 임시 세션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-132">The default value is "0:0:0", which specifies a transient session.</span></span> <span data-ttu-id="5af6f-133">최대 값은 "365:0:0" 365 일의 세션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-133">The maximum value is "365:0:0", which specifies a session of 365 days.</span></span> <span data-ttu-id="5af6f-134">다음과 같은 제한 사항이 따라 값을 지정 해야: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, 여기서 일 수를 지정 하는 왼쪽 값, 중간 값 (있는 경우) 지정 시간 및 분을 지정 하는 오른쪽 값 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="5af6f-134">The value should be specified according to the following restriction: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, where the leftmost value specifies days, the middle value (if present) specifies hours, and the rightmost value (if present) specifies minutes.</span></span>|  
|<span data-ttu-id="5af6f-135">RequireSsl</span><span class="sxs-lookup"><span data-stu-id="5af6f-135">requireSsl</span></span>|<span data-ttu-id="5af6f-136">작성 된 쿠키에 대 한 "Secure" 플래그는 내보내집니다 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-136">Specifies whether the "Secure" flag is emitted for any cookies written.</span></span> <span data-ttu-id="5af6f-137">이 값은 설정 로그인 세션 쿠키 내용을 HTTPS를 통해 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-137">If this value is set, the sign-in session cookies will only be available over HTTPS.</span></span> <span data-ttu-id="5af6f-138">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-138">The default is "true".</span></span>|  
|<span data-ttu-id="5af6f-139">hideFromScript</span><span class="sxs-lookup"><span data-stu-id="5af6f-139">hideFromScript</span></span>|<span data-ttu-id="5af6f-140">작성 된 쿠키에 대 한 "HttpOnly" 플래그는 내보내집니다 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-140">Controls whether the "HttpOnly" flag is emitted for any cookies written.</span></span> <span data-ttu-id="5af6f-141">특정 웹 브라우저 쿠키 값에 액세스할 수 없게 클라이언트 쪽 스크립트를 유지 하 여이 플래그를 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-141">Certain web browsers honor this flag by keeping client-side script from accessing the cookie value.</span></span> <span data-ttu-id="5af6f-142">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-142">The default is "true".</span></span>|  
|<span data-ttu-id="5af6f-143">도메인</span><span class="sxs-lookup"><span data-stu-id="5af6f-143">domain</span></span>|<span data-ttu-id="5af6f-144">작성 된 쿠키에 대 한 도메인 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-144">The domain value for any cookies written.</span></span> <span data-ttu-id="5af6f-145">기본값은 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-145">The default is "".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5af6f-146">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5af6f-146">Child Elements</span></span>  
  
|<span data-ttu-id="5af6f-147">요소</span><span class="sxs-lookup"><span data-stu-id="5af6f-147">Element</span></span>|<span data-ttu-id="5af6f-148">설명</span><span class="sxs-lookup"><span data-stu-id="5af6f-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5af6f-149">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="5af6f-149">\<chunkedCookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|<span data-ttu-id="5af6f-150">구성에서 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-150">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="5af6f-151">이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Default" 또는 "청크 방식"입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-151">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>|  
|[<span data-ttu-id="5af6f-152">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="5af6f-152">\<customCookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|<span data-ttu-id="5af6f-153">사용자 지정 쿠키 처리기 유형을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-153">Sets the custom cookie handler type.</span></span> <span data-ttu-id="5af6f-154">이 요소가 있어야 하는 경우는 `mode` 의 특성은 `<cookieHandler>` 요소는 "Custom"입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-154">This element must be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="5af6f-155">다른 값에 있을 수 없습니다는 `mode` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-155">It cannot be present for any other values of the `mode` attribute.</span></span> <span data-ttu-id="5af6f-156">사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-156">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5af6f-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5af6f-157">Parent Elements</span></span>  
  
|<span data-ttu-id="5af6f-158">요소</span><span class="sxs-lookup"><span data-stu-id="5af6f-158">Element</span></span>|<span data-ttu-id="5af6f-159">설명</span><span class="sxs-lookup"><span data-stu-id="5af6f-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5af6f-160">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="5af6f-160">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="5af6f-161">구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="5af6f-161">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5af6f-162">설명</span><span class="sxs-lookup"><span data-stu-id="5af6f-162">Remarks</span></span>  
 <span data-ttu-id="5af6f-163"><xref:System.IdentityModel.Services.CookieHandler> 는 읽기 및 쓰기 원시 쿠키는 http 프로토콜 수준에 대해 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-163">The <xref:System.IdentityModel.Services.CookieHandler> is responsible for reading and writing raw cookies at the HTTP protocol level.</span></span> <span data-ttu-id="5af6f-164">구성할 수 있습니다는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 또는에서 파생 된 사용자 지정 쿠키 처리기는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-164">You can configure either a <xref:System.IdentityModel.Services.ChunkedCookieHandler> or a custom cookie handler derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="5af6f-165">청크 분할된 쿠키가 처리기를 구성 하려면 "이 Chunked" 또는 "Default"를 모드 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-165">To configure a chunked cookie handler, set the mode attribute to "Chunked" or "Default".</span></span> <span data-ttu-id="5af6f-166">기본 청크 크기는 2000 바이트를 포함 하 여 필요에 따라 다른 청크 크기를 지정할 수 있지만 한 `<chunkedCookieHandler>` 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-166">The default chunk size is 2000 bytes, but you may optionally specify a different chunk size by including a `<chunkedCookieHandler>` child element.</span></span>  
  
 <span data-ttu-id="5af6f-167">사용자 지정 쿠키 처리기를 구성 하려면 mode 특성을 "Custom"를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-167">To configure a custom cookie handler, set the mode attribute to "Custom".</span></span> <span data-ttu-id="5af6f-168">도 지정 해야는 `<customCookieHandler>` 사용자 지정 오류 처리기의 형식을 참조 하는 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-168">You must also specify a `<customCookieHandler>` child element that references the type of your custom handler.</span></span>  
  
 <span data-ttu-id="5af6f-169">`<cookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-169">The `<cookieHandler>` element is represented by the <xref:System.IdentityModel.Services.CookieHandlerElement> class.</span></span> <span data-ttu-id="5af6f-170">구성에 지정 된 쿠키 처리기는에서 사용할 수는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 의 속성은 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 에 설정 하는 개체는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="5af6f-170">The cookie handler that was specified in configuration is available from the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> property of the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5af6f-171">예</span><span class="sxs-lookup"><span data-stu-id="5af6f-171">Example</span></span>  
 <span data-ttu-id="5af6f-172">XML은 다음 한 `<cookieHandler>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-172">The following XML shows a `<cookieHandler>` element.</span></span> <span data-ttu-id="5af6f-173">이 예제에서는 때문에 `mode` 특성 지정 하지 않으면, 기본 쿠키 처리기 SAM에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-173">In this example, because the `mode` attribute is not specified, the default cookie handler will be used by the SAM.</span></span> <span data-ttu-id="5af6f-174">인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-174">This is an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class.</span></span> <span data-ttu-id="5af6f-175">때문에 `<chunkedCookieHandler>` 자식 요소를 지정 하지 않으면, 기본 청크 크기 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-175">Because the `<chunkedCookieHandler>` child element is not specified, the default chunk size will be used.</span></span> <span data-ttu-id="5af6f-176">HTTPS 됩니다 필요 하기 때문에 `requireSsl` 특성이 설정 되어 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-176">HTTPS will not be required because the `requireSsl` attribute is set `false`.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5af6f-177">이 예제에서는 HTTPS 세션 쿠키를 작성 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-177">In this example, HTTPS is not required to write session cookies.</span></span> <span data-ttu-id="5af6f-178">때문에 이것이 `requireSsl` 특성에 `<cookieHandler>` 로 설정 된 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-178">This is because the `requireSsl` attribute on the `<cookieHandler>` element is set to `false`.</span></span> <span data-ttu-id="5af6f-179">이 설정은 보안 위험이 있습니다 대로 하지 대부분의 프로덕션 환경에 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5af6f-179">This setting is not recommended for most production environments as it may present a security risk.</span></span>  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="5af6f-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5af6f-180">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
