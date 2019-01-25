---
title: '&lt;claimTypeRequirements&gt; 요소의 &lt;clear&gt;'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: c64e5450e01fdb011eb726f3bef1a85a5698d0d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568337"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="2386f-102">&lt;claimTypeRequirements&gt; 요소의 &lt;clear&gt;</span><span class="sxs-lookup"><span data-stu-id="2386f-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="2386f-103">페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="2386f-104">이를 통해 컬렉션이 빈 상태로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="2386f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2386f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2386f-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2386f-106">\<bindings></span></span>  
<span data-ttu-id="2386f-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="2386f-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="2386f-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="2386f-108">\<binding></span></span>  
<span data-ttu-id="2386f-109">\<security></span><span class="sxs-lookup"><span data-stu-id="2386f-109">\<security></span></span>  
<span data-ttu-id="2386f-110">\<message></span><span class="sxs-lookup"><span data-stu-id="2386f-110">\<message></span></span>  
<span data-ttu-id="2386f-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2386f-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2386f-112">구문</span><span class="sxs-lookup"><span data-stu-id="2386f-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2386f-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2386f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2386f-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2386f-115">특성</span><span class="sxs-lookup"><span data-stu-id="2386f-115">Attributes</span></span>  
 <span data-ttu-id="2386f-116">없음</span><span class="sxs-lookup"><span data-stu-id="2386f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2386f-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2386f-117">Child Elements</span></span>  
 <span data-ttu-id="2386f-118">없음</span><span class="sxs-lookup"><span data-stu-id="2386f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2386f-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2386f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2386f-120">요소</span><span class="sxs-lookup"><span data-stu-id="2386f-120">Element</span></span>|<span data-ttu-id="2386f-121">설명</span><span class="sxs-lookup"><span data-stu-id="2386f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2386f-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2386f-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="2386f-123">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="2386f-124">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="2386f-125">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2386f-126">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2386f-127">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2386f-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2386f-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="2386f-128">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
