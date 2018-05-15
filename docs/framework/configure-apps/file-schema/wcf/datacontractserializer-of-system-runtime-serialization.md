---
title: '&lt;system.runtime.serialization&gt;의 &lt;dataContractSerializer&gt;'
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 96802100fe1b91d3e375363d2c36e239b1a1d330
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltdatacontractserializergt-of-ltsystemruntimeserializationgt"></a><span data-ttu-id="0744e-102">&lt;system.runtime.serialization&gt;의 &lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="0744e-102">&lt;dataContractSerializer&gt; of &lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="0744e-103"><xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="0744e-104">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="0744e-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="0744e-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0744e-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0744e-106">구문</span><span class="sxs-lookup"><span data-stu-id="0744e-106">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
            maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String">  
          <knownType type="String">  
             <parameter index="Integer"  
                        type="String" />  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0744e-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0744e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0744e-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0744e-109">특성</span><span class="sxs-lookup"><span data-stu-id="0744e-109">Attributes</span></span>  
  
|<span data-ttu-id="0744e-110">요소</span><span class="sxs-lookup"><span data-stu-id="0744e-110">Element</span></span>|<span data-ttu-id="0744e-111">설명</span><span class="sxs-lookup"><span data-stu-id="0744e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0744e-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="0744e-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="0744e-113">끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="0744e-114">이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="0744e-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="0744e-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="0744e-116">serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="0744e-117">이 특성은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0744e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0744e-118">Child Elements</span></span>  
  
|<span data-ttu-id="0744e-119">요소</span><span class="sxs-lookup"><span data-stu-id="0744e-119">Element</span></span>|<span data-ttu-id="0744e-120">설명</span><span class="sxs-lookup"><span data-stu-id="0744e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0744e-121">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="0744e-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="0744e-122">deserialize할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="0744e-123">데이터 계약 및 알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0744e-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0744e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0744e-125">요소</span><span class="sxs-lookup"><span data-stu-id="0744e-125">Element</span></span>|<span data-ttu-id="0744e-126">설명</span><span class="sxs-lookup"><span data-stu-id="0744e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0744e-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="0744e-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="0744e-128"><xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0744e-129">설명</span><span class="sxs-lookup"><span data-stu-id="0744e-129">Remarks</span></span>  
 <span data-ttu-id="0744e-130">알려진된 형식에 대 한 자세한 내용은 참조 <xref:System.Runtime.Serialization.DataContractSerializer> 및 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0744e-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0744e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0744e-131">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 [<span data-ttu-id="0744e-132">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="0744e-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
