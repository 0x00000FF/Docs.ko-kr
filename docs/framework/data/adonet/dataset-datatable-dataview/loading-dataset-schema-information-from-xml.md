---
title: "XML에서 데이터 집합 스키마 정보 로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 09fc69ba6d82fdab5aa03dd3987ec1acdf0be17e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="loading-dataset-schema-information-from-xml"></a>XML에서 데이터 집합 스키마 정보 로드
스키마는 <xref:System.Data.DataSet> (해당 테이블, 열, 관계 및 제약 조건) 정의할 수 있습니다, 프로그래밍 방식으로 개발한는 **채우기** 또는 **FillSchema** 의 메서드는 <xref:System.Data.Common.DataAdapter>, 또는에서 로드 된 프로그램 XML 문서입니다. 로드할 **데이터 집합** 스키마 정보는 XML 문서에서 사용할 수 있습니다는 **ReadXmlSchema** 또는 **InferXmlSchema** 의 메서드는 **데이터집합**. **ReadXmlSchema** 로드 하거나 유추할 수 있습니다 **DataSet** XML 스키마 정의 언어 (XSD) 스키마 또는 인라인 XML 스키마는 XML 문서를 포함 하는 문서에서 스키마 정보입니다. **InferXmlSchema** 지정한 특정 XML 네임 스페이스를 무시 하는 동안 XML 문서에서 스키마를 유추할 수 있습니다.  
  
> [!NOTE]
>  테이블에서 순서는 **DataSet** 전송할 웹 서비스나 XML serialization을 사용할 때 유지 되지 않을 수 있습니다는 **데이터 집합** XSD 구문 (예: 중첩된 관계)을 사용 하 여 메모리에서 만든 합니다. 따라서 받는 사람은 **데이터 집합** 테이블 순서에 경우에 종속 되지 않아야 합니다. 그러나 순서 지정 테이블은 항상 유지 하는 경우의 스키마는 **데이터 집합** 메모리를 생성 하는 대신 XSD 파일에서 읽은 전송 하는 중입니다.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 스키마를 로드 한 **데이터 집합** 모든 데이터를 로드 하지 않고 XML 문서에서 사용할 수 있습니다는 **ReadXmlSchema** 의 메서드는 **데이터 집합**합니다. **ReadXmlSchema** 만듭니다 **DataSet** XML 스키마 정의 언어 (XSD) 스키마를 사용 하 여 정의 된 스키마입니다.  
  
 **ReadXmlSchema** 파일 이름, 스트림, 단일 인수를 사용 하는 메서드 또는 **XmlReader** 로드할 XML 문서가 들어 있습니다. XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다. XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 세부 정보를 참조 하십시오. [파생 된 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.  
  
 XML 문서에 전달 하는 경우 **ReadXmlSchema** 인라인 스키마 정보가 없으면 포함 **ReadXmlSchema** XML 문서의 요소에서 스키마를 유추 합니다. 경우는 **DataSet** 이미 스키마가 포함 되어 이미 존재 하지 않는 경우 새 테이블을 추가 하 여 현재 스키마 확장 됩니다. 새 열은 기존 테이블에 추가되지 않습니다. 이미 추가 되는 열에 있는 경우는 **DataSet** 하지만 열과는 호환 되지 않는 형식에서에서 발견 되는 XML, 예외가 throw 됩니다. 자세한 방법에 대 한 내용은 **ReadXmlSchema** 스키마를 유추는 XML 문서에서 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.  
  
 하지만 **ReadXmlSchema** 로드 하거나 유추의 스키마만는 **DataSet**, **ReadXml** 의 메서드는 **데이터 집합** 로드 하거나 유추 둘 다 스키마 및 XML 문서에 포함 된 데이터입니다. 자세한 내용은 참조 [XML 로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)합니다.  
  
 다음 코드 예제는 로드 하는 방법을 보여는 **DataSet** 스키마에서 XML 문서 또는 스트림에 합니다. 첫 번째 예에 전달 되는 XML 스키마 파일 이름을 보여 줍니다.는 **ReadXmlSchema** 메서드. 두 번째 예에서는 한 **System.IO.StreamReader**합니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 지시할 수 있습니다는 **DataSet** 사용 하 여 XML 문서에서 해당 스키마를 유추 하는 **InferXmlSchema** 의 메서드는 **데이터 집합**합니다. **InferXmlSchema** 둘 다 수행과 동일한 함수가 **ReadXml** 와 **XmlReadMode** 의 **InferSchema** (데이터 로드으로 스키마를 유추) 및  **ReadXmlSchema** 읽는 중인 문서에 인라인 스키마가 없습니다. 그러나 **InferXmlSchema** 하면 스키마를 유추할 때 무시할 특정 XML 네임 스페이스를 지정할 수 있도록의 추가 기능을 제공 합니다. **InferXmlSchema** 는 두 개의 필수 인수: 스트림, 파일 이름으로 지정 된 XML 문서의 위치 또는 **XmlReader**; 및 해당 작업에서 무시 될 XML 네임 스페이스의 문자열 배열입니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 앞의 XML 문서에 있는 요소에 지정 된 특성으로 인해 둘 다는 **ReadXmlSchema** 메서드 및 **ReadXml** 메서드는 **XmlReadMode** 의 **InferSchema** 문서에서 모든 요소에 대 한 테이블을 만듭니다: **범주**, **CategoryID**, **CategoryName**, **설명**, **제품**, **ProductID**, **ReorderLevel**, 및 **중단**. (자세한 내용은 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) 그러나 더 적절 한 구조에만 만들 수는 **범주** 및 **제품** 테이블을 만든 다음 **CategoryID**, **CategoryName** , 및 **설명** 열에는 **범주** 테이블 및 **ProductID**, **ReorderLevel**, 및 **단종** 열에는 **제품** 테이블입니다. 유추 된 스키마는 XML 요소에 지정 된 특성을 무시 하려면 사용 하 여는 **InferXmlSchema** 메서드 XML 네임 스페이스를 지정 하 고 **officedata** 에서처럼 무시 되어야 하는 다음 예제에서는 합니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [XML 스키마 (XSD)에서 데이터 집합 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [XML 로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
