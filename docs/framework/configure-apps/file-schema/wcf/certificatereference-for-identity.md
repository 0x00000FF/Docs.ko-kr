---
title: "&lt;certificateReference&gt;의 &lt;ID&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7728f2ffc74462e43de32b07b819cc2371c9bc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a><span data-ttu-id="89ffb-102">&lt;certificateReference&gt;의 &lt;ID&gt;</span><span class="sxs-lookup"><span data-stu-id="89ffb-102">&lt;certificateReference&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="89ffb-103">X.509 인증서 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-103">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="89ffb-104">이 ID를 가진 끝점과 연결되는 보안 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트는 서버가 나타내는 클레임이 이 ID를 생성하는 데 사용된 ID 클레임을 포함함을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-104">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity verifies that the claims presented by the server contain the identity claim used to construct this identity.</span></span>  
  
 <span data-ttu-id="89ffb-105">\<identity ></span><span class="sxs-lookup"><span data-stu-id="89ffb-105">\<identity></span></span>  
<span data-ttu-id="89ffb-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="89ffb-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89ffb-107">구문</span><span class="sxs-lookup"><span data-stu-id="89ffb-107">Syntax</span></span>  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89ffb-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="89ffb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89ffb-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89ffb-110">특성</span><span class="sxs-lookup"><span data-stu-id="89ffb-110">Attributes</span></span>  
  
|<span data-ttu-id="89ffb-111">특성</span><span class="sxs-lookup"><span data-stu-id="89ffb-111">Attribute</span></span>|<span data-ttu-id="89ffb-112">설명</span><span class="sxs-lookup"><span data-stu-id="89ffb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89ffb-113">findValue</span><span class="sxs-lookup"><span data-stu-id="89ffb-113">findValue</span></span>|<span data-ttu-id="89ffb-114">X.509 인증서 저장소에서 검색할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-114">Specifies the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="89ffb-115">이 특성에 포함된 형식은 지정된 `X509FindType` 값의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-115">The type contained in this attribute must satisfy the requirements of the specified `X509FindType` value.</span></span> <span data-ttu-id="89ffb-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-116">The default is an empty string.</span></span>|  
|<span data-ttu-id="89ffb-117">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="89ffb-117">isChainIncluded</span></span>|<span data-ttu-id="89ffb-118">유효성 검사에서 인증서 체인을 사용하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-118">A Boolean value that specifies if the validation is done using a certificate chain.</span></span>|  
|<span data-ttu-id="89ffb-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="89ffb-119">storeLocation</span></span>|<span data-ttu-id="89ffb-120">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용할 수 있는 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-120">Specifies the location of the certificate store that the client can use to validate the server’s certificate.</span></span><br /><br /> <span data-ttu-id="89ffb-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="89ffb-122">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-122">-   LocalMachine: The cert store assigned to the local machine.</span></span><br /><span data-ttu-id="89ffb-123">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-123">-   CurrentUser: The cert store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="89ffb-124">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-124">The default value is LocalMachine.</span></span><br /><br /> <span data-ttu-id="89ffb-125">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-125">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|<span data-ttu-id="89ffb-126">storeName</span><span class="sxs-lookup"><span data-stu-id="89ffb-126">storeName</span></span>|<span data-ttu-id="89ffb-127">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-127">Specifies the name of the X.509 certificate store to open.</span></span><br /><br /> <span data-ttu-id="89ffb-128">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="89ffb-129">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-129">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="89ffb-130">-AuthRoot: 인증서 저장소 공급 업체 Ca (인증 기관)입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-130">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="89ffb-131">-CertificateAuthority: 중개 Ca에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-131">-   CertificateAuthority: Certificate store for intermediate CAs.</span></span><br /><span data-ttu-id="89ffb-132">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="89ffb-132">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="89ffb-133">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-133">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="89ffb-134">-Root: 신뢰할 수 있는 루트 Ca에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-134">-   Root: Certificate store for trusted root CAs.</span></span><br /><span data-ttu-id="89ffb-135">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-135">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="89ffb-136">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-136">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="89ffb-137">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-137">The default value is My.</span></span><br /><br /> <span data-ttu-id="89ffb-138">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-138">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="89ffb-139">X509FindType</span><span class="sxs-lookup"><span data-stu-id="89ffb-139">X509FindType</span></span>|<span data-ttu-id="89ffb-140">실행할 X.509 검색의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-140">Specifies the type of X.509 search to be executed.</span></span> <span data-ttu-id="89ffb-141">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-141">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="89ffb-142">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="89ffb-143">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="89ffb-143">-   FindByThumbPrint</span></span><br /><span data-ttu-id="89ffb-144">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="89ffb-144">-   FindBySubjectName</span></span><br /><span data-ttu-id="89ffb-145">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="89ffb-145">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="89ffb-146">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="89ffb-146">-   FindByIssuerName</span></span><br /><span data-ttu-id="89ffb-147">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="89ffb-147">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="89ffb-148">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="89ffb-148">-   FindBySerialNumber</span></span><br /><span data-ttu-id="89ffb-149">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="89ffb-149">-   FindByTimeValid</span></span><br /><span data-ttu-id="89ffb-150">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="89ffb-150">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="89ffb-151">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="89ffb-151">-   FindByTemplateName</span></span><br /><span data-ttu-id="89ffb-152">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="89ffb-152">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="89ffb-153">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="89ffb-153">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="89ffb-154">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="89ffb-154">-   FindByExtension</span></span><br /><span data-ttu-id="89ffb-155">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="89ffb-155">-   FindByKeyUsage</span></span><br /><span data-ttu-id="89ffb-156">-Findbysubjectkeyidentifier가</span><span class="sxs-lookup"><span data-stu-id="89ffb-156">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="89ffb-157">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-157">The default value is FindBySubjectDistinguishedName.</span></span><br /><br /> <span data-ttu-id="89ffb-158">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-158">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89ffb-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89ffb-159">Child Elements</span></span>  
 <span data-ttu-id="89ffb-160">없음</span><span class="sxs-lookup"><span data-stu-id="89ffb-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89ffb-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89ffb-161">Parent Elements</span></span>  
  
|<span data-ttu-id="89ffb-162">요소</span><span class="sxs-lookup"><span data-stu-id="89ffb-162">Element</span></span>|<span data-ttu-id="89ffb-163">설명</span><span class="sxs-lookup"><span data-stu-id="89ffb-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89ffb-164">\<identity ></span><span class="sxs-lookup"><span data-stu-id="89ffb-164">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="89ffb-165">한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ffb-165">Specifies settings that enable the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89ffb-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89ffb-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>
