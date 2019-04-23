---
title: DataTable 스키마 정의
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: e8710e7d92558f525a6feaedf8d0635c5ce6e2c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163074"
---
# <a name="datatable-schema-definition"></a>DataTable 스키마 정의
테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다. <xref:System.Data.DataTable>의 스키마는 <xref:System.Data.DataColumn> 개체를 비롯하여 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체를 사용하여 정의합니다. 테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.  
  
 테이블의 열, 관계 및 제약 조건을 이름에 따라 참조하는 경우 대/소문자를 구분합니다. 따라서 이름이 동일한 열, 관계 또는 제약 조건이 테이블에 두 개 이상 존재할 수 있지만, 대/소문자는 다르게 표기됩니다. 예를 들어, 있습니다 **Col1** 하 고 **col1**합니다. 이러한 경우 이름에 따라 열을 참조하려면 열 이름의 대/소문자가 정확하게 일치해야 하며, 그렇지 않으면 예외가 throw됩니다. 예를 들어 경우 테이블 **myTable** 열이 포함 **Col1** 하 고 **col1**를 참조 하 게 됩니다 **Col1** 로  **myTable.Columns["Col1"]**, 및 **col1** 으로 **myTable.Columns["col1"]** 합니다. 로 열 중 하나를 참조 하려고 **myTable.Columns["COL1"]** 예외가 발생 합니다.  
  
 특정 이름의 열, 관계 또는 제약 조건이 하나만 있으면 대/소문자 구분 규칙이 적용되지 않습니다. 즉, 테이블에 있는 기타 열, 관계 또는 제약 조건 개체의 이름이 특정한 열, 관계 또는 제약 조건 개체의 이름과 일치하지 않더라도 이름에 따라 대/소문자 구분 없이 해당 개체를 참조할 수 있으며, 예외가 throw되지 않습니다. 예를 들어 테이블에만 **Col1**를 사용 하 여 참조할 수 있습니다 **내입니다. 열 ["COL1"]** 합니다.  
  
> [!NOTE]
>  합니다 <xref:System.Data.DataTable.CaseSensitive%2A> 의 속성을 **DataTable** 이 동작에 영향을 주지 않습니다. 합니다 **CaseSensitive** 속성은 열, 관계 및 제약 조건에 대 한 참조가 아니라 데이터 테이블 및에 영향을 줍니다 정렬, 검색, 필터링, 제약 조건 및 등등으로 적용에 적용 됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataTable에 열 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 사용 하 여 테이블의 열을 정의 하는 방법에 설명 **DataColumn** 개체입니다.  
  
 [식 열 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 에 대해 설명 하는 방법을 **식** 행의 다른 열에서 값을 기반으로 하는 값을 계산 하려면 열의 속성을 사용할 수 있습니다.  
  
 [AutoIncrement 열 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 숫자 값을 자동으로 증가시켜 행마다 열 값이 고유하도록 열을 설정하는 방법을 설명합니다.  
  
 [기본 키 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 하나 이상의 테이블의 기본 키를 지정 하는 방법에 설명 **DataColumn** 개체입니다.  
  
 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 테이블에서 열의 외래 키와 UNIQUE 제약 조건을 정의하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고자료

- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
