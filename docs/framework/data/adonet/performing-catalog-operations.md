---
title: 카탈로그 작업 수행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: beb5d2db898df1c98662d53190ac1432acc746e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878229"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="dad71-102">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="dad71-102">Performing Catalog Operations</span></span>
<span data-ttu-id="dad71-103">만드는 CREATE TABLE 또는 CREATE PROCEDURE 문과 같은 카탈로그 또는 데이터베이스를 수정 하는 명령을 실행 하는 **명령** 적절 한 SQL 문을 사용 하 여 개체와 **연결** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dad71-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="dad71-104">사용 하 여 명령을 실행 합니다 **ExecuteNonQuery** 메서드의 **명령** 개체.</span><span class="sxs-lookup"><span data-stu-id="dad71-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="dad71-105">다음 코드 예제에서는 Microsoft SQL Server 데이터베이스에 저장 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dad71-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="dad71-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="dad71-106">See also</span></span>

- [<span data-ttu-id="dad71-107">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="dad71-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="dad71-108">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dad71-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="dad71-109">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="dad71-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
