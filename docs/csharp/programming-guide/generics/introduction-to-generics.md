---
title: 제네릭 소개(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 17f4c67792732be7a678ec858b6627fa712194c5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861289"
---
# <a name="introduction-to-generics-c-programming-guide"></a>제네릭 소개(C# 프로그래밍 가이드)
제네릭 클래스 및 메서드는 제네릭이 아닌 클래스 및 메서드에서는 결합할 수 없는 방식으로 재사용성, 형식 안전성 및 효율성을 결합합니다. 제네릭은 컬렉션 및 해당 컬렉션에서 작동하는 메서드에서 가장 자주 사용됩니다. .NET Framework 클래스 라이브러리 2.0 버전은 여러 가지 새로운 제네릭 기반 컬렉션 클래스가 포함된 새로운 네임스페이스 <xref:System.Collections.Generic>을 제공합니다. .NET Framework 2.0 이상을 대상으로 하는 모든 응용 프로그램은 <xref:System.Collections.ArrayList> 같은 이전의 제네릭이 아닌 컬렉션 클래스 대신 새로운 제네릭 컬렉션 클래스를 사용하는 것이 좋습니다. 자세한 내용은 [.NET의 제네릭](../../../standard/generics/index.md)을 참조하세요.  
  
 물론, 사용자 지정 제네릭 형식 및 메서드를 만들어 형식이 안전하고 효율적인 일반화된 솔루션 및 디자인 패턴을 직접 제공할 수도 있습니다. 다음 코드 예제에서는 데모용으로 간단한 제네릭 연결된 목록 클래스를 보여 줍니다. 대부분의 경우 직접 만드는 대신 .NET Framework 클래스 라이브러리에서 제공하는 <xref:System.Collections.Generic.List%601> 클래스를 사용해야 합니다. 형식 매개 변수 `T`는 일반적으로 구체적인 형식을 사용하여 목록에 저장된 항목의 형식을 나타내는 여러 위치에서 사용되며, 다음과 같은 방법으로 사용됩니다.  
  
-   `AddHead` 메서드에서 메서드 매개 변수의 형식.  
  
-   중첩 `Node` 클래스에서 `Data` 속성의 반환 형식.  
  
-   중첩 클래스에서 private 멤버 `data`의 형식.  
  
 T는 중첩 `Node` 클래스에 사용할 수 있습니다. `GenericList<T>`가 `GenericList<int>`와 같이 구체적인 형식으로 인스턴스화되면 `T`가 나타날 때마다 `int`로 바뀝니다.  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 다음 코드 예제에서는 클라이언트 코드에서 제네릭 `GenericList<T>` 클래스를 사용하여 정수 목록을 만드는 방법을 보여 줍니다. 형식 인수를 변경하기만 하면 다음 코드를 쉽게 수정하여 문자열이나 다른 모든 사용자 지정 형식 목록을 만들 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Collections.Generic>  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [제네릭](../../../csharp/programming-guide/generics/index.md)
