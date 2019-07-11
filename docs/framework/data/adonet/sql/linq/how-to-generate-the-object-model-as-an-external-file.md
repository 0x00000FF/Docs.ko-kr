---
title: '방법: 외부 파일로 개체 모델 생성'
ms.date: 03/30/2017
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
ms.openlocfilehash: 828e92903447b5c7cd3d7d27ed72bfe61d0dc6a9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743297"
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a>방법: 외부 파일로 개체 모델 생성
특성 기반 매핑을 사용하는 대신 SQLMetal 명령줄 도구를 사용하여 개체 모델을 외부 XML 파일로 생성할 수 있습니다. 자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요. 외부 XML 매핑 파일을 사용하면 코드를 간단하게 표시할 수 있습니다. 또한 응용 프로그램의 이진 파일을 다시 컴파일할 필요 없이 외부 파일을 수정하여 동작을 변경할 수 있습니다. 자세한 내용은 [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)합니다.  
  
> [!NOTE]
>  Object Relational Designer 외부 매핑 파일 생성을 지원 하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 명령에서는 Northwind 샘플 데이터베이스에서 외부 매핑 파일을 생성합니다.  
  
```  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 외부 매핑 파일의 일부로, Northwind 샘플 데이터베이스의 Customers 테이블에 대한 매핑을 보여 줍니다. 이 발췌 함께 SQLMetal을 실행 하 여 생성 된 합니다 **/map** 옵션입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>참고자료

- [개체 모델 만들기](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [외부 매핑](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [방법: Visual Basic 또는 C#에서 개체 모델 생성](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
