---
title: SQL Server에서 대량 복사 작업
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 787fc283a258842b762923b620541b709b119894
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518113"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="28639-102">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="28639-103">Microsoft SQL Server 명명 된 인기 있는 명령줄 유틸리티를 포함 **bcp** 에 대 한 신속 하 게 대량으로 SQL Server 데이터베이스의 테이블이 나 뷰로 큰 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="28639-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="28639-104"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 이와 유사한 기능을 제공하는 관리 코드 솔루션을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28639-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="28639-105">INSERT 문 같은 다른 방법으로도 SQL Server 테이블에 데이터를 로드할 수 있지만 <xref:System.Data.SqlClient.SqlBulkCopy>는 다른 방법에 비해 성능이 크게 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="28639-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="28639-106"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28639-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="28639-107">그러나 데이터 소스가 SQL Server로 제한되어 있지 않으므로 데이터를 <xref:System.Data.DataTable> 인스턴스로 로드하거나 <xref:System.Data.IDataReader> 인스턴스를 사용하여 읽을 수 있으면 모든 데이터 소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28639-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="28639-108"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28639-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
-   <span data-ttu-id="28639-109">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-109">A single bulk copy operation</span></span>  
  
-   <span data-ttu-id="28639-110">여러 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-110">Multiple bulk copy operations</span></span>  
  
-   <span data-ttu-id="28639-111">트랜잭션 내에서의 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28639-112">.NET Framework 1.1 또는 이전 버전을 사용 하는 경우 (지원 하지 않는 합니다 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스), SQL Server TRANSACT-SQL을 실행할 수 있습니다 **BULK INSERT** 문을 사용 하 여는 <xref:System.Data.SqlClient.SqlCommand> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="28639-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28639-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="28639-113">In This Section</span></span>  
 [<span data-ttu-id="28639-114">대량 복사 예제 설정</span><span class="sxs-lookup"><span data-stu-id="28639-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="28639-115">대량 복사 예제에 사용된 테이블에 대해 설명하고 AdventureWorks 데이터베이스에 테이블을 만들기 위한 SQL 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28639-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="28639-116">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="28639-117"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에서 데이터의 단일 대량 복사 작업을 수행하는 방법과 Transact-SQL 문과 <xref:System.Data.SqlClient.SqlCommand> 클래스를 사용하여 대량 복사 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28639-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="28639-118">여러 개의 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="28639-119"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 SQL Server 인스턴스에서 데이터의 여러 대량 복사 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28639-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="28639-120">트랜잭션 및 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="28639-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="28639-121">트랜잭션 내에서 대량 복사 작업을 수행하는 방법과 트랜잭션을 커밋하거나 롤백하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28639-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28639-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="28639-122">See also</span></span>
- [<span data-ttu-id="28639-123">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28639-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="28639-124">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="28639-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
