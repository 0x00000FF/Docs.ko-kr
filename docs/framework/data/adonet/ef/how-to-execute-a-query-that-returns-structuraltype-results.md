---
title: '방법: StructuralType 결과를 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
ms.openlocfilehash: c860f7b1fac7d2101f883e949218bd25bf78c1a6
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827489"
---
# <a name="how-to-execute-a-query-that-returns-structuraltype-results"></a><span data-ttu-id="c48aa-102">방법: StructuralType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="c48aa-102">How to: Execute a Query that Returns StructuralType Results</span></span>
<span data-ttu-id="c48aa-103">이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.StructuralType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.StructuralType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="c48aa-104"><xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> 및 <xref:System.Data.Metadata.Edm.ComplexType> 클래스는 <xref:System.Data.Metadata.Edm.StructuralType> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-104">The <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> and <xref:System.Data.Metadata.Edm.ComplexType> classes derive from the <xref:System.Data.Metadata.Edm.StructuralType> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="c48aa-105">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c48aa-105">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="c48aa-106">추가 합니다 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 프로젝트에 사용 하도록 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="c48aa-107">자세한 내용은 [방법: 엔터티 데이터 모델 마법사를 사용 하 여](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))입니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-107">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="c48aa-108">응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="c48aa-109">예제</span><span class="sxs-lookup"><span data-stu-id="c48aa-109">Example</span></span>  
 <span data-ttu-id="c48aa-110">이 예제에서는 <xref:System.Data.Metadata.Edm.EntityType> 결과를 반환하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-110">This example executes a query that returns <xref:System.Data.Metadata.Edm.EntityType> results.</span></span> <span data-ttu-id="c48aa-111">다음 쿼리를 `ExecuteStructuralTypeQuery` 함수에 인수로 전달하면 이 함수는 `Products`에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-111">If you pass the following query as an argument to the `ExecuteStructuralTypeQuery` function, the function displays details about the `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#selectproduct)]  
  
 <span data-ttu-id="c48aa-112">다음과 같은 매개 변수가 있는 쿼리를 전달하는 경우 <xref:System.Data.EntityClient.EntityParameter> 개체를 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 개체의 <xref:System.Data.EntityClient.EntityCommand> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c48aa-112">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## <a name="see-also"></a><span data-ttu-id="c48aa-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c48aa-113">See also</span></span>
- [<span data-ttu-id="c48aa-114">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c48aa-114">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="c48aa-115">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="c48aa-115">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
