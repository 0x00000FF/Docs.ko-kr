---
title: "데이터 멤버 기본값"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7d6aa8d695dd6fc79b23e6cbb69bf523ef680f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="data-member-default-values"></a><span data-ttu-id="bb184-102">데이터 멤버 기본값</span><span class="sxs-lookup"><span data-stu-id="bb184-102">Data Member Default Values</span></span>
<span data-ttu-id="bb184-103">에 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], 종류의 개념이 *기본값*합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-103">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], types have a concept of *default values*.</span></span> <span data-ttu-id="bb184-104">예를 들어 참조 형식의 기본값은 `null`이고 정수 형식의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-104">For example, for any reference type the default value is `null`, and for an integer type it is zero.</span></span> <span data-ttu-id="bb184-105">기본값으로 설정할 경우 serialize된 데이터에서 데이터 멤버를 생략하는 것이 좋을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-105">It is occasionally desirable to omit a data member from serialized data when it is set to its default value.</span></span> <span data-ttu-id="bb184-106">멤버에 기본값이 있기 때문에 실제 값을 serialize할 필요가 없으므로 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-106">Because the member has a default value, an actual value need not be serialized; this has a performance advantage.</span></span>  
  
 <span data-ttu-id="bb184-107">serialize된 데이터에서 멤버를 생략하려면 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 특성의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 `false`로 설정합니다. 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-107">To omit a member from serialized data, set the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to `false` (the default is `true`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb184-108">상호 운용성이나 데이터 크기 축소 등 특별히 필요한 경우에만 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 속성을 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-108">You should set the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property to `false` if there is a specific need to do so, such as for interoperability or data size reduction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb184-109">예제</span><span class="sxs-lookup"><span data-stu-id="bb184-109">Example</span></span>  
 <span data-ttu-id="bb184-110">다음 코드에는 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가 `false`로 설정된 여러 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-110">The following code has several members with the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> set to `false`.</span></span>  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 <span data-ttu-id="bb184-111">이 클래스의 인스턴스를 serialize하면 다음과 같은 결과가 나타납니다. `employeeName` 및 `employeeID`가 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-111">If an instance of this class is serialized, the result is as follows: `employeeName` and `employeeID` is serialized.</span></span> <span data-ttu-id="bb184-112">`employeeName` 값이 null이고 `employeeID` 값이 0이면 명시적으로 serialize된 데이터의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-112">The null value for `employeeName` and the zero value for `employeeID` is explicitly part of the serialized data.</span></span> <span data-ttu-id="bb184-113">그러나 `position`, `salary` 및 `bonus` 멤버는 serialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-113">However, the `position`, `salary`, and `bonus` members are not serialized.</span></span> <span data-ttu-id="bb184-114">마지막으로 57800은 정수에 대한 .NET 기본값인 0과 일치하지 않으므로 `targetSalary` 속성이 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>로 설정되어 있더라도 `false`는 평소와 같이 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-114">Finally, `targetSalary` is serialized as usual, even though the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property is set to `false`, because 57800 does not match the .NET default value for an integer, which is zero.</span></span>  
  
### <a name="xml-representation"></a><span data-ttu-id="bb184-115">XML 표현</span><span class="sxs-lookup"><span data-stu-id="bb184-115">XML Representation</span></span>  
 <span data-ttu-id="bb184-116">이전 예제가 XML로 serialize될 경우의 표현은 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-116">If the previous example is serialized to XML, the representation is similar to the following.</span></span>  
  
```xml  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 <span data-ttu-id="bb184-117">`xsi:nil` 특성은 null 값을 명시적으로 나타낼 수 있는 상호 운용 가능한 방법을 제공하는 W3C(World Wide Web Consortium) XML 스키마 인스턴스 네임스페이스의 특수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-117">The `xsi:nil` attribute is a special attribute in the World Wide Web Consortium (W3C) XML Schema instance namespace that provides an interoperable way to explicitly represent a null value.</span></span> <span data-ttu-id="bb184-118">XML에는 지위, 급여 및 보너스 데이터 멤버에 대한 정보는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-118">Note that there is no information at all in the XML about position, salary, and bonus data members.</span></span> <span data-ttu-id="bb184-119">받는 측에서 이 값을 `null`, 0 및 `null`로 각각 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-119">The receiving end can interpret these as `null`, zero, and `null`, respectively.</span></span> <span data-ttu-id="bb184-120">타사 deserializer에서도 올바른 해석을 한다는 보장이 없으므로 이 패턴은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-120">There is no guarantee that a third-party deserializer can make the correct interpretation, which is why this pattern is not recommended.</span></span> <span data-ttu-id="bb184-121"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스는 누락된 값에 대해 올바른 해석을 항상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-121">The <xref:System.Runtime.Serialization.DataContractSerializer> class always selects the correct interpretation for missing values.</span></span>  
  
### <a name="interaction-with-isrequired"></a><span data-ttu-id="bb184-122">IsRequired와의 상호 작용</span><span class="sxs-lookup"><span data-stu-id="bb184-122">Interaction with IsRequired</span></span>  
 <span data-ttu-id="bb184-123">에 설명 된 대로 [데이터 계약 버전 관리](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), <xref:System.Runtime.Serialization.DataMemberAttribute> 특성에는 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 속성 (기본값은 `false`).</span><span class="sxs-lookup"><span data-stu-id="bb184-123">As discussed in [Data Contract Versioning](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property (the default is `false`).</span></span> <span data-ttu-id="bb184-124">이 속성은 지정된 데이터 멤버가 deserialize될 때 serialize된 데이터에 있어야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-124">The property indicates whether a given data member must be present in the serialized data when it is being deserialized.</span></span> <span data-ttu-id="bb184-125">`IsRequired`가 `true`(값이 있어야 함을 표시)로 설정되고 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가 `false`(기본값으로 설정된 경우 값이 없어야 함을 표시)로 설정되어 있으면 결과가 모순될 수 있으므로 이 데이터 멤버의 기본값을 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-125">If `IsRequired` is set to `true`, (which indicates that a value must be present) and <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> is set to `false` (indicating that the value must not be present if it is set to its default value), default values for this data member cannot be serialized because the results would be contradictory.</span></span> <span data-ttu-id="bb184-126">그런 데이터 멤버를 기본값(일반적으로 `null` 또는 0)으로 설정하고 serialization을 시도하면 <xref:System.Runtime.Serialization.SerializationException>가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-126">If such a data member is set to its default value (usually `null` or zero) and a serialization is attempted, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>  
  
### <a name="schema-representation"></a><span data-ttu-id="bb184-127">스키마 표현</span><span class="sxs-lookup"><span data-stu-id="bb184-127">Schema Representation</span></span>  
 <span data-ttu-id="bb184-128">데이터 멤버의 XML 스키마 정의 언어 (XSD) 스키마 표시의 세부 정보는 경우는 `EmitDefaultValue` 속성이로 설정 되어 `false` 에 대해서는 설명 [데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-128">The details of the XML Schema definition language (XSD) schema representation of data members when the `EmitDefaultValue` property is set to `false` are discussed in [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span> <span data-ttu-id="bb184-129">여기서는 개요만 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-129">However, the following is a brief overview:</span></span>  
  
-   <span data-ttu-id="bb184-130"><xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>가 `false`로 설정되어 있으면 스키마에 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 특정한 주석으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-130">When the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> is set to `false`, it is represented in the schema as an annotation specific to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="bb184-131">이 정보를 나타내는 상호 운용 가능한 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-131">There is no interoperable way to represent this information.</span></span> <span data-ttu-id="bb184-132">특히 스키마의 "default" 특성은 이 용도로 사용되지 않고, `minOccurs` 특성은 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 설정의 영향만 받고, `nillable` 특성은 데이터 멤버 형식의 영향만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-132">In particular, the "default" attribute in the schema is not used for this purpose, the `minOccurs` attribute is affected only by the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> setting, and the `nillable` attribute is affected only by the type of the data member.</span></span>  
  
-   <span data-ttu-id="bb184-133">사용할 실제 기본값은 스키마에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-133">The actual default value to use is not present in the schema.</span></span> <span data-ttu-id="bb184-134">따라서 수신하는 끝점에서 누락된 요소를 적절하게 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-134">It is up to the receiving endpoint to appropriately interpret a missing element.</span></span>  
  
 <span data-ttu-id="bb184-135">스키마 가져오기에서는 앞에서 설명한 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> 관련 주석이 발견될 때마다 `false` 속성이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-135">On schema import, the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property is automatically set to `false` whenever the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-specific annotation mentioned previously is detected.</span></span> <span data-ttu-id="bb184-136">또한 `false` 웹 서비스를 사용할 때 일반적으로 발생하는 특정 상호 운용성 시나리오를 지원하기 위해 `nillable` 속성이 `false`로 설정된 참조 형식 값이 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb184-136">It is also set to `false` for reference types that have the `nillable` property set to `false` to support specific interoperability scenarios that commonly occur when consuming [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb184-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb184-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>
