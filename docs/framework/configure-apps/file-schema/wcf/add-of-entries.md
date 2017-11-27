---
title: "&lt;entries&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62236c604cd91c2dfe4b92cfaac4004fc18d439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a>&lt;entries&gt;의 &lt;add&gt;
이전에 정의된 클라이언트 끝점에 필터를 매핑하는 라우팅 항목을 나타냅니다. 이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.  
  
 \<system.serviceModel >  
\<라우팅 >  
\<routingTables >  
\<테이블 >  
\<항목 >  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|backupList|끝점의 백업 목록에 대한 참조를 지정하는 문자열입니다.|  
|끝점(endpoint)|`filterName` 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 끝점에 대한 참조를 지정하는 문자열입니다.|  
|filterName|필터 요소에 대한 참조를 지정하는 문자열입니다.|  
|priority|이 항목의 우선 순위를 지정하는 정수입니다.<br /><br /> 라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다. 특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.<br /><br /> 이 값은 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|라우팅 매핑 항목을 포함하는 구성 섹션입니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
