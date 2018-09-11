---
title: '람다 식: fun 키워드(F#)'
description: "F # '재미' 키워드를 사용 하 여 익명 함수는 람다 식을 정의 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: a37757f6b7328cd348bbf13f058a6dbc881769cf
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353709"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>람다 식: fun 키워드(F#)

`fun` 키워드 람다 식, 익명 함수를 정의 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>설명

합니다 *매개 변수 목록을* 이름 및 필요에 따라 매개 변수의 형식이 일반적으로 구성 됩니다. 보다 일반적으로 *매개 변수 목록을* F # 패턴 구성 될 수 있습니다. 가능한 패턴의 전체 목록을 참조 하세요 [패턴 일치](../pattern-matching.md)합니다. 올바른 매개 변수 목록에는 다음 예제에서는 포함 됩니다.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

합니다 *식* 함수 반환 값을 생성 하는 마지막 식의 본문입니다. 유효한 람다 식의 예는 다음과 같습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>람다 식 사용

람다 식 목록 또는 다른 컬렉션에 대 한 작업을 수행 하 고 함수를 정의 하는 추가 작업을 방지 하려면 하려는 경우에 특히 유용 합니다. 인수로 함수 값을 사용 하는 F # 라이브러리의 많은 함수 및 람다 식을 사용 하 여 이러한 경우에 특히 편리할 수 있습니다. 다음 코드에는 목록의 요소에 람다 식을 적용 됩니다. 이 경우 익명 함수 목록의 모든 요소에 1을 추가합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>참고자료

- [함수](index.md)
