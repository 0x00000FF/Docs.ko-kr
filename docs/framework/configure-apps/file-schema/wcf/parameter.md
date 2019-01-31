---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 8b14dc1908ef3a06549154f70efb2d4e5cb10076
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289437"
---
# <a name="parameter"></a><span data-ttu-id="369b5-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="369b5-101">\<parameter></span></span>
<span data-ttu-id="369b5-102">선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="369b5-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="369b5-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="369b5-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="369b5-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="369b5-105">\<declaredTypes > 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="369b5-106">\<추가 > 요소에 대 한 \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="369b5-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="369b5-107">\<knownType > 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-107">\<knownType> Element</span></span>  
<span data-ttu-id="369b5-108">\<매개 변수 > 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369b5-109">구문</span><span class="sxs-lookup"><span data-stu-id="369b5-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="369b5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="369b5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="369b5-112">특성</span><span class="sxs-lookup"><span data-stu-id="369b5-112">Attributes</span></span>  
  
|<span data-ttu-id="369b5-113">특성</span><span class="sxs-lookup"><span data-stu-id="369b5-113">Attribute</span></span>|<span data-ttu-id="369b5-114">설명</span><span class="sxs-lookup"><span data-stu-id="369b5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="369b5-115">인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-115">index</span></span>|<span data-ttu-id="369b5-116">선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="369b5-117">형식</span><span class="sxs-lookup"><span data-stu-id="369b5-117">type</span></span>|<span data-ttu-id="369b5-118">serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="369b5-119">index 특성</span><span class="sxs-lookup"><span data-stu-id="369b5-119">index Attribute</span></span>  
  
|<span data-ttu-id="369b5-120">값</span><span class="sxs-lookup"><span data-stu-id="369b5-120">Value</span></span>|<span data-ttu-id="369b5-121">설명</span><span class="sxs-lookup"><span data-stu-id="369b5-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="369b5-122">"0"</span><span class="sxs-lookup"><span data-stu-id="369b5-122">"0"</span></span>|<span data-ttu-id="369b5-123">제네릭 형식의 첫 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-123">The first parameter in the generic type.</span></span> <span data-ttu-id="369b5-124">예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="369b5-125">이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="369b5-126">"1"</span><span class="sxs-lookup"><span data-stu-id="369b5-126">"1"</span></span>|<span data-ttu-id="369b5-127">제네릭 형식의 두 번째 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-127">The second parameter in a generic type.</span></span> <span data-ttu-id="369b5-128">예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="369b5-129">이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="369b5-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-130">Child Elements</span></span>  
 <span data-ttu-id="369b5-131">없음</span><span class="sxs-lookup"><span data-stu-id="369b5-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="369b5-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="369b5-132">Parent Elements</span></span>  
  
|<span data-ttu-id="369b5-133">요소</span><span class="sxs-lookup"><span data-stu-id="369b5-133">Element</span></span>|<span data-ttu-id="369b5-134">설명</span><span class="sxs-lookup"><span data-stu-id="369b5-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="369b5-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="369b5-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="369b5-136">선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="369b5-137">설명</span><span class="sxs-lookup"><span data-stu-id="369b5-137">Remarks</span></span>  
 <span data-ttu-id="369b5-138">알려진된 형식에 대 한 자세한 내용은 참조 하세요. [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 고 <xref:System.Runtime.Serialization.DataContractSerializer>입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="369b5-139">참조 된 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="369b5-140">이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="369b5-141">두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="369b5-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369b5-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="369b5-142">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="369b5-143">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="369b5-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="369b5-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="369b5-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="369b5-145">\<add></span><span class="sxs-lookup"><span data-stu-id="369b5-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
