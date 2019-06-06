---
title: CAST(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: 743c90cd9bc77a89051c59a217befa4275b28572
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489954"
---
# <a name="cast-entity-sql"></a>CAST(Entity SQL)
데이터 형식의 식을 다른 형식의 식으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 `data_type`으로 변환 가능한 유효한 식입니다.  
  
 `data_type`  
 대상 시스템 제공 데이터 형식입니다. 기본(스칼라) 형식이어야 합니다. 사용되는 `data_type` 은 쿼리 공간에 따라 달라집니다. 쿼리가 <xref:System.Data.EntityClient.EntityCommand>로 실행되는 경우 데이터 형식은 개념적 모델에 정의된 형식입니다. 자세한 내용은 [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)을 참조하십시오. 쿼리가 <xref:System.Data.Objects.ObjectQuery%601>로 실행되는 경우 데이터 형식은 CLR(공용 언어 런타임) 형식입니다.  
  
## <a name="return-value"></a>반환 값  
 `data_type`와 동일한 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 Cast 식은 Transact SQL 변환 식으로 유사한 의미 체계를 있습니다. CAST 식은 한 형식의 값을 다른 형식의 값으로 변환하는 데 사용됩니다.  
  
```  
CAST( e as T )  
```  
  
 e가 S 형식에 속하고 S가 T로 변환 가능한 경우, 위의 식은 유효한 CAST 식입니다. T는 기본(스칼라) 형식이어야 합니다.  
  
 전체 자릿수 및 소수 자릿수 패싯 값은 `Edm.Decimal`로 캐스팅할 때 선택 사항으로 제공할 수 있습니다. 전체 자릿수 및 소수 자릿수가 명시적으로 제공되지 않은 경우 기본값은 각각 18과 0입니다. 구체적으로 말하면 `Decimal`에 대해 다음 오버로드가 지원됩니다.  
  
- `CAST( d as Edm.Decimal );`  
  
- `CAST( d as Edm.Decimal(precision) );`  
  
- `CAST( d as Edm.Decimal(precision, scale) );`  
  
 CAST 식 사용은 명시적인 변환으로 간주되며, 명시적인 변환이 발생하면 데이터가 잘리거나 전체 자릿수가 손실될 수 있습니다.  
  
> [!NOTE]
>  CAST는 기본 형식 및 열거형 멤버 형식에 대해서만 지원됩니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 CAST 연산자를 사용하여 한 데이터 형식의 식을 다른 데이터 형식의 식으로 캐스팅합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. 절차에 따라 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
