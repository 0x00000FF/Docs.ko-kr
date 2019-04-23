---
title: 중첩된 요소에 지정된 관계 매핑
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 9772f077991c758be65bbb44b9474f1ad341371f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203147"
---
# <a name="map-relations-specified-for-nested-elements"></a>중첩된 요소에 지정된 관계 매핑
스키마를 포함할 수는 **msdata: relationship** 스키마의 두 요소 간의 매핑을 명시적으로 지정 하는 주석입니다. 에 지정 된 두 요소 **msdata: relationship** 스키마에서 중첩 될 수 있지만 될 필요가 없습니다. 사용 하 여 매핑 프로세스 **msdata: relationship** 두 열 간에 기본 키/외래 키 관계를 생성 하려면 스키마에 있습니다.  
  
 다음 예제는 XML 스키마를 보여 줍니다.는 **OrderDetail** 의 자식 요소입니다 **순서**합니다. **msdata: relationship** 이 부모-자식 관계를 식별 하 고 지정 합니다 **OrderNumber** 결과 열의 **순서** 테이블이 관련 되어를 **OrderNo** 결과 열의 **OrderDetail** 테이블입니다.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
 <xs:complexType>  
  <xs:choice maxOccurs="unbounded">  
   <xs:element name="Order">  
    <xs:complexType>  
     <xs:sequence>  
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.  
  
-   **순서** 와 **OrderDetail** 테이블입니다.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   간의 관계는 **순서** 하 고 **OrderDetail** 테이블입니다. **중첩** 이 관계에 대 한 속성 **True** 때문에 **순서** 하 고 **OrderDetail** 요소가 스키마에서 중첩 .  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [XSD(XML 스키마)에서 데이터 세트 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [데이터 세트 제약 조건에 XSD(XML 스키마) 제약 조건 매핑](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
