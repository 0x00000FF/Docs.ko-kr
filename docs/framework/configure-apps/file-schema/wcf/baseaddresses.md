---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730128"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="0412e-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="0412e-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="0412e-103">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0412e-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="0412e-104">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0412e-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="0412e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0412e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0412e-106">\<client></span><span class="sxs-lookup"><span data-stu-id="0412e-106">\<client></span></span>  
<span data-ttu-id="0412e-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="0412e-107">\<endpoint></span></span>  
<span data-ttu-id="0412e-108">\<host></span><span class="sxs-lookup"><span data-stu-id="0412e-108">\<host></span></span>  
<span data-ttu-id="0412e-109">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="0412e-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0412e-110">구문</span><span class="sxs-lookup"><span data-stu-id="0412e-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="0412e-111">형식</span><span class="sxs-lookup"><span data-stu-id="0412e-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0412e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0412e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0412e-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0412e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0412e-114">특성</span><span class="sxs-lookup"><span data-stu-id="0412e-114">Attributes</span></span>  
 <span data-ttu-id="0412e-115">없음</span><span class="sxs-lookup"><span data-stu-id="0412e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0412e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0412e-116">Child Elements</span></span>  
  
|<span data-ttu-id="0412e-117">요소</span><span class="sxs-lookup"><span data-stu-id="0412e-117">Element</span></span>|<span data-ttu-id="0412e-118">설명</span><span class="sxs-lookup"><span data-stu-id="0412e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0412e-119">\<add></span><span class="sxs-lookup"><span data-stu-id="0412e-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="0412e-120">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0412e-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0412e-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0412e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0412e-122">요소</span><span class="sxs-lookup"><span data-stu-id="0412e-122">Element</span></span>|<span data-ttu-id="0412e-123">설명</span><span class="sxs-lookup"><span data-stu-id="0412e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0412e-124">\<host></span><span class="sxs-lookup"><span data-stu-id="0412e-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="0412e-125">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0412e-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0412e-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0412e-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="0412e-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="0412e-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
