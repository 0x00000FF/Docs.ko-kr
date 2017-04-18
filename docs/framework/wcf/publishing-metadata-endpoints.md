---
title: "메타데이터 끝점 게시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 메타데이터 끝점 게시
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스는 하나 이상의 메타데이터 끝점을 게시하여 메타데이터를 게시합니다.서비스 메타데이터를 게시하면 WS\-MetadataExchange\(MEX\) 및 HTTP\/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다.메타데이터 끝점은 주소, 바인딩 및 계약에 포함된 다른 서비스 끝점과 유사하며 구성 또는 코드를 통해 서비스 호스트에 추가할 수 있습니다.메타데이터 끝점 게시를 사용하도록 설정하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 서비스 동작을 서비스에 추가해야 합니다.  
  
## 단원 내용  
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 메타데이터를 게시하여 클라이언트가 WS\-MetadataExchange를 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP\/GET 요청을 검색할 수 있도록 구성하는 방법을 보여 줍니다.  
  
 [방법: 코드를 사용하여 서비스에 대한 메타데이터 게시](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 클라이언트가 WS\-MetadataExchange를 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP\/GET 요청을 검색할 수 있도록 메타데이터가 코드에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 게시할 수 있는 방법을 보여 줍니다.  
  
## 참고 항목  
 [메타데이터 게시](../../../docs/framework/wcf/feature-details/publishing-metadata.md)