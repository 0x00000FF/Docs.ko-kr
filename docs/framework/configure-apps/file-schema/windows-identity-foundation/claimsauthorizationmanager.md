---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4b4d86204d5f7225f167be125ce017488c851e98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="35a6c-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="35a6c-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="35a6c-103">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="35a6c-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="35a6c-104">\<system.identityModel></span></span>  
<span data-ttu-id="35a6c-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="35a6c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="35a6c-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="35a6c-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a6c-107">구문</span><span class="sxs-lookup"><span data-stu-id="35a6c-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35a6c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="35a6c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="35a6c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35a6c-110">특성</span><span class="sxs-lookup"><span data-stu-id="35a6c-110">Attributes</span></span>  
  
|<span data-ttu-id="35a6c-111">특성</span><span class="sxs-lookup"><span data-stu-id="35a6c-111">Attribute</span></span>|<span data-ttu-id="35a6c-112">설명</span><span class="sxs-lookup"><span data-stu-id="35a6c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35a6c-113">type</span><span class="sxs-lookup"><span data-stu-id="35a6c-113">type</span></span>|<span data-ttu-id="35a6c-114">사용자 지정 형식에서 파생 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="35a6c-115">지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35a6c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="35a6c-116">Child Elements</span></span>  
 <span data-ttu-id="35a6c-117">없을 경우 없습니다 `type` 특성 또는 경우에는 `type` 특성 참조는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthorizationManager> 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35a6c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="35a6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="35a6c-119">요소</span><span class="sxs-lookup"><span data-stu-id="35a6c-119">Element</span></span>|<span data-ttu-id="35a6c-120">설명</span><span class="sxs-lookup"><span data-stu-id="35a6c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35a6c-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="35a6c-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="35a6c-122">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a6c-123">설명</span><span class="sxs-lookup"><span data-stu-id="35a6c-123">Remarks</span></span>  
 <span data-ttu-id="35a6c-124">기본 동작을 통해 제공 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에는 항상 들어오는 클레임 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="35a6c-125">되지 않은 경우 `type` 특성이 지정 된 경우는 `type` 특성 지정는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="35a6c-126">지정할 수는 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용자 지정 동작을 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="35a6c-127">파생된 클래스의 자식 요소를 통해 구성을 지원할 수 있습니다는 `<claimsAuthorizationManager>` 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 메서드 이러한 요소를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="35a6c-128">디자이너 클래스의 최대는 자식 요소에 대해 정의 된 스키마가입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35a6c-129">사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 에서 참조 되는 id 구성 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 요소는 클레임 권한 부여 관리자 및 정책을 확인 하는 데 사용 되는 구성 권한 부여 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="35a6c-130">수동 웹 시나리오 예: Windows Communication Foundation (WCF) 응용 프로그램 또는 응용 프로그램은 웹 기반을 하지 않은 시나리오에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="35a6c-131">응용 프로그램 수동 웹 응용 프로그램이 아닌 경우는 `<claimsAuthorizationManager>` 요소 (및 해당 자식 정책 요소에 있는 경우)의 참조 된 id 구성이 적용 되는 유일한 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="35a6c-132">모든 다른 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-132">All other settings are ignored.</span></span> <span data-ttu-id="35a6c-133">자세한 내용은 참조는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="35a6c-134">설정 하는이 요소는 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35a6c-135">예제</span><span class="sxs-lookup"><span data-stu-id="35a6c-135">Example</span></span>  
 <span data-ttu-id="35a6c-136">다음 XML 클레임 권한 부여에 대 한 구성을 부울 조합을 요청자에 게 리소스에 대해 작업을 수행할 수 있어야 하는 클레임을 지정 하며 각 리소스 작업 쌍으로 구성 정책을 구현 하는 관리자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35a6c-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="35a6c-137">이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드에서 찾을 수 있습니다는 `ClaimsBasedAuthorization` 샘플.</span><span class="sxs-lookup"><span data-stu-id="35a6c-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
