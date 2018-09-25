---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: e63f02add81495e474b59b6c5cc090bd69add3d2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082989"
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="aa0de-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="aa0de-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="aa0de-103">끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="aa0de-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aa0de-104">\<system.identityModel></span></span>  
<span data-ttu-id="aa0de-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aa0de-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aa0de-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="aa0de-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa0de-107">구문</span><span class="sxs-lookup"><span data-stu-id="aa0de-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa0de-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aa0de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa0de-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa0de-110">특성</span><span class="sxs-lookup"><span data-stu-id="aa0de-110">Attributes</span></span>  
  
|<span data-ttu-id="aa0de-111">특성</span><span class="sxs-lookup"><span data-stu-id="aa0de-111">Attribute</span></span>|<span data-ttu-id="aa0de-112">설명</span><span class="sxs-lookup"><span data-stu-id="aa0de-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa0de-113">name</span><span class="sxs-lookup"><span data-stu-id="aa0de-113">name</span></span>|<span data-ttu-id="aa0de-114">토큰 처리기 컬렉션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="aa0de-115">프레임 워크에서 인식 유일한 값은 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="aa0de-116">토큰 처리기 컬렉션은 이러한 이름 중 하나를 사용 하 여 지정 된 경우에 각각 토큰 ActAs 또는 OnBehalfOf를 처리 하는 경우 컬렉션 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa0de-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aa0de-117">Child Elements</span></span>  
  
|<span data-ttu-id="aa0de-118">요소</span><span class="sxs-lookup"><span data-stu-id="aa0de-118">Element</span></span>|<span data-ttu-id="aa0de-119">설명</span><span class="sxs-lookup"><span data-stu-id="aa0de-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa0de-120">\<add></span><span class="sxs-lookup"><span data-stu-id="aa0de-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="aa0de-121">토큰 처리기 컬렉션에는 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="aa0de-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="aa0de-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="aa0de-123">토큰 처리기 컬렉션에서 모든 보안 토큰 처리기를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="aa0de-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="aa0de-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="aa0de-125">토큰 처리기 컬렉션에서 보안 토큰 처리기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="aa0de-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="aa0de-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="aa0de-127">토큰 처리기 컬렉션에 대 한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa0de-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aa0de-128">Parent Elements</span></span>  
  
|<span data-ttu-id="aa0de-129">요소</span><span class="sxs-lookup"><span data-stu-id="aa0de-129">Element</span></span>|<span data-ttu-id="aa0de-130">설명</span><span class="sxs-lookup"><span data-stu-id="aa0de-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa0de-131">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="aa0de-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="aa0de-132">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa0de-133">설명</span><span class="sxs-lookup"><span data-stu-id="aa0de-133">Remarks</span></span>  
 <span data-ttu-id="aa0de-134">서비스 구성에서 하나 이상의 명명 된 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="aa0de-135">사용 하 여 컬렉션의 이름을 지정할 수 있습니다는 `name` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="aa0de-136">프레임 워크를 처리 하는 유일한 이름에는 "ActAs" 및 "OnBehalfOf"입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="aa0de-137">이러한 컬렉션의 처리기가 없는 경우 사용할 보안 토큰 서비스 (STS)에서 기본 처리기를 대신 처리 하는 동안 `ActAs` 고 `OnBehalfOf` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="aa0de-138">기본적으로 컬렉션 채워집니다 처리기 형식은: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>를 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="aa0de-139">사용 하 여 컬렉션을 수정할 수는 `<add>`, `<remove>`, 및 `<clear>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="aa0de-140">특정 형식의 단일 처리기만 컬렉션에 있는지를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="aa0de-141">예를 들어에서 처리기를 파생 하는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 하거나 클래스 처리기 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 단일 컬렉션, 하지만 둘 다에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="aa0de-142">사용 된 `<securityTokenHandlerConfiguration>` 컬렉션의 처리기에 대 한 구성 설정을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="aa0de-143">이 요소를 통해 지정 된 설정을 재정의 통해 서비스에 지정 된 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="aa0de-144">일부 처리기 (몇 가지 기본 제공 처리기 형식을 포함)의 자식 요소를 통해 추가 구성을 지원할 수는 `<add>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="aa0de-145">처리기에 지정 된 설정은 컬렉션 또는 서비스에서 지정 된 해당 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0de-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
