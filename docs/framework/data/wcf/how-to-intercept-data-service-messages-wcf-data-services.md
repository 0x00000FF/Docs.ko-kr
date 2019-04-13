---
title: '방법: (WCF Data Services) 데이터 서비스 메시지 가로채기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: ad0673f72b1a81d6bcfaf0704ccd698eda7bb20c
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517837"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>방법: (WCF Data Services) 데이터 서비스 메시지 가로채기
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 사용자 지정 논리를 작업에 추가할 수 있도록 요청 메시지를 가로챌 수 있습니다. 메시지를 가로채 하려면 데이터 서비스에서 특별 한 특성이 있는 메서드를 사용 합니다. 자세한 내용은 [인터셉터](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 사용합니다. 이 서비스를 완료할 때 만든 합니다 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Orders 엔터티 집합에 대해 쿼리 인터셉터를 정의하려면  
  
1. Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.  
  
2. `Northwind` 클래스의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. `Northwind` 클래스에서 `OnQueryOrders`라는 서비스 작업 메서드를 다음과 같이 정의합니다.  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Products 엔터티 집합에 대해 변경 인터셉터를 정의하려면  
  
1. Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.  
  
2. `Northwind` 클래스에서 `OnChangeProducts`라는 서비스 작업 메서드를 다음과 같이 정의합니다.  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Orders` 엔터티 집합에 대해 람다 식을 반환하는 쿼리 인터셉터 메서드를 정의합니다. 이 식에는 특정 연락처 이름이 있는 관련 `Orders`를 기반으로 요청된 `Customers`를 필터링하는 대리자가 포함되어 있습니다. 이름은 요청하는 사용자를 기반으로 확인됩니다. 이 예제에서는 WCF를 사용하고 인증이 사용하도록 설정된 ASP.NET 웹 응용 프로그램 내에 데이터 서비스가 호스트된다고 가정합니다. <xref:System.Web.HttpContext> 클래스는 현재 요청의 사용자를 검색하는 데 사용됩니다.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Products` 엔터티 집합에 대해 변경 인터셉터 메서드를 정의합니다. 이 메서드는 <xref:System.Data.Services.UpdateOperations.Add> 또는 <xref:System.Data.Services.UpdateOperations.Change> 작업에 대해 서비스 입력의 유효성을 검사하고 판매가 중단된 제품이 변경되는 경우 예외를 발생시킵니다. 또한 제품 삭제를 지원되지 않는 작업으로 차단합니다.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>참고자료

- [방법: 서비스 작업 정의](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)
- [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
