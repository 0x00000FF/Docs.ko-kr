---
title: '방법: 엔터티 관계 (WCF Data Services)를 정의 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
ms.openlocfilehash: 6baf873e08bb65e97d9fdc9b0d0d500bf7a77836
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538365"
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>방법: 엔터티 관계 (WCF Data Services)를 정의 합니다.
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 새 엔터티를 추가할 때 새 엔터티와 관련 엔터티 간의 관계가 자동으로 정의되지 않습니다. 엔터티 인스턴스 간의 관계를 만들고 변경할 수 있으며 클라이언트 라이브러리에서 이러한 변경 사항을 데이터 서비스에 반영하도록 지정할 수 있습니다. 자세한 내용은 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 개체 인스턴스를 만든 다음 <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>의 <xref:System.Data.Services.Client.DataServiceContext> 메서드를 호출하여 관련 주문에 대한 링크와 함께 컨텍스트의 항목을 만듭니다. <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 HTTP POST 메시지가 데이터 서비스로 전송됩니다.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> 메서드를 사용하여 특정 `Order_Details` 개체에 대한 참조가 있는 관련 `Orders` 개체에 `Products` 개체를 추가하는 방법을 보여 줍니다. <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> 및 <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> 메서드는 관계를 정의합니다. 이 예제에서는 `Order_Details` 개체에 대한 탐색 속성도 명시적으로 설정됩니다.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>참고자료
- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [방법: 추가, 수정 및 엔터티를 삭제 합니다.](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md)
