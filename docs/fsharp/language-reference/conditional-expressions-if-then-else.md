---
title: '조건식: if... then...else(F#)'
description: 'F # 코드의 다른 분기를 실행 하려면 조건부 식을 작성 하는 방법을 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: a3ca3c20a659ccf5dc432d0a747ff176ec889e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563135"
---
# <a name="conditional-expressions-ifthenelse"></a>조건식: `if...then...else`

`if...then...else` 식 코드의 다른 분기를 실행 하 고 주어진 부울 식에 따라 다른 값으로 계산 합니다.


## <a name="syntax"></a>구문

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>설명
위 구문에서 *expression1* 부울 식으로 평가 되 면 실행 `true`, 그렇지 않으면 *expression2* 실행 합니다.

와 달리 다른 언어로 `if...then...else` 구문은 문이 식입니다. 즉, 실행 되는 분기의 마지막 식의 값은 값을 생성 합니다. 각 분기에서 얻은 값의 형식이 일치 해야 합니다. 없으면 더 명시적 `else` 분기, 해당 형식이 `unit`합니다. 따라서 경우 유형의 `then` 분기는 모든 형식 이외의 `unit`, 있어야는 `else` 동일한 반환 형식 갖는 분기 합니다. 연결 하는 경우 `if...then...else` 식을 키워드를 사용 하면 함께 `elif` 대신 `else if`; 동일 합니다.

## <a name="example"></a>예제
사용 하는 방법을 보여 주는 다음 예제는 `if...then...else` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

