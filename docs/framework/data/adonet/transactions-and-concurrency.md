---
title: 트랜잭션 및 동시성
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: bd47c5e0e2b2086e5fd0482bf4319ebab5674a54
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563389"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="d3401-102">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="d3401-102">Transactions and Concurrency</span></span>
<span data-ttu-id="d3401-103">트랜잭션은 패키지로 실행되는 하나의 명령 또는 명령 그룹으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="d3401-104">트랜잭션을 사용하여 여러 작업을 하나의 작업 단위로 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="d3401-105">또한 트랜잭션의 한 지점에서 오류가 발생하는 경우 모든 업데이트를 이전 트랜잭션 상태로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="d3401-106">트랜잭션은 데이터 일관성을 유지하기 위해 Atomicity(원자성), Consistency(일관성), Isolation(격리성) 및 Durability(영속성)를 나타내는 ACID 속성을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="d3401-107">Microsoft SQL Server 같은 대부분의 관계형 데이터베이스 시스템에서는 클라이언트 응용 프로그램이 작업을 업데이트, 삽입 또는 삭제할 때마다 잠금, 로깅 및 트랜잭션 관리 기능을 제공하여 트랜잭션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3401-108">잠금이 너무 길게 유지되면 트랜잭션에 여러 리소스가 관여하는 경우 동시성이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="d3401-109">따라서 트랜잭션은 가능한 한 짧게 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="d3401-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="d3401-110">같은 데이터베이스나 서버에 여러 테이블이 있는 트랜잭션의 경우에는 저장 프로시저의 명시적 트랜잭션이 더 효과적으로 수행되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="d3401-111">SQL Server 저장 프로시저에서는 Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` 및 `ROLLBACK TRANSACTION` 문을 사용하여 트랜잭션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="d3401-112">자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3401-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="d3401-113">SQL Server 및 Oracle 간의 트랜잭션 같은 다양 한 리소스 관리자와 관련 된 트랜잭션이 분산된 트랜잭션이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3401-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d3401-114">In This Section</span></span>  
 [<span data-ttu-id="d3401-115">로컬 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="d3401-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="d3401-116">데이터베이스에 대해 트랜잭션을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="d3401-117">분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="d3401-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="d3401-118">ADO.NET에서 분산 트랜잭션을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="d3401-119">SQL Server와의 System.Transactions 통합</span><span class="sxs-lookup"><span data-stu-id="d3401-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="d3401-120">설명 <xref:System.Transactions> 분산 트랜잭션 작업에 대 한 SQL Server와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="d3401-121">낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="d3401-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="d3401-122">낙관적 및 비관적 동시성에 대해 설명하고 동시성 위반을 테스트하는 방법에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3401-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3401-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3401-123">See Also</span></span>  
 [<span data-ttu-id="d3401-124">트랜잭션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="d3401-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [<span data-ttu-id="d3401-125">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="d3401-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="d3401-126">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3401-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="d3401-127">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="d3401-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="d3401-128">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="d3401-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="d3401-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d3401-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
