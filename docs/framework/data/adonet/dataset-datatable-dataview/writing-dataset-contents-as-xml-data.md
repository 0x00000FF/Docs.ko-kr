---
title: 데이터 집합 콘텐츠를 XML 데이터로 작성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: dae044a9d7802e858f1f24dd4aa0f1de8f6cba7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158954"
---
# <a name="writing-dataset-contents-as-xml-data"></a>데이터 집합 콘텐츠를 XML 데이터로 작성
ADO.NET에서는 해당 스키마의 사용 여부와 관계없이 <xref:System.Data.DataSet>을 XML 표현으로 작성할 수 있습니다. 스키마 정보가 XML과 함께 인라인에 포함된 경우에는 XSD(XML 스키마 정의 언어)를 사용하여 작성됩니다. 이 스키마에는 <xref:System.Data.DataSet>의 테이블 정의와 관계 및 제약 조건 정의가 포함됩니다.  
  
 <xref:System.Data.DataSet>이 XML 데이터로 작성되면 <xref:System.Data.DataSet>의 행은 자신의 현재 버전으로 작성됩니다. 그러나 <xref:System.Data.DataSet>은 DiffGram으로 작성될 수도 있으므로 행의 현재 및 원래 값이 모두 포함됩니다.  
  
 XML 표현을 합니다 <xref:System.Data.DataSet> 스트림, 파일에 쓸 수는 **XmlWriter**, 또는 문자열입니다. 이와 같이 다양한 작성이 가능하므로 <xref:System.Data.DataSet>의 XML 표현을 전송하는 방법은 매우 유연합니다. XML 표현을 가져올는 <xref:System.Data.DataSet> 문자열로 사용 하 여 합니다 **GetXml** 메서드는 다음 예와에서 같이 합니다.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** 의 XML 표현을 반환 합니다 <xref:System.Data.DataSet> 스키마 정보 없이. 스키마 정보를 기록 하는 <xref:System.Data.DataSet> (XML 스키마)로 문자열을 사용 하 여 **GetXmlSchema**합니다.  
  
 쓸를 <xref:System.Data.DataSet> 파일에 스트림 또는 **XmlWriter**를 사용 합니다 **WriteXml** 메서드. 첫 번째 매개 변수 전달 **WriteXml** XML 출력의 대상입니다. 예를 들어, 파일 이름을 포함 하는 문자열을 전달 된 **System.IO.TextWriter** 개체 및 등입니다. 선택적 두 번째 매개 변수로 전달할 수 있습니다는 **XmlWriteMode** XML 출력을 작성 하는 하는 방법을 지정 합니다.  
  
 다음 테이블에 대 한 옵션을 보여 줍니다 **XmlWriteMode**합니다.  
  
|XmlWriteMode 옵션|설명|  
|-------------------------|-----------------|  
|**IgnoreSchema**|<xref:System.Data.DataSet>의 현재 내용을 XML 스키마 없이 XML 데이터로 작성합니다. 이 값이 기본값입니다.|  
|**WriteSchema**|<xref:System.Data.DataSet>의 현재 내용을 인라인 XML 스키마와 동일한 관계형 구조를 가진 XML 데이터로 작성합니다.|  
|**DiffGram**|원래 및 현재 값을 포함하여 전체 <xref:System.Data.DataSet>을 DiffGram으로 작성합니다. 자세한 내용은 [Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)합니다.|  
  
 XML 표현을 작성 하는 경우는 <xref:System.Data.DataSet> 포함 된 **DataRelation** 개체, 관련된 된 부모 요소 내에 중첩 된 각 관계의 자식 행을 포함 하는 결과 XML 할 가능성이 높습니다. 이를 위해 설정를 **중첩** 의 속성을 **DataRelation** 에 **true** 추가 하는 경우를 **DataRelation** 하는 <xref:System.Data.DataSet>. 자세한 내용은 [중첩 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)합니다.  
  
 다음은 <xref:System.Data.DataSet>의 XML 표현을 파일로 작성하는 방법에 대한 두 가지 예제입니다. 첫 번째 예제는 결과 XML에 대 한 파일 이름에 문자열로 전달 **WriteXml**합니다. 두 번째 예제에서는 전달 된 **System.IO.StreamWriter** 개체입니다.  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>열을 XML 요소, 특성 및 텍스트에 매핑  
 xml에서 테이블의 열을 표현 하는 방법을 지정할 수 있습니다를 사용 하 여는 **ColumnMapping** 의 속성을 **DataColumn** 개체입니다. 다음 표에서 서로 다른 **MappingType** 에 대 한 값을 **ColumnMapping** 테이블 열 및 결과 XML의 속성입니다.  
  
|MappingType 값|설명|  
|-----------------------|-----------------|  
|**요소**|이 값이 기본값입니다. 열이 XML 요소로 작성되며, 이 때 ColumnName이 요소의 이름이 되고 열의 내용은 요소의 텍스트로 작성됩니다. 예를 들어:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**특성**|열이 현재 행에 대한 XML 요소의 XML 특성으로 작성되며, 이 때 특성의 이름은 ColumnName이며 열의 내용은 특성의 값으로 작성됩니다. 예를 들어:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|열의 내용이 현재 행에 대한 XML 요소의 텍스트로 작성됩니다. 예를 들어:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> 사실은 **SimpleContent** 이 있는 테이블의 열에 대해 설정할 수 없습니다 **요소** 열 또는 중첩 된 관계입니다.|  
|**숨김**|열이 XML 출력으로 작성되지 않습니다.|  
  
## <a name="see-also"></a>참고자료

- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [DataRelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [데이터 세트 스키마 정보를 XSD로 작성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
