---
title: "&lt;매개 변수&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9db1921e2a6ee1ae2780f744c45fdb25efbf797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="8272c-102">&lt;매개 변수&gt;</span><span class="sxs-lookup"><span data-stu-id="8272c-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="8272c-103">선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="8272c-104">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="8272c-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="8272c-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8272c-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="8272c-106">\<declaredTypes > 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="8272c-107">\<추가 > 요소에 대 한 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="8272c-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="8272c-108">\<knownType > 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-108">\<knownType> Element</span></span>  
<span data-ttu-id="8272c-109">\<매개 변수 > 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8272c-110">구문</span><span class="sxs-lookup"><span data-stu-id="8272c-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8272c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8272c-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8272c-113">특성</span><span class="sxs-lookup"><span data-stu-id="8272c-113">Attributes</span></span>  
  
|<span data-ttu-id="8272c-114">특성</span><span class="sxs-lookup"><span data-stu-id="8272c-114">Attribute</span></span>|<span data-ttu-id="8272c-115">설명</span><span class="sxs-lookup"><span data-stu-id="8272c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8272c-116">인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-116">index</span></span>|<span data-ttu-id="8272c-117">선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="8272c-118">형식</span><span class="sxs-lookup"><span data-stu-id="8272c-118">type</span></span>|<span data-ttu-id="8272c-119">serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="8272c-120">index 특성</span><span class="sxs-lookup"><span data-stu-id="8272c-120">index Attribute</span></span>  
  
|<span data-ttu-id="8272c-121">값</span><span class="sxs-lookup"><span data-stu-id="8272c-121">Value</span></span>|<span data-ttu-id="8272c-122">설명</span><span class="sxs-lookup"><span data-stu-id="8272c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8272c-123">"0"</span><span class="sxs-lookup"><span data-stu-id="8272c-123">"0"</span></span>|<span data-ttu-id="8272c-124">제네릭 형식의 첫 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-124">The first parameter in the generic type.</span></span> <span data-ttu-id="8272c-125">예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="8272c-126">이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="8272c-127">"1"</span><span class="sxs-lookup"><span data-stu-id="8272c-127">"1"</span></span>|<span data-ttu-id="8272c-128">제네릭 형식의 두 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-128">The second parameter in a generic type.</span></span> <span data-ttu-id="8272c-129">예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="8272c-130">이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8272c-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-131">Child Elements</span></span>  
 <span data-ttu-id="8272c-132">없음</span><span class="sxs-lookup"><span data-stu-id="8272c-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8272c-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8272c-133">Parent Elements</span></span>  
  
|<span data-ttu-id="8272c-134">요소</span><span class="sxs-lookup"><span data-stu-id="8272c-134">Element</span></span>|<span data-ttu-id="8272c-135">설명</span><span class="sxs-lookup"><span data-stu-id="8272c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8272c-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="8272c-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="8272c-137">선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8272c-138">설명</span><span class="sxs-lookup"><span data-stu-id="8272c-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="8272c-139">알려진 형식, 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8272c-140">참조는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="8272c-141">이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="8272c-142">두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8272c-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8272c-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8272c-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="8272c-144">데이터 계약 알려진된 형식</span><span class="sxs-lookup"><span data-stu-id="8272c-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="8272c-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8272c-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="8272c-146">\<add></span><span class="sxs-lookup"><span data-stu-id="8272c-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
