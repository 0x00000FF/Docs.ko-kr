---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 99bb7c6be02bad85792dfce9de1f6ef8ba1dcd17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="4d55d-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="4d55d-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="4d55d-103">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d55d-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="4d55d-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4d55d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d55d-105">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="4d55d-105">\<client></span></span>  
<span data-ttu-id="4d55d-106">\<메타 데이터 ></span><span class="sxs-lookup"><span data-stu-id="4d55d-106">\<metadata></span></span>  
<span data-ttu-id="4d55d-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="4d55d-107">\<policyImporters></span></span>  
<span data-ttu-id="4d55d-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="4d55d-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d55d-109">구문</span><span class="sxs-lookup"><span data-stu-id="4d55d-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d55d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4d55d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d55d-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d55d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d55d-112">특성</span><span class="sxs-lookup"><span data-stu-id="4d55d-112">Attributes</span></span>  
  
|<span data-ttu-id="4d55d-113">특성</span><span class="sxs-lookup"><span data-stu-id="4d55d-113">Attribute</span></span>|<span data-ttu-id="4d55d-114">설명</span><span class="sxs-lookup"><span data-stu-id="4d55d-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4d55d-115">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4d55d-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d55d-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4d55d-116">Child Elements</span></span>  
 <span data-ttu-id="4d55d-117">없음</span><span class="sxs-lookup"><span data-stu-id="4d55d-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d55d-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4d55d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4d55d-119">요소</span><span class="sxs-lookup"><span data-stu-id="4d55d-119">Element</span></span>|<span data-ttu-id="4d55d-120">설명</span><span class="sxs-lookup"><span data-stu-id="4d55d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d55d-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="4d55d-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="4d55d-122">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d55d-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d55d-123">설명</span><span class="sxs-lookup"><span data-stu-id="4d55d-123">Remarks</span></span>  
 <span data-ttu-id="4d55d-124">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d55d-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d55d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d55d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="4d55d-126">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4d55d-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="4d55d-127">클라이언트</span><span class="sxs-lookup"><span data-stu-id="4d55d-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
