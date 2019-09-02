---
title: 형식화된 데이터 세트에 주석 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 8ce7cd859ce0c9a5874751e9928e5bced33593d6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205255"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="26ccd-102">형식화된 데이터 세트에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="26ccd-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="26ccd-103">주석을 사용하면 원본으로 사용하는 스키마를 수정하지 않고 형식화된 <xref:System.Data.DataSet>의 요소 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="26ccd-104">기본 스키마의 요소 이름을 수정 하면 형식화 된 데이터 **집합이** 데이터 소스에 없는 개체를 참조 하 고 데이터 소스에 존재 하는 개체에 대 한 참조도 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="26ccd-105">주석을 사용 하 여 형식화 된 **데이터 집합** 의 개체 이름을 더 의미 있는 이름으로 사용자 지정 하 여, 클라이언트에서 사용할 수 있는 코드를 더 쉽게 읽고 형식화 된 **데이터 집합** 을 쉽게 만들 수 있습니다. 기본 스키마는 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="26ccd-106">예를 들어 **Northwind** 데이터베이스의 **Customers** 테이블에 대 한 다음 스키마 요소는 **customersrow** 및 <xref:System.Data.DataRowCollection> 명명 된 **고객**의 **DataRow** 개체 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="26ccd-107">**고객** 의 **DataRowCollection** 이름은 클라이언트 코드에서 의미가 있지만 **customersrow** 의 **DataRow** 이름은 단일 개체 이기 때문에 잘못 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="26ccd-108">또한 일반적인 시나리오에서 개체를 **행** 식별자 없이 참조 하 고 대신 **고객** 개체 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="26ccd-109">이 솔루션은 스키마에 주석을 달고 **DataRow** 및 **DataRowCollection** 개체의 새 이름을 식별 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="26ccd-110">다음 코드는 이전 스키마에 주석을 단 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="26ccd-111">**Customer** 의 **typedName** 값을 지정 하면 **DataRow** 개체 이름이 **customer**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="26ccd-112">**고객** 의 **typedPlural** 값을 지정 하면 **고객**의 **DataRowCollection** 이름이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="26ccd-113">다음 표에서는 사용할 수 있는 주석을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="26ccd-114">Annotation</span><span class="sxs-lookup"><span data-stu-id="26ccd-114">Annotation</span></span>|<span data-ttu-id="26ccd-115">Description</span><span class="sxs-lookup"><span data-stu-id="26ccd-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="26ccd-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="26ccd-116">**typedName**</span></span>|<span data-ttu-id="26ccd-117">개체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-117">Name of the object.</span></span>|  
|<span data-ttu-id="26ccd-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="26ccd-118">**typedPlural**</span></span>|<span data-ttu-id="26ccd-119">개체 컬렉션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="26ccd-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="26ccd-120">**typedParent**</span></span>|<span data-ttu-id="26ccd-121">부모 관계에서 참조될 때의 개체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="26ccd-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="26ccd-122">**typedChildren**</span></span>|<span data-ttu-id="26ccd-123">자식 관계에서 개체를 반환하기 위한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="26ccd-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="26ccd-124">**nullValue**</span></span>|<span data-ttu-id="26ccd-125">내부 값이 **DBNull**인 경우 값입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="26ccd-126">**Nullvalue** 주석에 대해서는 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26ccd-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="26ccd-127">기본값은 **_throw**입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="26ccd-128">다음 표에서는 **Nullvalue** 주석에 대해 지정할 수 있는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="26ccd-129">nullValue 값</span><span class="sxs-lookup"><span data-stu-id="26ccd-129">nullValue Value</span></span>|<span data-ttu-id="26ccd-130">Description</span><span class="sxs-lookup"><span data-stu-id="26ccd-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="26ccd-131">*대체 값*</span><span class="sxs-lookup"><span data-stu-id="26ccd-131">*Replacement Value*</span></span>|<span data-ttu-id="26ccd-132">반환될 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-132">Specify a value to be returned.</span></span> <span data-ttu-id="26ccd-133">반환되는 값은 요소의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="26ccd-134">예를 들어, `nullValue="0"`을 사용하여 null 정수 필드에 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="26ccd-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="26ccd-135">**_throw**</span></span>|<span data-ttu-id="26ccd-136">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-136">Throw an exception.</span></span> <span data-ttu-id="26ccd-137">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-137">This is the default.</span></span>|  
|<span data-ttu-id="26ccd-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="26ccd-138">**_null**</span></span>|<span data-ttu-id="26ccd-139">기본 형식이 발견되면 null 참조를 반환하거나 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="26ccd-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="26ccd-140">**_empty**</span></span>|<span data-ttu-id="26ccd-141">문자열의 경우 **system.string**을 반환 하 고, 그렇지 않은 경우 빈 생성자에서 만든 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="26ccd-142">기본 형식이 발견되면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="26ccd-143">다음 표에서는 형식화 된 **데이터 집합** 의 개체에 대 한 기본값과 사용 가능한 주석을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="26ccd-144">개체/메서드/이벤트</span><span class="sxs-lookup"><span data-stu-id="26ccd-144">Object/Method/Event</span></span>|<span data-ttu-id="26ccd-145">기본값</span><span class="sxs-lookup"><span data-stu-id="26ccd-145">Default</span></span>|<span data-ttu-id="26ccd-146">Annotation</span><span class="sxs-lookup"><span data-stu-id="26ccd-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="26ccd-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="26ccd-147">**DataTable**</span></span>|<span data-ttu-id="26ccd-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="26ccd-148">TableNameDataTable</span></span>|<span data-ttu-id="26ccd-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="26ccd-149">typedPlural</span></span>|  
|<span data-ttu-id="26ccd-150">**DataTable** 메서드</span><span class="sxs-lookup"><span data-stu-id="26ccd-150">**DataTable** Methods</span></span>|<span data-ttu-id="26ccd-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="26ccd-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="26ccd-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="26ccd-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="26ccd-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="26ccd-153">DeleteTableNameRow</span></span>|<span data-ttu-id="26ccd-154">typedName</span><span class="sxs-lookup"><span data-stu-id="26ccd-154">typedName</span></span>|  
|<span data-ttu-id="26ccd-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="26ccd-155">**DataRowCollection**</span></span>|<span data-ttu-id="26ccd-156">TableName</span><span class="sxs-lookup"><span data-stu-id="26ccd-156">TableName</span></span>|<span data-ttu-id="26ccd-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="26ccd-157">typedPlural</span></span>|  
|<span data-ttu-id="26ccd-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="26ccd-158">**DataRow**</span></span>|<span data-ttu-id="26ccd-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="26ccd-159">TableNameRow</span></span>|<span data-ttu-id="26ccd-160">typedName</span><span class="sxs-lookup"><span data-stu-id="26ccd-160">typedName</span></span>|  
|<span data-ttu-id="26ccd-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="26ccd-161">**DataColumn**</span></span>|<span data-ttu-id="26ccd-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="26ccd-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="26ccd-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="26ccd-163">DataRow.ColumnName</span></span>|<span data-ttu-id="26ccd-164">typedName</span><span class="sxs-lookup"><span data-stu-id="26ccd-164">typedName</span></span>|  
|<span data-ttu-id="26ccd-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="26ccd-165">**Property**</span></span>|<span data-ttu-id="26ccd-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="26ccd-166">PropertyName</span></span>|<span data-ttu-id="26ccd-167">typedName</span><span class="sxs-lookup"><span data-stu-id="26ccd-167">typedName</span></span>|  
|<span data-ttu-id="26ccd-168">**자식** 접근자</span><span class="sxs-lookup"><span data-stu-id="26ccd-168">**Child** Accessor</span></span>|<span data-ttu-id="26ccd-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="26ccd-169">GetChildTableNameRows</span></span>|<span data-ttu-id="26ccd-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="26ccd-170">typedChildren</span></span>|  
|<span data-ttu-id="26ccd-171">**부모** 접근자</span><span class="sxs-lookup"><span data-stu-id="26ccd-171">**Parent** Accessor</span></span>|<span data-ttu-id="26ccd-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="26ccd-172">TableNameRow</span></span>|<span data-ttu-id="26ccd-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="26ccd-173">typedParent</span></span>|  
|<span data-ttu-id="26ccd-174">**데이터 집합** 이벤트</span><span class="sxs-lookup"><span data-stu-id="26ccd-174">**DataSet** Events</span></span>|<span data-ttu-id="26ccd-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="26ccd-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="26ccd-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="26ccd-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="26ccd-177">typedName</span><span class="sxs-lookup"><span data-stu-id="26ccd-177">typedName</span></span>|  
  
 <span data-ttu-id="26ccd-178">형식화 된 **데이터 집합** 주석을 사용 하려면 XSD (XML 스키마 정의 언어) 스키마에 다음 **xmlns** 참조를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="26ccd-179">데이터베이스 테이블에서 xsd를 만들려면 또는 <xref:System.Data.DataSet.WriteXmlSchema%2A> [Visual Studio에서 데이터 집합 작업](/visualstudio/data-tools/dataset-tools-in-visual-studio)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26ccd-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="26ccd-180">다음은 포함 된 **Orders** 테이블과 관련 된 **Northwind** 데이터베이스의 **Customers** 테이블을 표시 하는 주석이 추가 된 샘플 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="26ccd-181">다음 코드 예제에서는 샘플 스키마에서 만든 강력한 형식의 **데이터 집합** 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="26ccd-182">하나 <xref:System.Data.SqlClient.SqlDataAdapter> 를 사용 하 여 **Customers** 테이블 <xref:System.Data.SqlClient.SqlDataAdapter> 을 채우고 **Orders** 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="26ccd-183">강력한 형식의 **데이터 집합** 은 **datarelations**을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ccd-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="26ccd-184">참고자료</span><span class="sxs-lookup"><span data-stu-id="26ccd-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="26ccd-185">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="26ccd-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="26ccd-186">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="26ccd-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="26ccd-187">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="26ccd-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
