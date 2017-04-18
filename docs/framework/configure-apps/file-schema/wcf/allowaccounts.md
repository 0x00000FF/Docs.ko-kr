---
title: "&lt;allowAccounts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;allowAccounts&gt;
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스의 사용자 계정을 지정하는 구성 요소 컬렉션을 포함합니다.  
  
 \<system.serviceModel.activation\>  
  
## 구문  
  
```  
  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|특성|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스를 수행할 수 있는 사용자 계정을 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<net.pipe\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) 또는 [\<net.tcp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>