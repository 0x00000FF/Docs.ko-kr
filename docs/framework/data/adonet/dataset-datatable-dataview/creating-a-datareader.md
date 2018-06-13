---
title: DataReader 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: c5073a553926fdfdd78b0b6837cdc07b58ac7faf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755515"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="b09eb-102">DataReader 만들기</span><span class="sxs-lookup"><span data-stu-id="b09eb-102">Creating a DataReader</span></span>
<span data-ttu-id="b09eb-103"><xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스에는 <xref:System.Data.DataTable.CreateDataReader%2A>의 내용이나 <xref:System.Data.DataTable> 개체의 <xref:System.Data.DataSet> 컬렉션 내용을 하나 이상의 정방향 읽기 전용 커서로 반환하는 <xref:System.Data.DataSet.Tables%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b09eb-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b09eb-104">예제</span><span class="sxs-lookup"><span data-stu-id="b09eb-104">Example</span></span>  
 <span data-ttu-id="b09eb-105">다음 콘솔 응용 프로그램에서는 <xref:System.Data.DataTable> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b09eb-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="b09eb-106">이 예제에서는 다음 채워진 전달 <xref:System.Data.DataTable> 를 호출 하는 프로시저는 <xref:System.Data.DataTable.CreateDataReader%2A> 메서드 내에 포함 된 결과를 반복 하는 <xref:System.Data.DataTableReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="b09eb-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="b09eb-107">이 예제에서는 콘솔 창에 다음 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b09eb-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="b09eb-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b09eb-108">See Also</span></span>  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [<span data-ttu-id="b09eb-109">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="b09eb-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="b09eb-110">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b09eb-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
