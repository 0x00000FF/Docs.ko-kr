---
title: "로컬 트랜잭션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f7b002c1439a95929ca177aeced91164430220c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="local-transactions"></a>로컬 트랜잭션
[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]의 트랜잭션은 여러 작업을 바인딩하여 하나의 작업 단위로 실행하려는 경우에 사용합니다. 예를 들어 응용 프로그램이 두 가지 작업을 수행한다고 가정합니다. 먼저 응용 프로그램에서 주문 정보로 테이블을 업데이트합니다. 그런 다음, 응용 프로그램에서 재고 정보가 포함된 테이블을 업데이트하고 주문이 들어온 품목을 차변에 기입합니다. 이 작업에 실패 하면 다음 두 업데이트가 모두 롤백됩니다.  
  
## <a name="determining-the-transaction-type"></a>트랜잭션 유형 결정  
 트랜잭션이 단일 단계 트랜잭션이 고 데이터베이스에서 직접 처리 되는 경우에 한 로컬 트랜잭션으로 간주 됩니다. 트랜잭션이는 트랜잭션 모니터로 조정 하 고 트랜잭션 확인에 2 단계 커밋 같은 오류 없이 안전한 메커니즘을 사용 하 여 분산된 트랜잭션이 되도록 간주 됩니다.  
  
 각 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에는 로컬 트랜잭션을 수행하기 위한 고유한 `Transaction` 개체가 있습니다. SQL Server 데이터베이스에서 트랜잭션을 수행해야 하는 경우 <xref:System.Data.SqlClient> 트랜잭션을 선택합니다. Oracle 트랜잭션의 경우 <xref:System.Data.OracleClient> 공급자를 사용합니다. 트랜잭션이 필요한 공급자 독립적인 코드를 작성하는 데 사용할 수 있는 새로운 <xref:System.Data.Common.DbTransaction> 클래스도 있습니다.  
  
> [!NOTE]
>  트랜잭션은 서버에서 수행하는 것이 가장 효율적입니다. 명시적 트랜잭션을 폭넓게 사용하는 SQL Server 데이터베이스를 사용하는 경우 Transact-SQL BEGIN TRANSACTION 문을 사용하여 트랜잭션을 저장 프로시저로 작성하는 것이 좋습니다. 서버측 트랜잭션 수행에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.  
  
## <a name="performing-a-transaction-using-a-single-connection"></a>단일 연결을 사용하여 트랜잭션 수행  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]에서는 `Connection` 개체로 트랜잭션을 제어합니다. `BeginTransaction` 메서드를 사용하면 로컬 트랜잭션을 시작할 수 있습니다. 트랜잭션이 시작되면 `Transaction` 개체의 `Command` 속성을 사용하여 해당 트랜잭션에 명령을 인리스트먼트할 수 있습니다. 그런 다음 트랜잭션 구성 요소의 성공 또는 실패에 따라 데이터 소스에서 수정된 내용을 커밋 또는 롤백할 수 있습니다.  
  
> [!NOTE]
>  `EnlistDistributedTransaction` 메서드는 로컬 트랜잭션에 사용할 수 없습니다.  
  
 트랜잭션의 범위는 연결로 제한됩니다. 다음 예제에서는 `try` 블록에서 두 개의 개별 명령으로 이루어진 명시적 트랜잭션을 수행합니다. 두 명령은 AdventureWorks [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 샘플 데이터베이스에서 Production.ScrapReason 테이블에 대해 INSERT 문을 실행합니다. 이 작업은 예외가 throw되지 않을 경우 커밋됩니다. `catch` 블록의 코드는 예외가 발생하는 경우 트랜잭션을 롤백합니다. 트랜잭션이 완료되기 전에 트랜잭션이 중단되거나 연결이 끊어지면 트랜잭션이 자동으로 롤백됩니다.  
  
## <a name="example"></a>예제  
 다음 단계를 사용하여 트랜잭션을 수행합니다.  
  
1.  <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> 개체의 <xref:System.Data.SqlClient.SqlConnection> 메서드를 호출하여 트랜잭션의 시작을 표시합니다. <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> 메서드는 트랜잭션에 대한 참조를 반환합니다. 이 참조는 트랜잭션에 인리스트먼트된 <xref:System.Data.SqlClient.SqlCommand> 개체에 할당됩니다.  
  
2.  `Transaction`의 <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> 속성에 실행할 <xref:System.Data.SqlClient.SqlCommand> 개체를 할당합니다. `Transaction` 개체를 `Transaction` 개체의 `Command` 속성에 할당하지 않은 상태에서 활성 트랜잭션 연결로 명령을 실행하면 예외가 throw됩니다.  
  
3.  명령을 실행합니다.  
  
4.  <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> 개체의 <xref:System.Data.SqlClient.SqlTransaction> 메서드를 호출하여 트랜잭션을 완료하거나 <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> 메서드를 호출하여 트랜잭션을 종료합니다. <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> 또는 <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> 메서드가 실행되기 전에 연결이 닫히거나 삭제되면 트랜잭션이 롤백됩니다.  
  
 다음 코드 예제에서는 Microsoft SQL Server와 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 트랜잭션 논리를 설명합니다.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [분산 트랜잭션](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 [SQL Server와의 System.Transactions 통합](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
