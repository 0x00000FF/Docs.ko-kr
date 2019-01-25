---
title: .NET Framework 데이터 공급자
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: d96be73fc63856e317b129c1fdd8c381c9df6c07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627267"
---
# <a name="net-framework-data-providers"></a>.NET Framework 데이터 공급자
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자는 데이터베이스에 연결하고 명령을 실행하며 결과를 검색하는 데 사용됩니다. 검색된 결과는 곧바로 처리되거나 <xref:System.Data.DataSet> 에 저장되어 필요한 경우 사용자에게 노출되거나 여러 소스의 데이터와 함께 사용되거나 계층 간에 원격으로 사용됩니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자는 간단하여 데이터 소스와 사용자 코드 간에 최소의 계층을 만들며 기능 저하 없이 성능을 향상시킵니다.  
  
 다음 표에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 포함되어 있는 데이터 공급자를 보여 줍니다.  
  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자|설명|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server|Microsoft SQL Server에 대한 데이터 액세스를 제공합니다. <xref:System.Data.SqlClient> 네임스페이스를 사용합니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB|OLE DB를 사용하여 노출된 데이터 소스에서 사용합니다. <xref:System.Data.OleDb> 네임스페이스를 사용합니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]Data Provider for ODBC|OLE DB를 사용하여 노출된 데이터 소스에서 사용합니다. <xref:System.Data.Odbc> 네임스페이스를 사용합니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle|Oracle 데이터 소스에서 사용합니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle은 Oracle 클라이언트 소프트웨어 버전 8.1.7 이상을 지원하며 <xref:System.Data.OracleClient> 네임스페이스를 사용합니다.|  
|EntityClient 공급자|EDM(엔터티 데이터 모델) 애플리케이션에 대한 데이터 액세스를 제공합니다. <xref:System.Data.EntityClient> 네임스페이스를 사용합니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server Compact 4.0입니다.|Microsoft SQL Server Compact 4.0에 대 한 데이터 액세스를 제공합니다. [System.Data.SqlServerCe](https://msdn.microsoft.com/library/system.data.sqlserverce.aspx) 네임스페이스를 사용합니다.|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>.NET Framework 데이터 공급자의 핵심 개체  
 다음 표에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자를 구성하는 네 가지 핵심 개체에 대해 간략하게 설명합니다.  
  
|개체|설명|  
|------------|-----------------|  
|`Connection`|특정 데이터 소스에 연결합니다. 모든 `Connection` 개체의 기본 클래스는 <xref:System.Data.Common.DbConnection> 클래스입니다.|  
|`Command`|데이터 소스에 대해 명령을 실행합니다. `Parameters`를 노출하고 `Transaction`의 `Connection` 범위 내에서 실행할 수 있습니다. 모든 `Command` 개체의 기본 클래스는 <xref:System.Data.Common.DbCommand> 클래스입니다.|  
|`DataReader`|데이터 소스에서 앞으로만 이동 가능한 읽기 전용 데이터 스트림을 읽습니다. 모든 `DataReader` 개체의 기본 클래스는 <xref:System.Data.Common.DbDataReader> 클래스입니다.|  
|`DataAdapter`|`DataSet`을 채우고 업데이트 내용을 데이터 소스에 적용합니다. 모든 `DataAdapter` 개체의 기본 클래스는 <xref:System.Data.Common.DbDataAdapter> 클래스입니다.|  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에는 이 문서의 이전 표에 나와 있는 핵심 클래스뿐만 아니라 다음 표에 나열된 클래스도 포함되어 있습니다.  
  
|개체|설명|  
|------------|-----------------|  
|`Transaction`|데이터 소스의 트랜잭션에 명령을 인리스트먼트합니다. 모든 `Transaction` 개체의 기본 클래스는 <xref:System.Data.Common.DbTransaction> 클래스입니다. ADO.NET에서는 <xref:System.Transactions> 네임스페이스에 있는 클래스를 사용하여 트랜잭션에 대한 지원을 제공합니다.|  
|`CommandBuilder`|`DataAdapter`의 명령 속성을 자동으로 생성하거나 저장 프로시저에서 매개 변수 정보를 파생하여 `Parameters` 개체의 `Command` 컬렉션을 채우는 도우미 개체입니다. 모든 `CommandBuilder` 개체의 기본 클래스는 <xref:System.Data.Common.DbCommandBuilder> 클래스입니다.|  
|`ConnectionStringBuilder`|`Connection` 개체에서 사용하는 연결 문자열의 내용을 간단히 만들고 관리할 수 있도록 하는 도우미 개체입니다. 모든 `ConnectionStringBuilder` 개체의 기본 클래스는 <xref:System.Data.Common.DbConnectionStringBuilder> 클래스입니다.|  
|`Parameter`|명령과 저장 프로시저에 대한 입력, 출력 및 반환 값 매개 변수를 정의합니다. 모든 `Parameter` 개체의 기본 클래스는 <xref:System.Data.Common.DbParameter> 클래스입니다.|  
|`Exception`|데이터 소스에서 오류가 발생하면 반환됩니다. 클라이언트에서 오류가 발생하는 경우 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 예외를 throw합니다. 모든 `Exception` 개체의 기본 클래스는 <xref:System.Data.Common.DbException> 클래스입니다.|  
|`Error`|데이터 소스에서 반환한 경고 또는 오류에서 정보를 노출시킵니다.|  
|`ClientPermission`|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에 코드 액세스 보안 특성을 제공합니다. 모든 `ClientPermission` 개체의 기본 클래스는 <xref:System.Data.Common.DBDataPermission> 클래스입니다.|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>.NET Framework Data Provider for SQL Server(SqlClient)  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server (SqlClient)는 자체 프로토콜을 사용 하 여 SQL Server와 통신할 수 있습니다. 간단 하 고 SQL Server OLE DB 또는 ODBC Open Database Connectivity () 계층을 추가 하지 않고 직접 액세스 하도록 최적화 되어 있으므로 잘 수행 합니다. 다음 그림에서는 비교 합니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB입니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB는 연결 풀링 및 트랜잭션 서비스를 제공하는 OLE DB 서비스 구성 요소와 데이터 소스에 대한 OLE DB 공급자 모두를 통해 OLE DB 데이터 소스와 통신합니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC 아키텍처는 ODBC 서비스 구성 요소를 호출하는 등 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB 아키텍처와 비슷한 부분이 있습니다.  
  
 ![데이터 공급자](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
.NET Framework Data Provider for SQL Server와 .NET Framework Data Provider for OLE DB 비교  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server 클래스에는 <xref:System.Data.SqlClient> 네임 스페이스입니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server는 로컬 및 분산 트랜잭션을 지원 합니다. 분산 트랜잭션의 경우 합니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server, 기본적으로 자동으로 트랜잭션을 참여 하 고 Windows Component Services 로부터 트랜잭션 세부 정보를 얻습니다 또는 <xref:System.Transactions>합니다. 자세한 내용은 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)합니다.  
  
 다음 코드 예제에서는 `System.Data.SqlClient` 네임스페이스를 애플리케이션에 포함하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>.NET Framework Data Provider for OLE DB  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB(OleDb)는 COM interop를 통해 네이티브 OLE DB를 사용하여 데이터 액세스를 활성화합니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB는 로컬 및 분산 트랜잭션을 모두 지원합니다. 분산 트랜잭션의 경우, 기본적으로 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB는 트랜잭션에 자동으로 참여하고 Windows Component Services로부터 트랜잭션 세부 정보를 얻습니다. 자세한 내용은 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)합니다.  
  
 다음 표에서는 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 테스트한 공급자를 보여 줍니다.  
  
|드라이버|공급자|  
|------------|--------------|  
|SQLOLEDB|SQL Server 용 Microsoft OLE DB 공급자|  
|MSDAORA|Microsoft OLE DB provider for Oracle|  
|Microsoft.Jet.OLEDB.4.0|OLE DB provider for Microsoft Jet|  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램과 같은 다중 스레드 응용 프로그램의 경우 Access(Jet) 데이터베이스를 데이터 소스로 사용하지 않는 것이 좋습니다. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램의 데이터 소스로 Jet을 사용하게 되면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에서 Access 데이터베이스에 연결할 때 연결 문제가 발생합니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB는 OLE DB 버전 2.5 인터페이스를 지원하지 않습니다. OLE DB 2.5 인터페이스 지원이 필요한 OLE DB 공급자는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB에서 제대로 작동하지 않습니다. 여기에는 Microsoft OLE DB Provider for Exchange와 Microsoft OLE DB Provider for Internet Publishing이 포함됩니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB는 MSDASQL(OLE DB Provider for ODBC)과 같이 사용할 수 없습니다. [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 ODBC 데이터 소스에 액세스하려면 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC를 사용하세요.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB 클래스는 <xref:System.Data.OleDb> 네임스페이스에 있습니다. 다음 코드 예제에서는 `System.Data.OleDb` 네임스페이스를 애플리케이션에 포함하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET Framework Data Provider for ODBC  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC(Odbc)는 네이티브 ODBC DM(드라이버 관리자)을 사용하여 데이터 액세스를 활성화합니다. ODBC 데이터 공급자는 로컬 및 분산 트랜잭션을 모두 지원합니다. 분산 트랜잭션의 경우, 기본적으로 ODBC 데이터 공급자는 트랜잭션에 자동으로 참여하고 Windows Component Services로부터 트랜잭션 세부 정보를 얻습니다. 자세한 내용은 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)합니다.  
  
 다음 표에서는 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 테스트한 ODBC 드라이버를 보여 줍니다.  
  
|드라이버|  
|------------|  
|SQL Server|  
|Microsoft ODBC for Oracle|  
|Microsoft Access Driver(*.mdb)|  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC 클래스는 <xref:System.Data.Odbc> 네임스페이스에 있습니다.  
  
 다음 코드 예제에서는 `System.Data.Odbc` 네임스페이스를 애플리케이션에 포함하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC는 MDAC 2.6 이상이 필요하며 MDAC 2.8 SP1을 사용하는 것이 좋습니다. [데이터 액세스 및 Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173)에서 MDAC 2.8 SP1을 다운로드할 수 있습니다.  
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET Framework Data Provider for Oracle  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle(OracleClient)을 사용하면 Oracle 클라이언트 연결 소프트웨어를 통해 Oracle 데이터 소스에 액세스할 수 있습니다. 이 데이터 공급자는 Oracle 클라이언트 소프트웨어 버전 8.1.7 이상을 지원합니다. 또한 로컬 및 분산 트랜잭션을 모두 지원합니다. 자세한 내용은 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)합니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle을 사용하여 Oracle 데이터 소스에 연결하려면 시스템에 Oracle 클라이언트 소프트웨어 8.1.7 이상 버전이 있어야 합니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle 클래스는 <xref:System.Data.OracleClient> 네임스페이스에 있으며 `System.Data.OracleClient.dll` 어셈블리에 포함되어 있습니다. 데이터 공급자를 사용하는 애플리케이션을 컴파일할 때 `System.Data.dll` 과 `System.Data.OracleClient.dll` 을 모두 참조해야 합니다.  
  
 다음 코드 예제에서는 `System.Data.OracleClient` 네임스페이스를 애플리케이션에 포함하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>.NET Framework 데이터 공급자 선택  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자를 선택하면 응용 프로그램의 디자인 및 데이터 소스에 따라 응용 프로그램의 성능, 기능 및 무결성이 향상될 수 있습니다. 다음 표에서는 각 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자의 장점 및 제한 사항에 대해 설명합니다.  
  
|공급자|노트|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server|Microsoft SQL Server를 사용 하는 중간 계층 응용 프로그램에 대 한 것이 좋습니다.<br /><br /> Microsoft Database Engine (MSDE) 또는 SQL Server를 사용 하는 단일 계층 응용 프로그램에 대 한 것이 좋습니다.<br /><br /> OLE DB 공급자 사용에 대 한 SQL Server (SQLOLEDB) 사용 하 여 보다 권장 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB입니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB|SQL server는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server는이 공급자 대신 것이 좋습니다.<br /><br /> Microsoft Access 데이터베이스를 사용하는 단일 계층 애플리케이션에 권장됩니다. 중간 계층 애플리케이션에는 Access 데이터베이스를 사용하지 않는 것이 좋습니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ``Data Provider for ODBC|ODBC 데이터 소스를 사용하는 중간 및 단일 계층 애플리케이션에 권장됩니다.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ' Data Provider for Oracle|Oracle 데이터 소스를 사용하는 중간 및 단일 계층 애플리케이션에 권장됩니다.|  
  
## <a name="entityclient-provider"></a>EntityClient 공급자  
 EntityClient 공급자는 EDM(엔터티 데이터 모델)을 기반으로 데이터에 액세스하는 데 사용됩니다. EntityClient 공급자는 다른 .NET Framework 데이터 공급자와 달리 데이터 소스와 직접 상호 작용하지 않고 대신 Entity SQL을 사용하여 기본 데이터 공급자와 통신합니다. 자세한 내용은 [EntityClient and Entity SQL](https://msdn.microsoft.com/library/49202ab9-ac98-4b4b-a05c-140e422bf527)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
