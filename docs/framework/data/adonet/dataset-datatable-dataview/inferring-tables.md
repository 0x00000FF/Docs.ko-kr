---
title: 테이블 유추
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 38709f91e01c7f85d9e8482bdd49bc0892121f09
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332855"
---
# <a name="inferring-tables"></a><span data-ttu-id="c0103-102">테이블 유추</span><span class="sxs-lookup"><span data-stu-id="c0103-102">Inferring Tables</span></span>
<span data-ttu-id="c0103-103">XML 문서로부터 <xref:System.Data.DataSet>의 스키마를 유추할 때 ADO.NET에서는 우선 테이블을 나타내는 XML 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="c0103-104">다음 XML 구조에 대 한 테이블의 결과 **데이터 집합** 스키마:</span><span class="sxs-lookup"><span data-stu-id="c0103-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="c0103-105">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="c0103-106">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="c0103-107">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="c0103-108">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-108">Elements with Attributes</span></span>  
 <span data-ttu-id="c0103-109">자신에 지정된 특성을 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="c0103-110">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="c0103-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c0103-111">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c0103-112">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c0103-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c0103-113">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="c0103-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c0103-114">attr1</span><span class="sxs-lookup"><span data-stu-id="c0103-114">attr1</span></span>|<span data-ttu-id="c0103-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c0103-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="c0103-116">value1</span><span class="sxs-lookup"><span data-stu-id="c0103-116">value1</span></span>||  
|<span data-ttu-id="c0103-117">value2</span><span class="sxs-lookup"><span data-stu-id="c0103-117">value2</span></span>|<span data-ttu-id="c0103-118">Text1</span><span class="sxs-lookup"><span data-stu-id="c0103-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="c0103-119">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="c0103-120">자식 요소를 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="c0103-121">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="c0103-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c0103-122">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c0103-123">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c0103-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c0103-124">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="c0103-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c0103-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c0103-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="c0103-126">Text1</span><span class="sxs-lookup"><span data-stu-id="c0103-126">Text1</span></span>|  
  
 <span data-ttu-id="c0103-127">문서 요소 또는 루트 요소는 열로 유추되는 특성이나 자식 요소를 갖고 있는 경우 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="c0103-128">문서 요소가 없는 특성과 열으로 유추 되는 자식 요소가 없는 요소도 유추 됩니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="c0103-129">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="c0103-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c0103-130">위 유추 과정에서 "DocumentElement"라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="c0103-131">**데이터 집합:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="c0103-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="c0103-132">**테이블:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c0103-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="c0103-133">Element1</span><span class="sxs-lookup"><span data-stu-id="c0103-133">Element1</span></span>|<span data-ttu-id="c0103-134">Element2</span><span class="sxs-lookup"><span data-stu-id="c0103-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="c0103-135">Text1</span><span class="sxs-lookup"><span data-stu-id="c0103-135">Text1</span></span>|<span data-ttu-id="c0103-136">Text2</span><span class="sxs-lookup"><span data-stu-id="c0103-136">Text2</span></span>|  
  
 <span data-ttu-id="c0103-137">또는 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="c0103-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c0103-138">유추 과정에서 생성 된 **데이터 집합** "Element1." 라는 테이블을 포함 하는 "DocumentElement" 라는</span><span class="sxs-lookup"><span data-stu-id="c0103-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="c0103-139">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c0103-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c0103-140">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="c0103-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c0103-141">attr1</span><span class="sxs-lookup"><span data-stu-id="c0103-141">attr1</span></span>|<span data-ttu-id="c0103-142">attr2</span><span class="sxs-lookup"><span data-stu-id="c0103-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="c0103-143">value1</span><span class="sxs-lookup"><span data-stu-id="c0103-143">value1</span></span>|<span data-ttu-id="c0103-144">value2</span><span class="sxs-lookup"><span data-stu-id="c0103-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="c0103-145">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="c0103-145">Repeating Elements</span></span>  
 <span data-ttu-id="c0103-146">반복되는 요소는 하나의 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="c0103-147">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="c0103-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c0103-148">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0103-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="c0103-149">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c0103-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c0103-150">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="c0103-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c0103-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="c0103-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="c0103-152">Text1</span><span class="sxs-lookup"><span data-stu-id="c0103-152">Text1</span></span>|  
|<span data-ttu-id="c0103-153">Text2</span><span class="sxs-lookup"><span data-stu-id="c0103-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0103-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0103-154">See Also</span></span>  
 [<span data-ttu-id="c0103-155">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="c0103-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="c0103-156">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="c0103-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="c0103-157">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="c0103-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="c0103-158">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="c0103-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="c0103-159">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="c0103-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="c0103-160">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c0103-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
