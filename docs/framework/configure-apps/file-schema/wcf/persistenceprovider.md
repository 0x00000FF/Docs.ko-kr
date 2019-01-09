---
title: '&lt;persistenceProvider&gt;'
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: ba02977a7df44931ae195040949e9a8eb0c141b5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152023"
---
# <a name="ltpersistenceprovidergt"></a>&lt;persistenceProvider&gt;
사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<serviceBehaviors>  
\<동작 >  
\<persistenceProvider >  
  
## <a name="syntax"></a>구문  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|persistenceOperationTimeout|지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다. 기본값은 "00: 00:30"입니다.|  
|형식|사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다. 이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
