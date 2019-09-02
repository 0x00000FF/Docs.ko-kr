---
title: 데이터 세트에 DataTable 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: d62d55771e4fda74d336163b3f53b3f50cfb1e39
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205284"
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="9b0e0-102">데이터 세트에 DataTable 추가</span><span class="sxs-lookup"><span data-stu-id="9b0e0-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="9b0e0-103">ADO.NET에서는 <xref:System.Data.DataTable> 개체를 만들어 기존 <xref:System.Data.DataSet>에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b0e0-104">또한 <xref:System.Data.DataTable> 및 <xref:System.Data.DataTable.PrimaryKey%2A> 속성을 사용하여 <xref:System.Data.DataColumn.Unique%2A>에 대한 제약 조건 정보를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b0e0-105">예제</span><span class="sxs-lookup"><span data-stu-id="9b0e0-105">Example</span></span>  
 <span data-ttu-id="9b0e0-106">다음 예제에서는 <xref:System.Data.DataSet>을 구성하고 새 <xref:System.Data.DataTable> 개체를 <xref:System.Data.DataSet>에 추가한 다음 세 개의 <xref:System.Data.DataColumn> 개체를 해당 테이블에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="9b0e0-107">마지막으로 이 코드에서는 열 하나를 기본 키 열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="9b0e0-108">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="9b0e0-108">Case Sensitivity</span></span>  
 <span data-ttu-id="9b0e0-109">이름은 같으나 대/소문자가 다른 두 개 이상의 테이블이나 관계가 하나의 <xref:System.Data.DataSet>에 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b0e0-110">이런 경우 테이블과 관계를 이름에 따라 참조할 때는 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="9b0e0-111">예를 들어 <xref:System.Data.DataSet> **데이터 집합** 에 **table1** 과 **table1**테이블이 포함 되어 있는 경우 table1은 이름으로 **table1** **["table1"]** 및 **table1** 은 **dataset ["table1"]** 로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="9b0e0-112">테이블 중 하나를 데이터 집합으로 참조 하려고 **합니다. tables ["TABLE1"]** 은 예외를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="9b0e0-113">특별한 이름의 테이블이나 관계가 하나만 있으면 대/소문자 구분 동작이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="9b0e0-114">예를 들어에 <xref:System.Data.DataSet> **Table1**만 있는 경우에는 **dataSet ["Table1"]** 을 사용 하 여 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b0e0-115"><xref:System.Data.DataSet.CaseSensitive%2A>의 <xref:System.Data.DataSet> 속성은 이 동작에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="9b0e0-116"><xref:System.Data.DataSet.CaseSensitive%2A> 속성은 <xref:System.Data.DataSet> 내의 데이터에 적용되며 정렬, 찾기, 필터링, 제약 조건 적용 등에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="9b0e0-117">네임스페이스 지원</span><span class="sxs-lookup"><span data-stu-id="9b0e0-117">Namespace Support</span></span>  
 <span data-ttu-id="9b0e0-118">ADO.NET 2.0보다 이전 버전에서는 네임스페이스가 서로 다르더라도 두 테이블의 이름이 같을 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="9b0e0-119">하지만 ADO.NET 2.0에서는 이러한 제한이 사라졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="9b0e0-120"><xref:System.Data.DataSet>에 <xref:System.Data.DataTable.TableName%2A> 속성 값은 같지만 <xref:System.Data.DataTable.Namespace%2A> 속성 값이 다른 두 테이블이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0e0-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0e0-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b0e0-121">See also</span></span>

- [<span data-ttu-id="9b0e0-122">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="9b0e0-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="9b0e0-123">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9b0e0-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
