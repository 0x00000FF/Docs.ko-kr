---
title: "&lt;policyImporter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;policyImporter&gt;
바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.  
  
## 구문  
  
```  
  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`type`|이 요소의 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<policyImporters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.|  
  
## 설명  
 정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>   
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 [WCF 클라이언트 구성](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [클라이언트](../../../../../docs/framework/wcf/feature-details/clients.md)