---
title: 테이블 유추
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 174d305688c7090c163df60a11e233aea24b8f79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587356"
---
# <a name="inferring-tables"></a>테이블 유추
XML 문서로부터 <xref:System.Data.DataSet>의 스키마를 유추할 때 ADO.NET에서는 우선 테이블을 나타내는 XML 요소를 결정합니다. 다음 XML 구조에 대 한 테이블의 결과 **데이터 집합** 스키마:  
  
- 특성이 있는 요소  
  
- 자식 요소가 있는 요소  
  
- 반복되는 요소  
  
## <a name="elements-with-attributes"></a>특성이 있는 요소  
 자신에 지정된 특성을 갖고 있는 요소는 유추된 테이블이 됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>자식 요소가 있는 요소  
 자식 요소를 갖고 있는 요소는 유추된 테이블이 됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 문서 요소 또는 루트 요소는 열로 유추되는 특성이나 자식 요소를 갖고 있는 경우 유추된 테이블이 됩니다. 문서 요소가 없는 특성과 열으로 유추 되는 자식 요소가 없는 요소도 유추 됩니다는 **데이터 집합**합니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "DocumentElement"라는 테이블이 생성됩니다.  
  
 **DataSet:** NewDataSet  
  
 **테이블:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 또는 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 유추 과정에서 생성 된 **데이터 집합** "Element1." 라는 테이블을 포함 하는 "DocumentElement" 라는  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>반복되는 요소  
 반복되는 요소는 하나의 유추된 테이블이 됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>참고자료

- [XML에서 데이터 세트 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 세트 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
