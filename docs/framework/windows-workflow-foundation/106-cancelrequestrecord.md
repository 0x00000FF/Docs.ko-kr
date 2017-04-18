---
title: "106 - CancelRequestRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f72a59aa-8093-4a8e-94df-40acaffb1ffb
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 106 - CancelRequestRecord
## 속성  
  
|||  
|-|-|  
|Id|106|  
|키워드|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 워크플로 인스턴스 내의 활동이 cancelrequestedrecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## 메시지  
 TrackRecord \= CancelRequestedRecord, InstanceID\=%1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityId\=%5, ActivityInstanceId\=%6, ActivityTypeName \= %7, ChildActivityName \= %8, ChildActivityId \= %9, ChildActivityInstanceId \= %10, ChildActivityTypeName \=%11, Annotations\=%12, ProfileName \= %13  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간\(UTC\)|  
|이름|xs:string|취소 작업을 요청한 활동의 이름|  
|ActivityId|xs:string|취소 작업을 요청한 활동의 ID|  
|ActivityInstanceId|xs:string|취소 작업을 요청한 활동의 인스턴스 ID|  
|ActivityTypeName|xs:string|취소 작업을 요청한 활동의 형식|  
|ChildActivityName|xs:string|취소되는 활동의 이름|  
|ChildActivityId|xs:string|취소되는 활동의 ID|  
|ChildActivityInstanceId|xs:string|취소되는 활동의 활동 인스턴스 ID|  
|ChildActivityTypeName|xs:string|취소할 활동의 형식|  
|주석|xs:string|이 이벤트에 추가된 주석입니다.값은 xml 요소에 \<items\>\<\> item  name \= "annotationName" type\="System.String"\<annotationValue\>\<\/item\>\/items 형식으로 저장됩니다.주석을 지정하지 않으면 문자열에 \<items\/\>가 포함됩니다.ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.이벤트 크기가 ETW 제한을 초과하면 주석을 삭제하고 주석 값을 \<items\>...\<\/items\>로 대체하여 이벤트를 자릅니다.|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|HostReference|xs:string|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'\(예: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'\)으로 정의됩니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|