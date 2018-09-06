---
title: Skip While 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: a3c0749560d8cea1e46d96298347ce54f0bf9185
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863376"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 절(Visual Basic)
지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`expression`|필수. 에 대 한 요소를 테스트 하는 조건을 나타내는 식입니다. 식을 반환 해야 합니다는 `Boolean` 값 또는 이와 동일한 기능 같은 `Integer` 으로 계산 되는 `Boolean`합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `Skip While` 일까 지 제공 된 쿼리 결과의 시작 부분에서 요소를 무시 하는 절 `expression` 반환 `false`합니다. 이후에 `expression` 반환 `false`, 나머지 모든 요소를 반환 하는 쿼리. `expression` 나머지 결과 대해 무시 됩니다.  
  
 `Skip While` 절에서 다른 합니다 `Where` 절에는 `Where` 특정 조건을 충족 하지 않는 쿼리에서 모든 요소를 제외 하려면 절을 사용할 수 있습니다. `Skip While` 절 조건이 충족 되지 않은 첫 번째 시간 까지만 요소를 제외 합니다. `Skip While` 절은 순서가 지정 된 쿼리 결과 사용 하 여 작업할 때 가장 유용 합니다.  
  
 특정 수의 쿼리 결과의 시작 부분에서 결과 사용 하 여 무시할 수 있습니다는 `Skip` 절.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Skip While` 절 미국에서 첫 번째 고객을 찾을 때까지 결과를 건너뜁니다.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
