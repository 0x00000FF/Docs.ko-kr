---
title: Oracle 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: c1fb3a6838e6a1b242255d4035c10ab0ec07d536
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771984"
---
# <a name="oracle-data-type-mappings"></a>Oracle 데이터 형식 매핑
다음 표에는 Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.  
  
|Oracle 데이터 형식|OracleDataReader.GetValue에 의해 반환되는 .NET Framework 데이터 형식|OracleDataReader.GetOracleValue에 의해 반환되는 OracleClient 데이터 형식|설명|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식 별칭으로 사용 되는 **수** 데이터 형식으로 설계 되었습니다 있도록를 <xref:System.Data.OracleClient.OracleDataReader> 반환를 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 부동 소수점 값 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식 별칭으로 사용 되는 **NUMBER(38)** 데이터 형식으로 설계 되었습니다 있도록를 <xref:System.Data.OracleClient.OracleDataReader> 반환을 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 정수 값 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**두 번째 간격 일**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|.NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** 데이터 형식에서 지원 되지 않습니다는 <xref:System.Data.OracleClient.OracleDataReader> 개체입니다.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**현지 표준 시간대를 사용 하 여 타임 스탬프**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**표준 시간대를 사용 하 여 타임 스탬프**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**부호 없는 정수**|**숫자**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식 별칭으로 사용 되는 **NUMBER(38)** 데이터 형식으로 설계 되었습니다 있도록를 <xref:System.Data.OracleClient.OracleDataReader> 반환을 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 부호 없는 정수 값 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 다음 표에서 Oracle 데이터 형식 및.NET Framework 데이터 형식 (**System.Data.DbType** 및 <xref:System.Data.OracleClient.OracleType>) 매개 변수로 바인딩할 때 사용 합니다.  
  
|Oracle 데이터 형식|매개 변수로 바인딩하는 DbType 열거형|매개 변수로 바인딩하는 OracleType 열거형|설명|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle에만 바인딩할 수 있습니다는 **BFILE** 으로 **BFILE** 매개 변수입니다. .NET Data Provider for Oracle 않습니다 하지 자동으로 생성 비-바인딩하려는 경우**BFILE** 값을 같은 **byte** 또는 <xref:System.Data.OracleClient.OracleBinary>합니다.|  
|**BLOB**||**Blob**|Oracle에만 바인딩할 수 있습니다는 **BLOB** 으로 **BLOB** 매개 변수입니다. .NET Data Provider for Oracle 않습니다 하지 자동으로 생성 비-바인딩하려는 경우**BLOB** 값을 같은 **byte** 또는 <xref:System.Data.OracleClient.OracleBinary>합니다.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle에만 바인딩할 수 있습니다는 **CLOB** 으로 **CLOB** 매개 변수입니다. .NET Data Provider for Oracle 않습니다 하지 자동으로 생성 비-바인딩하려는 경우**CLOB** 값을 같은 **System.String** 또는 <xref:System.Data.OracleClient.OracleString>합니다.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, 번호**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 결정 합니다 **System.Data.DBType** 고 <xref:System.Data.OracleClient.OracleType>입니다.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 결정 합니다 **System.Data.DBType** 고 <xref:System.Data.OracleClient.OracleType>입니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**두 번째 간격 일**|**개체**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle에만 바인딩할 수 있습니다는 **NCLOB** 으로 **NCLOB** 매개 변수입니다. .NET Data Provider for Oracle 않습니다 하지 자동으로 생성 비-바인딩하려는 경우**NCLOB** 값을 같은 **System.String** 또는 <xref:System.Data.OracleClient.OracleString>합니다.|  
|**NUMBER**|**VarNumeric**|**숫자**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Raw**||  
|**REF CURSOR**||**커서**|자세한 내용은 [Oracle REF Cursor](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)합니다.|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**타임스탬프**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**현지 표준 시간대를 사용 하 여 타임 스탬프**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**표준 시간대를 사용 하 여 타임 스탬프**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**부호 없는 정수**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> 결정 합니다 **System.Data.DBType** 고 <xref:System.Data.OracleClient.OracleType>입니다.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 합니다 **InputOutput**, **출력**, 및 **ReturnValue** **ParameterDirection** 사용 된 값을 <xref:System.Data.OracleClient.OracleParameter.Value%2A> 속성을 <xref:System.Data.OracleClient.OracleParameter> 입력된 값을 Oracle 데이터 형식이 아닌 개체는.NET Framework 데이터 형식 (예를 들어 <xref:System.Data.OracleClient.OracleNumber> 또는 <xref:System.Data.OracleClient.OracleString>). 에 적용 되지 않습니다 **REF CURSOR**를 **BFILE**, 또는 **LOB** 데이터 형식입니다.  
  
## <a name="see-also"></a>참고자료

- [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
