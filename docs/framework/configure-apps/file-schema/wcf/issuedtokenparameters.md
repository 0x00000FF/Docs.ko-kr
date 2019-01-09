---
title: '&lt;IssuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 2060f98e94cec9e656420ac073204a82bc592b92
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149243"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="7acee-102">&lt;IssuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="7acee-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="7acee-103">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="7acee-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7acee-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7acee-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="7acee-105">\<bindings></span></span>  
<span data-ttu-id="7acee-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7acee-106">\<customBinding></span></span>  
<span data-ttu-id="7acee-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="7acee-107">\<binding></span></span>  
<span data-ttu-id="7acee-108">\<security></span><span class="sxs-lookup"><span data-stu-id="7acee-108">\<security></span></span>  
<span data-ttu-id="7acee-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="7acee-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7acee-110">구문</span><span class="sxs-lookup"><span data-stu-id="7acee-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="7acee-111">형식</span><span class="sxs-lookup"><span data-stu-id="7acee-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7acee-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7acee-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7acee-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7acee-114">특성</span><span class="sxs-lookup"><span data-stu-id="7acee-114">Attributes</span></span>  
  
|<span data-ttu-id="7acee-115">특성</span><span class="sxs-lookup"><span data-stu-id="7acee-115">Attribute</span></span>|<span data-ttu-id="7acee-116">설명</span><span class="sxs-lookup"><span data-stu-id="7acee-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7acee-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="7acee-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="7acee-118">바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="7acee-119">이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="7acee-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="7acee-120">inclusionMode</span></span>|<span data-ttu-id="7acee-121">토큰 포함 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="7acee-122">이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="7acee-123">keySize</span><span class="sxs-lookup"><span data-stu-id="7acee-123">keySize</span></span>|<span data-ttu-id="7acee-124">토큰 키 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="7acee-125">기본값은 256입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-125">The default value is 256.</span></span>|  
|<span data-ttu-id="7acee-126">keyType</span><span class="sxs-lookup"><span data-stu-id="7acee-126">keyType</span></span>|<span data-ttu-id="7acee-127">키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="7acee-128">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="7acee-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="7acee-129">tokenType</span></span>|<span data-ttu-id="7acee-130">토큰 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-130">A string that specifies the token type.</span></span> <span data-ttu-id="7acee-131">기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7acee-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7acee-132">Child Elements</span></span>  
  
|<span data-ttu-id="7acee-133">요소</span><span class="sxs-lookup"><span data-stu-id="7acee-133">Element</span></span>|<span data-ttu-id="7acee-134">설명</span><span class="sxs-lookup"><span data-stu-id="7acee-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7acee-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="7acee-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="7acee-136">추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="7acee-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7acee-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="7acee-138">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="7acee-139">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7acee-140">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7acee-141">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="7acee-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="7acee-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="7acee-143">현재 토큰을 발급하는 엔드포인트를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="7acee-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="7acee-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="7acee-145">토큰 발급자의 메타데이터의 엔드포인트 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7acee-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7acee-146">Parent Elements</span></span>  
  
|<span data-ttu-id="7acee-147">요소</span><span class="sxs-lookup"><span data-stu-id="7acee-147">Element</span></span>|<span data-ttu-id="7acee-148">설명</span><span class="sxs-lookup"><span data-stu-id="7acee-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7acee-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="7acee-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="7acee-150">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="7acee-151">\<security></span><span class="sxs-lookup"><span data-stu-id="7acee-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="7acee-152">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7acee-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7acee-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7acee-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="7acee-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="7acee-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7acee-155">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="7acee-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="7acee-156">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="7acee-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="7acee-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7acee-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="7acee-158">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="7acee-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="7acee-159">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="7acee-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="7acee-160">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="7acee-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="7acee-161">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="7acee-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="7acee-162">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="7acee-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="7acee-163">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="7acee-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
