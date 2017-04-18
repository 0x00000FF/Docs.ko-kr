---
title: "1010 - ActivityCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1010 - ActivityCompleted
## 속성  
  
|||  
|-|-|  
|ID|1010|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 작업의 실행이 완료되었음을 나타냅니다.  
  
## 메시지  
 Activity '%1', DisplayName: '%2', InstanceId: '%3'이\(가\) '%4' 상태로 완료되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|상태|xs:string|작업의 상태입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|