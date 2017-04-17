---
title: "사용자 지정 데이터 서비스 공급자(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, 공급자"
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 사용자 지정 데이터 서비스 공급자(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 포함된 공급자 집합을 사용하면 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의할 수 있습니다.  
  
|공급자|설명|  
|---------|--------|  
|메타데이터 공급자|이 공급자는 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 구현하여 런타임에 사용자 지정 데이터 모델을 정의할 수 있도록 하는 핵심 사용자 지정 데이터 서비스 공급자입니다.|  
|쿼리 공급자|이 공급자를 사용하면 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 사용하여 정의된 사용자 지정 데이터 모델에 대해 쿼리를 실행할 수 있습니다.  쿼리 공급자는 <xref:System.Data.Services.Providers.IDataServiceQueryProvider> 인터페이스를 구현하여 만듭니다.|  
|업데이트 공급자|이 공급자를 사용하면 사용자 지정 데이터 서비스 공급자에 노출된 형식을 업데이트하고 동시성을 관리할 수 있습니다.  업데이트 공급자는 <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> 인터페이스를 구현하여 만듭니다.|  
|페이징 공급자|이 공급자는 사용자 지정 데이터 서비스 공급자와 함께 사용되어 서버 기반 페이징 지원을 사용하도록 설정합니다.  사용자 지정 데이터 서비스용 페이징 공급자는 <xref:System.Data.Services.Providers.IDataServicePagingProvider> 인터페이스를 구현하여 만듭니다.|  
|스트리밍 공급자|이 공급자를 사용하면 BLOB\(Binary Large Object\) 데이터 형식을 스트림으로 노출할 수 있습니다.  스트리밍 공급자는 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 인터페이스를 구현하여 만듭니다.  스트리밍 공급자는 Entity Framework 및 리플렉션 데이터 소스 공급자와 함께 사용할 수도 있습니다.  자세한 내용은 [스트리밍 공급자](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)을 참조하세요.|  
  
 자세한 내용은 [사용자 지정 데이터 서비스 공급자](http://go.microsoft.com/fwlink/?LinkID=186850)\(영문\) 문서 및 [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069)\(영문\)의 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 공급자 도구 키트를 참조하세요.  
  
## 참고 항목  
 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Entity Framework 공급자](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)   
 [리플렉션 공급자](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)