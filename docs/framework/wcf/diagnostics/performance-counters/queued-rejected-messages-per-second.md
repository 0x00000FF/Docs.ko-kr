---
title: "Queued Rejected Messages Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Queued Rejected Messages Per Second
카운터 이름: Queued Messages Rejected Per Second  
  
## 설명  
 초당 이 서비스에 대기 중인 전송에 의해 거부된 메시지의 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)로 되어 있습니다. 이 형식의 값은 다음과 같은 수식으로 계산됩니다.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)