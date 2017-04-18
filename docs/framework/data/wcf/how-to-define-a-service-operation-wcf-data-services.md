---
title: "방법: 서비스 작업 정의(WCF Data Services) | Microsoft Docs"
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
  - "서비스 작업 [WCF Data Services]"
  - "WCF Data Services, 서비스 작업"
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 서비스 작업 정의(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 서버에서 서비스 작업으로 정의된 메서드를 노출합니다.  데이터 서비스는 서비스 작업을 사용하여 URI를 통해 서버에 정의된 메서드에 액세스할 수 있도록 합니다.  서비스 작업을 정의하려면 \[`WebGet]` 또는 `[WebInvoke]` 특성을 메서드에 적용합니다.  쿼리 연산자를 지원하려면 서비스 작업에서 <xref:System.Linq.IQueryable%601> 인스턴스를 반환해야 합니다.  서비스 작업은 <xref:System.Data.Services.DataService%601>의 <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> 속성을 통해 기본 데이터 소스에 액세스할 수 있습니다. 자세한 내용은 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 `Orders`의 필터링된 <xref:System.Linq.IQueryable%601> 인스턴스 및 관련 `Order_Details` 개체를 반환하는 `GetOrdersByCity`라는 서비스 작업을 정의합니다.  이 예제에서는 Northwind 샘플 데이터 서비스의 데이터 소스인 <xref:System.Data.Objects.ObjectContext> 인스턴스에 액세스합니다.  이 서비스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
### Northwind 데이터 서비스에 서비스 작업을 정의하려면  
  
1.  Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.  
  
2.  `Northwind` 클래스에서 `GetOrdersByCity`라는 서비스 작업 메서드를 다음과 같이 정의합니다.  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  `Northwind` 클래스의 `InitializeService` 메서드에서 다음 코드를 추가하여 서비스 작업에 액세스할 수 있도록 합니다.  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### GetOrdersByCity 서비스 작업을 쿼리하려면  
  
-   웹 브라우저에서 다음 URI 중 하나를 입력하여 다음 예제에 정의된 서비스 작업을 호출합니다.  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## 예제  
 다음 예제에서는 Northwind 데이터 서비스에 `GetOrderByCity`라는 서비스 작업을 구현합니다.  이 작업은 ADO.NET Entity Framework를 사용하여 제공된 도시 이름을 기준으로 `Orders` 집합 및 관련 `Order_Details` 개체를 <xref:System.Linq.IQueryable%601> 인스턴스로 반환합니다.  
  
> [!NOTE]
>  메서드에서 <xref:System.Linq.IQueryable%601> 인스턴스를 반환하기 때문에 이 서비스 작업 끝점에서 쿼리 연산자가 지원됩니다.  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## 참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)