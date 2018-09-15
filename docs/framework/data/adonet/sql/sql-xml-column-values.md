---
title: SQL XML 열 값
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: b46c763e7cddfc7617c9a6a23428f83a54955ba0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45648176"
---
# <a name="sql-xml-column-values"></a>SQL XML 열 값
SQL Server를 지원 합니다 `xml` 데이터 형식으로 개발자의 표준 동작을 사용 하 여이 형식이 포함 된 결과 집합을 검색할 수 있습니다는 <xref:System.Data.SqlClient.SqlCommand> 클래스. `xml` 열은 다른 열과 마찬가지 방식으로 검색할 수 있지만(예: <xref:System.Data.SqlClient.SqlDataReader>로) 열의 내용을 XML로 작업하려면 <xref:System.Xml.XmlReader>를 사용해야 합니다.  
  
## <a name="example"></a>예제  
 다음 콘솔 응용 프로그램에는 두 개의 행을 포함 하는 각 선택는 `xml` 열에서는 **Sales.Store** 테이블에 **AdventureWorks** 데이터베이스를 <xref:System.Data.SqlClient.SqlDataReader> 인스턴스. 각 행에서 `xml` 열의 값은 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>의 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 사용하여 읽습니다. 값은 <xref:System.Xml.XmlReader>에 저장되어 있습니다. <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>는 <xref:System.Data.IDataRecord.GetValue%2A> 열의 값을 문자열로 반환하므로 내용을 <xref:System.Data.SqlTypes.SqlXml> 변수로 설정하려면 <xref:System.Data.IDataRecord.GetValue%2A> 메서드보다는 `xml`을 사용해야 합니다.  
  
> [!NOTE]
>  합니다 **AdventureWorks** SQL Server를 설치할 때 기본적으로 예제 데이터베이스 설치 되지 됩니다. SQL Server 설치 프로그램을 실행하여 설치할 수 있습니다.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.SqlTypes.SqlXml>  
 [SQL Server의 XML 데이터](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
