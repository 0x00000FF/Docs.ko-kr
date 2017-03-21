---
title: "쿼리 작업 (Visual Basic)의 형식 관계 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a966b69feca7a7021cafbccb7971913ea781c479
ms.lasthandoff: 03/13/2017

---
# <a name="type-relationships-in-query-operations-visual-basic"></a>쿼리 작업의 형식 관계(Visual Basic)
사용 되는 변수 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 쿼리 작업은 강력한 형식 및 서로 호환 되어야 합니다. 강력한 형식 지정 데이터 원본, 쿼리 자체 및 쿼리 실행에 사용 됩니다. 다음 그림에 설명 하는 데 사용 되는 용어를 식별 하는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 합니다. 쿼리의 부분에 대 한 자세한 내용은 참조 [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)합니다.  
  
 ![요소가 강조 표시 된 의사 코드 쿼리 합니다.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
LINQ 쿼리  
  
 쿼리에서 범위 변수의 종류는 데이터 원본에 있는 요소의 형식과 호환 되어야 합니다. 쿼리 변수의 형식에 정의 된 시퀀스 요소와 호환 되어야 합니다.는 `Select` 절. 마지막으로, 시퀀스 요소의 형식 되어야 합니다 루프 제어 변수에서 사용 되는 변수의 형식과 호환 되는 `For Each` 쿼리를 실행 하는 문입니다. 이 강력한 형식을 지정 하면 컴파일 시 형식 오류 식별을 용이해 집니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]사용 하면 강력한 형식 지정 편리한 라고도 지역 형식 유추를 구현 하 여 *암시적 형식 지정*합니다. 기능은 이전 예제에서 사용 하 고 전체에서 사용이 표시 됩니다는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 샘플 및 설명서입니다. Visual basic에서는 지역 형식 유추를 사용 하 여 간단히 이루어집니다는 `Dim` 없이 문을 `As` 절. 다음 예에서 `city` 강력한 형식의 문자열입니다.  
  
 [!code-vb[VbLINQTypeRels #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  경우에만 작동 하는 지역 형식 유추 `Option Infer` 로 설정 된 `On`합니다. 자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)합니다.  
  
 그러나 쿼리에서 지역 형식 유추를 사용 하는 경우에 동일한 형식 관계는 데이터 원본에서 변수, 쿼리 변수 및 쿼리 실행 루프 간에. 작성 하는 때는 이러한 형식 관계에 대 한 기본적인 이해 하는 것이 유용 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 또는 샘플 및 설명서의 코드 예제를 사용 합니다.  
  
 데이터 소스에서 반환 되는 형식 일치 하지 않는 범위 변수에 대 한 명시적 형식을 지정 해야 할 수도 있습니다. 사용 하 여 범위 변수의 종류를 지정할 수는 `As` 절. 그러나이 인해 오류가 변환 되 면는 [축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 `Option Strict` 로 설정 된 `On`합니다. 따라서 데이터 원본에서 검색 된 값에는 변환을 수행 하도록 하는 것이 좋습니다. 사용 하 여 명시적 범위 변수 형식으로 값은 데이터 소스에서 변환할 수는 <xref:System.Linq.Enumerable.Cast%2A>메서드.</xref:System.Linq.Enumerable.Cast%2A> 선택한 값으로 캐스팅할 수도 있습니다는 `Select` 절을 명시적 형식으로 된 범위 변수의 형식과 다릅니다. 이러한 요소는 다음 코드에 나와 있습니다.  
  
 [!code-vb[VbLINQTypeRels #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>원본 데이터의 전체 요소를 반환 하는 쿼리  
 다음 예제는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 원본 데이터에서 선택 된 요소의 시퀀스를 반환 하는 작업입니다. 소스, `names`, 문자열의 배열을 포함 및 쿼리 출력은 M으로 시작 하는 문자열을 포함 하는 시퀀스입니다.  
  
 [!code-vb[VbLINQTypeRels #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 다음 코드와 동일한 이지만이 훨씬 간단 하 고 더 쉽게 작성할 수 있습니다. 쿼리에서 지역 형식 유추에 대 한 의존성은 Visual Basic의 기본 스타일입니다.  
  
 [!code-vb[VbLINQTypeRels #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 형식은 암시적 또는 명시적으로 결정 됩니다 없이 모두 사용 하는 이전 코드 예제에 다음과 같은 관계가 있습니다.  
  
1.  데이터 원본에 있는 요소의 형식 `names`, 범위 변수의 형식이 `name`, 쿼리에서 합니다.  
  
2.  현재 선택 된 개체의 형식 `name`, 쿼리 변수의 형식을 결정 `mNames`합니다. 여기 `name` 는 문자열로, 쿼리 변수는 Visual Basic에서 IEnumerable (Of String).  
  
3.  에 정의 된 쿼리 `mNames` 에서 실행 되는 `For Each` 루프입니다. 루프는 쿼리 실행의 결과 반복 합니다. 때문에 `mNames`실행 될 때, 루프 반복 변수 문자열의 시퀀스를 반환 합니다 `nm`, 또한는 문자열입니다.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>선택한 요소에서 한 필드를 반환 하는 쿼리  
 다음 예제는 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 쿼리 데이터 원본에서 선택한 각 요소에의 한 부분을 포함 하는 시퀀스를 반환 하는 작업입니다. 컬렉션을 사용 하는 쿼리 `Customer` 데이터 원본으로 개체를 프로젝트에는 `Name` 결과의 속성입니다. 고객 이름은 문자열 이므로 쿼리 출력으로 문자열의 시퀀스를 생성 합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 변수 간의 관계는 간단한 예제에서와 같이 됩니다.  
  
1.  데이터 원본에 있는 요소의 형식 `customers`, 범위 변수의 형식이 `cust`, 쿼리에서 합니다. 이 예제에서는 유형이 `Customer`합니다.  
  
2.  `Select` 문에서 반환 된 `Name` 각 속성 `Customer` 개체 전체가 아니라 개체입니다. 때문에 `Name` 는 문자열로, 쿼리 변수 `custNames`, 다시 됩니다 IEnumerable (Of String)의 `Customer`합니다.  
  
3.  때문에 `custNames` 문자열의 시퀀스를 나타내는 `For Each` 루프의 반복 변수 `custName`, 문자열 이어야 합니다.  
  
 지역 형식 유추 하지 않고 앞의 예제를 작성 하 고 다음 예제와 같이 이해 하기에 다소 복잡 해질 것입니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="queries-that-require-anonymous-types"></a>익명 형식이 필요로 하는 쿼리  
 다음 예제에서는 좀 더 복잡 한 경우를 보여 줍니다. 앞의 예제에서 모든 변수 형식을 명시적으로 지정 하는 편리한 방법이 없었습니다. 이 예제에서는 불가능 합니다. 전체를 선택 하는 대신 `Customer` 데이터 원본 또는 각 요소에서 단일 필드에서 요소는 `Select` 원래의 두 가지 속성을 반환 하는 절이 쿼리에 `Customer` 개체: `Name` 및 `City`합니다. 에 대 한 응답은 `Select` 절 컴파일러가 이러한 두 속성을 포함 하는 익명 형식을 정의 합니다. 실행 한 결과 `nameCityQuery` 에 `For Each` 루프는 새 익명 형식의 인스턴스 컬렉션입니다. 형식을 지정할 수 없습니다 익명 형식에 사용할 수 있는 이름이 없으므로, `nameCityQuery` 또는 `custInfo` 명시적으로 합니다. 즉, 익명 형식을 사용 하면 형식 이름이 없습니다 대신 사용 하 여 `String` 에서 `IEnumerable(Of String)`합니다. 자세한 내용은 참조 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 이전 예제에서 모든 변수 형식을 지정할 수는 아니지만 관계가 그대로 유지 됩니다.  
  
1.  데이터 소스에 있는 요소의 형식은 쿼리에서 범위 변수의 형식을 다시 합니다. 이 예제에서는 `cust` 의 인스턴스가 `Customer`합니다.  
  
2.  때문에 `Select` 문은 쿼리 변수 익명 형식을 생성 `nameCityQuery`, 익명 형식으로 암시적으로 형식화 되어야 합니다. 익명 형식에 사용할 수 있는 이름이 없는 고 따라서 명시적으로 지정할 수 없습니다.  
  
3.  반복 변수 유형의 `For Each` 루프는 2 단계에서 만든 익명 형식입니다. 형식 이름이 없기 때문에 사용할 수 있는, 루프 반복 변수의 형식은 암시적으로 결정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)
