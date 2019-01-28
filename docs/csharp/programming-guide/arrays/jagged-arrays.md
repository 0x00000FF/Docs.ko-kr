---
title: 가변 배열 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 118e92be724723d4364cf8b40c9ff850fcb1931a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698399"
---
# <a name="jagged-arrays-c-programming-guide"></a>가변 배열(C# 프로그래밍 가이드)

가변 배열의 요소에는 배열이 사용됩니다. 가변 배열의 요소는 차원과 크기가 서로 다를 수 있습니다. 가변 배열을 “배열의 배열”이라고도 합니다. 다음 예제에서는 가변 배열을 선언, 초기화 및 액세스하는 방법을 보여 줍니다.  
  
 다음은 각각 정수의 1차원 배열인 세 개의 요소를 포함하는 1차원 배열의 선언입니다.  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 `jaggedArray`를 사용하려면 먼저 해당 요소를 초기화해야 합니다. 다음과 같이 요소를 초기화할 수 있습니다.  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 각 요소는 정수의 1차원 배열입니다. 첫 번째 요소는 5개 정수의 배열이고, 두 번째 요소는 4개 정수의 배열이고, 세 번째 요소는 2개 정수의 배열입니다.  
  
 이니셜라이저를 사용하여 배열 요소에 값을 채울 수도 있으며, 이 경우 배열 크기가 필요 없습니다. 예:  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 다음과 같이 선언 시 배열을 초기화할 수도 있습니다.  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 다음과 같은 약식 형태를 사용할 수 있습니다. 요소에 대한 기본 초기화가 없으므로 요소 초기화에서 `new` 연산자를 생략할 수 없습니다.  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.  
  
 다음 예제처럼 개별 배열 요소에 액세스할 수 있습니다.  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 가변 배열과 다차원 배열을 함께 사용할 수 있습니다. 다음은 서로 다른 크기의 세 가지 2차원 배열 요소를 포함하는 1차원 가변 배열의 선언과 초기화입니다. 2차원 배열에 대한 자세한 내용은 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)을 참조하세요.  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 이 예제와 같이, 첫 번째 배열의 `[1,0]` 요소 값(값 `5`)을 표시하는 개별 요소에 액세스할 수 있습니다.  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 `Length` 메서드는 가변 배열에 포함된 배열 수를 반환합니다. 예를 들어 이전 배열을 선언했다고 가정합니다.  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 이 경우 위 줄은 값 3을 반환합니다.  
  
## <a name="example"></a>예제

 이 예제에서는 요소 자체가 배열인 배열을 작성합니다. 각 배열 요소의 크기가 서로 다릅니다.  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Array>
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [배열](../../../csharp/programming-guide/arrays/index.md)
- [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
