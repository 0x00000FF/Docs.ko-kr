---
title: <basicHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399889"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="828b4-102">\<basicHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="828b4-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="828b4-103">[ \<BasicHttpBinding >](basichttpbinding.md)의 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="828b4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="828b4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="828b4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="828b4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="828b4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="828b4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="828b4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<basicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="828b4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="828b4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="828b4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="828b4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="828b4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828b4-110">구문</span><span class="sxs-lookup"><span data-stu-id="828b4-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="828b4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="828b4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="828b4-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="828b4-113">특성</span><span class="sxs-lookup"><span data-stu-id="828b4-113">Attributes</span></span>  
  
|<span data-ttu-id="828b4-114">특성</span><span class="sxs-lookup"><span data-stu-id="828b4-114">Attribute</span></span>|<span data-ttu-id="828b4-115">Description</span><span class="sxs-lookup"><span data-stu-id="828b4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="828b4-116">모드</span><span class="sxs-lookup"><span data-stu-id="828b4-116">mode</span></span>|<span data-ttu-id="828b4-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-117">Optional.</span></span> <span data-ttu-id="828b4-118">사용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="828b4-119">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-119">The default is `None`.</span></span> <span data-ttu-id="828b4-120">이 특성은 <xref:System.ServiceModel.BasicHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="828b4-121">mode 특성</span><span class="sxs-lookup"><span data-stu-id="828b4-121">mode Attribute</span></span>  
  
|<span data-ttu-id="828b4-122">값</span><span class="sxs-lookup"><span data-stu-id="828b4-122">Value</span></span>|<span data-ttu-id="828b4-123">설명</span><span class="sxs-lookup"><span data-stu-id="828b4-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="828b4-124">없음</span><span class="sxs-lookup"><span data-stu-id="828b4-124">None</span></span>|<span data-ttu-id="828b4-125">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="828b4-126">전송</span><span class="sxs-lookup"><span data-stu-id="828b4-126">Transport</span></span>|<span data-ttu-id="828b4-127">HTTPS 전송을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="828b4-128">SOAP 메시지는 HTTPS를 사용하여 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="828b4-129">이 서비스는 서비스의 X.509 인증서를 사용하여 클라이언트에 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="828b4-130">클라이언트는 제공된 ClientCredentialType을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="828b4-131">[ \<전송 >](transport-of-basichttpbinding.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="828b4-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="828b4-132">메시지</span><span class="sxs-lookup"><span data-stu-id="828b4-132">Message</span></span>|<span data-ttu-id="828b4-133">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="828b4-134">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="828b4-135">이 바인딩에서는 클라이언트에 out of band 방식으로 서버 인증서가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="828b4-136">이 바인딩의 유효한 `ClientCredentialType`은 `Certificate`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="828b4-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="828b4-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="828b4-138">전송 보안에 의해 무결성, 기밀성 및 서버 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="828b4-139">클라이언트 인증은 SOAP 메시지 보안에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="828b4-140">이 모드는 사용자가 사용자 이름/암호를 사용하여 인증되며 메시지 전송 보호를 위한 기존의 HTTP 배포가 있는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="828b4-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="828b4-141">TransportCredentialOnly</span></span>|<span data-ttu-id="828b4-142">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="828b4-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="828b4-143">http 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-143">It provides http-based client authentication.</span></span> <span data-ttu-id="828b4-144">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-144">This mode should be used with caution.</span></span> <span data-ttu-id="828b4-145">다른 방법 (예: IPSec)에서 전송 보안을 제공 하는 환경에서 사용 해야 하며, WCF 인프라에서 클라이언트 인증만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="828b4-146">자식 요소</span><span class="sxs-lookup"><span data-stu-id="828b4-146">Child Elements</span></span>  
  
|<span data-ttu-id="828b4-147">요소</span><span class="sxs-lookup"><span data-stu-id="828b4-147">Element</span></span>|<span data-ttu-id="828b4-148">설명</span><span class="sxs-lookup"><span data-stu-id="828b4-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="828b4-149">\<transport></span><span class="sxs-lookup"><span data-stu-id="828b4-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="828b4-150">기본 HTTP 서비스에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="828b4-151">이 요소는 <xref:System.ServiceModel.HttpTransportSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="828b4-152">\<message></span><span class="sxs-lookup"><span data-stu-id="828b4-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="828b4-153">기본 HTTP 서비스에 대한 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="828b4-154">이 요소는 <xref:System.ServiceModel.BasicHttpMessageSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="828b4-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="828b4-155">Parent Elements</span></span>  
  
|<span data-ttu-id="828b4-156">요소</span><span class="sxs-lookup"><span data-stu-id="828b4-156">Element</span></span>|<span data-ttu-id="828b4-157">설명</span><span class="sxs-lookup"><span data-stu-id="828b4-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="828b4-158">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="828b4-158">binding</span></span>|<span data-ttu-id="828b4-159">[ \<BasicHttpBinding >](basichttpbinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="828b4-160">설명</span><span class="sxs-lookup"><span data-stu-id="828b4-160">Remarks</span></span>  
 <span data-ttu-id="828b4-161">기본적으로 SOAP 메시지의 보안이 유지되지 않고 클라이언트가 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="828b4-162">이 요소를 사용하면 `basicHttpBinding` 요소에 대한 추가 보안 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828b4-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828b4-163">참고자료</span><span class="sxs-lookup"><span data-stu-id="828b4-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="828b4-164">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="828b4-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="828b4-165">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="828b4-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="828b4-166">바인딩</span><span class="sxs-lookup"><span data-stu-id="828b4-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="828b4-167">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="828b4-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="828b4-168">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="828b4-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="828b4-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="828b4-169">\<binding></span></span>](../../../misc/binding.md)
