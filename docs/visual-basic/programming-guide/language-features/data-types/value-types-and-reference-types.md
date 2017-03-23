---
title: "값 형식과 참조 형식이 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: de8016b4b2a5550b32373a41c89a484fa996c596
ms.lasthandoff: 03/13/2017

---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
Visual Basic의 데이터 형식은 분류에 따라 구현 됩니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 특정 형식의 변수는 자체 데이터 또는 데이터에 대 한 포인터를 저장 하는 여부에 따라 분류할 수 있습니다. 자체 데이터를 저장 하는 경우는 *값 형식*는 메모리의 다른 위치에서 데이터에 대 한 포인터를 보유 하는 경우는 *참조 형식*합니다.  
  
## <a name="value-types"></a>값 형식  
 데이터 형식은 *값 형식* 자신의 메모리 할당 내에서 데이터를 보유 하는 경우. 값 형식은 다음과 같습니다.  
  
-   모든 숫자 데이터 형식  
  
-   `Boolean`, `Char` 및 `Date`  
  
-   해당 멤버는 참조 형식인 경우에 모든 구조  
  
-   열거형의 내부 형식이 항상 이므로 `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, 또는`ULong`  
  
 모든 구조체는 값 형식에는 참조 형식 멤버를 포함 하는 경우에 합니다. 이러한 이유로 값과 같은 형식이 `Char` 및 `Integer` .NET Framework 구조에 의해 구현 됩니다.  
  
 예를 들어, 예약 된 키워드를 사용 하 여 값 형식을 선언할 수 `Decimal`합니다. 사용할 수도 있습니다는 `New` 값 형식을 초기화 하는 키워드입니다. 형식 매개 변수를 사용 하는 생성자에 경우에 특히 유용 합니다. 이 작업의 예로 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>새 작성 하는 생성자가 `Decimal` 는 지정 된 부분에서 값.</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>  
  
## <a name="reference-types"></a>참조 형식  
 A *참조 형식* 데이터를 보유 하는 다른 메모리 위치에 대 한 포인터를 포함 합니다. 참조 형식은 다음과 같습니다.  
  
-   `String`  
  
-   모든 배열의 해당 요소는 값 형식 하는 경우에  
  
-   와 같은 클래스 형식<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form>  
  
-   대리자  
  
 클래스는 한 *참조 형식*합니다. 이러한 이유로 같은 참조 형식이 `Object` 및 `String` 에서 지 원하는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스입니다. 않음을 유의 하십시오 모든 배열은 참조 형식에서 해당 멤버 값 형식의 경우에 합니다.  
  
 사용 해야 모든 참조 형식에는 기본.NET Framework 클래스를 나타내므로 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 초기화 합니다. 다음 문은 배열을 초기화합니다.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>형식 없는 요소  
 그 중 하나에서 선언 된 요소에 대 한 데이터 형식으로 지정할 수 없으므로 다음 프로그래밍 요소 형식으로 적합 하지 않습니다.  
  
-   네임스페이스  
  
-   모듈  
  
-   이벤트  
  
-   속성 및 프로시저  
  
-   변수, 상수 및 필드  
  
## <a name="working-with-the-object-data-type"></a>개체 데이터 형식 사용  
 참조 형식 또는 값 형식 변수에 할당할 수 있습니다는 `Object` 데이터 형식입니다. `Object` 항상 변수 데이터를 데이터 자체에 대 한 포인터를 가집니다. 그러나 값 형식이을 할당 하는 경우는 `Object` 변수인 것 처럼 동작 자체 데이터를 보유 합니다. 자세한 내용은 참조 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.  
  
 하는지를 알 수 있습니다는 `Object` 변수 역할을 하는 참조 형식 또는 값 형식을 전달 하 여는 <xref:Microsoft.VisualBasic.Information.IsReference%2A>에서 메서드는 <xref:Microsoft.VisualBasic.Information>의 클래스는 <xref:Microsoft.VisualBasic?displayProperty=fullName>네임 스페이스.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A> <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>반환 `True` 경우의 콘텐츠는 `Object` 참조 형식 변수를 나타냅니다.</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>참고 항목  
 [Nullable 값 형식](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [데이터 형식의 효율적 사용](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
