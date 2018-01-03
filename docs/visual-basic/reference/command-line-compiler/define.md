---
title: /define(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62669ec40803170cb623382b09472b82121d26bb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="define-visual-basic"></a>/define(Visual Basic)
조건부 컴파일러 상수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`symbol`|필수 요소. 정의할 기호입니다.|  
|`value`|선택 사항입니다. `symbol`을 할당할 값입니다. 경우 `value` 문자열이 백슬래시/따옴표 시퀀스로 묶어야 (\\") 따옴표 대신 합니다. 값을 지정하지 않으면 True가 지정됩니다.|  
  
## <a name="remarks"></a>설명  
 `/define` 옵션을 사용하는 경우의 결과는 소스 파일에서 `#Const` 전처리기 지시문을 사용하는 것과 비슷합니다. 단, `/define`으로 정의하는 상수는 공용 상수이며 프로젝트의 모든 파일에 적용된다는 차이점이 있습니다.  
  
 이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.  
  
 `/d`는 약식 `/define`입니다.  
  
 쉼표를 사용해 기호 정의를 구분하여 `/define`으로 여러 기호를 정의할 수 있습니다.  
  
|Visual Studio 통합 개발 환경에서 /define을 설정하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급**을 클릭합니다.<br />4.  값을 수정 된 **사용자 지정 상수** 상자입니다.|  
  
## <a name="example"></a>예  
 다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
