---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511269"
---
# <a name="4212---lockretrytimeout"></a>4212 - LockRetryTimeout
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4212|  
|키워드|WFInstanceStore|  
|수준|경고|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.  
  
## <a name="message"></a>메시지  
 인스턴스 잠금을 얻으려는 중 시간이 초과 되었습니다.  할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다. 이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|재시도 사이의 지연입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
