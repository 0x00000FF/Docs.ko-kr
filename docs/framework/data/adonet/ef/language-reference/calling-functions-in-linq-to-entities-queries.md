---
title: LINQ to Entities 쿼리에서 함수 호출
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 6fa1a7204a91a62c30e8683c449cc2be44132b4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605784"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>LINQ to Entities 쿼리에서 함수 호출
이 단원의 항목에서는 LINQ to Entities 쿼리에서 함수를 호출하는 방법에 대해 설명합니다.  
  
 <xref:System.Data.Objects.EntityFunctions> 및 <xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스를 사용하여 Entity Framework의 일부인 정식 함수와 데이터베이스 함수에 액세스할 수 있습니다. 자세한 내용은 [방법: 정식 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) 고 [방법: 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)합니다.  
  
 사용자 지정 함수를 호출하는 과정은 다음의 기본적인 세 단계로 이루어집니다.  
  
1. 개념적 모델에서 함수를 정의하거나 스토리지 모델에서 함수를 선언합니다.  
  
2. 애플리케이션에 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 모델의 함수에 매핑합니다.  
  
3. LINQ to Entities 쿼리에서 함수를 호출합니다.  
  
 자세한 내용은 이 단원의 해당 항목을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 정식 함수를 호출 합니다.](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [방법: 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [방법: 사용자 지정 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [방법: 쿼리에서 모델 정의 함수를 호출 합니다.](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [방법: 개체 메서드로 모델 정의 함수를 호출 합니다.](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>참고자료

- [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
- [.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [방법: 개념적 모델의 사용자 지정 함수 정의](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
