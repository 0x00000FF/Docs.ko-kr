---
title: 등가 연산자
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741700"
---
# <a name="equality-operators"></a>등가 연산자
이 섹션에서는 같음 연산자를 오버 로드 하는 방법을 설명 하 고 같음 연산자로 `operator==` 및 `operator!=`을 참조 합니다.

 ❌는 같음 연산자 중 하나를 오버 로드 하지 않고 다른 연산자를 오버 로드 하지 않습니다.

 <xref:System.Object.Equals%2A?displayProperty=nameWithType>와 같음 연산자에 정확히 동일한 의미 체계와 유사한 성능 특성이 있는지 확인 ✔️ 합니다.

 이것은 같음 연산자가 오버 로드 될 때 `Object.Equals`를 재정의 해야 하는 경우가 많습니다.

 ❌ 같음 연산자에서 예외가 throw 되지 않도록 합니다.

 예를 들어 `NullReferenceException`를 throw 하는 대신 인수 중 하나가 null 이면 false를 반환 합니다.

## <a name="equality-operators-on-value-types"></a>값 형식에 대 한 같음 연산자
 같음 값이 의미 하는 경우 값 형식에 대 한 같음 연산자를 오버 로드 ✔️ 합니다.

 대부분의 프로그래밍 언어에는 값 형식에 대 한 `operator==`의 기본 구현이 없습니다.

## <a name="equality-operators-on-reference-types"></a>참조 형식에 대 한 같음 연산자
 변경 가능한 참조 형식에 대해 같음 연산자를 오버 로드 하지 ❌ 합니다.

 많은 언어에는 참조 형식에 대 한 같음 연산자가 기본 제공 됩니다. 기본 제공 연산자는 일반적으로 참조 같음을 구현 하며, 대부분의 개발자는 기본 동작이 값 같음으로 변경 될 때 많은 개발자를 대상으로 합니다.

 불변성은 참조 같음 및 값 같음 간의 차이를 보다 쉽게 알 수 있으므로이 문제는 변경할 수 없는 참조 형식에 대해 완화 됩니다.

 구현은 참조가 일치 하는 것 보다 훨씬 느린 경우 참조 형식에 대해 같음 연산자를 오버 로드 하지 않도록 ❌ 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
