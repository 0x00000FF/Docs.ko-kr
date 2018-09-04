---
title: '&lt;schemaImporterExtensions&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 8bcd8abb138c645f61bf833b49cda2631d1778dd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513115"
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="1c16f-102">&lt;schemaImporterExtensions&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="1c16f-103"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c16f-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="1c16f-104">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c16f-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c16f-105">구문</span><span class="sxs-lookup"><span data-stu-id="1c16f-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="1c16f-106">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-106">Child Elements</span></span>  
  
|<span data-ttu-id="1c16f-107">요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-107">Element</span></span>|<span data-ttu-id="1c16f-108">설명</span><span class="sxs-lookup"><span data-stu-id="1c16f-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c16f-109">\<추가 > 요소에 대 한 \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="1c16f-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="1c16f-110"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 매핑을 만들기 위해 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c16f-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="1c16f-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-111">Parent Elements</span></span>  
  
|<span data-ttu-id="1c16f-112">요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-112">Element</span></span>|<span data-ttu-id="1c16f-113">설명</span><span class="sxs-lookup"><span data-stu-id="1c16f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c16f-114">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="1c16f-115">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c16f-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c16f-116">예제</span><span class="sxs-lookup"><span data-stu-id="1c16f-116">Example</span></span>  
 <span data-ttu-id="1c16f-117">다음 코드 예제에서는 XSD 형식을 .NET Framework 형식으로 매핑할 때 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c16f-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c16f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c16f-118">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="1c16f-119">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="1c16f-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1c16f-120">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="1c16f-121">\<추가 > 요소에 대 한 \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="1c16f-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
 [<span data-ttu-id="1c16f-122">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="1c16f-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
