---
title: "GUID 및 uniqueidentifier 값 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4cadc6af85c833013ac56399ae0821731dbf2d41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>GUID 및 uniqueidentifier 값 비교
SQL Server의 GUID(Globally Unique Identifier) 데이터 형식은 16바이트 이진 값을 저장하는 `uniqueidentifier` 데이터 형식으로 표현됩니다. GUID는 이진수이며 주로 여러 사이트에 많은 컴퓨터를 가지고 있는 네트워크에서 고유해야 하는 식별자로 사용됩니다. GUID는 Transact-SQL NEWID 함수를 호출하여 생성되며 전체 영역에서 고유성이 보장됩니다. 자세한 내용은 SQL Server 온라인 설명서의 "Using uniqueidentifier Data"를 참조하세요.  
  
## <a name="working-with-sqlguid-values"></a>SqlGuid 값 사용  
 GUID 값은 길고 모호하기 때문에 사용자가 의미를 이해하기가 어렵습니다. 임의로 생성된 GUID를 키 값에 사용하고 많은 행을 삽입하면 인덱스에 임의의 I/O가 발생하여 성능에 좋지 않은 영향을 줄 수 있습니다. GUID는 또한 다른 데이터 형식에 비해 비교적 큰 편입니다. 일반적으로 GUID는 적절한 데이터 형식이 없는 매우 특수한 상황에만 사용하는 것이 좋습니다.  
  
### <a name="comparing-guid-values"></a>GUID 값 비교  
 `uniqueidentifier` 값에는 비교 연산자를 사용할 수 있습니다. 그러나 두 값의 비트 패턴을 비교하면 정렬이 구현되지 않습니다. 연산만 대해 허용 되는 `uniqueidentifier` 값은 비교 (=, <>, \<, >, \<=, > =) 및 NULL (IS NULL 및 IS NOT NULL) 검사 합니다. 다른 산술 연산자는 허용되지 않습니다.  
  
 <xref:System.Guid> 및 <xref:System.Data.SqlTypes.SqlGuid>에는 서로 다른 GUID 값을 비교하기 위한 `CompareTo` 메서드가 있습니다. 그러나 `System.Guid.CompareTo` 및 `SqlTypes.SqlGuid.CompareTo`는 구현 방식이 서로 다릅니다. <xref:System.Data.SqlTypes.SqlGuid>는 값의 마지막 6바이트가 가장 중요한 SQL Server 동작을 사용하여 `CompareTo`를 구현합니다. <xref:System.Guid>는 16바이트를 모두 계산합니다. 다음 예제에서는 이러한 동작의 차이를 보여 줍니다. 코드의 첫 번째 부분에서는 정렬되지 않은 <xref:System.Guid> 값을 보여 주며, 두 번째 부분에는 정렬된 <xref:System.Guid> 값이 나와 있습니다. 세 번째 부분에서는 정렬된 <xref:System.Data.SqlTypes.SqlGuid> 값을 보여 줍니다. 출력은 코드 목록 아래에 표시되어 있습니다.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 데이터 형식 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
