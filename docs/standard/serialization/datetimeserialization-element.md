---
title: <dateTimeSerialization> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459268"
---
# <a name="datetimeserialization-element"></a>\<dateTimeSerialization> 요소
<xref:System.DateTime> 개체의 serialization 모드를 결정합니다.  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a>구문  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|----------------|-----------------|  
|`mode`|선택 사항입니다. serialization 모드를 지정합니다. <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다. 기본값은 **RoundTrip**입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|system.xml.serialization|XML serialization을 제어하기 위한 최상위 요소입니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework의 1.0, 1.1 및 2.0 이상 버전에서 이 속성이 **Local**로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 설정됩니다. 즉, 로컬 표준 시간대 정보는 항상 직렬화된 데이터에 포함됩니다. .NET Framework 이전 버전과의 호환성을 제공하려면 이 속성을 **Local**로 설정합니다.  
  
 이 속성이 **Roundtrip**으로 설정된 .NET Framework 버전 2.0 이상에서는 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다. 그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다. 이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 애플리케이션에 대해 이를 사용하는 것이 좋습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)
- [\<schemaImporterExtensions> 요소](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [\<schemaImporterExtensions>에 대한 \<add> 요소](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [\<system.xml.serialization> 요소](../../../docs/standard/serialization/system-xml-serialization-element.md)
