---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5fb89ce5a942db40b07a65f59ddd05ab4cd624aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbackuplistsgt"></a>&lt;backupLists&gt;
오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다. 각 자식 요소에는 기본 끝점에 도달할 수 없는 경우 사용 하도록 라우팅 서비스 할 끝점 집합을 열거 하는 백업 목록입니다. 목록의 첫 번째 끝점이 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 끝점으로 장애 조치(failover)됩니다.  따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 응용 프로그램에 지정할 필요 없이 응용 프로그램의 안정성을 빠르게 향상시킬 수 있습니다.  
  
 \<system.serviceModel>  
\<라우팅 >  
\<backupLists >  
  
## <a name="syntax"></a>구문  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 선택 하는 끝점의 목록을 포함 합니다. 이어야 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
