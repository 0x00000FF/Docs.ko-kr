---
title: LINQ to SQL의 보안
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 96951b3b3c8a6ee93a83ba24f6c6a19c3e36381c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="security-in-linq-to-sql"></a>LINQ to SQL의 보안
데이터베이스에 연결할 때는 항상 보안 위험이 따릅니다. LINQ to SQL에서는 SQL Server에서 데이터를 사용하는 여러 가지 새로운 방법을 제공하지만 추가적인 보안 메커니즘은 지원하지 않습니다.  
  
## <a name="access-control-and-authentication"></a>액세스 제어 및 인증  
 LINQ to SQL에는 고유의 사용자 모델이나 인증 메커니즘이 없으므로 SQL Server 보안을 사용하여 개체 모델에 매핑되는 데이터베이스, 데이터베이스 테이블, 뷰 및 저장 프로시저에 대한 액세스를 제어해야 합니다. 또한 사용자에게 필수적인 액세스 권한만 최소한으로 부여하고 사용자 인증을 위한 강력한 암호를 설정하도록 요청하세요.  
  
## <a name="mapping-and-schema-information"></a>매핑 및 스키마 정보  
 개체 모델 또는 외부 매핑 파일의 SQL-CLR 형식 매핑 및 데이터베이스 스키마 정보를 사용하여 파일 시스템의 파일에 액세스할 수 있습니다. 개체 모델 또는 외부 매핑 파일에 액세스할 수 있는 모든 사용자가 이러한 스키마 정보를 확인할 수 있다고 가정해 보세요. 스키마 정보에 아무나 액세스하지 않도록 제한하려면 파일 보안 메커니즘을 사용하여 소스 파일 및 매핑 파일을 보호해야 합니다.  
  
## <a name="connection-strings"></a>연결 문자열  
 가능하면 연결 문자열에 암호를 사용하지 않아야 합니다. 개체 관계형 디자이너 또는 SQLMetal 명령줄 도구를 사용하는 경우 연결 문자열은 자체적으로 보안 위험 요소일 뿐 아니라 개체 모델 또는 외부 매핑 파일에 일반 텍스트로 추가될 수도 있습니다. 따라서 파일 시스템을 통해 개체 모델 또는 외부 매핑 파일에 액세스할 수 있는 사용자는 누구든지 연결 문자열에 포함된 연결 암호를 볼 수 있습니다.  
  
 이러한 위험을 최소화 하려면 SQL Server와 함께 신뢰할 수 있는 연결을 통합된 보안을 사용 합니다. 이러한 접근 방식을 사용하면 연결 문자열에서 암호를 저장하지 않아도 됩니다. 자세한 내용은 참조 [SQL Server 보안](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md)합니다.  
  
 통합 보안을 사용하지 않는 경우에는 연결 문자열에 일반 텍스트 암호를 사용해야 합니다. 연결 문자열을 보호하는 가장 좋은 방법은 다음과 같습니다. 아래 항목은 위험 수준에 따라 오름차순으로 나열되어 있습니다.   
  
-   통합 보안을 사용합니다.  
  
-   암호를 사용하여 연결 문자열을 보호하고 연결 문자열의 경유를 최소화합니다.  
  
-   연결 문자열 대신 노출 기간이 제한되는 <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> 클래스를 사용합니다. <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>을 사용하여 LINQ to SQL <xref:System.Data.SqlClient.SqlConnection> 클래스를 인스턴스화할 수 있습니다.  
  
-   모든 연결 문자열의 수명과 접근할 수 있는 지점을 최소화합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [질문과 대답](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
