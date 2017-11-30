---
title: '&lt;certificateReference&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c8acf4b6d6e6e8a0fcf7d73139a1d2c5ea03f063
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="b990d-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="b990d-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="b990d-103">찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="b990d-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="b990d-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="b990d-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b990d-105">\<federationConfiguration></span></span>  
<span data-ttu-id="b990d-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="b990d-106">\<serviceCertificate></span></span>  
<span data-ttu-id="b990d-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="b990d-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b990d-108">구문</span><span class="sxs-lookup"><span data-stu-id="b990d-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b990d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b990d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b990d-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b990d-111">특성</span><span class="sxs-lookup"><span data-stu-id="b990d-111">Attributes</span></span>  
  
|<span data-ttu-id="b990d-112">특성</span><span class="sxs-lookup"><span data-stu-id="b990d-112">Attribute</span></span>|<span data-ttu-id="b990d-113">설명</span><span class="sxs-lookup"><span data-stu-id="b990d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b990d-114">storeName</span><span class="sxs-lookup"><span data-stu-id="b990d-114">storeName</span></span>|<span data-ttu-id="b990d-115">X.509 인증서 저장소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="b990d-116">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-116">The default is "My".</span></span> <span data-ttu-id="b990d-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-117">Optional.</span></span>|  
|<span data-ttu-id="b990d-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="b990d-118">storeLocation</span></span>|<span data-ttu-id="b990d-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소의 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="b990d-120">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="b990d-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-121">Optional.</span></span>|  
|<span data-ttu-id="b990d-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="b990d-122">x509FindType</span></span>|<span data-ttu-id="b990d-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 실행할 검색 유형을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="b990d-124">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="b990d-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-125">Optional.</span></span>|  
|<span data-ttu-id="b990d-126">findValue</span><span class="sxs-lookup"><span data-stu-id="b990d-126">findValue</span></span>|<span data-ttu-id="b990d-127">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="b990d-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-128">Optional.</span></span>|  
|<span data-ttu-id="b990d-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="b990d-129">isChainIncluded</span></span>|<span data-ttu-id="b990d-130">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="b990d-131">기본값은 "true"; 유효성 검사 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="b990d-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b990d-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b990d-133">Child Elements</span></span>  
 <span data-ttu-id="b990d-134">없음</span><span class="sxs-lookup"><span data-stu-id="b990d-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b990d-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b990d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="b990d-136">요소</span><span class="sxs-lookup"><span data-stu-id="b990d-136">Element</span></span>|<span data-ttu-id="b990d-137">설명</span><span class="sxs-lookup"><span data-stu-id="b990d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b990d-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="b990d-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="b990d-139">암호화 및 토큰 암호 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b990d-140">설명</span><span class="sxs-lookup"><span data-stu-id="b990d-140">Remarks</span></span>  
 <span data-ttu-id="b990d-141">`<certificateReference>` 요소를 찾아서 인증서 저장소에서 X.509 인증서 유효성 검사에 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="b990d-142">자식 요소로 지정 된 경우는 `<serviceCertficate>` 요소로, 암호화 및 토큰 암호 해독 하는 데 사용 되는 X.509 인증서의 위치 및 인증 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="b990d-143">`<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b990d-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
