---
title: "1006 - WorkflowApplicationUnhandledException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1006 - WorkflowApplicationUnhandledException
## 속성  
  
|||  
|-|-|  
|ID|1006|  
|키워드|WFRuntime|  
|수준|오류|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 워크플로 응용 프로그램에서 처리되지 않은 예외가 발생했음을 나타냅니다.  
  
## 메시지  
 WorkflowInstance Id: '%1'에서 처리되지 않은 예외가 발생했습니다. 예외는 작업 '%2', DisplayName: '%3'에서 발생했습니다. 다음 작업이 수행됩니다. %4.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|WorkflowInstanceId|`xs:string`|워크플로의 인스턴스 ID|  
|예외|`xs:string`|예외에 대한 예외 정보|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|