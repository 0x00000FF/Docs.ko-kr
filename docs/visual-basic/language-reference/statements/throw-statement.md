---
title: Throw 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: c17adc6df0f8cf94f06547b48a32b2ffb8f303ca
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973485"
---
# <a name="throw-statement-visual-basic"></a>Throw 문(Visual Basic)
프로시저 내에서 예외가 throw 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>파트  
 `expression`  
 예외를 throw 하는 방법에 대 한 정보를 제공 합니다. 에 있는 경우 선택 사항는 `Catch` 필요한 문입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `Throw` 구조적 예외 처리 코드로 처리할 수 있는 예외를 throw 하는 문 (`Try`... `Catch`... `Finally`) 또는 구조화 되지 않은 예외 처리 코드 (`On Error GoTo`). 사용할 수는 `Throw` Visual Basic에서는 적절 한 예외 처리 코드를 찾을 때까지 호출 스택 위로 이동 하므로 코드 내에서 오류를 트래핑 하는 문입니다.  
  
 `Throw` 문 식 에서만 사용할 수 있습니다를 `Catch` 문의 경우는에서 현재 처리 중인 예외를 다시 throw 문을 `Catch` 문입니다.  
  
 `Throw` 문에 대 한 호출 스택을 다시 설정 된 `expression` 예외입니다. 경우 `expression` 호출 스택을 제공 하지 않으면 그대로 유지 됩니다. 통해 예외에 대 한 호출 스택을 액세스할 수 있습니다는 <xref:System.Exception.StackTrace%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Throw` 문은 예외를 throw 합니다.  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a>요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:** `Interaction`  
  
 **어셈블리:** Visual Basic 런타임 라이브러리(Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>참고자료
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)
