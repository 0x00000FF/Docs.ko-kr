---
title: FILESTREAM 데이터
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 782674cb38669c400bd5d730c2fd0c144778a985
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357780"
---
# <a name="filestream-data"></a><span data-ttu-id="8439c-102">FILESTREAM 데이터</span><span class="sxs-lookup"><span data-stu-id="8439c-102">FILESTREAM Data</span></span>
<span data-ttu-id="8439c-103">FILESTREAM 저장소 특성은 varbinary(max) 열에 저장된 이진(BLOB) 데이터에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="8439c-104">FILESTREAM 이전에는 이진 데이터를 저장하려면 특별한 처리가 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="8439c-105">텍스트 문서, 이미지 및 비디오 같이 구조화되지 않은 데이터는 대개 데이터베이스의 외부에 저장되어 관리가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8439c-106">SqlClient에서 FILESTREAM 데이터로 작업하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="8439c-107">varbinary(max) 열에 FILESTREAM 특성을 지정하면 SQL Server에서는 데이터베이스 파일 대신 로컬 NTFS 파일 시스템에 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="8439c-108">데이터가 별도로 저장되기는 하지만 데이터베이스에 저장된 varbinary(max) 데이터로 작업할 때와 동일한 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="8439c-109">FILESTREAM에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="8439c-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="8439c-110">[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server <xref:System.Data.SqlClient>, 지원 읽기 및 쓰기를 사용 하 여 FILESTREAM 데이터는 <xref:System.Data.SqlTypes.SqlFileStream> 에 정의 된 클래스는 <xref:System.Data.SqlTypes> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="8439c-111">`SqlFileStream`은 데이터 스트림에 대한 읽기 및 쓰기 메서드를 제공하는 <xref:System.IO.Stream> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="8439c-112">스트림에서 읽으면 바이트 배열과 같은 데이터가 스트림에서 데이터 구조로 전송되고,</span><span class="sxs-lookup"><span data-stu-id="8439c-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="8439c-113">데이터를 쓰면 데이터가 데이터 구조에서 스트림으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-sql-server-table"></a><span data-ttu-id="8439c-114">SQL Server 테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="8439c-114">Creating the SQL Server Table</span></span>  
 <span data-ttu-id="8439c-115">다음 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문은 employees라는 테이블을 만들어 데이터 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="8439c-116">FILESTREAM 저장소를 설정한 후에는 다음에 나오는 코드 예제와 함께 이 테이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="8439c-117">SQL Server 온라인 설명서의 리소스에 대 한 링크는이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="8439c-118">예제: FILESTREAM 데이터 읽기, 덮어쓰기 및 삽입</span><span class="sxs-lookup"><span data-stu-id="8439c-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="8439c-119">다음 샘플에서는 FILESTREAM에서 데이터를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="8439c-120">이 코드에서는 `FileAccess`를 `Read`로 설정하고 `FileOptions`를 `SequentialScan`으로 설정하여 파일의 논리 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="8439c-121">그런 다음 코드에서는 SqlFileStream의 바이트를 버퍼로 읽어오고</span><span class="sxs-lookup"><span data-stu-id="8439c-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="8439c-122">콘솔 창에 바이트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="8439c-123">이 샘플에서는 FILESTREAM에 데이터를 써서 기존의 모든 데이터를 덮어쓰는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="8439c-124">이 코드에서는 `SqlFileStream`를 `FileAccess`로 설정하고 `Write`를 `FileOptions`으로 설정하여 파일의 논리 경로를 가져오고 `SequentialScan`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="8439c-125">그런 다음 `SqlFileStream`에 단일 바이트를 써서 파일의 모든 데이터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="8439c-126">이 샘플에서는 Seek 메서드로 파일 끝에 데이터를 추가하여 FILESTREAM에 데이터를 쓰는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="8439c-127">이 코드에서는 `SqlFileStream`를 `FileAccess`로 설정하고 `ReadWrite`를 `FileOptions`으로 설정하여 파일의 논리 경로를 가져오고 `SequentialScan`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="8439c-128">코드에서는 Seek 메서드를 사용하여 파일의 끝을 찾은 다음 기존 파일에 단일 바이트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 <span data-ttu-id="8439c-129">또 다른 예제를 참조 하십시오. [저장 하 고 파일 스트림 열에 이진 데이터를 인출 하는 방법을](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="8439c-130">SQL Server 온라인 설명서 리소스</span><span class="sxs-lookup"><span data-stu-id="8439c-130">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="8439c-131">FILESTREAM에 대 한 전체 설명서는 SQL Server 온라인 설명서의 다음 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="8439c-132">항목</span><span class="sxs-lookup"><span data-stu-id="8439c-132">Topic</span></span>|<span data-ttu-id="8439c-133">설명</span><span class="sxs-lookup"><span data-stu-id="8439c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8439c-134">[FILESTREAM 저장소 디자인 및 구현](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8439c-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="8439c-135">FILESTREAM 문서 및 관련 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="8439c-136">[FILESTREAM 개요](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8439c-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="8439c-137">FILESTREAM 저장소를 사용해야 하는 경우 및 FILESTREAM 저장소가 SQL Server 데이터베이스 엔진을 NTFS 파일 시스템과 통합하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="8439c-138">[FILESTREAM 저장소 시작](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8439c-138">[Getting Started with FILESTREAM Storage](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="8439c-139">SQL Server 인스턴스에서 FILESTREAM을 사용하도록 설정하는 방법, 저장된 FILESTREAM 데이터에 데이터베이스와 테이블을 만드는 방법 및 FILESTREAM 데이터가 포함된 행을 조작하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="8439c-140">[클라이언트 응용 프로그램에서 FILESTREAM 저장소 사용](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8439c-140">[Using FILESTREAM Storage in Client Applications](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="8439c-141">FILESTREAM 데이터로 작업하기 위한 Win32 API 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|<span data-ttu-id="8439c-142">[FILESTREAM 및 기타 SQL Server 기능](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8439c-142">[FILESTREAM and Other SQL Server Features](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span></span>|<span data-ttu-id="8439c-143">SQL Server의 다른 기능과 함께 FILESTREAM 데이터를 사용할 경우의 고려 사항, 지침 및 제한 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8439c-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8439c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8439c-144">See Also</span></span>  
 [<span data-ttu-id="8439c-145">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8439c-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="8439c-146">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="8439c-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="8439c-147">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8439c-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="8439c-148">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="8439c-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="8439c-149">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="8439c-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
