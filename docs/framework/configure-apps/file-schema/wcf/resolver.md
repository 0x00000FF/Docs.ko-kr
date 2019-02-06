---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f3d4b049afe55fb9fb80cbad56c49e8ec13e60db
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758744"
---
# <a name="resolver"></a><span data-ttu-id="eb450-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="eb450-101">\<resolver></span></span>
<span data-ttu-id="eb450-102">피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="eb450-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb450-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb450-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="eb450-104">\<bindings></span></span>  
<span data-ttu-id="eb450-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="eb450-105">\<netPeerBinding></span></span>  
<span data-ttu-id="eb450-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="eb450-106">\<binding></span></span>  
<span data-ttu-id="eb450-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="eb450-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb450-108">구문</span><span class="sxs-lookup"><span data-stu-id="eb450-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb450-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb450-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eb450-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb450-111">특성</span><span class="sxs-lookup"><span data-stu-id="eb450-111">Attributes</span></span>  
  
|<span data-ttu-id="eb450-112">특성</span><span class="sxs-lookup"><span data-stu-id="eb450-112">Attribute</span></span>|<span data-ttu-id="eb450-113">설명</span><span class="sxs-lookup"><span data-stu-id="eb450-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="eb450-114">이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="eb450-115">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="eb450-116">피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="eb450-117">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb450-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb450-118">Child Elements</span></span>  
  
|<span data-ttu-id="eb450-119">요소</span><span class="sxs-lookup"><span data-stu-id="eb450-119">Element</span></span>|<span data-ttu-id="eb450-120">설명</span><span class="sxs-lookup"><span data-stu-id="eb450-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb450-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="eb450-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="eb450-122">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb450-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb450-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eb450-124">요소</span><span class="sxs-lookup"><span data-stu-id="eb450-124">Element</span></span>|<span data-ttu-id="eb450-125">설명</span><span class="sxs-lookup"><span data-stu-id="eb450-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb450-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="eb450-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="eb450-127">모든 바인딩 기능을 정의 합니다 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb450-128">설명</span><span class="sxs-lookup"><span data-stu-id="eb450-128">Remarks</span></span>  
 <span data-ttu-id="eb450-129">피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="eb450-130">또한 이 확인자는 피어 노드가 알려지고 피어 메시에서 사용할 수 있게 되는 메커니즘인 피어 메시를 통해 노드를 "등록"하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="eb450-131">피어 확인자에 대 한 자세한 내용은 참조 하세요. [피어 확인 자의](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb450-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb450-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb450-132">See also</span></span>
- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="eb450-133">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="eb450-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="eb450-134">[PeerChannel 응용 프로그램에 사용자 지정 확인자 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eb450-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
