---
title: 문자열
description: 설명 하는 방법을 F# 'string' 형식은 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타냅니다.
ms.date: 07/05/2019
ms.openlocfilehash: b252aef7d7e6e299df8282407198714971e80cd5
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610171"
---
# <a name="strings"></a>문자열

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

`string` 형식은 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타냅니다. `string`은 .NET Framework에서 `System.String`의 별칭입니다.

## <a name="remarks"></a>설명

문자열 리터럴은 따옴표 (") 문자로 구분 됩니다. 백슬래시 문자 ( \\ ) 특정 특수 문자를 인코딩하는 데 사용 됩니다. 백슬래시와 함께 다음 문자는 라고는 *이스케이프 시퀀스*합니다. 이스케이프 시퀀스에서 지원 되는 F# 문자열 리터럴은 다음 표에 표시 됩니다.

|문자|이스케이프 시퀀스|
|---------|---------------|
|경고|`\a`|
|백스페이스|`\b`|
|폼 피드|`\f`|
|줄 바꿈|`\n`|
|캐리지 리턴|`\r`|
|탭|`\t`|
|세로 탭|`\v`|
|백슬래시|`\\`|
|따옴표|`\"`|
|아포스트로피|`\'`|
|유니코드 문자|`\DDD` (여기서 `D` 10 진수를 나타내는 숫자; 000-의 범위 255; 예: `\231` "ç" =)|
|유니코드 문자|`\xHH` (여기서 `H` 16 진수; 00-FF;의 범위를 나타내는 예: `\xE7` "ç" =)|
|유니코드 문자|`\uHHHH` (U T F-16) (여기서 `H` 16 진수; 0000-FFFF;의 범위를 나타냅니다  예를 들어 `\u00E7` "ç" =)|
|유니코드 문자|`\U00HHHHHH` (UTF-32) (여기서 `H` 16 진수; 000000-10ffff 까지의;의 범위를 나타냅니다  예를 들어 `\U0001F47D` = "👽")|

> [!IMPORTANT]
> `\DDD` 이스케이프 시퀀스는 소수 표기법, 대부분의 다른 언어에서 같은 하지 8 진수 표기법입니다. 따라서 자리 `8` 및 `9` 은 유효 및 시퀀스 `\032` 공백을 나타냅니다 (u+0020), 8 진수 표기법으로 동일한 코드 포인트를 수 있지만 `\040`합니다.

> [!NOTE]
> 범위는 0으로 제한 되-255 (0xff 인 경우)를 `\DDD` 및 `\x` 이스케이프 시퀀스는 효과적으로 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 하므로 처음 256 개의 유니코드 코드 포인트를 일치 하는 문자 집합을 합니다.

앞의 리터럴은 축 자 문자열 @ 기호입니다. 즉, 모든 이스케이프 시퀀스가 무시 되는 제외 하 고 두 개의 따옴표 문자 하나 따옴표 문자로 해석 됩니다.

또한 문자열 삼중 따옴표로 묶을 수 있습니다. 이 예제의 경우 이스케이프 시퀀스가 모두 무시 됩니다 큰따옴표 문자를 포함 하 여. 포함 된 따옴표 문자열이 포함 된 문자열을 지정 하려면 축 자 문자열 또는 삼중 따옴표가 붙은 문자열을 하거나 사용할 수 있습니다. 축 자 문자열을 사용 하면 단일 큰따옴표 문자를 나타내기 위해 두 개의 따옴표 문자를 지정 해야 합니다. 삼중 따옴표가 붙은 문자열을 사용 하는 경우 문자열의 끝으로 구문 분석 중인 없으면 작은따옴표 문자를 사용할 수 있습니다. 이 기술은 XML 또는 포함 된 따옴표를 포함 하는 다른 구조를 사용 하 여 작업할 때 유용할 수 있습니다.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

코드에서 줄 바꿈이 있는 문자열이 허용 되는 줄 바꿈이 그대로 해석 됩니다 줄 바꿈, 백슬래시 문자 줄 바꿈 앞 마지막 문자가 아닌을 백슬래시 문자를 사용할 때 다음 줄에서 선행 공백 무시 됩니다. 다음 코드는 문자열을 생성 `str1` 에 값을 갖는 `"abc\ndef"` 문자열과 `str2` 에 값을 갖는 `"abcdef"`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

다음과 같이 배열 유사 구문을 사용 하 여 문자열의 개별 문자를 액세스할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

출력은 `b`입니다.

또는 다음 코드 에서처럼 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

출력은 다음과 같습니다.

```
abc
def
```

형식이 부호 없는 바이트 배열에서 ASCII 문자열을 나타낼 수 있습니다 `byte[]`합니다. 접미사를 추가한 `B` 문자열 리터럴로 ASCII 문자열 임을 나타냅니다. 바이트 배열을 사용 하는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외 하 고 유니코드 문자열로 동일한 이스케이프 시퀀스를 지원 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>문자열 연산자

문자열을 연결 하는 방법은 두 가지:를 사용 하 여 합니다 `+` 연산자 또는 사용 하 여는 `^` 연산자입니다. `+` 연산자 기능을 처리 하는.NET Framework 문자열과 호환성이 유지 됩니다.

다음 예제에서는 문자열 연결을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String 클래스

문자열 형식에서 F# 는 실제로.NET 프레임 워크 `System.String` all을 입력 합니다 `System.String` 멤버를 사용할 수. 여기에 `+` 연산자에 사용 되는 문자열을 연결 하는 `Length` 속성 및 `Chars` 유니코드 문자의 배열 문자열을 반환 하는 속성입니다. 문자열에 대 한 자세한 내용은 참조 하세요. `System.String`합니다.

사용 하 여 합니다 `Chars` 속성의 `System.String`, 다음 코드에 표시 된 대로 인덱스를 지정 하 여 문자열의 개별 문자를 액세스할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>문자열 모듈

문자열 처리에 대 한 추가 기능이 포함 된 `String` 모듈에는 `FSharp.Core` 네임 스페이스. 자세한 내용은 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
