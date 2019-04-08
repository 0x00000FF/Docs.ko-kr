---
title: GoTo 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: c4dd249620ba1bf445642ce4600498f6beb30461
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827772"
---
# <a name="goto-statement"></a>GoTo 문
프로시저에 지정된 된 줄으로 무조건 분기 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
GoTo line  
```  
  
## <a name="part"></a>파트  
 `line`  
 필수 요소. 모든 줄 레이블을 합니다.  
  
## <a name="remarks"></a>설명  
 `GoTo` 문은 나타나는 프로시저의 줄에만 분기할 수 있습니다. 줄에 있는 줄 레이블이 있어야 `GoTo` 참조할 수 있습니다. 자세한 내용은 [방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.  
  
> [!NOTE]
>  `GoTo` 문을 코드를 읽고 관리 하기 어려울 수 있습니다. 가능 하면 제어 구조를 대신 사용 합니다. 자세한 내용은 [제어 흐름](../../../visual-basic/programming-guide/language-features/control-flow/index.md)합니다.  
  
 사용할 수 없습니다는 `GoTo` 문 외부에서 분기를 `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, 또는 `Using`... `End Using` 안에 레이블 생성 합니다.  
  
## <a name="branching-and-try-constructions"></a>분기 및 생성을 시도  
 내는 `Try`... `Catch`... `Finally` 생성을 사용 하 여 분기 다음 규칙이 적용 된 `GoTo` 문.  
  
|블록 또는 지역|외부에서 분기|내부에서 외부로 분기|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` 블록|만 `Catch` 동일한 생성 블록 <sup>1</sup>|에 전체 구문의 외부|  
|`Catch` 블록|허용 되지|에 전체 구문의 외부 또는 합니다 `Try` 동일한 생성 블록 <sup>1</sup>|  
|`Finally` 블록|허용 되지|허용 되지|  
  
 <sup>1</sup> 없으면 `Try`... `Catch`... `Finally` 생성 다른 내에 중첩 되어를 `Catch` 블록으로 분기할 수는 `Try` 자체 중첩 수준에 포함 되지 않습니다 다른 블록 `Try` 블록입니다. 중첩 된 `Try`... `Catch`... `Finally` 생성에 완전히 포함 되어야 합니다는 `Try` 또는 `Catch` 중첩 되는 생성 블록입니다.  
  
 다음 그림에 나와 하나 `Try` 다른 내에 중첩 된 생성 합니다. 두 구문의 블록 간에 다양 한 분기 잘못 되었거나 잘못 되었습니다.으로 표시 됩니다.  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>예제  
 다음 예제에서는 `GoTo` 문을 프로시저의 줄 레이블로 분기 합니다.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>참고자료

- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With 문](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
