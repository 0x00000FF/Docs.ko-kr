---
title: '&lt;serviceBehavior&gt;의 &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 5fb7febe365f73acf09ba74b07215fe9cc659efb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a>&lt;serviceBehavior&gt;의 &lt;routing&gt;
라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<serviceBehaviors>  
\<동작 >  
\<라우팅 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|filterTable|라우팅 서비스에서 평가할 필터를 포함하는 라우팅 테이블의 이름을 지정하는 문자열입니다. 이 값과 일치 해야는 `name` 특성에는 [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) 요소에는 [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) 섹션.|  
|routeOnHeaderOnly|필터를 사용하여 메시지 본문과 헤더를 모두 검사할지 또는 헤더만 검사할지를 지정하는 부울 값입니다. 기본값은 `true`입니다.|  
|soapProcessingEnabled|SOAP 처리가 발생해야 하는지 여부를 지정하는 부울 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소가 서비스 동작 구성에 추가되면 서비스에 대한 라우팅을 사용할 수 있습니다. 서비스에서 실제로 사용할 라우팅 테이블을 이 요소에서 지정할 수 있습니다.  
  
 이 구성 섹션을 사용하여 배포 패턴이 변경되는 경우 즉시 라우팅 설정을 변경할 수 있습니다. 런타임에 새로운 라우팅 설정을 사용하여 직접 작성한 라우팅 확장을 등록할 수 있습니다. 이렇게 하면 진행 중인 메시지/세션은 시작 시 적용되었던 규칙을 사용하여 그대로 유지하면서 새로운 메시지 및 세션에 업데이트된 구성 정보를 사용할 수 있습니다.  따라서 런타임 동안 라우팅 서비스를 세션에 관계없이 재활용을 줄이면서 재구성할 수 있습니다.  
  
