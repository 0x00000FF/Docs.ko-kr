---
title: "&lt;declaredTypes&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<declaredTypes> 요소"
  - "DataContractSerializer"
  - "dataContractSerializer 요소"
  - "declaredTypes 요소"
  - "KnownTypes"
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;declaredTypes&gt;
deserialize할 때 <xref:System.Runtime.Serialization.DataContractSerializer>에서 사용하는 알려진 형식을 포함합니다.  
  
 데이터 계약 및 알려진 형식에 대한 자세한 내용은 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)을 참조하세요.  
  
## 구문  
  
```  
  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
                <parameter index="Integer"/>  
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
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|알려진 형식을 필요로 하는 형식을 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.|  
  
## 설명  
 알려진 형식[!INCLUDE[crabout](../../../../../includes/crabout-md.md)] [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.  
  
## 예제  
 다음 XML 코드에서는 `DataContractSerializer` 요소에 추가된 선언된 형식 및 알려진 형식을 보여 줍니다.  예제에서는 추가되는 세 가지 형식을 보여 줍니다.  첫 번째는 "Item"이라는 알려진 형식을 사용하는 "Orders"라는 사용자 지정 형식입니다.  두 번째 선언된 형식은 `Item`을 알려진 형식으로 사용하는 <xref:System.Collections.Generic.List%601>입니다.  마지막으로 세 번째 선언된 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.  <xref:System.Collections.Generic.Dictionary%602> 클래스 형식은 두 개의 형식 매개 변수가 있는 제네릭 형식입니다.  첫 번째는 키를 나타내고 두 번째는 값을 나타냅니다.  다음 예제에서는 알려진 형식 목록에 두 번째 형식\(값\)의 <xref:System.Collections.Generic.List%601>을 추가합니다.  `index` 특성을 사용하여 알려진 형식에 사용할 형식 매개 변수를 지정해야 합니다.  이 경우 값 형식은 "1"로 설정된 index 특성으로 표시됩니다\(컬렉션은 0부터 시작\).  
  
```  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
            <parameter index="1"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)