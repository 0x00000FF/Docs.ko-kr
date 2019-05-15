---
title: 모듈
description: 에 대해 알아봅니다 어떻게는 F# 모듈은 그룹의 F# , 값, 형식 및 함수 값 등의 코드는 F# 프로그램입니다.
ms.date: 04/24/2017
ms.openlocfilehash: 07ea1eb9ed06988a780fd3c5acccbc8383a4dc55
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641794"
---
# <a name="modules"></a>모듈

컨텍스트에서 F# 언어를 *모듈* 그룹화 한 것 F# , 값, 형식 및 함수 값 등의 코드는 F# 프로그램입니다. 모듈로 코드를 그룹화하면 관련 코드를 함께 유지하고, 프로그램의 이름 충돌을 방지하는 데 도움이 됩니다.

## <a name="syntax"></a>구문

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>설명

F# 모듈은 그룹의 F# 형식, 값, 함수 값의 코드 등 코드 생성 `do` 바인딩. 정적 멤버만 있는 공용 언어 런타임 (CLR) 클래스로 구현 됩니다. 모듈 선언에 전체 파일을 모듈에 포함 되는지 여부에 따라 두 가지가: 최상위 모듈 선언 및 로컬 모듈 선언 합니다. 모듈의 전체 파일을 포함 하는 최상위 모듈 선언 합니다. 최상위 모듈 선언 파일의 첫 번째 선언 에서만 나타날 수 있습니다.

최상위 모듈 선언에서 선택적 구문에서 *정규화 된 네임 스페이스* 모듈이 들어 있는 중첩 된 네임 스페이스 이름의 시퀀스입니다. 정규화 된 네임 스페이스는 이전에 선언할 필요가 없습니다.

최상위 모듈에 선언 들여쓰기 필요가 없습니다. 로컬 모듈의 모든 선언 들여쓰기 수행 해야 합니다. 로컬 모듈 선언에서 해당 모듈 선언 아래에 들여쓰기 된 선언만 사용 하면 모듈에 속합니다.

모든 로컬 모듈을 포함 하는 파일의 전체 내용을 확장명 없이 파일 이름이 동일한 암시적으로 만든된 최상위 모듈의 일부가 최상위 모듈 선언 또는 네임 스페이스 선언을 사용 하 여 코드 파일을 시작 하지 않으면, 첫 번째 글자를 대문자로 변환 합니다. 예를 들어, 다음 파일을 고려 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

이 방식으로 작성 된 것 처럼이 파일을 컴파일할 수 것:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

여러 모듈 파일에 있는 경우에 각 모듈에 대 한 로컬 모듈 선언을 사용 해야 합니다. 바깥쪽 네임 스페이스를 선언 하는 경우 이러한 모듈은 바깥쪽 네임 스페이스의 일부입니다. 바깥쪽 네임 스페이스를 선언 하지 않은 경우 모듈은 암시적으로 만든된 최상위 모듈의 일부가 됩니다. 다음 코드 예제에서는 여러 모듈을 포함 하는 코드 파일을 보여 줍니다. 컴파일러는 암시적으로 명명 된 최상위 모듈을 만듭니다 `Multiplemodules`, 및 `MyModule1` 고 `MyModule2` 해당 최상위 모듈에 중첩 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

프로젝트 또는 단일 컴파일에서 여러 파일이 있는 경우 또는 라이브러리를 빌드하는 경우 파일의 맨 위에 있는 모듈 선언 또는 네임 스페이스 선언을 포함 해야 합니다. F# 컴파일러만 결정 모듈 이름을 암시적으로 프로젝트 또는 컴파일 명령줄에 하나의 파일이 있고 응용 프로그램을 작성 하는 경우.

*접근성 한정자* 다음 중 하나일 수 있습니다: `public`, `private`, `internal`합니다. 자세한 내용은 [액세스 제어](access-control.md)를 참조하세요. 기본값은 public입니다.

## <a name="referencing-code-in-modules"></a>모듈에서 참조 하는 코드

다른 모듈에서 함수, 형식 및 값을 참조할 때 정규화 된 이름을 사용 하거나 모듈을 엽니다. 정규화 된 이름을 사용 하는 경우 네임 스페이스, 모듈 및 필요한 프로그램 요소에 대 한 식별자를 지정 해야 합니다. 각 부분은 정규화 된 경로 점 (.)를 사용 하 여 다음과 같이 합니다.

`Namespace1.Namespace2.ModuleName.Identifier`

모듈 또는 하나 이상의 코드 단순화 하기 위해 네임 스페이스를 열 수 있습니다. 열기 네임 스페이스 및 모듈에 대 한 자세한 내용은 참조 하세요. [가져오기 선언: 합니다 `open` 키워드](import-declarations-the-open-keyword.md)합니다.

다음 코드 예제에서는 파일의 끝까지 모든 코드를 포함 하는 최상위 모듈을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

동일한 프로젝트에서 다른 파일에서이 코드를 사용 하려면 정규화 된 이름을 사용 하거나 또는 열면 모듈의 함수를 사용 하기 전에 다음 예와에서 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>중첩된 모듈

모듈을 중첩할 수 있습니다. 외부 모듈 선언 내부 모듈을 새 모듈이 아니라 되는지 나타내려면 만큼 내부 모듈을 써야 합니다. 예를 들어, 다음 두 예제를 비교 합니다. 모듈 `Z` 는 다음 코드의 내부 모듈입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

하지만 모듈 `Z` 모듈에는 형제인 `Y` 다음 코드에서입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
모듈 `Z` 모듈의 다른 선언 끝까지 들여쓰지 않은 때문에 다음 코드에서는 형제 모듈 이기도 `Y`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
마지막으로, 외부 모듈 선언이 없는 하는 바로 뒤에 다른 모듈 선언 하는 경우 새 모듈 선언은 모듈을 내부로 간주 됩니다 있지만 컴파일러는 경고를 표시 하는 경우 두 번째 모듈 정의 보다 더 멀게 들여쓰지 않습니다 합니다 첫 번째입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
이 경고를 제거 하려면 내부 모듈을 들여씁니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
단일 외부 모듈에 포함 되도록 파일의 모든 코드를 원하는 경우 내부 모듈을 원하는 외부 모듈 등호를 필요 하지 않습니다 하 고 외부 모듈에서 전송 되는 모든 내부 모듈 선언에 포함 하 여 선언 들여쓰기 될 필요가 없습니다. 내부 모듈 선언 안에 선언을 들 여 쓸 필요가 있습니다. 다음 코드에서는이 사례를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>재귀 모듈

F#4.1 상호 재귀를 모두 포함 된 코드에 대 한 허용 하는 모듈의 개념을 소개 합니다.  이 통해 이루어집니다 `module rec`합니다.  사용 `module rec` 의 종류와 모듈 간의 상호 참조 코드를 쓸 수 없는 몇 가지 문제를 완화할 수 있습니다.  다음은이 예제입니다.

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

    type BananaPeel() = class end

    type Banana(orientation : Orientation) =
        member val IsPeeled = false with get, set
        member val Orientation = orientation with get, set
        member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

        member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
        member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

    module BananaHelpers =
        let peel (b: Banana) =
            let flip (banana: Banana) =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides (banana: Banana) =
                banana.Sides
                |> List.map (function
                             | Unpeeled -> Peeled
                             | Peeled -> Peeled)

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.  또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로 참조할 수도 있습니다.  하지 않는 것이에서 표현할 수 F# 를 제거한 경우 합니다 `rec` 키워드를는 `RecursiveModule` 모듈입니다.

이 기능에서 가능한 이기도 [네임 스페이스](namespaces.md) 와 F# 4.1 합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [네임스페이스](namespaces.md)
- [F#RFC FS-1009-파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
