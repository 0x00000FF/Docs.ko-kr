---
title: "&lt;범위&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f198811483edb8a7be882588c38b1f3942f8bb4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="0a8bf-102">&lt;범위&gt;</span><span class="sxs-lookup"><span data-stu-id="0a8bf-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="0a8bf-103">쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8bf-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="0a8bf-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a8bf-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-105">\<behaviors></span></span>  
<span data-ttu-id="0a8bf-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0a8bf-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-107">\<behavior></span></span>  
<span data-ttu-id="0a8bf-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="0a8bf-109">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8bf-110">구문</span><span class="sxs-lookup"><span data-stu-id="0a8bf-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a8bf-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0a8bf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a8bf-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8bf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a8bf-113">특성</span><span class="sxs-lookup"><span data-stu-id="0a8bf-113">Attributes</span></span>  
 <span data-ttu-id="0a8bf-114">없음</span><span class="sxs-lookup"><span data-stu-id="0a8bf-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a8bf-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a8bf-115">Child Elements</span></span>  
  
|<span data-ttu-id="0a8bf-116">특성</span><span class="sxs-lookup"><span data-stu-id="0a8bf-116">Attribute</span></span>|<span data-ttu-id="0a8bf-117">설명</span><span class="sxs-lookup"><span data-stu-id="0a8bf-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="0a8bf-118">\<add></span><span class="sxs-lookup"><span data-stu-id="0a8bf-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="0a8bf-119">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 끝점의 범위 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8bf-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a8bf-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a8bf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0a8bf-121">요소</span><span class="sxs-lookup"><span data-stu-id="0a8bf-121">Element</span></span>|<span data-ttu-id="0a8bf-122">설명</span><span class="sxs-lookup"><span data-stu-id="0a8bf-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a8bf-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="0a8bf-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="0a8bf-124">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장명 등 끝점에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8bf-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a8bf-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a8bf-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
