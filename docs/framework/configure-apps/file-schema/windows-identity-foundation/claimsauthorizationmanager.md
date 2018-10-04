---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: a745339cffdada56a9b7f27f3f879b9d437c2da2
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793229"
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="4e59f-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="4e59f-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="4e59f-103">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="4e59f-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4e59f-104">\<system.identityModel></span></span>  
<span data-ttu-id="4e59f-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4e59f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="4e59f-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="4e59f-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e59f-107">구문</span><span class="sxs-lookup"><span data-stu-id="4e59f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e59f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e59f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4e59f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e59f-110">특성</span><span class="sxs-lookup"><span data-stu-id="4e59f-110">Attributes</span></span>  
  
|<span data-ttu-id="4e59f-111">특성</span><span class="sxs-lookup"><span data-stu-id="4e59f-111">Attribute</span></span>|<span data-ttu-id="4e59f-112">설명</span><span class="sxs-lookup"><span data-stu-id="4e59f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e59f-113">type</span><span class="sxs-lookup"><span data-stu-id="4e59f-113">type</span></span>|<span data-ttu-id="4e59f-114">사용자 지정 형식에서 파생 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="4e59f-115">지정 하는 방법에 대 한 자세한 내용은 합니다 `type` 특성을 참조 하십시오 [사용자 지정 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e59f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e59f-116">Child Elements</span></span>  
 <span data-ttu-id="4e59f-117">없는 경우 없습니다 `type` 특성을 또는 경우에는 `type` 특성 참조를 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스를 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthorizationManager> 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e59f-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e59f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4e59f-119">요소</span><span class="sxs-lookup"><span data-stu-id="4e59f-119">Element</span></span>|<span data-ttu-id="4e59f-120">설명</span><span class="sxs-lookup"><span data-stu-id="4e59f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e59f-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4e59f-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="4e59f-122">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e59f-123">설명</span><span class="sxs-lookup"><span data-stu-id="4e59f-123">Remarks</span></span>  
 <span data-ttu-id="4e59f-124">기본 동작을 통해 제공 된 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에는 항상 들어오는 클레임 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="4e59f-125">없으면 `type` 특성을 지정 경우는 `type` 특성을 지정 합니다 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="4e59f-126">지정할 수 있습니다 합니다 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용자 지정 동작을 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="4e59f-127">파생된 클래스의 자식 요소를 통해 구성을 지원할 수는 `<claimsAuthorizationManager>` 재정의 하 여 요소를 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="4e59f-128">자식 요소에 대해 정의 된 스키마 클래스의 디자이너에 게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e59f-129">사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 참조 되는 id 구성에서 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 요소는 클레임 권한 부여 관리자와 확인 하는 데 사용 되는 정책 구성 권한 부여를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="4e59f-130">예를 들어 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹을 기반으로 하지 않은 응용 프로그램 수동 웹 시나리오 하지 않은 시나리오에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="4e59f-131">응용 프로그램 수동 웹 응용 프로그램이 아닌 경우는 `<claimsAuthorizationManager>` 요소 (및 해당 자식 정책 요소에 있는 경우) 참조 된 id 구성에 적용 되는 유일한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="4e59f-132">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-132">All other settings are ignored.</span></span> <span data-ttu-id="4e59f-133">자세한 내용은 참조는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="4e59f-134">이 요소에 설정 된 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e59f-135">예제</span><span class="sxs-lookup"><span data-stu-id="4e59f-135">Example</span></span>  
 <span data-ttu-id="4e59f-136">다음 XML을 클레임 권한 부여에 대 한 구성을 요청 자가 리소스에 대해 작업을 수행할 수 있어야 하는 클레임의 부울 조합을 지정 하는 각 리소스 작업 쌍으로 이루어진 정책 구현 하는 관리자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="4e59f-137">이 정책을 사용할 수 있는 클레임 인증 관리자를 구현 하는 코드에서 찾을 수 있습니다는 `ClaimsBasedAuthorization` 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="4e59f-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
