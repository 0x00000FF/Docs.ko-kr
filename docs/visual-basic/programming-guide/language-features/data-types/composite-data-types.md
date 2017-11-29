---
title: "복합 데이터 형식(Visual Basic)"
ms.custom: 
ms.date: 04/25/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e9adb407757dbee2f7ac5a94118623a62212faec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="composite-data-types-visual-basic"></a>복합 데이터 형식(Visual Basic)
기본 데이터 형식 뿐만 아니라 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 공급 장치, 수 조합 하 여 만들려는 다른 형식의 항목 *복합 데이터 형식* 클래스, 구조체 및 배열, 등입니다. 복합 데이터 형식 및 다른 복합 형식의 기본 형식에서 만들 수 있습니다. 예를 들어 배열 멤버가 포함 된 구조 요소, 배열 또는 구조를 정의할 수 있습니다.  
  
## <a name="data-types"></a>데이터 형식  
 복합 형식이의 각 구성 요소의 데이터 형식과 다른 경우 예를 들어 배열을 `Integer` 요소 아닙니다는 `Integer` 데이터 형식.  
  
 배열 데이터 형식이 일반적으로 요소 형식, 괄호 및 쉼표를 사용 하 여 필요에 따라 표시 됩니다. 예를 들어 1 차원 배열이 `String` 요소로 표시 됩니다 `String()`와의 2 차원 배열을 `Boolean` 요소로 표시 됩니다 `Boolean(,)`합니다.  
  
## <a name="structure-types"></a>구조체 형식  
 모든 구조를 포함 하는 단일 데이터 형식은 없습니다. 대신, 구조체의 각 정의 두 개의 구조 동일한 순서로 동일한 요소를 정의 하는 경우에 고유한 데이터 형식을 나타냅니다. 그러나 동일한 구조를 두 개 이상의 인스턴스를 만드는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식이 동일한 것으로 간주 합니다.  
  
## <a name="tuples"></a>튜플

튜플은 그 형식은 미리 정의 된 두 개 이상의 필드를 포함 하는 간단한 구조입니다. 튜플은 Visual Basic 2017부터 사용할 수 있습니다. 튜플 참조로 인수를 전달할 필요가 또는 더 복잡 클래스 또는 구조체에 반환 되는 필드를 패키징 없이 단일 메서드 호출에서 여러 값을 반환 하려면 가장 일반적으로 사용 됩니다. 참조는 [튜플](tuples.md) 튜플에 대 한 자세한 내용은 항목입니다.

## <a name="array-types"></a>배열 형식  
 모든 배열을 포함 하는 단일 데이터 형식은 없습니다. 데이터 형식의 배열의 특정 인스턴스는 다음에 의해 결정 됩니다.  
  
-   배열 이라는 사실  
  
-   배열의 차수 (차원 수)  
  
-   배열의 요소 형식  
  
 특히, 지정 된 차원의 길이 인스턴스의 데이터 형식의 일부가 아닙니다. 다음은 이에 대한 예입니다.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 앞의 예제에서 배열 변수 `arrayA` 및 `arrayB` 동일한 데이터 형식으로 간주 됩니다- `Byte()` -길이가 서로 다른 초기화 하는 경우에 합니다. 변수 `arrayB` 및 `arrayC` 는 해당 요소 형식이 다른 동일한 형식이 아닙니다. 변수 `arrayC` 및 `arrayD` 는 차수가 다른 동일한 형식이 아닙니다. 변수 `arrayD` 및 `arrayE` 유형이 다르므로- `Short(,)` -같기 때문에 차수 및 요소 형식, 경우에 `arrayD` 아직 초기화 되지 않았습니다.  
  
 배열에 대 한 자세한 내용은 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="class-types"></a>클래스 형식  
 모든 클래스를 포함 하는 단일 데이터 형식은 없습니다. 하나의 클래스 다른 클래스에서 상속할 수 있지만 각각 별도 데이터 형식입니다. 동일한 클래스의 여러 인스턴스는 동일한 데이터 형식입니다. 다른 클래스 인스턴스 변수를 할당 하는 경우 뿐 아니라 동일한 데이터 형식이 서로, 메모리의 동일한 클래스 인스턴스를 가리키는지 합니다.  
  
 클래스에 대 한 자세한 내용은 참조 하십시오. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [방법: 변수에 두 개 이상의 값 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
