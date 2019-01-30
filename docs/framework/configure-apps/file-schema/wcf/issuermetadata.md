---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: c557bd903462ccf4029b7317cbd45610e3fba165
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264455"
---
# <a name="issuermetadata"></a><span data-ttu-id="ec6c3-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="ec6c3-101">\<issuerMetadata></span></span>
<span data-ttu-id="ec6c3-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ec6c3-102">\<system.serviceModel></span></span>  
<span data-ttu-id="ec6c3-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ec6c3-103">\<bindings></span></span>  
<span data-ttu-id="ec6c3-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ec6c3-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="ec6c3-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="ec6c3-105">\<binding></span></span>  
<span data-ttu-id="ec6c3-106">\<security></span><span class="sxs-lookup"><span data-stu-id="ec6c3-106">\<security></span></span>  
<span data-ttu-id="ec6c3-107">\<message></span><span class="sxs-lookup"><span data-stu-id="ec6c3-107">\<message></span></span>  
<span data-ttu-id="ec6c3-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="ec6c3-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6c3-109">구문</span><span class="sxs-lookup"><span data-stu-id="ec6c3-109">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec6c3-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ec6c3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ec6c3-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec6c3-112">특성</span><span class="sxs-lookup"><span data-stu-id="ec6c3-112">Attributes</span></span>  
  
|<span data-ttu-id="ec6c3-113">특성</span><span class="sxs-lookup"><span data-stu-id="ec6c3-113">Attribute</span></span>|<span data-ttu-id="ec6c3-114">설명</span><span class="sxs-lookup"><span data-stu-id="ec6c3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec6c3-115">address</span><span class="sxs-lookup"><span data-stu-id="ec6c3-115">address</span></span>|<span data-ttu-id="ec6c3-116">필수 `string` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="ec6c3-117">끝점의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ec6c3-118">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-118">The address must be an absolute URI.</span></span> <span data-ttu-id="ec6c3-119">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec6c3-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ec6c3-120">Child Elements</span></span>  
  
|<span data-ttu-id="ec6c3-121">요소</span><span class="sxs-lookup"><span data-stu-id="ec6c3-121">Element</span></span>|<span data-ttu-id="ec6c3-122">설명</span><span class="sxs-lookup"><span data-stu-id="ec6c3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec6c3-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="ec6c3-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ec6c3-124">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ec6c3-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="ec6c3-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ec6c3-126">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec6c3-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ec6c3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ec6c3-128">요소</span><span class="sxs-lookup"><span data-stu-id="ec6c3-128">Element</span></span>|<span data-ttu-id="ec6c3-129">설명</span><span class="sxs-lookup"><span data-stu-id="ec6c3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec6c3-130">\<message></span><span class="sxs-lookup"><span data-stu-id="ec6c3-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="ec6c3-131">에 대 한 메시지 수준 보안 설정을 정의 합니다 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec6c3-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec6c3-132">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="ec6c3-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="ec6c3-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ec6c3-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="ec6c3-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ec6c3-135">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="ec6c3-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ec6c3-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="ec6c3-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
