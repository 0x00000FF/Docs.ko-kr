---
title: "117 - WorkflowInstanceTerminatedRecordWithId | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 117 - WorkflowInstanceTerminatedRecordWithId
## 속성  
  
|||  
|-|-|  
|ID|117|  
|키워드|HealthMonitoring, WFTracking|  
|수준|오류|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 워크플로 인스턴스가 WorkflowInstanceTerminatedRecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## 메시지  
 TrackRecord \= WorkflowInstanceTerminatedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5,  Annotations \= %6, ProfileName \= %7, WorkflowDefinitionIdentity \= %8  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간\(UTC\)|  
|ActivityDefinitionId|xs:string|워크플로의 루트 활동 이름|  
|상태|xs:string|워크플로의 현재 상태|  
|주석|xs:string|이 이벤트에 추가된 주석입니다.  값은 xml 요소에 \<items\>\< item name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> 형식으로 저장됩니다.  주석을 지정하지 않으면 문자열에 \<items\/\>가 포함됩니다.  ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.  이벤트 크기가 ETW 제한을 초과하면 주석을 삭제하고 주석 값을 \<items\>...\<\/items\>로 대체하여 이벤트를 자릅니다.|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|WorkflowDefinitionIdentity|xs:string|워크플로 정의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|