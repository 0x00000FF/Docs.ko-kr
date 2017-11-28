---
title: "방법: 쿼리에 람다 식 사용(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ccc94b1932336ff4a6b1787304846114869400e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>방법: 쿼리에 람다 식 사용(C# 프로그래밍 가이드)
람다 식은 쿼리 구문에 직접 사용하지 않고 메서드 호출에 사용하며, 쿼리 식에 메서드 호출이 포함될 수 있습니다. 실제로 일부 쿼리 작업은 메서드 구문으로만 표현할 수 있습니다. 쿼리 구문과 메서드 구문 간의 차이점에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 표준 쿼리 연산자를 사용하여 메서드 기반 쿼리에 람다 식을 사용하는 방법을 보여 줍니다. 이 예제의 <xref:System.Linq.Enumerable.Where%2A> 메서드에는 대리자 형식 <xref:System.Func%601>의 입력 매개 변수가 있으며, 해당 대리자는 정수를 입력으로 사용하고 부울을 반환합니다. 람다 식을 해당 대리자로 변환할 수 있습니다. <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> 메서드를 사용하는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 쿼리인 경우 매개 변수 형식은 `Expression<Func\<int,bool>>`이지만 람다 식은 정확히 동일하게 표시됩니다. 식 형식에 대한 자세한 내용은 <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>을 참조하세요.  
  
 [!code-csharp[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 쿼리 식의 메서드 호출에 람다 식을 사용하는 방법을 보여 줍니다. 쿼리 구문을 사용하여 <xref:System.Linq.Enumerable.Sum%2A> 표준 쿼리 연산자를 호출할 수 없기 때문에 람다가 필요합니다.  
  
 쿼리는 먼저 `GradeLevel` 열거형에 정의된 성적 수준에 따라 학생을 그룹화합니다. 그런 다음 각 그룹에 대해 각 학생의 총 점수를 더합니다. 이 경우 두 개의 `Sum` 연산이 필요합니다. 안쪽 `Sum`은 각 학생의 총 점수를 계산하고, 바깥쪽 `Sum`은 그룹에 속한 모든 학생에 대해 합산된 누계를 유지합니다.  
  
 [!code-csharp[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 실행하려면 메서드를 복사하고 [방법: 개체 컬렉션 쿼리](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)에 제공된 `StudentClass`에 붙여넣은 다음 `Main` 메서드에서 호출합니다.  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [식 트리](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
