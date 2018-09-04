---
title: '&lt;webHttpBinding&gt;의 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 52146fa08ec63ef63fa996cdc09f9185b9f42e02
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560262"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="940b2-102">&lt;webHttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="940b2-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="940b2-103">구성 된 끝점에 대 한 보안 요구 사항을 지정 된 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="940b2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="940b2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="940b2-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="940b2-105">\<bindings></span></span>  
<span data-ttu-id="940b2-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="940b2-106">\<webHttpBinding></span></span>  
<span data-ttu-id="940b2-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="940b2-107">\<binding></span></span>  
<span data-ttu-id="940b2-108">\<security></span><span class="sxs-lookup"><span data-stu-id="940b2-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940b2-109">구문</span><span class="sxs-lookup"><span data-stu-id="940b2-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="940b2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="940b2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="940b2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="940b2-112">특성</span><span class="sxs-lookup"><span data-stu-id="940b2-112">Attributes</span></span>  
  
|<span data-ttu-id="940b2-113">특성</span><span class="sxs-lookup"><span data-stu-id="940b2-113">Attribute</span></span>|<span data-ttu-id="940b2-114">설명</span><span class="sxs-lookup"><span data-stu-id="940b2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="940b2-115">모드</span><span class="sxs-lookup"><span data-stu-id="940b2-115">mode</span></span>|<span data-ttu-id="940b2-116">끝점에서 전송 수준 보안을 사용하거나 보안을 사용하지 않는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="940b2-117">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-117">The default is `None`.</span></span> <span data-ttu-id="940b2-118">이 특성은 <xref:System.ServiceModel.WebHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="940b2-119">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="940b2-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="940b2-120">값</span><span class="sxs-lookup"><span data-stu-id="940b2-120">Value</span></span>|<span data-ttu-id="940b2-121">설명</span><span class="sxs-lookup"><span data-stu-id="940b2-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="940b2-122">없음</span><span class="sxs-lookup"><span data-stu-id="940b2-122">None</span></span>|<span data-ttu-id="940b2-123">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-123">Security is disabled.</span></span>|  
|<span data-ttu-id="940b2-124">전송</span><span class="sxs-lookup"><span data-stu-id="940b2-124">Transport</span></span>|<span data-ttu-id="940b2-125">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="940b2-126">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="940b2-127">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="940b2-128">클라이언트 인증을 통해 제어 됩니다 합니다 `ClientCredentialType` 특성을 [ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="940b2-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="940b2-129">TransportCredentialOnly</span></span>|<span data-ttu-id="940b2-130">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="940b2-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="940b2-131">HTTP 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="940b2-132">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-132">This mode should be used with caution.</span></span> <span data-ttu-id="940b2-133">전송 보안 (예: IPSec) 다른 방법으로 제공 되 고 WCF 인프라에서 클라이언트 인증만 제공 하는 환경에서는 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="940b2-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="940b2-134">Child Elements</span></span>  
  
|<span data-ttu-id="940b2-135">요소</span><span class="sxs-lookup"><span data-stu-id="940b2-135">Element</span></span>|<span data-ttu-id="940b2-136">설명</span><span class="sxs-lookup"><span data-stu-id="940b2-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="940b2-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="940b2-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="940b2-138">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-138">Defines the transport security settings.</span></span> <span data-ttu-id="940b2-139">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="940b2-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="940b2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="940b2-141">요소</span><span class="sxs-lookup"><span data-stu-id="940b2-141">Element</span></span>|<span data-ttu-id="940b2-142">설명</span><span class="sxs-lookup"><span data-stu-id="940b2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="940b2-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="940b2-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="940b2-144">Windows Communication Foundation (WCF) 웹 서비스 SOAP 메시지 대신 HTTP 요청에 응답 하는 끝점을 구성 하는 데 사용 되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="940b2-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="940b2-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="940b2-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="940b2-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="940b2-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="940b2-147">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="940b2-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="940b2-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="940b2-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="940b2-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="940b2-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="940b2-150">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="940b2-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="940b2-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="940b2-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="940b2-152">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="940b2-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
