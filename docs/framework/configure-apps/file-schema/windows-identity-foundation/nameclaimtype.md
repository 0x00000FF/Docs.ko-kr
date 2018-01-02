---
title: '&lt;nameClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 2c53886458b4c6e2867e1f9fddd4ab50b199c660
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="9060c-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="9060c-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="9060c-103">클레임 유형을 지정 하는 설정의 <xref:System.Security.Principal.IIdentity.Name%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="9060c-104">클레임 유형을 검색 하기 위해 사용 되는 <xref:System.Security.Claims.Claim> 의 컬렉션에서 <xref:System.Security.Claims.ClaimsIdentity> 에서 반환 된 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 이 토큰 처리기의 메서드.</span><span class="sxs-lookup"><span data-stu-id="9060c-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="9060c-105">일치 하는 클레임 값의 이름으로 설정 됩니다는 <xref:System.Security.Principal.IIdentity> 토큰 처리기에서 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="9060c-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9060c-106">\<system.identityModel></span></span>  
<span data-ttu-id="9060c-107">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9060c-107">\<identityConfiguration></span></span>  
<span data-ttu-id="9060c-108">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="9060c-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9060c-109">\<add></span><span class="sxs-lookup"><span data-stu-id="9060c-109">\<add></span></span>  
<span data-ttu-id="9060c-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="9060c-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="9060c-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="9060c-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9060c-112">구문</span><span class="sxs-lookup"><span data-stu-id="9060c-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9060c-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9060c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9060c-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9060c-115">특성</span><span class="sxs-lookup"><span data-stu-id="9060c-115">Attributes</span></span>  
  
|<span data-ttu-id="9060c-116">특성</span><span class="sxs-lookup"><span data-stu-id="9060c-116">Attribute</span></span>|<span data-ttu-id="9060c-117">설명</span><span class="sxs-lookup"><span data-stu-id="9060c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9060c-118">값</span><span class="sxs-lookup"><span data-stu-id="9060c-118">value</span></span>|<span data-ttu-id="9060c-119">에 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열은 <xref:System.Security.Principal.IIdentity.Name%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="9060c-120">필수.</span><span class="sxs-lookup"><span data-stu-id="9060c-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9060c-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9060c-121">Child Elements</span></span>  
 <span data-ttu-id="9060c-122">없음</span><span class="sxs-lookup"><span data-stu-id="9060c-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9060c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9060c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9060c-124">요소</span><span class="sxs-lookup"><span data-stu-id="9060c-124">Element</span></span>|<span data-ttu-id="9060c-125">설명</span><span class="sxs-lookup"><span data-stu-id="9060c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9060c-126">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="9060c-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="9060c-127">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9060c-128">설명</span><span class="sxs-lookup"><span data-stu-id="9060c-128">Remarks</span></span>  
 <span data-ttu-id="9060c-129">`<nameClaimType>` 요소 집합에서 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> 속성 때는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9060c-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9060c-130">예</span><span class="sxs-lookup"><span data-stu-id="9060c-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9060c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9060c-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
