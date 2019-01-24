---
title: Nullable 값 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 522526392dd12ede729fe8b96677029c05af57c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665697"
---
# <a name="nullable-value-types-visual-basic"></a>Nullable 값 형식(Visual Basic)
경우에 따라 특정 상황에서 정의 된 값이 없는 값 형식을 사용 하 여 작업할 수도 있습니다. 예를 들어 데이터베이스의 필드 구분 하기 위해 의미 있는 있는 할당 된 값이 있는 할당된 된 값 없는 한 있을 수 있습니다. 값 형식 매개 변수 정상 값 또는 null 값을 확장할 수 있습니다. 이러한 확장은 호출을 *nullable 형식*합니다.  
  
 Nullable 형식에 각 제네릭에서 생성 되 <xref:System.Nullable%601> 구조입니다. 데이터베이스를 작업 관련 작업을 추적 하는 것이 좋습니다. 다음 예제에서는 null을 허용 생성 `Boolean` 형식과 해당 형식의 변수를 선언 합니다. 세 가지 방법으로 선언을 작성할 수 있습니다.  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 변수의 `ridesBusToWork` 의 값을 보유할 수 `True`, 값 `False`, 또는 모두에 값이 없습니다. 초기 기본값은 값에는 예에서 것을 의미할 수도이 사용자에 대 한 정보를 아직 획득 하지. 반면, `False` 가져온 정보를 사용자 버스로 작동 하지 않는 의미할 수 있습니다.  
  
 Nullable 형식의 변수 및 속성을 선언할 수 있습니다 하 고 nullable 형식의 요소가 있는 배열을 선언할 수 있습니다. 프로시저 매개 변수로 null 허용 형식으로 선언할 수 있으며에서 nullable 형식을 반환할 수 있습니다는 `Function` 프로시저입니다.  
  
 배열 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다. 한 `String`, 또는 클래스. 기본 형식이 값 형식 이어야 합니다. 자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.  
  
## <a name="using-a-nullable-type-variable"></a>Nullable 형식 변수를 사용 하 여  
 Nullable 형식의 가장 중요 한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A> 고 <xref:System.Nullable%601.Value%2A> 속성입니다. Nullable 형식의 변수에 대 한 <xref:System.Nullable%601.HasValue%2A> 변수에 정의 된 값을 포함 하는 여부를 알려 줍니다. 하는 경우 <xref:System.Nullable%601.HasValue%2A> 됩니다 `True`에서 값을 읽을 수 있습니다 <xref:System.Nullable%601.Value%2A>합니다. 둘 다 <xref:System.Nullable%601.HasValue%2A> 하 고 <xref:System.Nullable%601.Value%2A> 는 `ReadOnly` 속성입니다.  
  
### <a name="default-values"></a>기본값  
 Nullable 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False`합니다. 이 기본적으로 변수에 정의 된 값이 없으며 기본 값 형식의 기본값 대신 의미 합니다. 다음 예에서 변수 `numberOfChildren` 처음에 정의 된 값이 없으며도의 기본값은 `Integer` 형식은 0입니다.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 Null 값이 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다. 하는 경우 `numberOfChildren` 로 선언 `Integer`, 정보를 현재 사용할 수 없는 나타낼 수 있는 값이 표시 됩니다.  
  
### <a name="storing-values"></a>값 저장  
 일반적인 방식으로 변수 또는 nullable 형식의 속성에 값을 저장 합니다. 다음 예제에서는 값을 변수에 할당 `numberOfChildren` 이전 예제의 선언 합니다.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 변수 또는 nullable 형식의 속성에 정의 된 값이 있으면 해당 하지 않는 경우 할당 된 값의 초기 상태로 되돌리려면 발생할 수 있습니다. 변수 또는 속성을 설정 하 여이 작업을 수행 `Nothing`다음 예제와 같이 합니다.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  할당할 수 있지만 `Nothing` nullable 형식의 변수에 대해 테스트할 수 없습니다 있습니다 `Nothing` 등호를 사용 하 여 합니다. 등호를 사용 하는 비교 `someVar = Nothing`를 항상 평가 `Nothing`합니다. 변수를 테스트할 수 있습니다 <xref:System.Nullable%601.HasValue%2A> 속성에 대 한 `False`, 또는 사용 하 여 테스트 합니다 `Is` 또는 `IsNot` 연산자입니다.  
  
### <a name="retrieving-values"></a>값 검색  
 Nullable 형식의 변수 값을 검색 하려면 먼저을 테스트 해야 해당 <xref:System.Nullable%601.HasValue%2A> 속성 값이 있는지 확인 합니다. 값을 읽을 하려고 하면 때 <xref:System.Nullable%601.HasValue%2A> 됩니다 `False`, Visual Basic throw는 <xref:System.InvalidOperationException> 예외입니다. 다음 예제에서는 변수를 읽을 수 있는 좋은 `numberOfChildren` 앞의 예제입니다.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a>Nullable 형식 비교  
 Null을 허용 하는 경우 `Boolean` 변수는 부울 식에 사용 되 고, 표시 될 수 있습니다 `True`하십시오 `False`, 또는 `Nothing`합니다. 다음은 한 진리표 `And` 고 `Or`입니다. 때문에 `b1` 및 `b2` 이제 다음 3 가지 가능한 값인 9 조합을 평가 해야 합니다.  
  
|b1|b2|b1 및 b2|b1 또는 b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 부울 변수 또는 식의 값이 `Nothing`를 둘 다를 것 `true` 도 `false`합니다. 다음 예제를 살펴보십시오.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 이 예에서 `b1 And b2` 로 `Nothing`합니다. 결과적으로 `Else` 각 절이 실행 `If` 문과 출력은 다음과 같습니다.  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` 및 `OrElse`를 사용 하는 평가 단락 (short-circuit) 계산 되어야 합니다 두 번째 피연산자를 첫 번째 평가 되 면 `Nothing`합니다.  
  
## <a name="propagation"></a>전파  
 하나 또는 두 피연산자는 산술, 비교, 시프트 또는 형식 작업의 nullable 인 경우 작업의 결과 nullable 이기도 합니다. 두 피연산자 모두 값이 없는 경우 `Nothing`, 작업을 둘 다 있는 것 처럼 기본 피연산자 값에 수행할는 nullable 형식입니다. 다음 예에서 변수 `compare1` 고 `sum1` 를 암시적으로 형식화 합니다. 위로 마우스 포인터를 놓으면 컴파일러는 둘 다에 대 한 nullable 형식 유추는 표시 메시지가 표시 됩니다.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 하나 또는 두 피연산자의 값이 있어야 하는 경우 `Nothing`에 반환 됩니다 `Nothing`합니다.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a>데이터를 사용 하 여 Nullable 형식 사용  
 데이터베이스는 null 허용 형식을 사용 하 여 가장 중요 한 위치 중 하나입니다. 일부 데이터베이스 개체에는 현재 nullable 형식 지원 않지만 테이블 디자이너에서 생성 된 어댑터입니다. "TableAdapter Nullable 형식 지원"을 참조 하세요 [TableAdapter 개요](/visualstudio/data-tools/tableadapter-overview)합니다.
  
## <a name="see-also"></a>참고자료
- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Nullable 형식 사용](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [TableAdapter 개요](/visualstudio/data-tools/tableadapter-overview)
- [If 연산자](../../../../visual-basic/language-reference/operators/if-operator.md)
- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)
