---
title: '방법: 서비스 작업 (WCF Data Services)를 정의 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 75691a49624c179166d18225fac9fdc6c17a2308
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138101"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>방법: 서비스 작업 (WCF Data Services)를 정의 합니다.
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 서비스 작업으로 서버에 정의 된 메서드를 노출 합니다. 서비스 작업 URI 서버의 정의 된 메서드를 통해 액세스를 제공 하는 데이터 서비스를 허용 합니다. 서비스 작업을 정의 하려면 적용 된 [`WebGet]` 또는 `[WebInvoke]` 특성을 메서드에 있습니다. 쿼리 연산자를 지원 하려면 서비스 작업 반환 해야 합니다는 <xref:System.Linq.IQueryable%601> 인스턴스. 서비스 작업은 <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>의 <xref:System.Data.Services.DataService%601> 속성을 통해 기본 데이터 소스에 액세스할 수 있습니다. 자세한 내용은 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 `GetOrdersByCity`의 필터링된 <xref:System.Linq.IQueryable%601> 인스턴스 및 관련 `Orders` 개체를 반환하는 `Order_Details`라는 서비스 작업을 정의합니다. 이 예제에서는 Northwind 샘플 데이터 서비스의 데이터 소스인 <xref:System.Data.Objects.ObjectContext> 인스턴스에 액세스합니다. 이 서비스를 완료할 때 만든 합니다 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>Northwind 데이터 서비스에 서비스 작업을 정의하려면  
  
1.  Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.  
  
2.  `Northwind` 클래스에서 `GetOrdersByCity`라는 서비스 작업 메서드를 다음과 같이 정의합니다.  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  `InitializeService` 클래스의 `Northwind` 메서드에서 다음 코드를 추가하여 서비스 작업에 액세스할 수 있도록 합니다.  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a>GetOrdersByCity 서비스 작업을 쿼리하려면  
  
-   웹 브라우저에서 다음 URI 중 하나를 입력하여 다음 예제에 정의된 서비스 작업을 호출합니다.  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a>예제  
 다음 예제에서는 Northwind 데이터 서비스에 `GetOrderByCity`라는 서비스 작업을 구현합니다. 이 작업은 ADO.NET Entity Framework를 사용하여 제공된 도시 이름을 기준으로 `Orders` 집합 및 관련 `Order_Details` 개체를 <xref:System.Linq.IQueryable%601> 인스턴스로 반환합니다.  
  
> [!NOTE]
>  메서드에서 <xref:System.Linq.IQueryable%601> 인스턴스를 반환하기 때문에 이 서비스 작업 엔드포인트에서 쿼리 연산자가 지원됩니다.  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
