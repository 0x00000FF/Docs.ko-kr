---
title: 451 - MessageLogInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 485b4b29-dc21-4a35-93f8-5f4726d6aa5a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c222efc0a23c6239dd2b03ff31c5279b2eda04cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="451---messageloginfo"></a>451 - MessageLogInfo
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|451|  
|키워드가|문제 해결, WCFMessageLogging|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 이 이벤트는 메시지 로그 정보가 전송될 때 내보내집니다.  
  
## <a name="message"></a>메시지  
 %1  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
