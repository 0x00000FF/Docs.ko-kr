---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: f23f0103e228bc23a06a3ff0e0c5c2a12bdae73f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748105"
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="15d4e-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="15d4e-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="15d4e-103">토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="15d4e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="15d4e-104">\<system.identityModel></span></span>  
<span data-ttu-id="15d4e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="15d4e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="15d4e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="15d4e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="15d4e-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="15d4e-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="15d4e-108">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="15d4e-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d4e-109">구문</span><span class="sxs-lookup"><span data-stu-id="15d4e-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15d4e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="15d4e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="15d4e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15d4e-112">특성</span><span class="sxs-lookup"><span data-stu-id="15d4e-112">Attributes</span></span>  
  
|<span data-ttu-id="15d4e-113">특성</span><span class="sxs-lookup"><span data-stu-id="15d4e-113">Attribute</span></span>|<span data-ttu-id="15d4e-114">설명</span><span class="sxs-lookup"><span data-stu-id="15d4e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15d4e-115">형식</span><span class="sxs-lookup"><span data-stu-id="15d4e-115">type</span></span>|<span data-ttu-id="15d4e-116">형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="15d4e-117">사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d4e-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15d4e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15d4e-118">Child Elements</span></span>  
  
|<span data-ttu-id="15d4e-119">요소</span><span class="sxs-lookup"><span data-stu-id="15d4e-119">Element</span></span>|<span data-ttu-id="15d4e-120">설명</span><span class="sxs-lookup"><span data-stu-id="15d4e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15d4e-121">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="15d4e-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="15d4e-122">경우는 `type` 구성 기반 발급자 이름 레지스트리를 지정 하는 특성 (합니다 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스)의 [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="15d4e-123">합니다 [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소 들 `<add>`를 `<clear>`, 또는 `<remove>` 자식 요소로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15d4e-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15d4e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="15d4e-125">요소</span><span class="sxs-lookup"><span data-stu-id="15d4e-125">Element</span></span>|<span data-ttu-id="15d4e-126">설명</span><span class="sxs-lookup"><span data-stu-id="15d4e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15d4e-127">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="15d4e-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="15d4e-128">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15d4e-129">설명</span><span class="sxs-lookup"><span data-stu-id="15d4e-129">Remarks</span></span>  
 <span data-ttu-id="15d4e-130">모든 발급자 토큰 발급자 이름 레지스트리를 사용 하 여 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="15d4e-131">이것은에서 파생 되는 개체는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="15d4e-132">발급자 이름 레지스트리는 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 암호화 자료에 니모닉 이름을 연결 하 여 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="15d4e-133">발급자 이름 레지스트리 신뢰 당사자 (RP) 응용 프로그램에서 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="15d4e-134">발급자 이름 레지스트리 형식을 사용 하 여 지정 된 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="15d4e-135">`<issuerNameRegistry>` 요소는 지정된 된 형식에 대 한 구성을 제공 하는 하나 이상의 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="15d4e-136">재정의 하 여 이러한 하위 요소를 처리 하는 논리를 제공 합니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="15d4e-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="15d4e-137">WIF는 제공 단일 발급자 이름 레지스트리 형식 기본적으로 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="15d4e-138">이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="15d4e-139">자식 구성 요소에 필요한 `<trustedIssuers>`, 아래에 있는 신뢰할 수 있는 발급자 인증서의 컬렉션 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="15d4e-140">ASN.1을 사용 하 여 인코딩된 인증서 지문 및 추가 또는 제거 컬렉션에서 사용 하 여 지정 된 인증서를 신뢰할 수 있는 `<add>`하십시오 `<clear>`, 또는 `<remove>` 요소.</span><span class="sxs-lookup"><span data-stu-id="15d4e-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="15d4e-141">합니다 `<issuerNameRegistry>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15d4e-142">지정 된 `<issuerNameRegistry>` 의 자식 요소로 요소를 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소에 사용 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="15d4e-143">설정 합니다 `<securityTokenHandlerConfiguration>` 요소에 있는 구성을 재정의 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15d4e-144">예제</span><span class="sxs-lookup"><span data-stu-id="15d4e-144">Example</span></span>  
 <span data-ttu-id="15d4e-145">다음 XML 기반 구성을 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15d4e-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15d4e-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="15d4e-146">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
