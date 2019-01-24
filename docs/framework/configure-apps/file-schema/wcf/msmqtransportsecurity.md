---
title: '&lt;msmqTransportSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 2a4daea50e1b6c24d923e01a6bc7ae913c241001
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593487"
---
# <a name="ltmsmqtransportsecuritygt"></a><span data-ttu-id="99048-102">&lt;msmqTransportSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="99048-102">&lt;msmqTransportSecurity&gt;</span></span>
<span data-ttu-id="99048-103">사용자 지정 바인딩에 MSMQ 전송 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-103">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="99048-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99048-104">\<system.serviceModel></span></span>  
<span data-ttu-id="99048-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="99048-105">\<bindings></span></span>  
<span data-ttu-id="99048-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99048-106">\<customBinding></span></span>  
<span data-ttu-id="99048-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="99048-107">\<binding></span></span>  
<span data-ttu-id="99048-108">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="99048-108">\<msmqIntegration></span></span>  
<span data-ttu-id="99048-109">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="99048-109">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99048-110">구문</span><span class="sxs-lookup"><span data-stu-id="99048-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99048-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="99048-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99048-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99048-113">특성</span><span class="sxs-lookup"><span data-stu-id="99048-113">Attributes</span></span>  
  
|<span data-ttu-id="99048-114">특성</span><span class="sxs-lookup"><span data-stu-id="99048-114">Attribute</span></span>|<span data-ttu-id="99048-115">설명</span><span class="sxs-lookup"><span data-stu-id="99048-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="99048-116">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="99048-117">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="99048-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99048-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99048-119">-None. 인증 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-119">-   None: No authentication.</span></span><br /><span data-ttu-id="99048-120">-   Windows: 인증 메커니즘 Active Directory를 사용 하 여 메시지를 사용 하 여 연결 된 SID에 대 한 X.509 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99048-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="99048-121">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99048-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="99048-122">-인증서: 채널은 인증서 저장소에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99048-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="99048-123">기본값은 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-123">The default value is Windows.</span></span> <span data-ttu-id="99048-124">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="99048-125">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="99048-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99048-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99048-127">-   RC4Stream</span><span class="sxs-lookup"><span data-stu-id="99048-127">-   RC4Stream</span></span><br /><span data-ttu-id="99048-128">-   AES</span><span class="sxs-lookup"><span data-stu-id="99048-128">-   AES</span></span><br /><br /> <span data-ttu-id="99048-129">기본값은 RC4Stream입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-129">The default value is RC4Stream.</span></span> <span data-ttu-id="99048-130">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="99048-131">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="99048-132">EncryptAndSign이 메시지 무결성 및 비부인을 보장하는 반면 암호화는 메시지 무결성을 보장합니다. 즉, 메시지는 실제로 보낸 사람으로부터 나오고 보낸 사람은 보낸 사람임을 밝히는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="99048-133">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99048-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99048-134">-None. 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99048-134">-   None: No protection.</span></span><br /><span data-ttu-id="99048-135">기호: 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="99048-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="99048-136">-   EncryptAndSign: 메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="99048-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="99048-137">기본값은 Sign입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-137">The default value is Sign.</span></span> <span data-ttu-id="99048-138">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="99048-139">시그니처의 일부로 다이제스트를 계산하는 데 사용되는 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="99048-140">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99048-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99048-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="99048-141">-   MD5</span></span><br /><span data-ttu-id="99048-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="99048-142">-   SHA1</span></span><br /><span data-ttu-id="99048-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="99048-143">-   SHA256</span></span><br /><span data-ttu-id="99048-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="99048-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="99048-145">기본값은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-145">The default value is SHA1.</span></span> <span data-ttu-id="99048-146">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99048-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99048-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="99048-147">Child Elements</span></span>  
 <span data-ttu-id="99048-148">없음</span><span class="sxs-lookup"><span data-stu-id="99048-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99048-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="99048-149">Parent Elements</span></span>  
  
|<span data-ttu-id="99048-150">요소</span><span class="sxs-lookup"><span data-stu-id="99048-150">Element</span></span>|<span data-ttu-id="99048-151">설명</span><span class="sxs-lookup"><span data-stu-id="99048-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99048-152">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="99048-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="99048-153">MSMQ(메시지 큐) 전송자 또는 수신자와의 상호 작용에 필요한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="99048-154">\<msmqTransport></span><span class="sxs-lookup"><span data-stu-id="99048-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="99048-155">네이티브 MSMQ 프로토콜을 사용하는 WCF(Windows Communication Foundation) 서비스에 대한 큐 통신 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99048-156">설명</span><span class="sxs-lookup"><span data-stu-id="99048-156">Remarks</span></span>  
 <span data-ttu-id="99048-157">전송 보안에 대 한 자세한 내용은 참조 하세요. [전송 보안](../../../../../docs/framework/wcf/feature-details/transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99048-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99048-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="99048-158">See also</span></span>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="99048-159">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="99048-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="99048-160">전송</span><span class="sxs-lookup"><span data-stu-id="99048-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="99048-161">전송 선택</span><span class="sxs-lookup"><span data-stu-id="99048-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="99048-162">바인딩</span><span class="sxs-lookup"><span data-stu-id="99048-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="99048-163">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="99048-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="99048-164">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="99048-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="99048-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99048-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="99048-166">전송 보안</span><span class="sxs-lookup"><span data-stu-id="99048-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
