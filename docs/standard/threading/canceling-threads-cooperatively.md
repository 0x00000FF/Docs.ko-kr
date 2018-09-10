---
title: 스레드 함께 취소
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24cacf0323c96f6959442dea94b0540633661bce
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485601"
---
# <a name="canceling-threads-cooperatively"></a>스레드 함께 취소

.NET Framework 4 이전에는 .NET Framework에서 시작된 스레드를 동시에 취소하는 기본 제공 방법이 없었습니다. 그러나 .NET Framework 4부터는 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>를 사용하여 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 PLINQ 쿼리를 취소하는 것처럼 스레드를 취소할 수 있습니다. <xref:System.Threading.Thread?displayProperty=nameWithType> 클래스는 취소 토큰에 대한 기본 제공 지원을 제공하지 않지만 <xref:System.Threading.Thread> 대리자를 받아들이는 <xref:System.Threading.ParameterizedThreadStart> 생성자를 사용하여 스레드 프로시저에 토큰을 전달할 수 있습니다. 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>참고 항목

 [스레드 및 스레딩 사용](using-threads-and-threading.md)  
