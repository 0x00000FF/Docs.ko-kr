---
title: Sub 또는 Function이 정의되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349571"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub 또는 Function이 정의되지 않았습니다(Visual Basic).
`Sub` 또는 `Function`를 호출 하기 위해 정의 해야 합니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
- 프로시저 이름의 철자가 틀린 경우  
  
- **참조** 대화 상자에서 해당 프로젝트에 대 한 참조를 명시적으로 추가 하지 않고 다른 프로젝트에서 프로시저를 호출 하려고 합니다.  
  
- 호출 하는 프로시저에 표시 되지 않는 프로시저 지정  
  
- 지정 된 라이브러리 또는 코드 리소스에 없는 Windows DLL (동적 연결 라이브러리) 루틴 또는 Macintosh 코드 리소스 루틴을 선언 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 프로시저 이름의 철자가 정확한 지 확인 합니다.  
  
2. **참조** 대화 상자에서 호출 하려는 프로시저를 포함 하는 프로젝트의 이름을 찾습니다. 표시 되지 않으면 **찾아보기** 단추를 클릭 하 여 검색 합니다. 프로젝트 이름 왼쪽의 확인란을 선택 하 고 **확인**을 클릭 합니다.  
  
3. 루틴의 이름을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목

- [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
