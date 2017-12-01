---
title: "방법: 스레드 로컬 변수를 사용하는 Parallel.ForEach 루프 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6102274f75d2fe66b89f917cf9095d3a6dfaa3e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-parallelforeach-loop-with-thread-local-variables"></a>방법: 스레드 로컬 변수를 사용하는 Parallel.ForEach 루프 작성
다음 예제에서는 스레드 지역 변수를 사용하는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드를 작성하는 방법을 보여 줍니다. <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프가 실행되면 해당 소스 컬렉션이 여러 파티션으로 나뉩니다. 각 파티션은 "스레드 지역" 변수의 자체 복사본을 갖게 됩니다. (여기서 "스레드 지역"이라는 용어는 다소 부정확합니다. 일부 경우 두 개의 파티션이 동일한 스레드에서 실행될 수 있기 때문입니다.)  
  
 이 예제의 코드와 매개 변수는 해당 <xref:System.Threading.Tasks.Parallel.For%2A> 메서드와 매우 흡사합니다. 자세한 내용은 참조 [하는 방법: 스레드 로컬 변수를 사용 하는 Parallel.For 루프 작성](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)합니다.  
  
 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프에 스레드 지역 변수를 사용하려면 두 가지 형식의 매개 변수를 사용하는 메서드 오버로드 중 하나를 호출해야 합니다. 첫 번째 형식 매개 변수인 `TSource`는 소스 요소의 형식을 지정하고, 두 번째 형식 매개 변수인 `TLocal`은 스레드 지역 변수의 형식을 지정합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> 오버로드를 호출하여 1백만 개의 요소가 포함된 배열의 합계를 계산합니다. 이 오버로드에는 다음과 같은 4개의 매개 변수가 있습니다.  
  
-   `source`: 데이터 소스이며, <xref:System.Collections.Generic.IEnumerable%601>를 구현해야 합니다. 이 예제에서 데이터 소스는 `IEnumerable<Int32>` 메서드에서 반환된 1백만 개의 멤버 <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType> 개체입니다.  
  
-   `localInit` 또는 스레드 지역 변수를 초기화하는 함수입니다. 이 함수는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 작업이 실행되는 각 파티션에 대해 한 번 호출됩니다. 이 예제에서는 스레드 지역 변수를 0으로 초기화합니다.  
  
-   `body`: 루프가 반복될 때마다 병렬 루프에 의해 호출되는 <xref:System.Func%604>입니다. 해당 시그니처는 `Func\<TSource, ParallelLoopState, TLocal, TLocal>`입니다. 사용자는 대리자의 코드를 제공하고, 루프는 다음과 같은 입력 매개 변수를 전달합니다.  
  
    -   <xref:System.Collections.Generic.IEnumerable%601>의 현재 요소  
  
    -   루프의 상태를 검토하기 위해 대리자 코드에 사용할 수 있는 <xref:System.Threading.Tasks.ParallelLoopState> 변수  
  
    -   스레드 지역 변수  
  
     대리자는 스레드 지역 변수를 반환하고, 그런 다음 스레드 지역 변수는 해당 특정 파티션에서 실행되는 루프의 다음 반복으로 전달됩니다. 각 루프 파티션에서는 이 변수의 별도의 인스턴스를 유지합니다.  
  
     이 예제에서는 대리자가 각 정수 값을 스레드 지역 변수에 더하고, 스레드 지역 변수는 해당 파티션에서 정수 요소 값의 누계를 유지합니다.  
  
-   `localFinally`: 각 파티션의 루프 작업이 완료될 때 `Action<TLocal>`가 호출하는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 대리자입니다. <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 메서드는 이 스레드(또는 루프 파티션)에 대한 스레드 지역 변수의 최종 값을 `Action<TLocal>` 대리자에게 전달하고, 사용자는 이 파티션의 결과를 다른 파티션의 결과와 결합하는 데 필요한 작업을 수행하는 코드를 제공합니다. 이 대리자는 여러 작업에서 동시에 호출할 수 있습니다. 그렇기 때문에 이 예제에서는 <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> 메서드를 사용하여 `total` 변수에 대한 액세스를 동기화합니다. 대리자 형식이 <xref:System.Action%601>이므로 반환 값은 없습니다.  
  
 [!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
 [!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 병렬 처리](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [방법: 스레드 로컬 변수를 사용하는 Parallel.For 루프 작성](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)  
 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
