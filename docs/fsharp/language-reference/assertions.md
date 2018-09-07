---
title: 어설션(F#)
description: "F # 프로그래밍 언어에서 식 테스트에 대 한 디버깅 기능으로 'assert' 식을 사용 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097540"
---
# <a name="assertions"></a>어설션

`assert` 식 식을 테스트 하는 데 사용할 수 있는 디버깅 기능입니다. 디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.

## <a name="syntax"></a>구문

```fsharp
assert condition
```

## <a name="remarks"></a>설명

합니다 `assert` 식에 형식 `bool -> unit`합니다.

이전 구문에서 *조건을* 테스트 하는 부울 식을 나타냅니다. 식이 계산 되는 경우 `true`, 영향을 받지 않고 계속 실행 합니다. 이면 `false`, 시스템 오류 대화 상자가 열립니다. 오류 대화 상자에 문자열을 포함 하는 캡션이 **어설션 오류**합니다. 대화 상자에 어설션 오류가 발생 한 위치를 지정 하는 스택 추적을 포함 합니다.

디버그 모드에서 컴파일할 때에 가능 어설션 검사 즉, 경우 상수 `DEBUG` 정의 됩니다. 프로젝트 시스템에서 기본적으로 `DEBUG` 상수 릴리스 구성에 없습니다. 디버그 구성에서 정의 됩니다.

F # 예외 처리를 사용 하 여 어설션 실패 오류를 낼 수 없습니다.

>[!NOTE]
합니다 `assert` 함수는 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 `assert` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
