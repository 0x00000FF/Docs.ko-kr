---
title: 사용자 정의 함수
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742707"
---
# <a name="user-defined-functions"></a>사용자 정의 함수
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델에 메서드를 사용하여 사용자 정의 함수를 제공합니다. 필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 함수로 지정합니다. 자세한 내용은 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)합니다.  
  
 <xref:System.InvalidOperationException>을 방지하려면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 사용자 정의 함수는 다음 폼 중 하나에 있어야 합니다.  
  
- 올바른 매핑 특성이 있는 메서드 호출로 래핑된 함수입니다. 자세한 내용은 [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 관련된 정적 SQL 메서드입니다.  
  
- .NET Framework 메서드에서 지원 되는 함수입니다.  
  
 이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 애플리케이션에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다. 일반적으로 개발자가 Visual Studio를 사용 하 여 사용자 정의 함수에 매핑할 개체 관계형 디자이너를 사용 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 스칼라 반환 사용자 정의 함수를 사용 합니다.](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 스칼라 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.  
  
 [방법: 테이블 반환 사용자 정의 함수 사용](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 표 값을 반환하는 함수를 구현하는 방법에 대해 설명합니다.  
  
 [방법: 사용자 정의 함수 인라인 호출](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 함수를 인라인 호출하는 방법과 인라인 호출을 통한 실행의 차이점에 대해 설명합니다.
