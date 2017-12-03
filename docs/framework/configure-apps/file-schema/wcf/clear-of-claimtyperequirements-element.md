---
title: "&lt;claimTypeRequirements&gt; 요소의 &lt;clear&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a5c3b101c51bcba1c1a579dcf99001c4b8dbab2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="d7697-102">&lt;claimTypeRequirements&gt; 요소의 &lt;clear&gt;</span><span class="sxs-lookup"><span data-stu-id="d7697-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="d7697-103">페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="d7697-104">이를 통해 컬렉션이 빈 상태로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="d7697-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d7697-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7697-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d7697-106">\<bindings></span></span>  
<span data-ttu-id="d7697-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="d7697-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="d7697-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d7697-108">\<binding></span></span>  
<span data-ttu-id="d7697-109">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="d7697-109">\<security></span></span>  
<span data-ttu-id="d7697-110">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="d7697-110">\<message></span></span>  
<span data-ttu-id="d7697-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="d7697-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7697-112">구문</span><span class="sxs-lookup"><span data-stu-id="d7697-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7697-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7697-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d7697-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7697-115">특성</span><span class="sxs-lookup"><span data-stu-id="d7697-115">Attributes</span></span>  
 <span data-ttu-id="d7697-116">없음</span><span class="sxs-lookup"><span data-stu-id="d7697-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7697-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7697-117">Child Elements</span></span>  
 <span data-ttu-id="d7697-118">없음</span><span class="sxs-lookup"><span data-stu-id="d7697-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7697-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7697-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d7697-120">요소</span><span class="sxs-lookup"><span data-stu-id="d7697-120">Element</span></span>|<span data-ttu-id="d7697-121">설명</span><span class="sxs-lookup"><span data-stu-id="d7697-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7697-122">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="d7697-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="d7697-123">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="d7697-124">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="d7697-125">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d7697-126">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d7697-127">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7697-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7697-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7697-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
