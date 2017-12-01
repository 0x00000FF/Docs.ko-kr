---
title: "방법: 데이터 흐름 블록에 메시지 쓰기 및 테이터 흐름 블록에서 메시지 읽기"
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
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf609a8c350a44fc802cce0ec10693431bbf4f42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>방법: 데이터 흐름 블록에 메시지 쓰기 및 테이터 흐름 블록에서 메시지 읽기
이 문서에서는 TPL 데이터 흐름 라이브러리를 사용하여 데이터 흐름 블록에서 메시지를 읽고 쓰는 방법을 설명합니다. TPL 데이터 흐름 라이브러리는 데이터 흐름 블록에서 메시지를 쓰고 읽기 위한 동기 메서드와 비동기 메서드를 모두 제공합니다. 이 문서에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> 클래스를 사용합니다. <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 메시지를 버퍼링하고 메시지 소스와 메시지 대상으로 작동합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>동기적으로 데이터 흐름 블록에서 읽고 쓰기  
 다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 데이터 흐름 블록에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 사용하여 동일한 개체에서 읽습니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 또한 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 다음 예제와 같이 데이터 흐름 블록에서 읽을 수 있습니다. <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 현재 스레드를 차단하지 않고 때때로 데이터를 폴링할 때 유용합니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드가 동기적으로 작동하기 때문에 앞의 예제에 있는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체는 두 번째 루프에서 데이터를 읽기 전에 모든 데이터를 받습니다. 다음 예제에서는 <xref:System.Threading.Tasks.Parallel.Invoke%2A>를 사용하여 메시지 블록에서 동시에 읽고 쓰는 방법으로 첫 번째 예제를 확장합니다. <xref:System.Threading.Tasks.Parallel.Invoke%2A>가 작업을 동시에 수행하기 때문에 값은 특정 순서로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 기록되지 않습니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>비동기적으로 데이터 흐름 블록에서 읽고 쓰기  
 다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드를 사용하여 비동기적으로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드를 사용하여 비동기적으로 동일한 개체에서 읽습니다. 이 예제에서는 [async](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md)(Visual Basic에서는 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)) 연산자를 사용하여 비동기적으로 대상 블록에 데이터를 보내고 대상 블록에서 데이터를 읽습니다. <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드는 데이터 흐름 블록이 메시지를 연기할 수 있도록 해야 하는 경우에 유용합니다. <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드는 데이터를 사용할 수 있게 될 때 데이터에 대한 작업을 수행하려는 경우에 유용합니다. 메시지가 메시지 블록 간에 전파되는 방법에 대한 자세한 내용은 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)의 [메시지 전달] 섹션을 참조하세요.  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>전체 예제  
 다음 예제에서는 이 문서의 전체 코드를 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowReadWrite.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowReadWrite.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## <a name="next-steps"></a>다음 단계  
 이 예제에서는 메시지 블록에서 직접 읽고 쓰는 방법을 보여 줍니다. 데이터 흐름 블록을 연결하여 데이터 흐름 블록의 선형 시퀀스인 *파이프라인*이나 데이터 흐름 블록의 그래프인 *네트워크*를 만들 수도 있습니다. 파이프라인 또는 네트워크에서 소스는 데이터를 사용할 수 있게 되면 대상에 데이터를 비동기적으로 전파합니다. 기본 데이터 흐름 파이프라인을 만드는 예제는 [연습: 데이터 흐름 파이프라인 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)를 참조하세요. 더 복잡한 데이터 흐름 네트워크를 만드는 예제는 [연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
