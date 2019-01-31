---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: ba1484644c57651fc0feadcc61d71d03eec1899b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254925"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="c0d59-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="c0d59-101">\<servicePrincipalName></span></span>
<span data-ttu-id="c0d59-102">SPN(서비스 사용자 이름)으로 서비스 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="c0d59-103">SPN을 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c0d59-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="c0d59-104">\<identity></span></span>  
<span data-ttu-id="c0d59-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="c0d59-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d59-106">구문</span><span class="sxs-lookup"><span data-stu-id="c0d59-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0d59-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0d59-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c0d59-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0d59-109">특성</span><span class="sxs-lookup"><span data-stu-id="c0d59-109">Attributes</span></span>  
  
|<span data-ttu-id="c0d59-110">특성</span><span class="sxs-lookup"><span data-stu-id="c0d59-110">Attribute</span></span>|<span data-ttu-id="c0d59-111">설명</span><span class="sxs-lookup"><span data-stu-id="c0d59-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0d59-112">값</span><span class="sxs-lookup"><span data-stu-id="c0d59-112">value</span></span>|<span data-ttu-id="c0d59-113">클라이언트에서 서비스의 인스턴스를 고유하게 식별하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="c0d59-114">포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="c0d59-115">클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0d59-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0d59-116">Child Elements</span></span>  
 <span data-ttu-id="c0d59-117">없음</span><span class="sxs-lookup"><span data-stu-id="c0d59-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0d59-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0d59-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c0d59-119">요소</span><span class="sxs-lookup"><span data-stu-id="c0d59-119">Element</span></span>|<span data-ttu-id="c0d59-120">설명</span><span class="sxs-lookup"><span data-stu-id="c0d59-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0d59-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="c0d59-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c0d59-122">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0d59-123">설명</span><span class="sxs-lookup"><span data-stu-id="c0d59-123">Remarks</span></span>  
 <span data-ttu-id="c0d59-124">이 id 가진 끝점과 연결 하는 안전한 Windows Communication Foundation (WCF) 클라이언트 끝점과 SSPI 인증을 수행할 때 SPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d59-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d59-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0d59-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="c0d59-126">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="c0d59-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c0d59-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="c0d59-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
