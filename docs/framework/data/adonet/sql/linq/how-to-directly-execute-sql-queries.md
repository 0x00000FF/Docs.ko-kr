---
title: '방법: SQL 쿼리 직접 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 04353361f8356b1d2b2aa3b930bb9b5ab88b9c0b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583675"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="e5836-102">방법: SQL 쿼리 직접 실행</span><span class="sxs-lookup"><span data-stu-id="e5836-102">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e5836-103">을 작성한 쿼리를 텍스트 형식의 매개 변수가 있는 SQL 쿼리로 변환하고 SQL 서버에 전달하여 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-103">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="e5836-104">SQL에서는 응용 프로그램에서 로컬로 사용할 수 있는 다양한 메서드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e5836-105">에서 이러한 로컬 메서드를 해당 작업과 SQL 환경 내부에서 사용 가능한 함수로 변환하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-105">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="e5836-106">대부분의 메서드 및.NET Framework 기본 제공 형식에서 연산자가 SQL 명령으로 직접 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-106">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="e5836-107">일부는 사용할 수 있는 함수에서 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="e5836-108">생성될 수 없는 일부는 런타임 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="e5836-109">자세한 내용은 [SQL-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="e5836-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리가 부족하여 특수한 작업을 수행할 수 없는 경우 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드를 사용하여 SQL 쿼리를 실행하고 쿼리의 결과를 직접 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5836-111">예제</span><span class="sxs-lookup"><span data-stu-id="e5836-111">Example</span></span>  
 <span data-ttu-id="e5836-112">다음 예제에서는 `Customer` 클래스의 데이터가 두 개의 테이블(customer1 및 customer2)에 나누어져 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="e5836-113">쿼리는 `Customer` 개체의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="e5836-114">표 형식 결과의 열 이름이 엔터티 클래스의 열 속성과 일치할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 모든 SQL 쿼리에서 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5836-115">예제</span><span class="sxs-lookup"><span data-stu-id="e5836-115">Example</span></span>  
 <span data-ttu-id="e5836-116">또한 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드는 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="e5836-117">다음의 코드를 사용하여 매개 변수가 있는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="e5836-118">매개 변수는 `Console.WriteLine()` 및 `String.Format()`에서 사용되는 동일한 중괄호 표기법을 사용하여 쿼리 텍스트에서 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5836-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="e5836-119">사실 `String.Format()` 중괄호 중괄호로 묶인된 매개 변수를 대체와 같은 매개 변수 이름 생성을 제공 하는 쿼리 문자열에서 실제로 라고 @p0를 @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="e5836-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5836-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5836-120">See also</span></span>

- [<span data-ttu-id="e5836-121">배경 정보</span><span class="sxs-lookup"><span data-stu-id="e5836-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="e5836-122">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="e5836-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
