---
title: "217 - ClientOperationPrepared | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 217 - ClientOperationPrepared
## 속성  
  
|||  
|-|-|  
|ID|217|  
|키워드|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 서비스에 작업을 보내기 바로 전에 클라이언트에서 내보내집니다.  
  
## 메시지  
 클라이언트가 '%2' 계약과 연결된 '%1' 작업을 실행하는 중입니다.메시지를 '%3'\(으\)로 보냅니다.  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|동작|`xs:string`|보내는 메시지의 SOAP 동작 헤더입니다.|  
|Contract Name|`xs:string`|계약 이름입니다.예를 들면 ICalculator와 같습니다.|  
|Destination|`xs:string`|메시지를 받는 서비스 끝점의 주소입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|