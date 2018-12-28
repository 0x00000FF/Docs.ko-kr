---
title: '&lt;namedCaches&gt; 요소 (캐시 설정)'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d6f741f4ecd3ea52dacc9f981024690a0031a533
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611089"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; 요소 (캐시 설정)
명명 된 구성 설정의 컬렉션을 지정 <xref:System.Runtime.Caching.MemoryCache> 인스턴스. 합니다 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 하나 이상의 구성 설정의 컬렉션을 참조 하는 속성 `namedCaches` 구성 파일의 요소입니다.  
  
 \<configuration>  
\< system.runtime.caching >  
\<memoryCache>  
\<namedCaches >  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a>형식  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|메가바이트에서의 최대 허용 크기를 지정 하는 정수 값은 인스턴스에 <xref:System.Runtime.Caching.MemoryCache> 증가할 수 있습니다. 기본값은 0으로, 자동 크기 조정 추론이의 의미는 <xref:System.Runtime.Caching.MemoryCache> 클래스는 기본적으로 사용 됩니다.|  
|`name`|캐시의 이름입니다.|  
|`physicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 물리적으로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0과 100 사이의 정수 값입니다. 기본값은 0으로, 자동 크기 조정 추론이의 의미는 <xref:System.Runtime.Caching.MemoryCache> 클래스는 기본적으로 사용 됩니다.|  
|`pollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 이 값은 "hh: mm:" 형식으로 입력 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|메모리 캐시용으로 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|메모리 캐시에 대해 `namedCaches` 컬렉션을 지웁니다.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.|  
  
## <a name="remarks"></a>설명  
 Web.config 파일의 메모리 캐시 구성 섹션에 포함 될 수 있습니다 `add`, `remove`, 및 `clear` 에 대 한 특성을 `namedCaches` 컬렉션입니다. 각 `namedCaches` 항목으로 고유 하 게 식별 되는 `name` 특성입니다.  
  
 응용 프로그램 구성 파일의 정보를 참조 하 여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다. 기본적으로 기본 캐시 인스턴스만 구성 파일에는 항목이 있습니다. 기본 캐시 인스턴스는에서 반환 되는 인스턴스는 <xref:System.Runtime.Caching.MemoryCache.Default%2A> 속성입니다.  
  
 이름 특성을 "default"로 설정 하면 요소의 기본 메모리 캐시 인스턴스를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 캐시 항목 이름을 설정 하 여 캐시의 이름을 설정 하는 방법을 보여 줍니다는 `name` 특성을 "기본값"입니다.  
  
 `cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다. 자동 크기 조정 추론이 의미 이러한 특성을 0으로 설정 된 <xref:System.Runtime.Caching.MemoryCache> 클래스 사용 됩니다. 캐시 구현이 현재 메모리 로드를 절대 및 백분율 기반 메모리 제한과 2 분 마다 비교합니다.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
- [\<memoryCache > 요소 (캐시 설정)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
