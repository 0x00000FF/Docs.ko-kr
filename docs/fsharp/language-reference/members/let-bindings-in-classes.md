---
title: 클래스의 let 바인딩(F#)
description: "클래스 정의에 'let' 바인딩을 사용 하 여 개인 필드와 F # 클래스에 대 한 전용 함수를 정의 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46561541"
---
# <a name="let-bindings-in-classes"></a>클래스의 let 바인딩

사용 하 여 개인 필드와 F # 클래스에 대 한 전용 함수를 정의할 수 있습니다 `let` 클래스 정의에서 바인딩.

## <a name="syntax"></a>구문

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>설명

이전 구문 클래스 제목 및 상속 선언 뒤 아니라 멤버 정의 앞에 나타납니다. 구문은 `let` 아니라 클래스에서 정의 된 이름이 외부 바인딩 클래스에 제한 된 범위를 갖습니다. `let` 바인딩 private 필드 또는 데이터를 노출 하려면 함수를 만들거나 함수는 멤버 메서드나 속성에 공개적으로 선언 합니다.

A `let` 아닙니다 바인딩을 정적 것을 인스턴스라고 부릅니다 `let` 바인딩. 인스턴스 `let` 바인딩은 개체를 만들 때 실행 됩니다. 정적 `let` 항상 형식을 처음 사용 하기 전에 실행 되는 클래스의 정적 이니셜라이저의 일부인 바인딩.

인스턴스 내에서 코드 `let` 바인딩에서는 기본 생성자의 매개 변수를 사용할 수 있습니다.

에 특성 및 액세스 가능성 한정자를 사용할 수 없습니다 `let` 바인딩 클래스에 있습니다.

다음 코드 예제에서는 여러 유형의 설명 `let` 바인딩 클래스에 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

출력은 다음과 같습니다.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>필드를 만드는 방법

사용할 수도 있습니다는 `val` 키워드를 개인 필드를 만듭니다. 사용 하는 경우는 `val` 키워드를 필드 값이 주어 지는 개체가 만들어지면 하지만 대신 기본값을 사용 하 여 초기화 됩니다. 자세한 내용은 [명시적 필드: val 키워드](explicit-fields-the-val-keyword.md)합니다.

멤버 정의 사용 하 여 키워드를 추가 하 여 클래스에서 private 필드를 정의할 수도 있습니다 `private` 정의 합니다. 이 코드를 다시 작성 하지 않고 멤버의 액세스 가능성을 변경 하려는 경우에 유용할 수 있습니다. 자세한 내용은 [액세스 제어](../access-control.md)를 참조하세요.

## <a name="see-also"></a>참고자료

- [멤버](index.md)
- [클래스의 `do` 바인딩](do-bindings-in-classes.md)
- [`let` 바인딩](../functions/let-bindings.md)
