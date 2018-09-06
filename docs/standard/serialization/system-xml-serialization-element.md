---
title: '&lt;system.xml.serialization&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: b67c1ec1ec737976e4e50b80b42f34e508dc0224
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43879366"
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="e20e5-102">&lt;system.xml.serialization&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="e20e5-103">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="e20e5-104">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e20e5-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="e20e5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e20e5-105">\<configuration></span></span>  
<span data-ttu-id="e20e5-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e20e5-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e20e5-107">구문</span><span class="sxs-lookup"><span data-stu-id="e20e5-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e20e5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e20e5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e20e5-110">특성</span><span class="sxs-lookup"><span data-stu-id="e20e5-110">Attributes</span></span>  
 <span data-ttu-id="e20e5-111">없음</span><span class="sxs-lookup"><span data-stu-id="e20e5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e20e5-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-112">Child Elements</span></span>  
  
|<span data-ttu-id="e20e5-113">요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-113">Element</span></span>|<span data-ttu-id="e20e5-114">설명</span><span class="sxs-lookup"><span data-stu-id="e20e5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e20e5-115">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="e20e5-116"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="e20e5-117">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="e20e5-118"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e20e5-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e20e5-120">요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-120">Element</span></span>|<span data-ttu-id="e20e5-121">설명</span><span class="sxs-lookup"><span data-stu-id="e20e5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e20e5-122">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="e20e5-123">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e20e5-124">예제</span><span class="sxs-lookup"><span data-stu-id="e20e5-124">Example</span></span>  
 <span data-ttu-id="e20e5-125">다음 코드 예제에서는 <xref:System.DateTime> 개체의 serialization 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e20e5-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e20e5-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="e20e5-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="e20e5-127">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e20e5-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="e20e5-128">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
- [<span data-ttu-id="e20e5-129">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="e20e5-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="e20e5-130">\<추가 > 요소에 대 한 \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="e20e5-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
