---
title: '&lt;netTcpBinding&gt;의 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 8c2a0de73db2ec4a1c2150fc7e62b7a3a9f086bc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515054"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="e4030-102">&lt;netTcpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="e4030-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="e4030-103">구성 된 끝점에 대 한 메시지 수준 보안 요구 사항 형식을 정의 합니다 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="e4030-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e4030-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e4030-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="e4030-105">\<bindings></span></span>  
<span data-ttu-id="e4030-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e4030-106">\<netTcpBinding></span></span>  
<span data-ttu-id="e4030-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="e4030-107">\<binding></span></span>  
<span data-ttu-id="e4030-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e4030-108">\<security></span></span>  
<span data-ttu-id="e4030-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e4030-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4030-110">구문</span><span class="sxs-lookup"><span data-stu-id="e4030-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"             sslProtocols="Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4030-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e4030-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e4030-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4030-113">특성</span><span class="sxs-lookup"><span data-stu-id="e4030-113">Attributes</span></span>  
  
|<span data-ttu-id="e4030-114">특성</span><span class="sxs-lookup"><span data-stu-id="e4030-114">Attribute</span></span>|<span data-ttu-id="e4030-115">설명</span><span class="sxs-lookup"><span data-stu-id="e4030-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4030-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e4030-116">clientCredentialType</span></span>|<span data-ttu-id="e4030-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-117">Optional.</span></span> <span data-ttu-id="e4030-118">전송 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="e4030-119">-기본값은 `Windows`합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="e4030-120">-이 특성은 형식 <xref:System.ServiceModel.TcpClientCredentialType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="e4030-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e4030-121">protectionLevel</span></span>|<span data-ttu-id="e4030-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-122">Optional.</span></span> <span data-ttu-id="e4030-123">TCP 전송의 수준에 보안을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="e4030-124">메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e4030-125">암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="e4030-126">기본값은 `EncryptAndSign`입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="e4030-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="e4030-127">sslProtocols</span></span>|<span data-ttu-id="e4030-128">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="e4030-129">기본값은 Tls&#124;Tls11&#124;Tls12 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="e4030-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="e4030-130">policyEnforcement</span></span>|<span data-ttu-id="e4030-131">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e4030-132">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="e4030-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e4030-133">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e4030-134">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e4030-135">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e4030-136">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="e4030-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e4030-137">값</span><span class="sxs-lookup"><span data-stu-id="e4030-137">Value</span></span>|<span data-ttu-id="e4030-138">설명</span><span class="sxs-lookup"><span data-stu-id="e4030-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4030-139">없음</span><span class="sxs-lookup"><span data-stu-id="e4030-139">None</span></span>|<span data-ttu-id="e4030-140">클라이언트는 익명입니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-140">The client is anonymous.</span></span> <span data-ttu-id="e4030-141">여기에는 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="e4030-142">Windows</span><span class="sxs-lookup"><span data-stu-id="e4030-142">Windows</span></span>|<span data-ttu-id="e4030-143">SP 협상(Kerberos 협상)을 사용하는 클라이언트의 Windows 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="e4030-144">인증서</span><span class="sxs-lookup"><span data-stu-id="e4030-144">Certificate</span></span>|<span data-ttu-id="e4030-145">클라이언트는 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="e4030-146">클라이언트에서는 SSL 협상을 사용하며 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="e4030-147">protectionLevel 특성</span><span class="sxs-lookup"><span data-stu-id="e4030-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="e4030-148">값</span><span class="sxs-lookup"><span data-stu-id="e4030-148">Value</span></span>|<span data-ttu-id="e4030-149">설명</span><span class="sxs-lookup"><span data-stu-id="e4030-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4030-150">없음</span><span class="sxs-lookup"><span data-stu-id="e4030-150">None</span></span>|<span data-ttu-id="e4030-151">보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-151">No protection.</span></span>|  
|<span data-ttu-id="e4030-152">Sign</span><span class="sxs-lookup"><span data-stu-id="e4030-152">Sign</span></span>|<span data-ttu-id="e4030-153">메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-153">Messages are signed.</span></span>|  
|<span data-ttu-id="e4030-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="e4030-154">EncryptAndSign</span></span>|<span data-ttu-id="e4030-155">-메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4030-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e4030-156">Child Elements</span></span>  
 <span data-ttu-id="e4030-157">없음</span><span class="sxs-lookup"><span data-stu-id="e4030-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4030-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e4030-158">Parent Elements</span></span>  
  
|<span data-ttu-id="e4030-159">요소</span><span class="sxs-lookup"><span data-stu-id="e4030-159">Element</span></span>|<span data-ttu-id="e4030-160">설명</span><span class="sxs-lookup"><span data-stu-id="e4030-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4030-161">\<security></span><span class="sxs-lookup"><span data-stu-id="e4030-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="e4030-162">보안 기능을 지정 합니다 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4030-163">설명</span><span class="sxs-lookup"><span data-stu-id="e4030-163">Remarks</span></span>  
 <span data-ttu-id="e4030-164">SOAP 메시지의 무결성 및 기밀성과 상호 인증을 위해 전송 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="e4030-165">바인딩에서 이 보안 모드를 선택하면 보안 전송을 사용하여 채널 스택이 구성되고 Windows(협상) 또는 SSL over TCP 같은 전송 보안을 사용하여 SOAP 메시지가 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4030-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4030-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4030-166">See Also</span></span>  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="e4030-167">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e4030-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e4030-168">바인딩</span><span class="sxs-lookup"><span data-stu-id="e4030-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e4030-169">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="e4030-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e4030-170">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="e4030-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e4030-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="e4030-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
