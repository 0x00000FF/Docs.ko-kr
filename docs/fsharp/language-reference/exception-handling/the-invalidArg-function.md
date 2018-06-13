---
title: '예외: invalidArg 함수(F#)'
description: "F # 'invalidArg' 함수에서 인수 예외를 생성 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 43e1b6f3f36774ac50aeff147f75f133d6e3e5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564510"
---
# <a name="exceptions-the-invalidarg-function"></a>예외: invalidArg 함수

`invalidArg` 함수 인수 예외를 생성 합니다.


## <a name="syntax"></a>구문

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>설명
위 구문에서 매개 변수 이름 인 인수가 잘못 되었습니다. 매개 변수 이름 문자열입니다. *오류 메시지 문자열* 리터럴 문자열 또는 형식의 값은 `string`합니다. 됩니다는 `Message` 예외 개체의 속성입니다.

생성 된 예외 `invalidArg` 는 `System.ArgumentException` 예외입니다. 다음 코드에서는 `invalidArg` 예외를 throw 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

출력은 다음 (표시 되지 않음) 하는 스택 추적 옵니다.

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>참고 항목
[예외 처리](index.md)

[예외 형식](exception-types.md)

[예외: `try...with` 식](the-try-with-expression.md)

[예외: `try...finally` 식](the-try-finally-expression.md)

[예외: `raise` 함수](the-raise-function.md)

[예외: `failwith` 함수](the-failwith-function.md)
