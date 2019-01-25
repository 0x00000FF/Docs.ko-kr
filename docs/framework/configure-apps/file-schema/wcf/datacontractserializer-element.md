---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: d8e0f2ac6e417609ec17d345d1cb20f2a4255dba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657582"
---
# <a name="ltdatacontractserializergt"></a>&lt;DataContractSerializer&gt;
<xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다. 이 요소는 서로 다른 두 가지 계층 구조에서 발생합니다. 하나는 다음 스키마 계층 구조 부분에 나열되고 다른 하나는 설명 부분에 나열됩니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<dataContractSerializer>  
  
## <a name="syntax"></a>구문  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|요소|설명|  
|-------------|-----------------|  
|ignoreExtensionDataObject|끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다. 이 특성은 `<dataContractSerializer>` 요소의 `<behavior>`에서만 설정할 수 있습니다.|  
|maxItemsInObjectGraph|serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다. 이 특성은 65536입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|서비스의 동작에 대한 설정 컬렉션입니다.|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이는 두 번째 계층 구조는이 항목의 소개에서 설명 했 듯이 \<X509Extension > 요소가 발생 합니다.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [데이터 전송 및 Serialization](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
