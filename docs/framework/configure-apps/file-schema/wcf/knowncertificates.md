---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 4c1dc15621138aa692f0a30d285f729c2bd670d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274120"
---
# <a name="knowncertificates"></a><span data-ttu-id="41683-101">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="41683-101">\<knownCertificates></span></span>
<span data-ttu-id="41683-102">STS(보안 토큰 서비스)에서 발급한 보안 자격 증명을 인증하기 위해 제공된 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41683-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="41683-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="41683-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="41683-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="41683-104">\<behaviors></span></span>  
<span data-ttu-id="41683-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="41683-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="41683-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="41683-106">\<behavior></span></span>  
<span data-ttu-id="41683-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="41683-107">\<serviceCredentials></span></span>  
<span data-ttu-id="41683-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="41683-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="41683-109">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="41683-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41683-110">구문</span><span class="sxs-lookup"><span data-stu-id="41683-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41683-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="41683-111">Attributes and Elements</span></span>  
 <span data-ttu-id="41683-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41683-113">특성</span><span class="sxs-lookup"><span data-stu-id="41683-113">Attributes</span></span>  
 <span data-ttu-id="41683-114">없음</span><span class="sxs-lookup"><span data-stu-id="41683-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41683-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="41683-115">Child Elements</span></span>  
  
|<span data-ttu-id="41683-116">요소</span><span class="sxs-lookup"><span data-stu-id="41683-116">Element</span></span>|<span data-ttu-id="41683-117">설명</span><span class="sxs-lookup"><span data-stu-id="41683-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41683-118">\<add></span><span class="sxs-lookup"><span data-stu-id="41683-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="41683-119">컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41683-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="41683-120">Parent Elements</span></span>  
  
|<span data-ttu-id="41683-121">요소</span><span class="sxs-lookup"><span data-stu-id="41683-121">Element</span></span>|<span data-ttu-id="41683-122">설명</span><span class="sxs-lookup"><span data-stu-id="41683-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41683-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="41683-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="41683-124">서비스 자격 증명으로 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41683-125">설명</span><span class="sxs-lookup"><span data-stu-id="41683-125">Remarks</span></span>  
 <span data-ttu-id="41683-126">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41683-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="41683-127">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트 라고 한 *보안 토큰 서비스*합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="41683-128">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="41683-129">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41683-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="41683-130">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="41683-131">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="41683-132">합니다 [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="41683-132">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="41683-133">인증서를 추가 하려면 사용 합니다 [ \<knownCertificates > 요소](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-133">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="41683-134">삽입 된 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예와에서 같이 각 인증서에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-134">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="41683-135">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="41683-136">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="41683-137">이 구성 요소를 사용 하 여 자세한 정보 뿐만 아니라 페더레이션된 서비스에 의해 인증 되어야 클라이언트에 대 한 필수 조건, 참조 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="41683-138">페더레이션된 시나리오에 대 한 자세한 내용은 참조 하세요. [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="41683-139">구성에서 컬렉션을 채우는 방법을 보여 주는 예제를 보려면 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41683-139">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41683-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="41683-140">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="41683-141">\<add></span><span class="sxs-lookup"><span data-stu-id="41683-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="41683-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="41683-142">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="41683-143">보안 동작</span><span class="sxs-lookup"><span data-stu-id="41683-143">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="41683-144">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="41683-144">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="41683-145">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="41683-145">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="41683-146">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="41683-146">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="41683-147">\<add></span><span class="sxs-lookup"><span data-stu-id="41683-147">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="41683-148">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="41683-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
