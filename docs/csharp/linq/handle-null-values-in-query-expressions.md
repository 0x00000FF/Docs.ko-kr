---
title: "쿼리 식의 Null 값 처리"
description: "쿼리 식의 Null 값을 처리하는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: d16256e31b073a599504ffef6501ed34430a7694
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="handle-null-values-in-query-expressions"></a>쿼리 식의 Null 값 처리

이 예제에서는 소스 컬렉션에서 가능한 null 값을 처리하는 방법을 보여 줍니다. <xref:System.Collections.Generic.IEnumerable%601> 등의 개체 컬렉션에는 값이 [null](../language-reference/keywords/null.md)인 요소가 포함될 수 있습니다. 소스 컬렉션이 null이거나 값이 null인 요소를 포함하고 사용 중인 쿼리가 null 값을 처리하지 않는 경우 쿼리를 실행하면 <xref:System.NullReferenceException>이 throw됩니다.  
  
## <a name="example"></a>예제

 다음 예제와 같이 null 참조 예외를 피하도록 방어적으로 코딩할 수 있습니다.  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 이전 예제에서 `where` 절은 범주 시퀀스에서 모든 null 요소를 필터링합니다. 이 방법은 join 절의 null 확인과 관계가 없습니다. `Products.CategoryID`가 `Nullable<int>`의 축약형인 `int?` 형식이므로 이 예제에서는 null이 있는 조건식이 적용됩니다.  
  
## <a name="example"></a>예제

 join 절에서 비교 키 중 하나만 nullable 값 형식인 경우에는 쿼리 식에서 다른 키를 nullable 형식으로 캐스트할 수 있습니다. 다음 예제에서는 `EmployeeID`가 `int?` 형식의 값이 포함된 열이라고 가정합니다.  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Nullable%601>  
 [LINQ 쿼리 식](index.md)  
 [Nullable 형식](../programming-guide/nullable-types/index.md)
