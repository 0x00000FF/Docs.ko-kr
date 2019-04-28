---
title: <certificate> <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 98e60d750dad1529ffb35055d26e278ceb7c873a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704351"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="799bf-102">\<인증서 >의 \<clientCertificate > 요소</span><span class="sxs-lookup"><span data-stu-id="799bf-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="799bf-103">메시지 서명 및 암호화에 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="799bf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="799bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="799bf-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="799bf-105">\<behaviors></span></span>  
<span data-ttu-id="799bf-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="799bf-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="799bf-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="799bf-107">\<behavior></span></span>  
<span data-ttu-id="799bf-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="799bf-108">\<serviceCredentials></span></span>  
<span data-ttu-id="799bf-109">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="799bf-109">\<clientCertificate></span></span>  
<span data-ttu-id="799bf-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="799bf-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799bf-111">구문</span><span class="sxs-lookup"><span data-stu-id="799bf-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="799bf-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="799bf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="799bf-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="799bf-114">특성</span><span class="sxs-lookup"><span data-stu-id="799bf-114">Attributes</span></span>  
  
|<span data-ttu-id="799bf-115">특성</span><span class="sxs-lookup"><span data-stu-id="799bf-115">Attribute</span></span>|<span data-ttu-id="799bf-116">설명</span><span class="sxs-lookup"><span data-stu-id="799bf-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="799bf-117">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="799bf-118">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="799bf-119">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="799bf-120">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="799bf-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="799bf-122">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="799bf-123">-CurrentUser: 현재 사용자에 게 할당 하는 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="799bf-124">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="799bf-125">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="799bf-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="799bf-127">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="799bf-128">-   AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="799bf-129">-   CertificationAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="799bf-130">-허용 되지 않습니다. 해지 된 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="799bf-131">-내: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="799bf-132">-   Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="799bf-133">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="799bf-134">-   TrustedPublisher: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="799bf-135">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="799bf-136">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="799bf-137">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="799bf-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="799bf-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="799bf-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="799bf-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="799bf-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="799bf-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="799bf-141">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="799bf-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="799bf-142">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="799bf-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="799bf-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="799bf-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="799bf-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="799bf-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="799bf-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="799bf-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="799bf-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="799bf-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="799bf-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="799bf-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="799bf-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="799bf-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="799bf-149">-   FindByExtension</span><span class="sxs-lookup"><span data-stu-id="799bf-149">-   FindByExtension</span></span><br /><span data-ttu-id="799bf-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="799bf-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="799bf-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="799bf-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="799bf-152">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="799bf-153">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="799bf-154">자식 요소</span><span class="sxs-lookup"><span data-stu-id="799bf-154">Child Elements</span></span>  
 <span data-ttu-id="799bf-155">없음</span><span class="sxs-lookup"><span data-stu-id="799bf-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="799bf-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="799bf-156">Parent Elements</span></span>  
  
|<span data-ttu-id="799bf-157">요소</span><span class="sxs-lookup"><span data-stu-id="799bf-157">Element</span></span>|<span data-ttu-id="799bf-158">설명</span><span class="sxs-lookup"><span data-stu-id="799bf-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="799bf-159">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="799bf-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="799bf-160">설명</span><span class="sxs-lookup"><span data-stu-id="799bf-160">Remarks</span></span>  
 <span data-ttu-id="799bf-161">서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 `<certificate>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="799bf-162">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="799bf-163">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="799bf-164">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="799bf-165">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="799bf-166">이중 서비스에 대 한 자세한 내용은 참조 하세요. [방법: 이중 계약 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="799bf-167">예제</span><span class="sxs-lookup"><span data-stu-id="799bf-167">Example</span></span>  
 <span data-ttu-id="799bf-168">다음 코드에서는 적절한 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="799bf-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="799bf-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="799bf-169">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="799bf-170">보안 동작</span><span class="sxs-lookup"><span data-stu-id="799bf-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="799bf-171">방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="799bf-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="799bf-172">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="799bf-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
