---
title: '&lt;basicHttpBinding&gt;의 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2adb5736cca59d42ab3c62d61513bbfd80a4be04
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43565218"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="c292f-102">&lt;basicHttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="c292f-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="c292f-103">보안 기능을 정의 합니다 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="c292f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c292f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c292f-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c292f-105">\<bindings></span></span>  
<span data-ttu-id="c292f-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c292f-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="c292f-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c292f-107">\<binding></span></span>  
<span data-ttu-id="c292f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c292f-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c292f-109">구문</span><span class="sxs-lookup"><span data-stu-id="c292f-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c292f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c292f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c292f-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c292f-112">특성</span><span class="sxs-lookup"><span data-stu-id="c292f-112">Attributes</span></span>  
  
|<span data-ttu-id="c292f-113">특성</span><span class="sxs-lookup"><span data-stu-id="c292f-113">Attribute</span></span>|<span data-ttu-id="c292f-114">설명</span><span class="sxs-lookup"><span data-stu-id="c292f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c292f-115">모드</span><span class="sxs-lookup"><span data-stu-id="c292f-115">mode</span></span>|<span data-ttu-id="c292f-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-116">Optional.</span></span> <span data-ttu-id="c292f-117">사용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="c292f-118">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-118">The default is `None`.</span></span> <span data-ttu-id="c292f-119">이 특성은 <xref:System.ServiceModel.BasicHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c292f-120">mode 특성</span><span class="sxs-lookup"><span data-stu-id="c292f-120">mode Attribute</span></span>  
  
|<span data-ttu-id="c292f-121">값</span><span class="sxs-lookup"><span data-stu-id="c292f-121">Value</span></span>|<span data-ttu-id="c292f-122">설명</span><span class="sxs-lookup"><span data-stu-id="c292f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c292f-123">없음</span><span class="sxs-lookup"><span data-stu-id="c292f-123">None</span></span>|<span data-ttu-id="c292f-124">-메시지 전송 하는 동안 보안이 유지 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="c292f-125">전송</span><span class="sxs-lookup"><span data-stu-id="c292f-125">Transport</span></span>|<span data-ttu-id="c292f-126">HTTPS 전송을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="c292f-127">SOAP 메시지는 HTTPS를 사용하여 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="c292f-128">이 서비스는 서비스의 X.509 인증서를 사용하여 클라이언트에 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="c292f-129">클라이언트는 제공된 ClientCredentialType을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="c292f-130">참조 된 [ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="c292f-131">메시지</span><span class="sxs-lookup"><span data-stu-id="c292f-131">Message</span></span>|<span data-ttu-id="c292f-132">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="c292f-133">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="c292f-134">이 바인딩에서는 클라이언트에 out of band 방식으로 서버 인증서가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="c292f-135">이 바인딩의 유효한 `ClientCredentialType`은 `Certificate`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="c292f-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c292f-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="c292f-137">전송 보안에 의해 무결성, 기밀성 및 서버 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="c292f-138">클라이언트 인증은 SOAP 메시지 보안에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="c292f-139">이 모드는 사용자가 사용자 이름/암호를 사용하여 인증되며 메시지 전송 보호를 위한 기존의 HTTP 배포가 있는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="c292f-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="c292f-140">TransportCredentialOnly</span></span>|<span data-ttu-id="c292f-141">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="c292f-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="c292f-142">http 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-142">It provides http-based client authentication.</span></span> <span data-ttu-id="c292f-143">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-143">This mode should be used with caution.</span></span> <span data-ttu-id="c292f-144">전송 보안 (예: IPSec) 다른 방법으로 제공 되 고 WCF 인프라에서 클라이언트 인증만 제공 하는 환경에서는 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c292f-145">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c292f-145">Child Elements</span></span>  
  
|<span data-ttu-id="c292f-146">요소</span><span class="sxs-lookup"><span data-stu-id="c292f-146">Element</span></span>|<span data-ttu-id="c292f-147">설명</span><span class="sxs-lookup"><span data-stu-id="c292f-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c292f-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="c292f-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="c292f-149">기본 HTTP 서비스에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="c292f-150">이 요소는 <xref:System.ServiceModel.HttpTransportSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="c292f-151">\<message></span><span class="sxs-lookup"><span data-stu-id="c292f-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="c292f-152">기본 HTTP 서비스에 대한 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="c292f-153">이 요소는 <xref:System.ServiceModel.BasicHttpMessageSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c292f-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c292f-154">Parent Elements</span></span>  
  
|<span data-ttu-id="c292f-155">요소</span><span class="sxs-lookup"><span data-stu-id="c292f-155">Element</span></span>|<span data-ttu-id="c292f-156">설명</span><span class="sxs-lookup"><span data-stu-id="c292f-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c292f-157">바인딩</span><span class="sxs-lookup"><span data-stu-id="c292f-157">binding</span></span>|<span data-ttu-id="c292f-158">바인딩 요소를 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c292f-159">설명</span><span class="sxs-lookup"><span data-stu-id="c292f-159">Remarks</span></span>  
 <span data-ttu-id="c292f-160">기본적으로 SOAP 메시지의 보안이 유지되지 않고 클라이언트가 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="c292f-161">이 요소를 사용하면 `basicHttpBinding` 요소에 대한 추가 보안 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c292f-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c292f-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c292f-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="c292f-163">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c292f-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c292f-164">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="c292f-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="c292f-165">바인딩</span><span class="sxs-lookup"><span data-stu-id="c292f-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c292f-166">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="c292f-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c292f-167">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c292f-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c292f-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="c292f-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
