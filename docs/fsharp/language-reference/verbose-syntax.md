---
title: 자세한 구문(F#)
description: 'F # 프로그래밍 언어에서 자세한 정보 및 간단한 구문 간의 차이점에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972321"
---
# <a name="verbose-syntax"></a>자세한 구문

F # 언어의 많은 구문을 사용할 수 있는 두 가지 형태의 구문이 있습니다: *자세한 구문* 하 고 *간단한 구문을*합니다. 자세한 구문 일반적으로 사용 되지 않지만 되 들여쓰기로 덜 중요 한 장점이 있습니다. 같은 추가 키워드 보다는 간단한 구문은 짧은 및 들여쓰기를 사용 하 여 구문의 시작과 끝을 알리기 위해 `begin`, `end`, `in`등입니다. 기본 구문은 간단한 구문입니다. 이 항목에서는 간단한 구문을 사용 하지 않는 경우 F # 구문에 대 한 구문을 설명 합니다. 간단한 구문을 사용 하도록 설정한 경우에 사용할 수 있도록 계속 자세한 구문 일부 구문에 대 한 자세한 구문은 항상 활성화 됩니다. 사용 하 여 간단한 구문을 사용 하지 않도록 설정할 수는 `#light "off"` 지시문입니다.

## <a name="table-of-constructs"></a>구문 표

다음 표에서 상황에서 F # 언어 구문에 대 한 간단 하 고 자세한 구문을 보여 줍니다. 여기서 두 가지 형식 사이 차이가 있습니다. 이 테이블에서 꺾쇠 괄호 (&lt;&gt;) 사용자가 제공한 구문 요소를 묶습니다. 이러한 구문 내에서 사용 된 구문에 대 한 자세한 정보에 대 한 각 언어 구문에 대 한 설명서를 참조 하십시오.

<table>
<tr>
<th>언어 구문</th>
<th>간단한 구문</th>
<th>자세한 구문</th>
</tr>
<tr>
<td>
복합 식
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


중첩 된 `let` 바인딩

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
코드 블록
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td>레코드
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>클래스
</td><td>
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>구조체(structure)</td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>구별 된 공용 구조체</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td>interface(인터페이스)</td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>개체 식</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>인터페이스 구현</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>형식 확장</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>name</td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [컴파일러 지시문](compiler-directives.md)
- [코드 서식 지정 지침](code-formatting-guidelines.md)
