---
title: 인터페이스 속성(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: eea2bb524496a3db22146586df323437d9f84242
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396733"
---
# <a name="interface-properties-c-programming-guide"></a>인터페이스 속성(C# 프로그래밍 가이드)
[interface](../../../csharp/language-reference/keywords/interface.md)에 속성을 선언할 수 있습니다. 다음은 인터페이스 속성 접근자의 예입니다.  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 인터페이스 속성의 접근자에는 본문이 없습니다. 따라서 접근자의 목적은 속성이 읽기/쓰기인지, 읽기 전용인지, 쓰기 전용인지를 지정하는 것입니다.  
  
## <a name="example"></a>예  
 이 예제에서 `IEmployee` 인터페이스에는 읽기/쓰기 속성 `Name`과 읽기 전용 속성 `Counter`가 있습니다. `Employee` 클래스는 `IEmployee` 인터페이스를 구현하고 이러한 두 속성을 사용합니다. 프로그램은 새 직원의 이름과 현재 직원 수를 읽고 직원 이름과 계산된 직원 수를 표시합니다.  
  
 멤버가 선언된 인터페이스를 참조하는 속성의 정규화된 이름을 사용할 수 있습니다. 예:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 이를 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)이라고 합니다. 예를 들어 `Employee` 클래스가 두 인터페이스 `ICitizen` 및 `IEmployee`를 구현하고 두 인터페이스에 모두 `Name` 속성이 있으면 명시적 인터페이스 멤버 구현이 필요합니다. 즉, 다음과 같은 속성 선언이 있다고 가정합니다.  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 이 선언은 `IEmployee` 인터페이스의 `Name` 속성을 구현합니다. 또한 다음과 같은 선언이 있다고 가정합니다.  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 이 선언은 `ICitizen` 인터페이스의 `Name` 속성을 구현합니다.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>샘플 출력  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [속성 및 인덱서 비교](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
 [인덱서](../../../csharp/programming-guide/indexers/index.md)  
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)
