---
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 0a98bfd401aaabfb754c422cc753bc5092f9f76c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64633334"
---
# <a name="oracle-ref-cursors"></a>Oracle REF CURSOR
.NET Framework Data Provider for Oracle은 Oracle 지원 **REF CURSOR** 데이터 형식입니다. Oracle REF CURSOR를 사용하는 데이터 공급자를 사용할 경우 다음 동작을 고려해야 합니다.  
  
> [!NOTE]
>  일부 동작이 MSDAORA(Microsoft OLE DB Provider for Oracle)의 동작과 다릅니다.  
  
- 성능상의 이유로 Data Provider for Oracle 자동으로 바인딩할 수 없으면 **REF CURSOR** 데이터 형식은 MSDAORA 에서처럼 명시적으로 지정 합니다.  
  
- 데이터 공급자는 REF CURSOR 매개 변수를 지정하는 데 사용되는 {resultset} 이스케이프를 포함하여 ODBC 이스케이프 시퀀스를 지원하지 않습니다.  
  
- REF Cursor를 반환 하는 저장된 프로시저를 실행 하려면 매개 변수를 정의 해야 합니다 <xref:System.Data.OracleClient.OracleParameterCollection> 사용 하 여는 <xref:System.Data.OracleClient.OracleType> 의 **커서** 와 <xref:System.Data.OracleClient.OracleParameter.Direction%2A> 의 **출력**합니다. 데이터 공급자는 REF CURSOR를 출력 매개 변수로만 바인딩하는 것을 지원하며 REF CURSOR를 입력 매개 변수로 지원하지 않습니다.  
  
- 매개 변수 값에서 <xref:System.Data.OracleClient.OracleDataReader>를 가져오는 것은 지원되지 않습니다. 값의 형식은 명령이 실행된 후의 <xref:System.DBNull>입니다.  
  
- 유일한 **CommandBehavior** REF Cursor를 사용 하 여 작동 하는 열거형 값 (호출 하는 경우에 예를 들어 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>)는 **CloseConnection**; 나머지는 무시 됩니다.  
  
- REF Cursor의 순서를 **OracleDataReader** 매개 변수 순서에 따라 합니다 **OracleParameterCollection**합니다. <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 속성은 무시됩니다.  
  
- PL/SQL **테이블** 데이터 형식이 지원 되지 않습니다. 그러나 REF CURSOR가 더 효율적입니다. 사용 해야 하는 경우는 **테이블** 데이터 형식, OLE DB.NET Data Provider와 MSDAORA를 함께 사용 하 여 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [REF CURSOR 예제](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 REF CURSOR의 사용을 보여 주는 세 가지 예제가 들어 있습니다.  
  
 [OracleDataReader의 REF CURSOR 매개 변수](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 값을 읽고 REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하는 방법에 설명 된 **OracleDataReader**합니다.  
  
 [OracleDataReader를 사용하여 여러 REF CURSOR에서 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 사용 하 여 값을 읽고 두 개의 REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하는 방법에 설명 된 **OracleDataReader**합니다.  
  
 [하나 이상의 REF CURSOR를 사용하여 데이터 세트 채우기](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 두 개의 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하여 반환되는 행으로 <xref:System.Data.DataSet>을 채우는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고자료

- [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
