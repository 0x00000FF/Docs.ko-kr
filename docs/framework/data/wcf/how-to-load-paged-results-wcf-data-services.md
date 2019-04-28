---
title: '방법: 페이징 결과 로드 (WCF 데이터 Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 0be7dcbefb23d2f2b283ac498f3b0ea43278f2d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875841"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>방법: 페이징 결과 로드 (WCF 데이터 Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 데이터 서비스에서 단일 응답 피드에 반환되는 엔터티 수를 제한할 수 있습니다. 이 경우 피드의 최종 항목에 다음 데이터 페이지에 대한 링크가 포함됩니다. 다음 데이터 페이지의 URI는 <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>를 실행할 때 반환되는 <xref:System.Data.Services.Client.QueryOperationResponse%601>의 <xref:System.Data.Services.Client.DataServiceQuery%601> 메서드를 호출하여 가져옵니다. 이 개체가 나타내는 URI를 사용하여 다음 결과 페이지를 로드합니다. 자세한 내용은 [지연 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `do…while` 루프를 사용하여 데이터 서비스의 페이징 결과에서 `Customers` 엔터티를 로드합니다.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 각 `Orders` 엔터티와 관련된 `Customers` 엔터티를 반환하고, `do…while` 루프를 사용하여 `Customers` 엔터티 페이지를 로드하고, 중첩된 `while` 루프를 사용하여 데이터 서비스에서 관련된 `Orders` 엔터티 페이지를 로드합니다.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>참고자료

- [지연 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [방법: 관련된 엔터티 로드](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)
