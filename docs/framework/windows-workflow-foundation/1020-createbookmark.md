---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1020|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 작업에 대한 책갈피가 만들어졌음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 책갈피를 만든 작업 '%1', DisplayName: '%2', InstanceId: '%3'.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|BookmarkName|xs:string|책갈피 이름입니다.|  
|BookmarkScope|xs:string|책갈피의 범위입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
