---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 743b16232e239929f75e269faa16799a37043495
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1034---completeruntimeworkitem"></a>1034 - CompleteRuntimeWorkItem
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1034|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 RuntimeWorkItem이 완료되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
