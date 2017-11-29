---
title: "Windows Communication Foundation 트랜잭션 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2be5e7622c51da37c0f39c12258f50b74483fa53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a>Windows Communication Foundation 트랜잭션 개요
트랜잭션은 동작 또는 작업 집합을 하나의 개별 실행 단위로 그룹화하는 방법을 제공합니다. 트랜잭션은 다음 속성을 가진 작업 컬렉션입니다.  
  
-   원자성. 특정 트랜잭션에서 완료된 모든 업데이트가 커밋되어 영구화되거나 모두 중단되어 이전 상태로 롤백되도록 합니다.  
  
-   일관성. 트랜잭션에서 변경된 내용이 하나의 일관된 상태에서 다른 일관된 상태로의 변환을 나타내도록 합니다. 예를 들어 당좌 예금 계좌에서 보통 예금 계좌로 돈을 이체하는 트랜잭션은 전체 은행 계좌의 금액을 변경하지 않습니다.  
  
-   격리성 트랜잭션이 다른 동시 트랜잭션에 속하는 커밋되지 않은 변경 내용을 인식하지 않도록 합니다. 격리는 한 트랜잭션의 유지가 다른 트랜잭션의 실행에 예기치 않은 영향을 주지 않도록 하는 동시에 추상적인 동시성을 제공합니다.  
  
-   지속성. 커밋되고 나면 데이터베이스 레코드 같은 관리되는 리소스에 대한 업데이트가 실패한 경우에도 지속되도록 합니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 웹 서비스 응용 프로그램에서 분산 트랜잭션을 만들 수 있는 다양한 기능을 제공합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램이 타사 기술을 사용하여 작성된 상호 운용 가능한 웹 서비스 같은 상호 운용 가능한 응용 프로그램으로 트랜잭션을 이동할 수 있도록 하는 WS-AT(WS-AtomicTransaction) 프로토콜 지원을 구현합니다. 또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 트랜잭션 흐름을 가능하게 하는 interop 기능이 필요하지 않은 시나리오에서 사용할 수 있는 OLE 트랜잭션 프로토콜 지원을 구현합니다.  
  
 응용 프로그램 구성 파일에서 바인딩을 구성하여 트랜잭션 흐름을 가능하거나 불가능하게 하고 바인딩에 원하는 트랜잭션 프로토콜을 설정할 수 있습니다. 또한 구성 파일을 사용하여 서비스 수준에서 트랜잭션 시간 초과를 설정할 수 있습니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][트랜잭션 흐름 사용](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)합니다.  
  
 <xref:System.ServiceModel> 네임스페이스의 트랜잭션 특성을 사용하여 다음을 수행할 수 있습니다.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 사용하여 트랜잭션 시간 초과와 격리 수준 필터링을 구성합니다.  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 트랜잭션 기능을 활성화하고 트랜잭션 완료 동작을 구성합니다.  
  
-   계약 메서드의 <xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.OperationContractAttribute> 특성을 사용하여 트랜잭션 흐름을 필요로 하거나 허용 또는 거부합니다.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ServiceModel 트랜잭션 특성](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ServiceModel 트랜잭션 특성](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [트랜잭션 흐름 사용](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
