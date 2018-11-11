---
title: '조건식: if... then...else(F#)'
description: F# 코드의 다른 분기를 실행 하려면 조건부 식을 작성 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 10e4224bef772f00520cf5a0fff2f2920147c2fc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2018
ms.locfileid: "44177603"
---
# <a name="conditional-expressions-ifthenelse"></a>조건식: `if...then...else`

`if...then...else` 식 코드의 다른 분기를 실행 하 고 지정 된 부울 식에 따라 다른 값으로 평가 합니다.

## <a name="syntax"></a>구문

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>설명

이전 구문에서 *expression1* 부울 식으로 평가 되 면 실행 `true`이 고, 그렇지 않으면 *expression2* 실행 합니다.

달리 다른 언어로 된 `if...then...else` 구문은 문이 아닌 식입니다. 즉, 실행 하는 분기의 마지막 식의 값을 생성 하는 것을 의미 합니다. 각 분기에서 생성 된 값의 형식과 일치 해야 합니다. 없으면 더 명시적 `else` 분기에 해당 형식이 `unit`합니다. 따라서 경우 형식의 합니다 `then` 아닌 다른 분기는 모든 형식 `unit`, 있어야는 `else` 동일한 반환 형식 사용 하 여 분기 합니다. 연결 하는 경우 `if...then...else` 식을 그룹화 키워드를 사용할 수 있습니다 `elif` 대신 `else if`; 동일 합니다.

## <a name="example"></a>예제

다음 예제를 사용 하는 방법의 `if...then...else` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
