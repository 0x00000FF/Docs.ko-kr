---
title: "Event-based Asynchronous Pattern (EAP) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asynchronous calls"
  - "asynchronous programming, design patterns"
  - "asynchronous programming"
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Event-based Asynchronous Pattern (EAP)
비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다.  이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 한 가지 방법을 규정합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 작업 병렬 라이브러리에서 비동기 및 병렬 프로그래밍을 위한 새로운 모델을 제공합니다.  자세한 내용은 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)을 참조하세요.  
  
## 단원 내용  
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 이벤트 기반 비동기 패턴이 다중 스레드 디자인에 본질적으로 존재하는 복잡한 여러 가지 문제를 숨기면서 다중 스레드 응용 프로그램의 장점을 이용할 수 있게 해주는 방법을 설명합니다.  
  
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 비동기 기능을 포함하는 클래스를 패키징하는 표준화된 방법을 설명합니다.  
  
 [최선의 이벤트 기반 비동기 패턴 구현 방법](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴에 따라 비동기 기능을 노출하기 위한 요구 사항을 설명합니다.  
  
 [Deciding When to Implement the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <xref:System.IAsyncResult> 패턴 대신 이벤트 기반 비동기 패턴을 구현하도록 선택해야 하는 경우를 확인하는 방법을 설명합니다.  
  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 보여 줍니다.  구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=fullName> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.  
  
 [How to: Use Components That Support the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴을 지원하는 구성 요소를 사용하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperation> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.ComponentModel.AsyncOperationManager> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
## 관련 단원  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 비동기 및 병렬 작업용 프로그래밍 모델에 대해 설명합니다.  
  
 [Threading](../../../docs/standard/threading/index.md)  
 .NET Framework 다중 스레딩 기능에 대해 설명합니다.  
  
 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)  
 C\# 및 Visual Basic 언어의 다중 스레딩 기능에 대해 설명합니다.  
  
## 참고 항목  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)   
 [이벤트](../../../docs/standard/events/index.md)   
 [구성 요소에서 다중 스레딩](../Topic/Multithreading%20in%20Components.md)   
 [Asynchronous Programming Design Patterns](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)