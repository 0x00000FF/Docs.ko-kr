---
title: ADO.NET 아키텍처
ms.date: 03/30/2017
ms.assetid: fcd45b99-ae8f-45ab-8b97-d887beda734e
ms.openlocfilehash: 282f18cc7d379dffc410a0c62dc3b3e66e0a44f6
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267974"
---
# <a name="adonet-architecture"></a>ADO.NET 아키텍처
기존의 데이터 처리는 연결 기반의 2계층 모델에 의존해 왔습니다. 그러나 다중 계층 아키텍처를 사용하는 데이터 처리가 증가함에 따라 프로그래머는 연결되지 않은 방법으로 전환하여 응용 프로그램의 확장성을 개선하고 있습니다.  
  
## <a name="adonet-components"></a>ADO.NET 구성 요소  
 데이터 액세스 및 조작을 위한 ADO.NET의 두 가지 주요 구성 요소는.NET Framework 데이터 공급자 및 <xref:System.Data.DataSet>합니다.  
  
### <a name="net-framework-data-providers"></a>.NET Framework 데이터 공급자  
 .NET Framework 데이터 공급자는 데이터 조작과 정방향 읽기 전용 고속 데이터 액세스를 위해 명시적으로 디자인된 구성 요소입니다. `Connection` 개체는 데이터 소스에 대한 연결을 제공합니다. `Command` 개체를 사용하면 데이터베이스 명령에 액세스하여 데이터를 반환 및 수정하고 저장 프로시저를 실행하며 매개 변수 정보를 보내거나 검색할 수 있습니다. `DataReader`는 데이터 소스의 데이터에 대한 고성능 스트림을 제공합니다. 마지막으로 `DataAdapter`는 `DataSet` 개체와 데이터 소스 사이를 연결합니다. `DataAdapter`는 `Command` 개체로 데이터 소스에서 SQL 명령을 실행하여 `DataSet`을 데이터와 함께 로드하고 `DataSet`에 포함된 데이터의 변경 내용을 데이터 소스로 되돌려 조정합니다. 자세한 내용은 [.NET Framework 데이터 공급자](../../../../docs/framework/data/adonet/data-providers.md) 하 고 [ADO.NET에서 데이터 수정 및 검색](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)합니다.  
  
### <a name="the-dataset"></a>DataSet  
 ADO.NET `DataSet`은 데이터 소스에 관계없이 데이터에 액세스할 수 있도록 명시적으로 디자인되었습니다. 따라서 응용 프로그램에 로컬인 데이터를 관리하기 위해 이를 단독으로 사용하거나 다양한 여러 데이터 소스 또는 XML 데이터와 함께 사용할 수도 있습니다. `DataSet`에는 데이터 행과 열로 구성된 하나 이상의 <xref:System.Data.DataTable> 개체의 컬렉션뿐만 아니라 `DataTable` 개체의 데이터에 대한 기본 키, 외래 키, 제약 조건 및 관련 정보가 들어 있습니다. 자세한 내용은 [Dataset, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)합니다.  
  
 다음 다이어그램에.NET Framework 데이터 공급자 간의 관계 및 `DataSet`합니다.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
ADO.NET 아키텍처  
  
### <a name="choosing-a-datareader-or-a-dataset"></a>DataReader 또는 DataSet 선택  
 응용 프로그램을 사용할지 여부를 결정 하는 `DataReader` (참조 [DataReader를 사용 하 여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)) 또는 `DataSet` (참조 [Dataset, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)), 함수의 유형을 고려 응용 프로그램에 필요한 기능입니다. `DataSet`을 사용하면 다음을 수행할 수 있습니다.  
  
- 데이터를 조작할 수 있도록 응용 프로그램에서 데이터를 로컬로 캐시합니다. 쿼리 결과만 읽으면 되는 경우에는 `DataReader`를 사용하는 것이 좋습니다.  
  
- 계층 간 데이터나 XML Web services의 데이터를 원격화합니다.  
  
- Windows Forms 컨트롤에 바인딩하거나 여러 소스의 데이터를 결합하고 연관시키는 등 데이터와 동적으로 상호 작용합니다.  
  
- 데이터 소스에 대한 개방형 연결이 필요 없는 광범위한 데이터 처리를 수행하여 다른 클라이언트가 사용하는 연결을 제거합니다.  
  
 `DataSet`에서 제공하는 기능이 필요하지 않은 경우에는 `DataReader`로 데이터를 정방향 읽기 전용 방식으로 반환하여 응용 프로그램의 성능을 향상시킬 수 있습니다. 있지만 `DataAdapter` 사용 하 여는 `DataReader` 의 내용에 맞게를 `DataSet` (참조 [DataAdapter에서 DataSet 채우기](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md))를 사용 하 여는 `DataReader`, 메모리 저장 하기 때문에 성능을 향상 시킬 수 있습니다 사용할 수 있는 합니다 `DataSet`를 만들고 내용을 채우는 데 필요한 처리를 방지 하 고는 `DataSet`합니다.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 LINQ to DataSet은 DataSet 개체에 캐시된 데이터에 대해 쿼리 기능과 컴파일 타임 형식 검사 기능을 제공합니다. LINQ to DataSet을 사용하면 C#이나 Visual Basic 같은 .NET Framework 개발 언어 중 하나로 쿼리를 작성할 수 있습니다. 자세한 내용은 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)을 참조하세요.  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL은 중간 개념 모델을 사용하지 않고 관계형 데이터베이스의 데이터 구조에 매핑되는 개체 모델을 직접 쿼리할 수 있도록 지원합니다. 각 테이블은 개체 모델을 관계형 데이터베이스 스키마와 긴밀하게 연결하는 별도의 클래스로 나타납니다. LINQ to SQL은 개체 모델의 통합 언어 쿼리를 Transact-SQL로 변환한 후 실행을 위해 데이터베이스로 보냅니다. 데이터베이스에서 결과를 반환하면 LINQ to SQL이 결과를 다시 개체로 변환합니다. 자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 ADO.NET Entity Framework는 개발자가 관계형 저장소 스키마에 대해 직접 프로그래밍하는 대신 개념적 응용 프로그램 모델에 대해 프로그래밍하는 방법으로 데이터 액세스 응용 프로그램을 만들 수 있도록 설계되었습니다. 이 프레임워크의 목표는 데이터 지향 응용 프로그램에 필요한 코드와 유지 관리 작업의 양을 줄이는 것입니다. 자세한 내용은 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)합니다.  
  
## <a name="wcf-data-services"></a>WCF Data Services  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 웹 또는 인트라넷에 데이터 서비스를 배포하는 데 사용됩니다. 데이터는 엔터티 데이터 모델의 사양에 따라 엔터티와 관계로 구조화됩니다. 이 모델에 배포되는 데이터는 표준 HTTP 프로토콜로 주소를 지정할 수 있습니다. 자세한 내용은 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)를 참조하세요.  
  
## <a name="xml-and-adonet"></a>XML 및 ADO.NET  
 ADO.NET 연결 되지 않은 데이터에 액세스할 수 있도록 XML의 강력한 기능을 활용 합니다. ADO.NET가 설계 된 직접 관련 않으며.NET Framework의 XML 클래스를 사용 하 여 모두 단일 아키텍처의 구성 요소입니다.  
  
 ADO.NET 및.NET Framework의 XML 클래스에서 수렴 된 `DataSet` 개체입니다. `DataSet`은 파일이든 XML 스트림이든 간에 XML 소스의 데이터로 채울 수 있습니다. `DataSet`은 `DataSet`의 데이터 소스에 관계없이 해당 스키마를 XSD(XML 스키마 정의 언어) 스키마로 포함하여 W3C(World-Wide Web 컨소시엄) 규격의 XML로 작성할 수 있습니다. `DataSet`의 네이티브 serialization 형식은 XML로 `DataSet`은 XML Web services를 통해 데이터 및 스키마 컨텍스트를 원격화하는 데 최적으로 사용할 수 있으므로 계층 간 데이터를 이동하기 위한 탁월한 수단입니다. 자세한 내용은 [XML 문서 및 데이터](../../../../docs/standard/data/xml/index.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
