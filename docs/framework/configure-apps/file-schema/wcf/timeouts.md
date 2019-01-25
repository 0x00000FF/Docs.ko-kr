---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629659"
---
# <a name="lttimeoutsgt"></a>&lt;timeOuts&gt;
서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host>  
\<timeOuts>  
  
## <a name="syntax"></a>구문  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`closeTimeout`|서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.|  
|`openTimeout`|서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<host>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|서비스 호스트의 설정을 지정하는 구성 요소입니다.|  
  
## <a name="see-also"></a>참고자료
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [호스팅](../../../../../docs/framework/wcf/feature-details/hosting.md)
