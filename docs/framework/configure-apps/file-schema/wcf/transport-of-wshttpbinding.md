---
title: '&lt;wsHttpBinding&gt;의 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: a759f74e923c9d81391abf82fa08491f3b31c990
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517953"
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a><span data-ttu-id="580b4-102">&lt;wsHttpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="580b4-102">&lt;transport&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="580b4-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="580b4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="580b4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="580b4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="580b4-105">\<bindings></span></span>  
<span data-ttu-id="580b4-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="580b4-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="580b4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="580b4-107">\<binding></span></span>  
<span data-ttu-id="580b4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="580b4-108">\<security></span></span>  
<span data-ttu-id="580b4-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="580b4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="580b4-110">구문</span><span class="sxs-lookup"><span data-stu-id="580b4-110">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtecutionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="580b4-111">형식</span><span class="sxs-lookup"><span data-stu-id="580b4-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="580b4-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="580b4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="580b4-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="580b4-114">특성</span><span class="sxs-lookup"><span data-stu-id="580b4-114">Attributes</span></span>  
  
|<span data-ttu-id="580b4-115">특성</span><span class="sxs-lookup"><span data-stu-id="580b4-115">Attribute</span></span>|<span data-ttu-id="580b4-116">설명</span><span class="sxs-lookup"><span data-stu-id="580b4-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="580b4-117">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="580b4-118">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="580b4-119">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="580b4-120">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="580b4-121">다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="580b4-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="580b4-123">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="580b4-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="580b4-124">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="580b4-125">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="580b4-126">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="580b4-127">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="580b4-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="580b4-128">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="580b4-129">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="580b4-130">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="580b4-131">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="580b4-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="580b4-132">값</span><span class="sxs-lookup"><span data-stu-id="580b4-132">Value</span></span>|<span data-ttu-id="580b4-133">설명</span><span class="sxs-lookup"><span data-stu-id="580b4-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="580b4-134">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="580b4-135">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="580b4-136">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="580b4-137">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="580b4-138">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="580b4-139">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="580b4-140">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="580b4-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="580b4-141">값</span><span class="sxs-lookup"><span data-stu-id="580b4-141">Value</span></span>|<span data-ttu-id="580b4-142">설명</span><span class="sxs-lookup"><span data-stu-id="580b4-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="580b4-143">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="580b4-144">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="580b4-145">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="580b4-146">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="580b4-147">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="580b4-148">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="580b4-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="580b4-149">Child Elements</span></span>  
 <span data-ttu-id="580b4-150">없음</span><span class="sxs-lookup"><span data-stu-id="580b4-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="580b4-151">부모 요소</span><span class="sxs-lookup"><span data-stu-id="580b4-151">Parent Elements</span></span>  
  
|<span data-ttu-id="580b4-152">요소</span><span class="sxs-lookup"><span data-stu-id="580b4-152">Element</span></span>|<span data-ttu-id="580b4-153">설명</span><span class="sxs-lookup"><span data-stu-id="580b4-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="580b4-154">\<security></span><span class="sxs-lookup"><span data-stu-id="580b4-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="580b4-155">보안 기능을 나타내는 합니다 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="580b4-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="580b4-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="580b4-156">See also</span></span>
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="580b4-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="580b4-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="580b4-158">바인딩</span><span class="sxs-lookup"><span data-stu-id="580b4-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="580b4-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="580b4-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="580b4-160">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="580b4-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="580b4-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="580b4-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
