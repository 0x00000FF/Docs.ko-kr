---
title: "DataSet별 연산자 예제(LINQ to DataSet)"
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
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dea56be6aad0e596eaf9a61fae1352474f99fb04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="469e7-102">DataSet별 연산자 예제(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="469e7-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="469e7-103">이 항목의 예제에서는 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드와 <xref:System.Data.DataRowComparer> 클래스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="469e7-104">`FillDataSet` 에 이러한 예제에서 사용 하는 방법이 지정 되어 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="469e7-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="469e7-106">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="469e7-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="469e7-107">자세한 내용은 참조 [하는 방법: Visual Studio에서 데이터 집합 프로젝트에 LINQ 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="469e7-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="469e7-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="469e7-109">예제</span><span class="sxs-lookup"><span data-stu-id="469e7-109">Example</span></span>  
 <span data-ttu-id="469e7-110">이 예제에서는 <xref:System.Data.DataTable> 메서드를 사용하여 쿼리 결과가 있는 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="469e7-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="469e7-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="469e7-112">예제</span><span class="sxs-lookup"><span data-stu-id="469e7-112">Example</span></span>  
 <span data-ttu-id="469e7-113">이 예제에서는 <xref:System.Data.DataRowComparer>를 사용하여 서로 다른 두 데이터 행을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="469e7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="469e7-114">See Also</span></span>  
 [<span data-ttu-id="469e7-115">데이터 집합으로 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="469e7-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="469e7-116">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="469e7-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
