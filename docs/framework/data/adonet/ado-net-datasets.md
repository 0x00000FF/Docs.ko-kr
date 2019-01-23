---
title: ADO.NET 데이터 집합
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: f9821f07aae8a761a3890e93347f9cf727f8bdd0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569429"
---
# <a name="adonet-datasets"></a>ADO.NET 데이터 집합
<xref:System.Data.DataSet> 개체는 연결되지 않은 분산 데이터 시나리오를 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 지원하는 데 핵심적인 역할을 수행합니다. 합니다 **데이터 집합** 데이터 소스에 관계 없이 일관성 있는 관계형 프로그래밍 모델을 제공 하는 데이터는 메모리 상주 표현입니다. 이 개체는 다양한 여러 데이터 소스에 사용하거나 XML 데이터에 사용할 수 있을 뿐 아니라 이 개체를 사용하여 응용 프로그램의 로컬 데이터를 관리할 수도 있습니다. 합니다 **데이터 집합** 관련된 테이블, 제약 조건 및 테이블 간의 관계를 포함 하 여 데이터의 전체 집합을 나타냅니다. 다음 그림에 표시 된 **데이터 집합** 개체 모델입니다.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet 개체 모델  
  
 메서드 및 개체에는 **데이터 집합** 관계형 데이터베이스 모델에 있는 것과 일치 합니다.  
  
 합니다 **데이터 집합** 유지 될 수 있으며 해당 내용을 XML로 및 XML 스키마 정의 언어 (XSD)로 스키마를 다시 로드 합니다. 자세한 내용은 [데이터 세트에서 XML 사용](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **데이터 집합** 으로 표시 하는 0 개 이상의 테이블의 컬렉션을 포함 <xref:System.Data.DataTable> 개체입니다. 합니다 <xref:System.Data.DataTableCollection> 모두 포함 합니다 **DataTable** 개체를 **데이터 집합**합니다.  
  
 **DataTable** 에 정의 된 <xref:System.Data> 네임 스페이스 되며 메모리 상주형 데이터의 단일 테이블을 나타냅니다. 여기에는 <xref:System.Data.DataColumnCollection>에 의해 표현되는 열의 컬렉션과 <xref:System.Data.ConstraintCollection>에 의해 표현되는 제약 조건의 컬렉션이 포함됩니다. 이 두 컬렉션은 테이블의 스키마를 정의합니다. A **DataTable** 나타내는 행의 컬렉션도 포함 합니다 <xref:System.Data.DataRowCollection>, 테이블의 데이터를 포함 하는 합니다. 이와 함께 <xref:System.Data.DataRow>는 현재 버전과 원래 버전을 모두 보유하므로 행에 저장된 값에 대한 변경 사항을 식별할 수 있습니다.  
  
## <a name="the-dataview-class"></a>DataView 클래스  
 <xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다. <xref:System.Data.DataView>를 사용하면 테이블의 데이터를 여러 정렬 순서로 노출시킬 수 있으며 행 상태에 따라 또는 필터 식을 기준으로 데이터를 필터링할 수 있습니다. 자세한 내용은 [Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)합니다.  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 A **데이터 집합** 의 관계를 포함 합니다. 해당 <xref:System.Data.DataRelationCollection> 개체입니다. 표현 되는 관계는 <xref:System.Data.DataRelation> 개체를 연결 행에 대 한 **DataTable** 의 다른 행과 **DataTable**. 이 관계는 관계형 데이터베이스의 기본 키 열과 외래 키 열 간에 존재하는 조인 경로와 유사합니다. A **DataRelation** 의 두 테이블에 일치 하는 열을 식별 하는 **데이터 집합**합니다.  
  
 관계에서 다른 한 테이블에서 탐색 사용 하도록 설정 된 **데이터 집합**합니다. 필수 요소는 **DataRelation** 관계의 이름, 관련 되는 테이블의 이름 및 각 테이블의 관련된 열입니다. <xref:System.Data.DataColumn> 개체의 배열을 키 열로 지정하면 테이블당 두 개 이상의 열에 대한 관계를 빌드할 수 있습니다. 에 대 한 관계를 추가 하는 경우는 <xref:System.Data.DataRelationCollection>, 필요에 따라 추가할 수 있습니다를 **UniqueKeyConstraint** 및 **ForeignKeyConstraint** 관련된 열이 변경 될 때 무결성 제약 조건을 적용 하려면 값입니다.  
  
 자세한 내용은 [Datarelation 추가](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)합니다.  
  
## <a name="xml"></a>XML  
 채울 수 있습니다는 **데이터 집합** XML 스트림이나 문서에서 합니다. 에 제공 하는 XML 스트림이나 문서를 사용할 수 있습니다 합니다 **데이터 집합** 데이터, 스키마 정보 또는 둘 다. XML 스트림이나 문서에서 제공 되는 정보를 기존 데이터 나 스키마 정보와에 이미 있는와 결합할 수는 **데이터 집합**합니다. 자세한 내용은 [데이터 세트에서 XML 사용](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 합니다 **데이터 집합**를 **DataTable**, 및 **DataColumn** 모두를 **ExtendedProperties** 속성입니다. **ExtendedProperties** 되는 **PropertyCollection** 결과 집합을 생성 하는 SELECT 문이나 데이터가 생성 된 시간 등의 사용자 지정 정보를 배치할 수 있습니다. 합니다 **ExtendedProperties** 컬렉션에 대 한 스키마 정보를 함께 유지 되는 **데이터 집합**합니다.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서는 데이터 집합에 저장되어 있는 연결되지 않은 데이터에 대한 통합 언어 쿼리 기능을 제공합니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] standard를 사용 하 여 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 구문을 Visual Studio IDE를 사용 하는 경우 컴파일 타임 구문 검사, 정적 입력 및 IntelliSense 지원을 제공 합니다.  
  
 자세한 내용은 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
