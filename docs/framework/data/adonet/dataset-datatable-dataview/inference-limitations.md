---
title: 유추 제한
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: e584d8c5fa9e8c4f659b57f8fe24b12339ae79d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639590"
---
# <a name="inference-limitations"></a>유추 제한
XML에서 <xref:System.Data.DataSet> 스키마를 유추하는 과정을 통해 만들어지는 스키마는 각 문서의 XML 요소에 따라 다를 수 있습니다. 예를 들어, 다음과 같은 XML 문서를 가정해 봅시다.  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 "Document1," 유추 과정에서 생성 된 **데이터 집합** "Element1" 반복 요소 이기 때문에 "DocumentElement" 및 "Element1," 라는 테이블을 명명 된 합니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 그러나 "문서 2"에 대 한 유추 과정에서 생성 된 **데이터 집합** "NewDataSet" 및 "DocumentElement." 라는 테이블 "Element1"은 특성이나 자식 요소가 없으므로 열로 유추됩니다.  
  
 **DataSet:** NewDataSet  
  
 **테이블:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 이러한 두 XML 문서는 동일한 스키마를 생성하려는 의도로 만들어졌겠지만, 각 문서에 포함된 요소에 따라 유추 과정의 결과가 크게 달라졌습니다.  
  
 XML 문서에서 스키마를 생성할 때 발생할 수 있는 불일치를 방지 하려면 스키마를 로드할 때 XML 스키마 정의 언어 (XSD) 또는 Xml-data Reduced (XDR)를 사용 하 여 명시적으로 지정 하는 권장 된 **데이터 집합** 에서 XML입니다. 명시적으로 지정 하는 방법에 대 한 자세한 내용은 **데이터 집합** XML 스키마를 사용 하 여 스키마를 참조 하십시오 [파생 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.  
  
## <a name="see-also"></a>참고자료
- [XML에서 데이터 세트 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 세트 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
