---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 2849d159fbfdb0c0739b76fd288a987d4ce3d02f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786068"
---
# <a name="datatables"></a><span data-ttu-id="bf0fe-102">DataTables</span><span class="sxs-lookup"><span data-stu-id="bf0fe-102">DataTables</span></span>
<span data-ttu-id="bf0fe-103"><xref:System.Data.DataSet>은 테이블 컬렉션, 관계 및 제약 조건으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="bf0fe-104">Ado.net에서는 <xref:System.Data.DataTable> 개체에서 테이블을 나타내는 데 사용 되며를 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="bf0fe-105">A **DataTable** 메모리 내 관계형 데이터의 테이블 데이터가 로컬 합니다. 상주 하지만 Microsoft SQL Server를 사용 하 여 같은 데이터 원본에서 채울 수 있습니다 하는.NET 기반 응용 프로그램을 **DataAdapter** 자세한 내용은 참조 하십시오 [DataAdapter에서 DataSet 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .</span><span class="sxs-lookup"><span data-stu-id="bf0fe-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="bf0fe-106">합니다 **DataTable** 클래스의 멤버인 합니다 **System.Data** .NET Framework 클래스 라이브러리 내의 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="bf0fe-107">만들고 사용할 수는 **DataTable** 독립적으로 또는 멤버인을 **데이터 집합**, 및 **DataTable** 개체 다른.NET Framework 개체와 함께에서 사용할 수도 있습니다 포함 된 <xref:System.Data.DataView>합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="bf0fe-108">테이블 컬렉션에 액세스를 **데이터 집합** 를 통해를 **테이블** 속성을 **데이터 집합** 개체.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="bf0fe-109">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="bf0fe-110">스키마를 정의 하는 **DataTable** 사용 하 여 <xref:System.Data.DataColumn> 개체 뿐만 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="bf0fe-111">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="bf0fe-112">스키마 이외에 **DataTable** 포함 하 고 데이터를 정렬 하는 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="bf0fe-113"><xref:System.Data.DataRow> 클래스는 테이블에 포함된 실제 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="bf0fe-114">사용할 합니다 **DataRow** 및 해당 속성 및 메서드를 검색, 평가 및 테이블의 데이터를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="bf0fe-115">액세스 하는 행 내에서 데이터를 변경 합니다 **DataRow** 개체의 현재 및 원래 상태를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="bf0fe-116">테이블에서 하나 이상의 관련 열을 사용하면 테이블 간에 부모-자식 관계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="bf0fe-117">간의 관계를 만들면 **DataTable** 사용 하 여 개체를 <xref:System.Data.DataRelation>입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="bf0fe-118">**DataRelation** 개체는 특정 행의 관련된 자식 또는 부모 행을 반환 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="bf0fe-119">자세한 내용은 [Datarelation 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf0fe-120">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bf0fe-120">In This Section</span></span>  
 [<span data-ttu-id="bf0fe-121">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="bf0fe-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="bf0fe-122">만드는 방법을 설명를 **DataTable** 에 추가 하는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="bf0fe-123">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="bf0fe-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="bf0fe-124">만들기 및 사용 하는 방법에 대 한 정보를 제공 **DataColumn** 개체 및 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="bf0fe-125">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="bf0fe-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="bf0fe-126">테이블에서 데이터를 추가, 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="bf0fe-127">사용 하는 방법에 설명 **DataTable** 데이터 테이블의 변경 내용을 검사 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="bf0fe-128">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="bf0fe-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="bf0fe-129">사용에 대 한 사용할 수 있는 이벤트에 대 한 정보를 제공 된 **DataTable**, 열 값을 수정 하거나 행을 추가 하거나 삭제할 때 이벤트를 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bf0fe-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="bf0fe-130">Related Sections</span></span>  
 [<span data-ttu-id="bf0fe-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bf0fe-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="bf0fe-132">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="bf0fe-133">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="bf0fe-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="bf0fe-134">ADO.NET에 대 한 정보를 제공 **데이터 집합** 테이블 간의 관계를 만드는 방법을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="bf0fe-135">에 대 한 참조 정보를 제공 합니다 **제약 조건** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="bf0fe-136">에 대 한 참조 정보를 제공 합니다 **DataColumn** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="bf0fe-137">에 대 한 참조 정보를 제공 합니다 **데이터 집합** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="bf0fe-138">에 대 한 참조 정보를 제공 합니다 **DataTable** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="bf0fe-139">클래스 라이브러리 개요</span><span class="sxs-lookup"><span data-stu-id="bf0fe-139">Class Library Overview</span></span>](../../../../../docs/standard/class-library-overview.md)  
 <span data-ttu-id="bf0fe-140">.NET Framework 클래스 라이브러리에 간략하게 포함 하 여는 **시스템** 네임 스페이스의 두 번째 수준 네임 스페이스와 **System.Data**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0fe-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0fe-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf0fe-141">See Also</span></span>  
 [<span data-ttu-id="bf0fe-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bf0fe-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
