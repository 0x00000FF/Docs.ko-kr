---
title: DataAdapter 및 DataReader
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 6e711b11ef9a3eca53806b825f1e721169ab662d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476224"
---
# <a name="dataadapters-and-datareaders"></a>DataAdapter 및 DataReader
ADO.NET을 사용할 수 있습니다 **DataReader** 데이터베이스에서 데이터를 읽기 전용, 정방향 전용 스트림을 검색할 수 있습니다. 쿼리가 실행 되 고 해당 작업을 요청할 때까지 클라이언트의 네트워크 버퍼에 저장 된 대로 결과가 반환 됩니다 사용 하 여는 **읽기** 메서드는 **DataReader**합니다. 사용 하는 **DataReader** (기본적으로) 및 사용 가능한 즉시 데이터를 검색 하 여 응용 프로그램 성능을 향상 시킬 수 시스템 오버 헤드를 줄임으로써 메모리에서 한 번에 하나의 행을 저장 합니다.  
  
 <xref:System.Data.Common.DataAdapter>는 데이터 소스에서 데이터를 검색하고 <xref:System.Data.DataSet> 내의 테이블을 채우는 데 사용됩니다. `DataAdapter`는 `DataSet`의 변경 내용을 다시 데이터 소스에 적용합니다. `DataAdapter`는 .NET Framework 데이터 공급자의 `Connection` 개체를 사용하여 데이터 소스에 연결하며 `Command` 개체를 사용하여 데이터 소스에서 데이터를 검색하고 변경 내용을 데이터 소스에 적용합니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbDataReader> 및 <xref:System.Data.Common.DbDataAdapter> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.OleDb.OleDbDataAdapter> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlDataReader> 및 <xref:System.Data.SqlClient.SqlDataAdapter> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcDataReader> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleDataReader> 및 <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataReader를 사용하여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 ADO.NET에 설명 합니다 **DataReader** 개체 및 사용 데이터 소스에서 결과 스트림을 반환 하는 방법입니다.  
  
 [DataAdapter에서 데이터 집합 채우기](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 `DataSet`를 사용하여 테이블, 열 및 행으로 `DataAdapter`을 채우는 방법을 설명합니다.  
  
 [DataAdapter 매개 변수](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 `DataAdapter`의 열 내용을 명령 매개 변수에 매핑하는 방법을 비롯하여 `DataSet`의 명령 속성에 매개 변수를 사용하는 방법을 설명합니다.  
  
 [데이터 집합에 기존 제약 조건 추가](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 `DataSet`에 기존 제약 조건을 추가하는 방법을 설명합니다.  
  
 [DataAdapter DataTable 및 DataColumn 매핑](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 `DataTableMappings`에 대해 `ColumnMappings` 및 `DataAdapter`를 설정하는 방법을 설명합니다.  
  
 [쿼리 결과를 통해 페이징](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 쿼리 결과를 데이터 페이지로 보는 예제를 제공합니다.  
  
 [DataAdapter로 데이터 원본 업데이트](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 `DataAdapter`를 사용하여 `DataSet`의 변경 내용을 데이터베이스에 적용하는 방법을 설명합니다.  
  
 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 `DataAdapter` 이벤트와 이벤트 사용 방법을 설명합니다.  
  
 [DataAdapter를 사용하여 일괄 작업 수행](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 `DataSet`의 업데이트를 적용할 때 SQL Server로의 라운드트립 횟수를 줄여 응용 프로그램의 성능을 향상시키는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
