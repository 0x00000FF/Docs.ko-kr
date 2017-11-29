---
title: "코드 서식 지정 지침(F#)"
description: "F # 프로그래밍 가독성, 미관, 표준화 및 컴파일에 대 한 언어에 대 한 코드 들여쓰기 서식 지정 지침에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3f79717c-f84e-448d-9ce4-90e40a644ba1
ms.openlocfilehash: cc56c67f356b99defd8dc28770f87be1f58443c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="code-formatting-guidelines"></a>코드 서식 지정 지침

이 항목에서는 F #에 대 한 코드 들여쓰기 지침을 요약 합니다. 되기 때문에 F # 언어의 영향을 줄 바꿈과 없습니다, 가독성 문제 미적인 문제 또는 코드의 서식을 올바르게 지정할 코딩 표준화 문제 뿐입니다. 올바르게 컴파일하기 위해 올바르게에 코드를 포맷 해야 합니다.


## <a name="general-rules-for-indentation"></a>들여쓰기에 대 한 일반 규칙
들여쓰기 요구 되는 경우 탭이 아니라 공백을 사용 해야 합니다. 하나 이상의 공간이 필요 합니다. 조직은 들여쓰기;에 사용할 공백 수를 지정 하려면 코딩 표준을 만들 수 있습니다. 들여쓰기가 필요한 경우 각 수준에서 들여쓰기의 공백 서너 개의 일반적입니다. Visual Studio에서 옵션을 변경 하 여 조직의 들여쓰기 표준에 맞게 구성할 수 있습니다는 `Options` 에서 사용할 수 있는 대화 상자는 `Tools` 메뉴. 에 `Text Editor` 노드를 확장 하 고 `F#` 클릭 한 다음 `Tabs`합니다. 사용 가능한 옵션에 대 한 참조 [옵션, 텍스트 편집기, 모든 언어, 탭](https://msdn.microsoft.com/library/7sffa753.aspx)합니다.

일반적으로 컴파일러 코드 구문 분석 하는 경우 현재 중첩 수준을 나타내는 내부 스택을 유지 됩니다. 코드를 들여쓰는 경우 새로운 수준의 중첩을 만들거나이 내부 스택에서 푸시됩니다. 구문이 끝나면 수준이 팝 됩니다. 들여쓰기 수준의 끝을 표시 하 고 내부 스택을 팝 하는 한 가지 방법은 지지만 특정 토큰 또한 수준와 같은 팝 될 수는 `end` 키워드 또는 닫는 중괄호 또는 괄호입니다.

함수 정의 형식 정의 등의 여러 줄로 된 구문에 코드 `try...with` 구문을 구문과 루프 구문, 써야는 구문의 첫 줄을 기준으로 합니다. 들여쓰기 된 첫 번째 줄 동일한 구문에서 다음 코드에 대 한 열 위치를 설정합니다. 들여쓰기 수준을 라고는 *컨텍스트*합니다. 라고 하는 최소 열을 설정 하는 열 위치는 *오프 사이드 줄*, 동일한 컨텍스트에 있는 코드의 다음 줄에 대 한 합니다. 코드의 줄에 오류가 발생이 설정 된 열 위치 보다 덜 들여쓴, 컴파일러 컨텍스트 일정이 종료 되 고 있는지 지금 코딩 하는 다음에, 이전 컨텍스트에 있다고 가정 합니다. 용어 *사이드* 코드 줄을 충분히 멀리 들여쓰지 구문의 끝이 트리거되 하는 데 사용 됩니다. 즉, 오프 사이드 줄의 왼쪽에는 코드는 사이드입니다. 올바르게 들여쓰기 된 코드에서 구문 끝 명확 하 게 구분할 사이드 규칙의 기능을 사용할 수 있습니다. 들여쓰기를 잘못 사용 하는 경우 사이드 조건에서 경고가 발생 하도록 하면 컴파일러 또는 코드의 잘못 된 해석 될 수 있습니다.

오프 사이드 줄은 다음과 같이 결정 됩니다.


- `=` 연관 된 토큰을 `let` 오프 사이드 줄 뒤에 있는 첫 번째 토큰의 열에는 `=` 기호입니다.


- 에 `if...then...else` 식, 후 첫 번째 토큰의 열 위치는 `then` 키워드 또는 `else` 키워드 오프 사이드 줄을 정의 합니다.


- 에 `try...with` 식, 후 첫 번째 토큰 `try` 오프 사이드 줄.


- 에 `match` 식, 후 첫 번째 토큰 `with` 및 각 뒤에 있는 첫 번째 토큰 `->` 사이드 줄이 있습니다.


- 뒤에 있는 첫 번째 토큰 `with` 확장 형식에서 오프 사이드 줄을 소개 합니다.


- 첫 번째 토큰 후 또는 여는 중괄호 또는 괄호, 여는 `begin` 키워드, 사이드 줄을 정의 합니다.


- 키워드의 첫 번째 문자 `let`, `if`, 및 `module` 사이드 줄이 있습니다.


다음 코드 예제는 들여쓰기 규칙을 설명 합니다. 여기에서 print 문은 적절 한 컨텍스트가와 연결할 들여쓰기에 의존 합니다. 들여쓰기가 바뀔 때마다 컨텍스트 팝 되 고 이전 컨텍스트로 돌아갑니다. 각 반복의 끝에 공백이 표시 되며, 따라서 "Done"! 루프의 일부가 아닌지 사이드 들여쓰기를 설정 하기 때문에 한 번만 나와 있습니다. 문자열 "최상위 컨텍스트" 인쇄 함수의 일부가 아닙니다. 따라서 인쇄할 먼저 정적 초기화 하는 동안 함수를 호출 하기 전에.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

출력은 다음과 같습니다.

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

긴 줄으로 된 중단할 경우 줄의 연속 바깥쪽 구문 보다 더 많이 써야 합니다. 예를 들어 다음 코드에 나와 있는 것 처럼 함수 인수 함수 이름의 첫 번째 문자 보다 더 강력 하 들여씁니다 해야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

다음 섹션에 설명 된 대로 다음이 규칙을 예외가 있습니다.


## <a name="indentation-in-modules"></a>모듈의 들여쓰기
로컬 모듈의 코드 모듈을 기준으로 써야 있지만 최상위 모듈에 코드를 들 여 쓸 필요가 없습니다. Namespace 요소 들 여 쓰도록 필요가 없습니다.

다음 코드 예제에서는 이러한 경우를 설명 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

자세한 내용은 참조 [모듈](modules.md)합니다.


## <a name="exceptions-to-the-basic-indentation-rules"></a>기본 들여쓰기 규칙에 대 한 예외
일반적인 규칙을 이전 섹션에 설명 된 대로 여러 줄로 된 구문에 대 한 코드를 해당 구문의 첫 번째 줄의 들여쓰기를 기준으로 써야 하며 첫 번째 사이드 줄 발생할 때 해당 구문의 끝에 의해 결정 됩니다. 컨텍스트가 끝나는 경우에 일부 구문와 같은 하는 방법에 대 한 규칙에 예외는 `try...with` 식은 `if...then...else` 식을 사용 하 여 `and` 선언 상호 재귀 함수 또는 형식에 대 한 구문을 여러 부분으로 구성 합니다. 뒷부분에 나오는 부분을와 같은 들여쓰기 `then` 및 `else` 에 `if...then...else` 식의 같은 식을 시작 하는 토큰으로 수준 하지만 동일한 컨텍스트의 다음 부분이 컨텍스트 끝을 가리키는 것이 아니라 나타냅니다. 따라서는 `if...then...else` 다음 코드 예제와 같이 식을 작성할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

사이드 규칙의 예외에만 적용 됩니다는 `then` 및 `else` 키워드입니다. 따라서 오류가 발생 하지는 않지만 `then` 및 `else` 줄의 코드를 들여쓰려면 또한 실패 한 `then` 블록에서 경고를 생성 합니다. 다음 코드 줄에 설명 되어 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

코드에 대 한 프로그램 `else` 블록, 추가 특별 한 규칙이 적용 됩니다. 이전 예제에서이 경고의 코드에 대해서만 발생는 `then` 블록의 코드에 없는 `else` 블록입니다. 함수의 시작 부분에서 다양 한 조건에 함수에 대 한 코드의 나머지 부분을 시작 하지 않고 검사 하는 코드를 작성할 수 있습니다는 `else` 블록 들여쓰기 됩니다. 따라서 다음 경고를 생성 하지 않고 작성할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

컨텍스트는 들여쓰지 않은 줄 앞 줄과 같은 중 위 연산자가 관련해 서 면를 종료 하는 규칙에 다른 예외 `+` 및 `|>`합니다. 중 위 연산자로 시작 하는 줄을 시작 하도록 허용 된 `(1 + oplength)` 열은 일반적인 위치는 컨텍스트에 끝을 트리거하지 않고 앞 여기서 `oplength` 연산자 구성 하는 문자 수입니다. 이렇게 하면 이전 줄을 맞춰 연산자 다음 첫 번째 토큰입니다.

예를 들어 다음 코드에에서는 `+` 들여쓰기 된 두 개의 열이 이전 줄 보다 작은 되도록 기호를 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

들여쓰기 중첩 수준이 더 높은 되었을 때 일반적으로 증가 하지만 컴파일러가 허용 들여쓰기 낮은 열 위치를 다시 설정 해야 하는 몇 가지 구문이 있습니다.

열 위치를 다시 설정할 수 있는 구문은 다음과 같습니다.


- 익명 함수의 본문입니다. 다음 코드에서는 인쇄 식은 보다 왼쪽에 있는 열의 위치에서 시작 된 `fun` 키워드입니다. 그러나 해당 줄에서 시작할 수 없습니다 이전 들여쓰기 수준 시작의 왼쪽에 열 (즉, 왼쪽에는 `L` 에 `List`).
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- 묶은 괄호 또는 구문 `begin` 및 `end` 에 `then` 또는 `else` 블록는 `if...then...else` 식에 제공 된 들여쓰기는의 열 위치 보다 더 작은 `if` 키워드입니다. 이 예외는 코딩 스타일에 대 한 사용 여는 괄호 또는 `begin` 뒤에 줄의 끝에 사용 되는 `then` 또는 `else`합니다.


- 모듈, 클래스, 인터페이스 및 구조체로 구분 된 본문 `begin...end`, `{...}`, `class...end`, 또는 `interface...end`합니다. 그러면 스타일 전체 본문 더 많이 opening 키워드 들여쓰지을 시작 하지 않고 형식 정의의 여는 키워드는 형식 이름으로 같은 줄에 있을 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
