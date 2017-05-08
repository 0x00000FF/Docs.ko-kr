---
title: "&lt;system.runtime.serialization&gt;의 &lt;dataContractSerializer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;system.runtime.serialization&gt;의 &lt;dataContractSerializer&gt;
<xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.  
  
## 구문  
  
```  
  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|요소|설명|  
|--------|--------|  
|ignoreExtensionDataObject|끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.  이 특성은 `<behavior>` 요소의 `<dataContractSerializer>`에서만 설정할 수 있습니다.|  
|maxItemsInObjectGraph|serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.  이 특성은 65536입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<declaredTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|deserialize할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.<br /><br /> 데이터 계약 및 알려진 형식에 대한 자세한 내용은 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)을 참조하세요.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<xref:System.Runtime.Serialization> 네임스페이스 섹션의 루트 요소를 나타내며 <xref:System.Runtime.Serialization.DataContractSerializer>의 옵션을 설정하기 위한 요소를 포함합니다.|  
  
## 설명  
 알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 및 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)