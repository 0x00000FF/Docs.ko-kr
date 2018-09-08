---
title: '&lt;wsFederationHttpBinding&gt;의 &lt;message&gt; 요소'
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 820ee7015a51ecc5510889516faef20292cfbc07
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44184717"
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="981ab-102">&lt;wsFederationHttpBinding&gt;의 &lt;message&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="981ab-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="981ab-103">에 대 한 메시지 수준 보안 설정을 정의 합니다 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="981ab-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="981ab-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="981ab-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="981ab-105">\<bindings></span></span>  
<span data-ttu-id="981ab-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="981ab-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="981ab-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="981ab-107">\<binding></span></span>  
<span data-ttu-id="981ab-108">\<security></span><span class="sxs-lookup"><span data-stu-id="981ab-108">\<security></span></span>  
<span data-ttu-id="981ab-109">\<message></span><span class="sxs-lookup"><span data-stu-id="981ab-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981ab-110">구문</span><span class="sxs-lookup"><span data-stu-id="981ab-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="981ab-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="981ab-111">Attributes and Elements</span></span>  
 <span data-ttu-id="981ab-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="981ab-113">특성</span><span class="sxs-lookup"><span data-stu-id="981ab-113">Attributes</span></span>  
  
|<span data-ttu-id="981ab-114">특성</span><span class="sxs-lookup"><span data-stu-id="981ab-114">Attribute</span></span>|<span data-ttu-id="981ab-115">설명</span><span class="sxs-lookup"><span data-stu-id="981ab-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="981ab-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="981ab-116">algorithmSuite</span></span>|<span data-ttu-id="981ab-117">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="981ab-118">이 특성의 유효한 값은 "algorithmSuite 특성" 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="981ab-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="981ab-119">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="981ab-120">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="981ab-121">이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="981ab-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="981ab-122">issuedKeyType</span></span>|<span data-ttu-id="981ab-123">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="981ab-124">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="981ab-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="981ab-125">-   SymmetricKey</span></span><br /><span data-ttu-id="981ab-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="981ab-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="981ab-127">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="981ab-128">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="981ab-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="981ab-129">issuedTokenType</span></span>|<span data-ttu-id="981ab-130">발급될 토큰 형식을 지정하는 URI가 들어 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="981ab-131">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-131">The default is `null`.</span></span>|  
|<span data-ttu-id="981ab-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="981ab-132">negotiateServiceCredential</span></span>|<span data-ttu-id="981ab-133">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="981ab-134">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="981ab-135">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="981ab-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="981ab-136">값</span><span class="sxs-lookup"><span data-stu-id="981ab-136">Value</span></span>|<span data-ttu-id="981ab-137">설명</span><span class="sxs-lookup"><span data-stu-id="981ab-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="981ab-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="981ab-138">Basic128</span></span>|<span data-ttu-id="981ab-139">Basic128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="981ab-140">Basic192</span></span>|<span data-ttu-id="981ab-141">Basic192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="981ab-142">Basic256</span></span>|<span data-ttu-id="981ab-143">Basic256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-144">Basic256Rsa15</span></span>|<span data-ttu-id="981ab-145">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-146">Basic192Rsa15</span></span>|<span data-ttu-id="981ab-147">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="981ab-148">TripleDes</span></span>|<span data-ttu-id="981ab-149">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-150">Basic128Rsa15</span></span>|<span data-ttu-id="981ab-151">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-152">TripleDesRsa15</span></span>|<span data-ttu-id="981ab-153">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="981ab-154">Basic128Sha256</span></span>|<span data-ttu-id="981ab-155">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="981ab-156">Basic192Sha256</span></span>|<span data-ttu-id="981ab-157">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="981ab-158">Basic256Sha256</span></span>|<span data-ttu-id="981ab-159">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="981ab-160">TripleDesSha256</span></span>|<span data-ttu-id="981ab-161">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="981ab-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="981ab-163">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="981ab-165">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="981ab-167">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="981ab-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="981ab-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="981ab-169">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="981ab-170">자식 요소</span><span class="sxs-lookup"><span data-stu-id="981ab-170">Child Elements</span></span>  
  
|<span data-ttu-id="981ab-171">요소</span><span class="sxs-lookup"><span data-stu-id="981ab-171">Element</span></span>|<span data-ttu-id="981ab-172">설명</span><span class="sxs-lookup"><span data-stu-id="981ab-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="981ab-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="981ab-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="981ab-174">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="981ab-175">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="981ab-176">issuer</span><span class="sxs-lookup"><span data-stu-id="981ab-176">issuer</span></span>|<span data-ttu-id="981ab-177">보안 토큰을 발급하는 끝점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="981ab-178">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="981ab-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="981ab-179">issuerMetadata</span></span>|<span data-ttu-id="981ab-180">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="981ab-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="981ab-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="981ab-182">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-182">A collection of token request parameters.</span></span> <span data-ttu-id="981ab-183">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="981ab-184">부모 요소</span><span class="sxs-lookup"><span data-stu-id="981ab-184">Parent Elements</span></span>  
  
|<span data-ttu-id="981ab-185">요소</span><span class="sxs-lookup"><span data-stu-id="981ab-185">Element</span></span>|<span data-ttu-id="981ab-186">설명</span><span class="sxs-lookup"><span data-stu-id="981ab-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="981ab-187">\<security></span><span class="sxs-lookup"><span data-stu-id="981ab-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="981ab-188">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="981ab-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="981ab-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="981ab-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="981ab-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [서비스 및 클라이언트 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="981ab-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="981ab-191">바인딩</span><span class="sxs-lookup"><span data-stu-id="981ab-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="981ab-192">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="981ab-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="981ab-193">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="981ab-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="981ab-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="981ab-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
