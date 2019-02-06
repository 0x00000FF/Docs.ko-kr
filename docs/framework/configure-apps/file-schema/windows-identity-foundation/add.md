---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 34643d10ef1ed2e87152e5013634e62859e0594e
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759485"
---
# <a name="add"></a><span data-ttu-id="021d0-101">\<add></span><span class="sxs-lookup"><span data-stu-id="021d0-101">\<add></span></span>
<span data-ttu-id="021d0-102">토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="021d0-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="021d0-103">\<system.identityModel></span></span>  
<span data-ttu-id="021d0-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="021d0-104">\<identityConfiguration></span></span>  
<span data-ttu-id="021d0-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="021d0-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="021d0-106">\<add></span><span class="sxs-lookup"><span data-stu-id="021d0-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021d0-107">구문</span><span class="sxs-lookup"><span data-stu-id="021d0-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="021d0-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="021d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="021d0-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="021d0-110">특성</span><span class="sxs-lookup"><span data-stu-id="021d0-110">Attributes</span></span>  
  
|<span data-ttu-id="021d0-111">특성</span><span class="sxs-lookup"><span data-stu-id="021d0-111">Attribute</span></span>|<span data-ttu-id="021d0-112">설명</span><span class="sxs-lookup"><span data-stu-id="021d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="021d0-113">형식</span><span class="sxs-lookup"><span data-stu-id="021d0-113">type</span></span>|<span data-ttu-id="021d0-114">추가할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="021d0-115">지정 하는 방법에 대 한 자세한 내용은 합니다 `type` 특성을 참조 하십시오 [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="021d0-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="021d0-116">Child Elements</span></span>  
  
|<span data-ttu-id="021d0-117">요소</span><span class="sxs-lookup"><span data-stu-id="021d0-117">Element</span></span>|<span data-ttu-id="021d0-118">설명</span><span class="sxs-lookup"><span data-stu-id="021d0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="021d0-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="021d0-119">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="021d0-120">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="021d0-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="021d0-121">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="021d0-122">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="021d0-123">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="021d0-123">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="021d0-124">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="021d0-125">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="021d0-125">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="021d0-126">에 대 한 선택적 구성을 제공 합니다 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="021d0-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="021d0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="021d0-128">요소</span><span class="sxs-lookup"><span data-stu-id="021d0-128">Element</span></span>|<span data-ttu-id="021d0-129">설명</span><span class="sxs-lookup"><span data-stu-id="021d0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="021d0-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="021d0-130">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="021d0-131">끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="021d0-132">설명</span><span class="sxs-lookup"><span data-stu-id="021d0-132">Remarks</span></span>  
 <span data-ttu-id="021d0-133">`<add>` 요소 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="021d0-134">이것이 처리기 클래스를 통해 참조 되는 여부에 따라 달라 집니다 합니다 `type` 특성을 `<add>` 요소는이 기능에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="021d0-135">이 기능을 제공 하는 토큰 처리기 클래스가 사용 하는 생성자를 노출 해야 합니다는 <xref:System.Xml.XmlElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="021d0-136">이 기능을 제공 수행할 다양 한 기본 제공 보안 토큰 처리기 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="021d0-137">이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>를 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>합니다 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="021d0-138">토큰 처리기 컬렉션에 지정 된 형식의 단일 처리기만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="021d0-139">즉, 예를 들어에서 파생 되는 처리기를 추가 하려는 경우를 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 컬렉션을 먼저 제거 해야 합니다 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>는 컬렉션에서 기본적으로 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="021d0-140">사용할 수 있습니다를 [ \<제거 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) 단일 처리기 사용 하 여 컬렉션에서 제거할 요소의 [ \<지우기 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) 컬렉션에서 모든 처리기를 제거할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-140">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="021d0-141">처리기에 지정 된 설정은 아래에 있는 토큰 처리기 컬렉션에 지정 된 동일한 설정을 재정의 합니다 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소 및 아래에 있는 서비스 수준에서 지정 된 합니다 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="021d0-142">예제</span><span class="sxs-lookup"><span data-stu-id="021d0-142">Example</span></span>  
 <span data-ttu-id="021d0-143">다음 XML의 사용을 보여 줍니다.는 `<add>` 및 `<remove>` 사용자 지정 세션 토큰 처리기를 사용 하 여 기본 세션 토큰 처리기를 바꿀 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="021d0-144">XML에서 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="021d0-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
