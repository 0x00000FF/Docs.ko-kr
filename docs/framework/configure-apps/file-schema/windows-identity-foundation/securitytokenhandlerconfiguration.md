---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206092"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="e4fe3-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="e4fe3-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="e4fe3-103">토큰 처리기 컬렉션에 대 한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="e4fe3-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e4fe3-104">\<system.identityModel></span></span>  
<span data-ttu-id="e4fe3-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e4fe3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e4fe3-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e4fe3-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e4fe3-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4fe3-108">구문</span><span class="sxs-lookup"><span data-stu-id="e4fe3-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4fe3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e4fe3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e4fe3-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4fe3-111">특성</span><span class="sxs-lookup"><span data-stu-id="e4fe3-111">Attributes</span></span>  
  
|<span data-ttu-id="e4fe3-112">특성</span><span class="sxs-lookup"><span data-stu-id="e4fe3-112">Attribute</span></span>|<span data-ttu-id="e4fe3-113">설명</span><span class="sxs-lookup"><span data-stu-id="e4fe3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4fe3-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="e4fe3-114">saveBootstrapContext</span></span>|<span data-ttu-id="e4fe3-115">세션 토큰에 부트스트랩 토큰을 포함시킬지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="e4fe3-116">값을 설정할 수도 있습니다 토큰 처리기 컬렉션에 대해 설정 하 여 합니다 `saveBootstrapContext` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="e4fe3-117">토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="e4fe3-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="e4fe3-118">maximumClockSkew</span></span>|<span data-ttu-id="e4fe3-119"><xref:System.TimeSpan> 허용 된 최대 클럭 오차를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="e4fe3-120">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="e4fe3-121">기본값은 5 분 "00: 05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="e4fe3-122">지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하세요 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="e4fe3-123">최대 클럭 오차 설정할 수도 있습니다 서비스 수준에서 설정 하 여 합니다 `maximumClockSkew` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="e4fe3-124">토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4fe3-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e4fe3-125">Child Elements</span></span>  
  
|<span data-ttu-id="e4fe3-126">요소</span><span class="sxs-lookup"><span data-stu-id="e4fe3-126">Element</span></span>|<span data-ttu-id="e4fe3-127">설명</span><span class="sxs-lookup"><span data-stu-id="e4fe3-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4fe3-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="e4fe3-129">이 신뢰 당사자의 식별자를 허용 되는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="e4fe3-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-130">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-131">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="e4fe3-132">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="e4fe3-133">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e4fe3-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-134">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="e4fe3-136">토큰 처리기 인증서의 유효성을 검사 하는 데 사용 되는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="e4fe3-137">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e4fe3-138">특정 처리기를 자체 유효성 검사기를 사용 하 여 구성 된 경우이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="e4fe3-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-139">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="e4fe3-141">토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e4fe3-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-142">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="e4fe3-144">토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e4fe3-145">발급자 토큰 확인자는 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e4fe3-146">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-146">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="e4fe3-148">토큰 처리기 컬렉션의 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e4fe3-149">서비스 토큰 확인자는 들어오는 토큰에 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="e4fe3-150">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-150">Optional.</span></span>|  
|[<span data-ttu-id="e4fe3-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="e4fe3-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="e4fe3-152">토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="e4fe3-153">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e4fe3-154">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4fe3-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e4fe3-155">Parent Elements</span></span>  
  
|<span data-ttu-id="e4fe3-156">요소</span><span class="sxs-lookup"><span data-stu-id="e4fe3-156">Element</span></span>|<span data-ttu-id="e4fe3-157">설명</span><span class="sxs-lookup"><span data-stu-id="e4fe3-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4fe3-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e4fe3-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="e4fe3-159">끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4fe3-160">설명</span><span class="sxs-lookup"><span data-stu-id="e4fe3-160">Remarks</span></span>  
 <span data-ttu-id="e4fe3-161">이 섹션에서는 속성 값을 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="e4fe3-162">이 섹션에 구성 된 설정 서비스에서 구성한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="e4fe3-163">이러한 설정 중 일부 처리기는 보안 토큰 처리기 컬렉션에 추가 되 면 지정 된 설정으로 재정의 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4fe3-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fe3-164">예제</span><span class="sxs-lookup"><span data-stu-id="e4fe3-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
