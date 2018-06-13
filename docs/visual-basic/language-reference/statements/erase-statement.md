---
title: Erase 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601795"
---
# <a name="erase-statement-visual-basic"></a>Erase 문(Visual Basic)
배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리 할당을 취소 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>요소  
 `arraylist`  
 필수. 지울 배열 변수 목록입니다. 여러 변수는 쉼표로 구분됩니다.  
  
## <a name="remarks"></a>설명  
 `Erase` 문을 프로시저 수준 에서만 사용할 수 있습니다. 즉, 배열을 프로시저 내의 하지만 클래스 또는 모듈 수준에 없는 해제할 수 있습니다.  
  
 `Erase` 문을 할당 같습니다 `Nothing` 각 배열 변수에 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Erase` 두 배열을 지우고 되 고 해당 메모리를 확보 문을 (1000 개 및 100 저장소 요소 각각). `ReDim` 그런 다음 문은 3 차원 배열에는 새 배열 인스턴스를 할당 합니다.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)
