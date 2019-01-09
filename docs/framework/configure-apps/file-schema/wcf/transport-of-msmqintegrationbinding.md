---
title: '&lt;msmqIntegrationBinding&gt;의 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 27876d819f766c130a29b07524e30ac77e9ba05d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144940"
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="63429-102">&lt;msmqIntegrationBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="63429-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="63429-103">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="63429-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="63429-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="63429-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="63429-105">\<bindings></span></span>  
<span data-ttu-id="63429-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="63429-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="63429-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="63429-107">\<binding></span></span>  
<span data-ttu-id="63429-108">\<security></span><span class="sxs-lookup"><span data-stu-id="63429-108">\<security></span></span>  
<span data-ttu-id="63429-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="63429-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63429-110">구문</span><span class="sxs-lookup"><span data-stu-id="63429-110">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63429-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="63429-111">Attributes and Elements</span></span>  
 <span data-ttu-id="63429-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63429-113">특성</span><span class="sxs-lookup"><span data-stu-id="63429-113">Attributes</span></span>  
  
|<span data-ttu-id="63429-114">특성</span><span class="sxs-lookup"><span data-stu-id="63429-114">Attribute</span></span>|<span data-ttu-id="63429-115">설명</span><span class="sxs-lookup"><span data-stu-id="63429-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="63429-116">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="63429-117">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="63429-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="63429-119">-None. 인증 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-119">-   None: No authentication.</span></span><br /><span data-ttu-id="63429-120">-WindowsDomain: 인증 메커니즘 Active Directory를 사용 하 여 메시지를 사용 하 여 연결 된 SID에 대 한 X.509 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63429-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="63429-121">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63429-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="63429-122">-인증서: 채널은 인증서 저장소에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63429-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="63429-123">기본값은 WindowsDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="63429-124">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="63429-125">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="63429-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="63429-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="63429-127">-   RC4Stream</span></span><br /><span data-ttu-id="63429-128">-   AES</span><span class="sxs-lookup"><span data-stu-id="63429-128">-   AES</span></span><br /><br /> <span data-ttu-id="63429-129">기본값은 RC4Stream입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-129">The default value is RC4Stream.</span></span> <span data-ttu-id="63429-130">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="63429-131">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="63429-132">EncryptAndSign이 메시지 무결성 및 비부인을 보장하는 반면 암호화는 메시지 무결성을 보장합니다. 즉, 메시지는 실제로 보낸 사람으로부터 나오고 보낸 사람은 보낸 사람임을 밝히는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="63429-133">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="63429-134">-None. 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-134">-   None: No protection.</span></span><br /><span data-ttu-id="63429-135">기호: 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="63429-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="63429-136">-EncryptAndSign: 메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="63429-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="63429-137">기본값은 Sign입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-137">The default value is Sign.</span></span> <span data-ttu-id="63429-138">이 특성은 ProtectionLevel 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="63429-139">-서명의 일부로 다이제스트를 계산 하는 데 사용할 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="63429-140">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-140">Valid values include the following:</span></span><br /><span data-ttu-id="63429-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="63429-141">-   MD5</span></span><br /><span data-ttu-id="63429-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="63429-142">-   SHA1</span></span><br /><span data-ttu-id="63429-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="63429-143">-   SHA256</span></span><br /><span data-ttu-id="63429-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="63429-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="63429-145">기본값은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-145">The default value is SHA1.</span></span> <span data-ttu-id="63429-146">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63429-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="63429-147">Child Elements</span></span>  
 <span data-ttu-id="63429-148">없음</span><span class="sxs-lookup"><span data-stu-id="63429-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63429-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="63429-149">Parent Elements</span></span>  
  
|<span data-ttu-id="63429-150">요소</span><span class="sxs-lookup"><span data-stu-id="63429-150">Element</span></span>|<span data-ttu-id="63429-151">설명</span><span class="sxs-lookup"><span data-stu-id="63429-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63429-152">\<security></span><span class="sxs-lookup"><span data-stu-id="63429-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="63429-153">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63429-154">설명</span><span class="sxs-lookup"><span data-stu-id="63429-154">Remarks</span></span>  
 <span data-ttu-id="63429-155">이 요소는 메시지 큐 통합 전송을 위한 보안 설정을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="63429-156">설정은 메시지 큐 통합 및 대기 중인 전송에서 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="63429-157">이 요소를 사용하여 인증 모드, 암호화 알고리즘, 보안 해시 알고리즘 및 보호 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63429-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63429-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="63429-159">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="63429-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="63429-160">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="63429-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="63429-161">바인딩</span><span class="sxs-lookup"><span data-stu-id="63429-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="63429-162">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="63429-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="63429-163">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="63429-163">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="63429-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="63429-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
