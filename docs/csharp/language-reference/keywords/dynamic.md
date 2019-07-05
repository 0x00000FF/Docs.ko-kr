---
title: dynamic - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: c8748f1869e8e2d5246910fac0100a6c70790579
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306643"
---
# <a name="dynamic-c-reference"></a>dynamic(C# 참조)

`dynamic` 형식을 통해 컴파일 시간 형식 검사를 우회하는 작업을 사용할 수 있습니다. 대신, 이러한 작업은 런타임에 확인됩니다. `dynamic` 형식은 Office Automation API 등의 COM API, IronPython 라이브러리 등의 동적 API 및 HTML DOM(문서 개체 모델)에 대한 액세스를 간소화합니다.

`dynamic` 형식은 대부분의 상황에서 `object` 형식처럼 동작합니다. 그러나 `dynamic` 형식의 식을 포함하는 작업은 컴파일러에서 확인되거나 형식이 검사되지 않습니다. 컴파일러는 작업에 대한 정보를 패키지하며, 나중에 해당 정보는 런타임에 작업을 평가하는 데 사용됩니다. 이 과정에서 `dynamic` 형식의 변수는 `object` 형식의 변수로 컴파일됩니다. 따라서 `dynamic` 형식은 컴파일 시간에만 존재하고 런타임에는 존재하지 않습니다.

다음 예제에서는 `dynamic` 형식의 변수와 `object` 형식의 변수를 비교합니다. 컴파일 시간에 각 변수의 형식을 확인하려면 `WriteLine` 문의 `dyn` 또는 `obj` 위에 마우스 포인터를 놓습니다. IntelliSense는 `dyn`에 대해 **dynamic**을 표시하고 `obj`에 대해 **object**를 표시합니다.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

`WriteLine` 문은 `dyn` 및 `obj`의 런타임 형식을 표시합니다. 이 시점에는 둘 다 동일한 형식인 정수입니다. 다음 출력이 생성됩니다.

`System.Int32`

`System.Int32`

컴파일 시간에 `dyn` 및 `obj` 간의 차이를 보려면 앞의 예제에서 선언과 `WriteLine` 문 사이에 다음 두 줄을 추가합니다.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 `obj + 3` 식에 정수와 개체를 추가하려는 시도와 관련해서 컴파일러 오류가 보고됩니다. 하지만 `dyn + 3`에 대한 오류는 보고되지 않습니다. `dyn`의 형식이 `dynamic`이기 때문에 `dyn`을 포함하는 식은 컴파일 시간에 확인되지 않습니다.

## <a name="context"></a>컨텍스트

`dynamic` 키워드는 직접 또는 다음과 같은 경우에 생성된 형식의 구성 요소로 표시될 수 있습니다.

- 선언에서 속성, 필드, 인덱서, 매개 변수, 반환 값, 지역 변수 또는 형식 제약 조건으로. 다음 클래스 정의는 여러 선언에 `dynamic`을 사용합니다.

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- 명시적 형식 변환에서 변환의 대상 형식으로.

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- `is` 연산자 또는 `as` 연산자의 오른쪽, 생성된 형식의 일부로 포함된 `typeof` 인수 등 형식이 값으로 사용되는 모든 컨텍스트에서. 예를 들어 다음 식에서 `dynamic`을 사용할 수 있습니다.

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a>예

다음 예제에서는 여러 선언에 `dynamic`을 사용합니다. 또한 `Main` 메서드는 컴파일 시간 형식 검사를 런타임 형식 검사와 비교합니다.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

자세한 내용 및 예제는 [dynamic 형식 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [dynamic 형식 사용](../../programming-guide/types/using-type-dynamic.md)
- [object](object.md)
- [is](../operators/type-testing-and-conversion-operators.md#is-operator)
- [as](../operators/type-testing-and-conversion-operators.md#as-operator)
- [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator)
- [방법: 패턴 일치, as 및 is 연산자를 사용하여 안전하게 캐스트](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [연습: 동적 개체 만들기 및 사용](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
