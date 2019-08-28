---
title: 단일 대량 복사 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 07c705b9daeeb043ef36f1e3272a3bf259a3c23e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043889"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="70463-102">단일 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="70463-102">Single Bulk Copy Operations</span></span>

<span data-ttu-id="70463-103">SQL Server 대량 복사 작업을 수행하는 가장 간단한 접근 방식은 데이터베이스에 단일 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70463-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="70463-104">기본적으로 대량 복사 작업은 격리된 작업으로 수행됩니다. 복사 작업은 롤백할 수 없는 비트랜잭트 방식으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="70463-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>

> [!NOTE]
> <span data-ttu-id="70463-105">오류가 발생할 때 대량 복사의 전체 또는 일부를 롤백해야 하는 경우에는 <xref:System.Data.SqlClient.SqlBulkCopy>에서 관리되는 트랜잭션을 사용하거나 기존 트랜잭션 내에서 대량 복사 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="70463-106">**SqlBulkCopy** 는 연결이 <xref:System.Transactions> **시스템 트랜잭션** 트랜잭션에 암시적 또는 명시적으로 참여 하는 경우에도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>
>
> <span data-ttu-id="70463-107">자세한 내용은 [트랜잭션 및 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70463-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>

<span data-ttu-id="70463-108">일반적으로 대량 복사 작업을 수행하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-108">The general steps for performing a bulk copy operation are as follows:</span></span>

1. <span data-ttu-id="70463-109">소스 서버에 연결하고 복사할 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70463-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="70463-110">데이터를 <xref:System.Data.IDataReader> 또는 <xref:System.Data.DataTable> 개체에서 검색할 수 있으면 다른 소스에서 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>

2. <span data-ttu-id="70463-111">**SqlBulkCopy** 에 대 한 연결을 설정 하지 않으려는 경우 대상 서버에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>

3. <span data-ttu-id="70463-112"><xref:System.Data.SqlClient.SqlBulkCopy> 개체를 만들고 필요한 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>

4. <span data-ttu-id="70463-113">**Destinationtablename** 속성을 설정 하 여 대량 삽입 작업의 대상 테이블을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>

5. <span data-ttu-id="70463-114">**WriteToServer** 메서드 중 하나를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-114">Call one of the **WriteToServer** methods.</span></span>

6. <span data-ttu-id="70463-115">필요에 따라 속성을 업데이트 하 고 **WriteToServer** 를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>

7. <span data-ttu-id="70463-116"><xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>를 호출하거나 대량 복사 작업을 `Using` 문 내에 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>

> [!CAUTION]
> <span data-ttu-id="70463-117">소스 열과 대상 열의 데이터 형식은 일치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="70463-118">데이터 형식이 일치 하지 않는 경우 **SqlBulkCopy** 는에서 <xref:System.Data.SqlClient.SqlParameter.Value%2A>사용 하는 규칙을 사용 하 여 각 원본 값을 대상 데이터 형식으로 변환 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="70463-119">변환을 수행하면 성능에 영향을 줄 뿐 아니라 예기치 않은 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="70463-120">예를 들어, `Double` 데이터 형식은 일반적으로 `Decimal` 데이터 형식으로 변환되지만 항상 그런 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="70463-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>

## <a name="example"></a><span data-ttu-id="70463-121">예제</span><span class="sxs-lookup"><span data-stu-id="70463-121">Example</span></span>

<span data-ttu-id="70463-122">다음 콘솔 애플리케이션에서는 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하여 데이터를 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70463-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="70463-123">이 예제에서는 <xref:System.Data.SqlClient.SqlDataReader> 에서 데이터를 복사 하는 데 사용 되는 **Production.Product** SQL Server의 테이블 **AdventureWorks** 동일한 데이터베이스의 유사한 테이블에는 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="70463-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70463-124">이 샘플에 설명 된 대로 작업 테이블을 만든 경우가 아니면 실행 되지 것입니다 [대량 복사 예제 설정](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="70463-125">이 코드는 사용 하는 구문을 보여 주기 위해 제공 됩니다 **SqlBulkCopy** 만 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="70463-126">소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70463-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="70463-127">Transact-SQL 및 Command 클래스를 사용하여 대량 복사 작업 수행</span><span class="sxs-lookup"><span data-stu-id="70463-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>

<span data-ttu-id="70463-128">다음 예제에서는 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> 메서드를 사용하여 BULK INSERT 문을 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70463-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>

> [!NOTE]
> <span data-ttu-id="70463-129">데이터 소스의 파일 경로는 서버에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="70463-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="70463-130">대량 복사 작업을 올바르게 수행하려면 서버 프로세스에서 해당 경로에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70463-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>

```vb
Using connection As SqlConnection = New SqlConnection(connectionString)
Dim queryString As String = _
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"
connection.Open()
SqlCommand command = New SqlCommand(queryString, connection);

command.ExecuteNonQuery()
End Using
```

```csharp
using (SqlConnection connection = New SqlConnection(connectionString))
{
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +
    "FROM 'f:\mydata\data.tbl' " +
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";
connection.Open();
SqlCommand command = new SqlCommand(queryString, connection);

command.ExecuteNonQuery();
}
```

## <a name="see-also"></a><span data-ttu-id="70463-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="70463-131">See also</span></span>

- [<span data-ttu-id="70463-132">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="70463-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="70463-133">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="70463-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
