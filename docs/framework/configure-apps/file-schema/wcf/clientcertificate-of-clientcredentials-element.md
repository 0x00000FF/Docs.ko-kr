---
title: "&lt;clientCredentials&gt; 요소의 &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 961e745f15b4c7b7ae489a8b2b3128c1a64c6eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="18a41-102">&lt;clientCredentials&gt; 요소의 &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="18a41-102">&lt;clientCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="18a41-103">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-103">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="18a41-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="18a41-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="18a41-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="18a41-105">\<behaviors></span></span>  
<span data-ttu-id="18a41-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="18a41-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="18a41-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="18a41-107">\<behavior></span></span>  
<span data-ttu-id="18a41-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="18a41-108">\<clientCredentials></span></span>  
<span data-ttu-id="18a41-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="18a41-109">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a41-110">구문</span><span class="sxs-lookup"><span data-stu-id="18a41-110">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18a41-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="18a41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="18a41-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18a41-113">특성</span><span class="sxs-lookup"><span data-stu-id="18a41-113">Attributes</span></span>  
  
|<span data-ttu-id="18a41-114">특성</span><span class="sxs-lookup"><span data-stu-id="18a41-114">Attribute</span></span>|<span data-ttu-id="18a41-115">설명</span><span class="sxs-lookup"><span data-stu-id="18a41-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="18a41-116">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="18a41-117">이 특성에 포함된 형식은 `X509FindType` 특성 값의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-117">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="18a41-118">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="18a41-119">클라이언트가 서비스에 자신을 인증하는 데 사용하는 X.509 인증서의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-119">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="18a41-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="18a41-121">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="18a41-122">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="18a41-123">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-123">The default is LocalMachine.</span></span> <span data-ttu-id="18a41-124">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-124">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="18a41-125">검색할 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-125">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="18a41-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="18a41-127">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="18a41-128">-AuthRoot: 인증서 저장소에서 타사 인증 기관 (Ca)입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="18a41-129">-CertificateAuthority: 중개 ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="18a41-130">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="18a41-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="18a41-131">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="18a41-132">-Root: 신뢰할 수 있는 루트 인증 기관 (Ca)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="18a41-133">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="18a41-134">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="18a41-135">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-135">The default is My.</span></span> <span data-ttu-id="18a41-136">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="18a41-137">X509FindType</span><span class="sxs-lookup"><span data-stu-id="18a41-137">X509FindType</span></span>|<span data-ttu-id="18a41-138">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-138">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="18a41-139">`findValue` 특성에 포함된 형식은 이 특성의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-139">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="18a41-140">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="18a41-141">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="18a41-141">-   FindByThumbPrint</span></span><br /><span data-ttu-id="18a41-142">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="18a41-142">-   FindBySubjectName</span></span><br /><span data-ttu-id="18a41-143">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="18a41-143">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="18a41-144">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="18a41-144">-   FindByIssuerName</span></span><br /><span data-ttu-id="18a41-145">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="18a41-145">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="18a41-146">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="18a41-146">-   FindBySerialNumber</span></span><br /><span data-ttu-id="18a41-147">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="18a41-147">-   FindByTimeValid</span></span><br /><span data-ttu-id="18a41-148">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="18a41-148">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="18a41-149">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="18a41-149">-   FindByTemplateName</span></span><br /><span data-ttu-id="18a41-150">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="18a41-150">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="18a41-151">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="18a41-151">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="18a41-152">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="18a41-152">-   FindByExtension</span></span><br /><span data-ttu-id="18a41-153">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="18a41-153">-   FindByKeyUsage</span></span><br /><span data-ttu-id="18a41-154">-Findbysubjectkeyidentifier가</span><span class="sxs-lookup"><span data-stu-id="18a41-154">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="18a41-155">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-155">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="18a41-156">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-156">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18a41-157">자식 요소</span><span class="sxs-lookup"><span data-stu-id="18a41-157">Child Elements</span></span>  
 <span data-ttu-id="18a41-158">없음</span><span class="sxs-lookup"><span data-stu-id="18a41-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18a41-159">부모 요소</span><span class="sxs-lookup"><span data-stu-id="18a41-159">Parent Elements</span></span>  
  
|<span data-ttu-id="18a41-160">요소</span><span class="sxs-lookup"><span data-stu-id="18a41-160">Element</span></span>|<span data-ttu-id="18a41-161">설명</span><span class="sxs-lookup"><span data-stu-id="18a41-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18a41-162">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="18a41-162">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="18a41-163">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-163">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18a41-164">설명</span><span class="sxs-lookup"><span data-stu-id="18a41-164">Remarks</span></span>  
 <span data-ttu-id="18a41-165">이 구성 요소는 이 요소로 클라이언트를 인증하는 데 사용하는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-165">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="18a41-166">[하는 방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18a41-166"> [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a41-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18a41-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="18a41-168">보안 동작</span><span class="sxs-lookup"><span data-stu-id="18a41-168">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="18a41-169">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="18a41-169">How to: Specify Client Credential Values</span></span>](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [<span data-ttu-id="18a41-170">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="18a41-170">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="18a41-171">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="18a41-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="18a41-172">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="18a41-172">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
