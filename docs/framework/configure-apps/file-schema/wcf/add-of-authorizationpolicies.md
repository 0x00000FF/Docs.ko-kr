---
title: "&lt;authorizationPolicies&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72af0529cea2e6810bdb7a518874a313e3ceab40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="bdd58-102">&lt;authorizationPolicies&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="bdd58-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="bdd58-103">클레임 변형에 대한 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="bdd58-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bdd58-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bdd58-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="bdd58-105">\<behaviors></span></span>  
<span data-ttu-id="bdd58-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="bdd58-106">\<behavior></span></span>  
<span data-ttu-id="bdd58-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="bdd58-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="bdd58-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="bdd58-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="bdd58-109">\<add></span><span class="sxs-lookup"><span data-stu-id="bdd58-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd58-110">구문</span><span class="sxs-lookup"><span data-stu-id="bdd58-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## <a name="type"></a><span data-ttu-id="bdd58-111">형식</span><span class="sxs-lookup"><span data-stu-id="bdd58-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdd58-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bdd58-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bdd58-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdd58-114">특성</span><span class="sxs-lookup"><span data-stu-id="bdd58-114">Attributes</span></span>  
  
|<span data-ttu-id="bdd58-115">특성</span><span class="sxs-lookup"><span data-stu-id="bdd58-115">Attribute</span></span>|<span data-ttu-id="bdd58-116">설명</span><span class="sxs-lookup"><span data-stu-id="bdd58-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="bdd58-117">필수 String 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="bdd58-118">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 액세스 제어 모델은 권한 부여 정책 집합을 형식으로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-118">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="bdd58-119">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 권한 부여 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="bdd58-120">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdd58-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bdd58-121">Child Elements</span></span>  
 <span data-ttu-id="bdd58-122">없음</span><span class="sxs-lookup"><span data-stu-id="bdd58-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdd58-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bdd58-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bdd58-124">요소</span><span class="sxs-lookup"><span data-stu-id="bdd58-124">Element</span></span>|<span data-ttu-id="bdd58-125">설명</span><span class="sxs-lookup"><span data-stu-id="bdd58-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdd58-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="bdd58-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="bdd58-127">권한 부여 정책 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdd58-128">설명</span><span class="sxs-lookup"><span data-stu-id="bdd58-128">Remarks</span></span>  
 <span data-ttu-id="bdd58-129">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="bdd58-130">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="bdd58-131">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="bdd58-132">권한 부여 정책 작동 하는 방법에 대 한 자세한 내용은 참조 하십시오. <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 [권한 부여 정책](../../../../../docs/framework/wcf/samples/authorization-policy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd58-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd58-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdd58-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="bdd58-134">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="bdd58-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="bdd58-135">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="bdd58-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="bdd58-136">\<add></span><span class="sxs-lookup"><span data-stu-id="bdd58-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="bdd58-137">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="bdd58-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
