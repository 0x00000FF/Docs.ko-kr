---
title: "Reliable Messaging Sessions Faulted Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Reliable Messaging Sessions Faulted Per Second
카운터 이름: Reliable Messaging Sessions Faulted Per Second.  
  
## 설명  
 초당 이 서비스에서 오류가 발생한 신뢰할 수 있는 메시징 세션의 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)로 되어 있습니다. 이 형식의 값은 다음과 같은 수식으로 계산됩니다.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)