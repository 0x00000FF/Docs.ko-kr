---
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879439"
---
# <a name="where-entity-sql"></a>WHERE(Entity SQL)
WHERE 절 바로 다음에 적용 되는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) 절.  
  
## <a name="syntax"></a>구문  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 Boolean 형식입니다.  
  
## <a name="remarks"></a>설명  
 WHERE 절의 의미 체계는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에 대해 설명한 의미 체계와 같습니다. WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.  
  
```  
select c from cs as c where e  
```  
  
 식 `e`에는 부운 형식이 있어야 합니다.  
  
 WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다. FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
