---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="1016---completecompletionworkitem"></a>1016 - CompleteCompletionWorkItem
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1016|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 CompletionWorkItem이 완료되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|부모 작업의 형식 이름입니다.|  
|ParentDisplayName|xs:string|부모 작업의 표시 이름입니다.|  
|ParentInstanceId|xs:string|부모 작업의 인스턴스 ID입니다.|  
|CompletedActivity|xs:string|완료된 작업의 형식 이름입니다.|  
|CompletedActivityDisplayName|xs:string|완료된 작업의 표시 이름입니다.|  
|CompletedActivityInstanceId|xs:string|완료된 작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
