---
title: 관계 유추
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666852"
---
# <a name="inferring-relationships"></a><span data-ttu-id="d5e78-102">관계 유추</span><span class="sxs-lookup"><span data-stu-id="d5e78-102">Inferring Relationships</span></span>
<span data-ttu-id="d5e78-103">테이블로 유추되는 요소에 역시 테이블로 유추되는 자식 요소가 있으면 두 테이블 사이에 <xref:System.Data.DataRelation>이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="d5e78-104">새 열 이름 가진 **ParentTableName_Id** 부모 요소에 대해 만들어진 테이블과 자식 요소에 대해 생성 된 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="d5e78-105">합니다 **ColumnMapping** id 열 속성에 설정할 **MappingType.Hidden**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="d5e78-106">열은 부모 테이블에 대 한 자동 증분 기본 키 되며 사용할지 합니다 **DataRelation** 두 테이블 간에 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="d5e78-107">추가 id 열의 데이터 형식은 **System.Int32**에 데이터 형식의 다른 모든 유추 된 열과 달리 **System.String**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="d5e78-108">A <xref:System.Data.ForeignKeyConstraint> 사용 하 여 **DeleteRule** = **Cascade** 부모 테이블과 자식 테이블에 새 열을 사용 하 여도 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="d5e78-109">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d5e78-110">유추 과정에서 두 테이블을 생성 합니다. **Element1** 하 고 **ChildElement1**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="d5e78-111">**Element1** 테이블 두 개의 열이 포함 됩니다. **Element1_Id** 하 고 **ChildElement2**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="d5e78-112">합니다 **ColumnMapping** 의 속성을 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="d5e78-113">합니다 **ColumnMapping** 의 속성을 **ChildElement2** 열으로 설정 됩니다 **MappingType.Element**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="d5e78-114">**Element1_Id** 의 기본 키로 설정할 열을 **Element1** 테이블.</span><span class="sxs-lookup"><span data-stu-id="d5e78-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="d5e78-115">**ChildElement1** 테이블 3 개 열이 포함 됩니다. **attr1**, **attr2** 및 **Element1_Id**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="d5e78-116">**ColumnMapping** 에 대 한 속성을 **attr1** 및 **attr2** 열에 설정할 **MappingType.Attribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="d5e78-117">합니다 **ColumnMapping** 의 속성을 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="d5e78-118">A **DataRelation** 및 **ForeignKeyConstraint** 사용 하 여 만들어집니다 합니다 **Element1_Id** 두 테이블의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e78-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="d5e78-119">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d5e78-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d5e78-120">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="d5e78-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d5e78-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d5e78-121">Element1_Id</span></span>|<span data-ttu-id="d5e78-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="d5e78-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="d5e78-123">0</span><span class="sxs-lookup"><span data-stu-id="d5e78-123">0</span></span>|<span data-ttu-id="d5e78-124">Text2</span><span class="sxs-lookup"><span data-stu-id="d5e78-124">Text2</span></span>|  
  
 <span data-ttu-id="d5e78-125">**테이블:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d5e78-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="d5e78-126">attr1</span><span class="sxs-lookup"><span data-stu-id="d5e78-126">attr1</span></span>|<span data-ttu-id="d5e78-127">attr2</span><span class="sxs-lookup"><span data-stu-id="d5e78-127">attr2</span></span>|<span data-ttu-id="d5e78-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d5e78-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="d5e78-129">value1</span><span class="sxs-lookup"><span data-stu-id="d5e78-129">value1</span></span>|<span data-ttu-id="d5e78-130">value2</span><span class="sxs-lookup"><span data-stu-id="d5e78-130">value2</span></span>|<span data-ttu-id="d5e78-131">0</span><span class="sxs-lookup"><span data-stu-id="d5e78-131">0</span></span>|  
  
 <span data-ttu-id="d5e78-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d5e78-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="d5e78-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="d5e78-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="d5e78-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d5e78-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="d5e78-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d5e78-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="d5e78-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d5e78-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="d5e78-137">**중첩 된:** True</span><span class="sxs-lookup"><span data-stu-id="d5e78-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="d5e78-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d5e78-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="d5e78-139">**열:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d5e78-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="d5e78-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="d5e78-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="d5e78-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d5e78-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="d5e78-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="d5e78-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="d5e78-143">**AcceptRejectRule:** 없음</span><span class="sxs-lookup"><span data-stu-id="d5e78-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e78-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5e78-144">See Also</span></span>  
 [<span data-ttu-id="d5e78-145">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="d5e78-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="d5e78-146">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="d5e78-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="d5e78-147">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="d5e78-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="d5e78-148">DataRelation 중첩</span><span class="sxs-lookup"><span data-stu-id="d5e78-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="d5e78-149">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="d5e78-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="d5e78-150">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="d5e78-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d5e78-151">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d5e78-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
