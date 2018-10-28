---
title: XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 76fd0126f32eb2b22a12ee0b67e1f81794ff9445
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195296"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="ac1c4-102">XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="ac1c4-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="ac1c4-103">이 단원에서는 XSD(XML 스키마 정의 언어) 스키마 문서에서 `DataSet`의 관계형 스키마를 빌드하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="ac1c4-104">일반적으로 각각에 대해 `complexType` 스키마 요소의 자식 요소 테이블에서 생성 되는 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="ac1c4-105">테이블 구조는 복합 형식의 정의에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="ac1c4-106">만들어진 테이블은 `DataSet` 스키마의 최상위 요소에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="ac1c4-107">그러나 테이블에만 만들어집니다 최상위 수준에 대 한 `complexType` 요소 때를 `complexType` 요소는 다른 내부에 중첩 `complexType` 는 요소인 경우 중첩 된 `complexType` 요소에 매핑되는 `DataTable` 내는 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="ac1c4-108">XSD에 대 한 자세한 내용은 World Wide Web Consortium (W3C)을 참조 하세요 [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/)서 [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), 및 [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="ac1c4-109">다음 예제에서는 XML 스키마를 보여 줍니다. 여기서 `customers` 의 자식 요소를 `MyDataSet` 요소의 **데이터 집합** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ac1c4-110">앞의 예제에서 `customers` 요소는 복합 형식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="ac1c4-111">따라서 복합 형식 정의가 구문 분석되고 매핑 프로세스에서는 다음 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="ac1c4-112">테이블의 각 열에 대한 데이터 형식은 지정된 해당 요소 또는 특성의 XML 스키마 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac1c4-113">경우 요소 `customers` 와 같은 간단한 XML 스키마 데이터 형식입니다 **정수**, 테이블이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="ac1c4-114">테이블은 복합 형식인 최상위 요소에 대해서만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="ac1c4-115">다음 XML 스키마에는 **스키마** 요소에 두 명의 요소 자식이 `InStateCustomers` 및 `OutOfStateCustomers`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ac1c4-116">`InStateCustomers` 및 `OutOfStateCustomers` 자식 요소는 모두 복합 형식 요소(`customerType`)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="ac1c4-117">따라서 매핑 프로세스의 다음 두 개의 동일한 테이블을 생성 합니다 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ac1c4-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ac1c4-118">In This Section</span></span>  
 [<span data-ttu-id="ac1c4-119">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="ac1c4-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="ac1c4-120">고유 및 외래 키 제약 조건을 만드는 데 필요한 XML 스키마 요소에 설명 된 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ac1c4-121">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="ac1c4-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="ac1c4-122">테이블 열 간의 관계를 만드는 데 XML 스키마 요소에 설명 된 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ac1c4-123">XML 스키마 제약 조건 및 관계</span><span class="sxs-lookup"><span data-stu-id="ac1c4-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="ac1c4-124">관계가 만들어지는 방법을 암시적으로 XML 스키마 요소에 대 한 제약 조건을 만드는 데 사용 하는 경우에 대해 설명 된 `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ac1c4-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ac1c4-125">Related Sections</span></span>  
 [<span data-ttu-id="ac1c4-126">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="ac1c4-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="ac1c4-127">로드 하 고 관계형 구조와 데이터를 유지 하는 방법을 설명는 `DataSet` XML 데이터로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac1c4-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac1c4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac1c4-128">See Also</span></span>  
 [<span data-ttu-id="ac1c4-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ac1c4-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
