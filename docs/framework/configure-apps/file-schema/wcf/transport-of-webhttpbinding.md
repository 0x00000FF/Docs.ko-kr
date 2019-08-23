---
title: <webHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: f78add5397644dc40bfd22f10bd84aa5c5eb29e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923206"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="7e48c-102">\<webHttpBinding >의 \<전송 ></span><span class="sxs-lookup"><span data-stu-id="7e48c-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="7e48c-103">HTTP 요청을 수신하도록 구성된 서비스 엔드포인트의 전송 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="7e48c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7e48c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e48c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7e48c-105">\<bindings></span></span>  
<span data-ttu-id="7e48c-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7e48c-106">\<webHttpBinding></span></span>  
<span data-ttu-id="7e48c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7e48c-107">\<binding></span></span>  
<span data-ttu-id="7e48c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="7e48c-108">\<security></span></span>  
<span data-ttu-id="7e48c-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="7e48c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e48c-110">구문</span><span class="sxs-lookup"><span data-stu-id="7e48c-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="7e48c-111">형식</span><span class="sxs-lookup"><span data-stu-id="7e48c-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e48c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7e48c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7e48c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e48c-114">특성</span><span class="sxs-lookup"><span data-stu-id="7e48c-114">Attributes</span></span>  
  
|<span data-ttu-id="7e48c-115">특성</span><span class="sxs-lookup"><span data-stu-id="7e48c-115">Attribute</span></span>|<span data-ttu-id="7e48c-116">Description</span><span class="sxs-lookup"><span data-stu-id="7e48c-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="7e48c-117">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="7e48c-118">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="7e48c-119">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="7e48c-120">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="7e48c-121">다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="7e48c-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7e48c-123">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="7e48c-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="7e48c-124">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="7e48c-125">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="7e48c-126">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7e48c-127">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="7e48c-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7e48c-128">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7e48c-129">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7e48c-130">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7e48c-131">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7e48c-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7e48c-132">값</span><span class="sxs-lookup"><span data-stu-id="7e48c-132">Value</span></span>|<span data-ttu-id="7e48c-133">Description</span><span class="sxs-lookup"><span data-stu-id="7e48c-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="7e48c-134">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="7e48c-135">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="7e48c-136">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="7e48c-137">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="7e48c-138">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="7e48c-139">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7e48c-140">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7e48c-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7e48c-141">값</span><span class="sxs-lookup"><span data-stu-id="7e48c-141">Value</span></span>|<span data-ttu-id="7e48c-142">Description</span><span class="sxs-lookup"><span data-stu-id="7e48c-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="7e48c-143">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="7e48c-144">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="7e48c-145">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="7e48c-146">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="7e48c-147">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e48c-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7e48c-148">Child Elements</span></span>  
 <span data-ttu-id="7e48c-149">없음</span><span class="sxs-lookup"><span data-stu-id="7e48c-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e48c-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7e48c-150">Parent Elements</span></span>  
  
|<span data-ttu-id="7e48c-151">요소</span><span class="sxs-lookup"><span data-stu-id="7e48c-151">Element</span></span>|<span data-ttu-id="7e48c-152">설명</span><span class="sxs-lookup"><span data-stu-id="7e48c-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e48c-153">\<security></span><span class="sxs-lookup"><span data-stu-id="7e48c-153">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="7e48c-154">WsHttpBinding > 요소의 보안 기능 [ \<](wshttpbinding.md) 을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e48c-154">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e48c-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e48c-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="7e48c-156">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7e48c-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7e48c-157">바인딩</span><span class="sxs-lookup"><span data-stu-id="7e48c-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7e48c-158">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7e48c-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7e48c-159">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7e48c-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7e48c-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="7e48c-160">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="7e48c-161">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="7e48c-161">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
