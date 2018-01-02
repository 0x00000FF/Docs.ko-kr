---
title: "샘플 공급자의 SQL 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 853bf55f96be3adeba11ff14e36fd56631536b69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sql-generation-in-the-sample-provider"></a>샘플 공급자의 SQL 생성
[Entity Framework 샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) 새 구성 요소가 지 원하는 ADO.NET 데이터 공급자는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.  샘플 공급자는 SQL Server 2005 데이터베이스와 작동하며 System.Data.SqlClient ADO.NET 2.0 데이터 공급자에 대한 래퍼로 구현됩니다.  
  
 샘플 공급자의 SQL 생성 모듈(DmlSqlGenerator.cs 파일을 제외하고 SQL Generation 폴더에 있음)은 DbQueryCommandTree 입력을 사용하고 단일 SQL SELECT 문을 생성합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 이 단원에 포함된 항목은 다음과 같습니다.  
  
 [아키텍처 및 디자인](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [연습: SQL 생성](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>참고 항목  
 [SQL 생성](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
