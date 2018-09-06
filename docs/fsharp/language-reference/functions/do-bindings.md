---
title: do 바인딩(F#)
description: "F # 'do' 바인딩에 사용법 함수 또는 값을 정의 하지 않고 코드를 실행할 수에 대해 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882735"
---
# <a name="do-bindings"></a>do 바인딩

`do` 함수 또는 값을 정의 하지 않고 코드를 실행 하려면 바인딩이 사용 됩니다. 또한 수행 바인딩 수 있습니다 참조 클래스를 사용 [ `do` 클래스에 바인딩](../members/do-bindings-in-classes.md)합니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>설명

사용 된 `do` 함수 또는 값의 정의 의존 하지 않고 코드를 실행 하려는 경우 바인딩. 식에는 `do` 바인딩을 반환 해야 합니다 `unit`합니다. 코드에서 최상위 `do` 바인딩 모듈 초기화 될 때 실행 됩니다. 키워드 `do` 선택 사항입니다.

최상위 수준에 특성을 적용할 수 있습니다 `do` 바인딩. 예를 들어, 프로그램 COM interop를 사용 하는 경우 적용할는 `STAThread` 프로그램 특성입니다. 특성을 사용 하 여이 수행할 수는 `do` 다음 코드 에서처럼 바인딩.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>참고자료

- [F# 언어 참조](../index.md)
- [함수](index.md)
