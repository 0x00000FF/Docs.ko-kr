---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3881ecfd895bd22a476bdac7dd0b7c1b112092e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526380"
---
# <a name="datatablereaders"></a><span data-ttu-id="f6ffd-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="f6ffd-102">DataTableReaders</span></span>
<span data-ttu-id="f6ffd-103"><xref:System.Data.DataTableReader>는 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용을 하나 이상의 정방향 읽기 전용 결과 집합 형태로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="f6ffd-104">만들 때를 **DataTableReader** 에서 **DataTable**에 결과 **DataTableReader** 개체와 동일한 데이터를 가진 하나의 결과 집합이 포함 되어 있습니다.는  **DataTable** 에서 생성 된, 삭제 된 것으로 표시 된 모든 행을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="f6ffd-105">열이 원래와 동일한 순서로 표시 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="f6ffd-106">A **DataTableReader** 를 호출 하 여 만든 경우 여러 결과 집합을 포함할 수 있습니다 <xref:System.Data.DataSet.CreateDataReader%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="f6ffd-107">결과가 동일한 순서로 합니다 **DataTables** 에 **데이터 집합** 개체의 <xref:System.Data.DataSet.Tables%2A> 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6ffd-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f6ffd-108">In This Section</span></span>  
 [<span data-ttu-id="f6ffd-109">DataReader 만들기</span><span class="sxs-lookup"><span data-stu-id="f6ffd-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="f6ffd-110">만드는 방법에 설명 된 **DataTableReader** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="f6ffd-111">DataTable 탐색</span><span class="sxs-lookup"><span data-stu-id="f6ffd-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="f6ffd-112">사용 방법을 설명 합니다는 **읽기** 의 콘텐츠를 이동 하는 메서드를 **DataTableReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ffd-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ffd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6ffd-113">See Also</span></span>  
 [<span data-ttu-id="f6ffd-114">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="f6ffd-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="f6ffd-115">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="f6ffd-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
