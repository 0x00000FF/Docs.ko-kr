---
title: XSD(XML 스키마)에서 데이터 집합 관계 생성
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 29c0e9ee96c376c6da392692febccbbae3c6a33f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170224"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="7458c-102">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="7458c-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="7458c-103"><xref:System.Data.DataSet>에서는 부모-자식 관계를 만들어 둘 이상의 열을 연결시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="7458c-104">나타내는 세 가지는 **데이터 집합** XML 스키마 정의 언어 (XSD) 스키마 내의 관계:</span><span class="sxs-lookup"><span data-stu-id="7458c-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
-   <span data-ttu-id="7458c-105">중첩된 복합 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-105">Specify nested complex types.</span></span>  
  
-   <span data-ttu-id="7458c-106">사용 된 **msdata: relationship** 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-106">Use the **msdata:Relationship** annotation.</span></span>  
  
-   <span data-ttu-id="7458c-107">지정는 **xs: keyref** 없이 **사용** 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="7458c-108">중첩된 복합 형식</span><span class="sxs-lookup"><span data-stu-id="7458c-108">Nested Complex Types</span></span>  
 <span data-ttu-id="7458c-109">스키마에서 중첩된 복합 형식의 정의는 요소의 부모-자식 관계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="7458c-110">다음 XML 스키마 조각에 따르면 **OrderDetail** 의 자식 요소를 **순서** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="7458c-111">XML 스키마 매핑 프로세스에 테이블을 만듭니다는 **데이터 집합** 스키마에서 중첩된 된 복합 형식에 해당 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="7458c-112">또한 부모로 사용 되는 추가 열을 만듭니다**-** 생성된 된 테이블에 대 한 자식 열입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="7458c-113">이러한 부모 보면**-** 자식 열에서는 없는 기본 키/외래 키 제약 조건을 지정 하는 것과 관계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="7458c-114">msdata:Relationship 주석</span><span class="sxs-lookup"><span data-stu-id="7458c-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="7458c-115">합니다 **msdata: relationship** 주석을 사용 하면 명시적으로 중첩 되지 않은 스키마의 요소 간의 부모-자식 관계를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="7458c-116">다음 예제에서는의 구조를 표시 합니다 **관계** 요소.</span><span class="sxs-lookup"><span data-stu-id="7458c-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="7458c-117">특성을 **msdata: relationship** 주석으로도 부모-자식 관계에 관련 된 요소를 식별 합니다 **parentkey** 및 **childkey** 요소 및 특성 관계를 맺고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="7458c-118">테이블을 생성 하려면이 정보를 사용 하는 매핑 프로세스를 **데이터 집합** 고 이러한 테이블 간에 기본 키/외래 키 관계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="7458c-119">예를 들어 다음 스키마 조각 지정 **순서** 하 고 **OrderDetail** 동일한 수준에서 요소 (중첩 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="7458c-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="7458c-120">스키마 지정는 **msdata: relationship** 주석에 이러한 두 요소 간의 부모-자식 관계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="7458c-121">이 경우 관계를 명시적으로 지정 해야 합니다 **msdata: relationship** 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="7458c-122">매핑 프로세스를 사용 하는 **관계** 요소 간의 부모-자식 관계를 만들려면를 **OrderNumber** 열에는 **순서** 테이블과 합니다 **OrderNo** 열에는 **OrderDetail** 테이블에 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="7458c-123">매핑 프로세스에서는 관계만 지정합니다. 즉, 관계형 데이터베이스의 기본 키/외래 키 제약 조건처럼 이러한 열의 값에 대해 제약 조건을 자동으로 지정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="7458c-124">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7458c-124">In This Section</span></span>  
 [<span data-ttu-id="7458c-125">중첩된 스키마 요소 사이에 암시적 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="7458c-125">Map Implicit Relations Between Nested Schema Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="7458c-126">제약 조건 및에서 암시적으로 만든 관계에 설명 합니다는 **데이터 집합** XML 스키마에서 중첩 된 요소가 발생 한 경우.</span><span class="sxs-lookup"><span data-stu-id="7458c-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="7458c-127">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="7458c-127">Map Relations Specified for Nested Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="7458c-128">관계를 명시적으로 설정 하는 방법에 설명 된 **데이터 집합** XML 스키마의 중첩 된 요소에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="7458c-129">중첩 없이 요소 사이에 관계 지정</span><span class="sxs-lookup"><span data-stu-id="7458c-129">Specify Relations Between Elements with No Nesting</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="7458c-130">관계를 만드는 방법을 설명 합니다는 **데이터 집합** 중첩 되지 않은 XML 스키마 요소 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="7458c-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7458c-131">Related Sections</span></span>  
 [<span data-ttu-id="7458c-132">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="7458c-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="7458c-133">관계형 구조 또는 스키마를 설명 합니다는 **데이터 집합** XML 스키마 정의 언어 (XSD)에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="7458c-134">데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="7458c-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="7458c-135">고유 및 외래 키 제약 조건을 만드는 데 필요한 XML 스키마 요소에 설명 합니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="7458c-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7458c-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="7458c-136">See also</span></span>

- [<span data-ttu-id="7458c-137">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="7458c-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
