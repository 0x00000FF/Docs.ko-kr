---
title: "Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
WS\-AT 프로토콜 서비스가 인식할 수 없는 일시적 참가자로부터 Prepared 또는 Replay 메시지를 받았습니다.트랜잭션 결과가 확실하지 않음을 선언하는 결함을 참가자에게 반환했습니다.  
  
## 설명  
 로컬 트랜잭션 관리자가 이미 잊어 버린 일시적인 인리스트먼트로부터 Prepared 또는 Replay 메시지를 받는 경우 추적됩니다.  
  
## 문제 해결  
 일시적 참가자가 보내는 최신 메시지의 잠재적 원인을 조사합니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)