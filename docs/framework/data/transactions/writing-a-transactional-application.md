---
title: 트랜잭션 응용 프로그램 작성
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793493"
---
# <a name="writing-a-transactional-application"></a>트랜잭션 응용 프로그램 작성
트랜잭션 응용 프로그램 프로그래머는 <xref:System.Transactions> 네임스페이스가 제공하는 두 가지 프로그래밍 모델을 활용하여 트랜잭션을 만들 수 있습니다. 사용 하 여 명시적 프로그래밍 모델을 활용할 수 있습니다 합니다 <xref:System.Transactions.Transaction> 클래스 또는 트랜잭션을 관리 하는 자동으로 인프라에서 사용 하 여 암시적 프로그래밍 모델을 <xref:System.Transactions.TransactionScope> 클래스입니다. 암시적 트랜잭션 모델을 사용 하 여 개발 하는 것이 좋습니다. 트랜잭션 범위를 사용 하는 방법에 자세한 정보를 찾을 수 있습니다 합니다 [트랜잭션 범위를 사용 하 여 암시적 트랜잭션 구현](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) 항목입니다.  
  
 두 모델은 모두 프로그램이 일관된 상태에 도달할 때 트랜잭션을 커밋하는 기능을 지원합니다. 커밋이 성공하면 트랜잭션이 영구적으로 커밋됩니다. 커밋이 실패하면 트랜잭션이 중단됩니다. 응용 프로그램에서 트랜잭션을 성공적으로 완료할 수 없는 경우 트랜잭션을 중단하고 그 결과를 취소합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
### <a name="creating-a-transaction"></a>트랜잭션 만들기  
 <xref:System.Transactions> 네임스페이스에서는 트랜잭션을 만드는 두 가지 모델을 제공합니다. 이 모델에 대해서는 다음 항목에서 설명합니다.  
  
 [트랜잭션 범위를 사용하여 암시적 트랜잭션 구현](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.TransactionScope> 클래스를 사용하여 암시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.  
  
 [CommittableTransaction을 사용하여 명시적 트랜잭션 구현](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.CommittableTransaction> 클래스를 사용하여 명시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.  
  
### <a name="escalating-transaction-management"></a>트랜잭션 관리 에스컬레이션  
 트랜잭션이 다른 응용 프로그램 도메인의 리소스에 액세스해야 하는 경우 또는 다른 지속적인 리소스 관리자를 참여시키려는 경우 트랜잭션이 MSDTC에 의해 관리되도록 자동으로 에스컬레이션됩니다. 트랜잭션 에스컬레이션에 대해서는 설명 된 [트랜잭션 관리 에스컬레이션](../../../../docs/framework/data/transactions/transaction-management-escalation.md) 항목입니다.  
  
### <a name="concurrency"></a>동시성  
 항목 [DependentTransaction으로 동시성 관리](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) 사용 하 여 비동기 작업 간의 동시성을 실현할 수 있는 방법을 보여 줍니다는 <xref:System.Transactions.DependentTransaction> 클래스입니다.  
  
### <a name="com-interop"></a>COM+ Interop  
 항목 [엔터프라이즈 서비스 및 COM + 트랜잭션과 상호 운용성](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) COM + 트랜잭션과 상호 작용 하 여 분산된 트랜잭션을 만드는 방법을 보여 줍니다.  
  
### <a name="diagnostics"></a>진단  
 [진단 추적](../../../../docs/framework/data/transactions/diagnostic-traces.md) 에서 생성 되는 추적 코드를 사용 하는 방법에 대해 설명 합니다 <xref:System.Transactions> 응용 프로그램에서 오류를 해결 하는 인프라입니다.  
  
### <a name="working-within-aspnet"></a>ASP.NET 작업  
 합니다 [ASP.NET에서 System.Transactions를 사용 하 여](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) 성공적으로 사용 하는 방법에 대해 설명 <xref:System.Transactions> ASP.NET 응용 프로그램 내에서.
