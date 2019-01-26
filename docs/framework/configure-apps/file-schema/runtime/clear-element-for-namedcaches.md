---
title: '&lt;지우기&gt; 요소에 대 한 &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: d71c5de42104961bc096b786dfe50bb4097bc4fc
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083563"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a>&lt;지우기&gt; 요소에 대 한 &lt;namedCaches&gt;
모두 지웁니다 `namedCache` 에서 항목을 `namedCaches` 메모리 캐시에 대 한 컬렉션입니다.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 `None`  
  
### <a name="child-elements"></a>자식 요소  
 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.|  
  
## <a name="remarks"></a>설명  
 합니다 `clear` 요소를 모두 지웁니다 `namedCache` 메모리 캐시에 대 한 명명 된 캐시 컬렉션의 항목입니다. 사용할 수는 `clear` 요소를 사용 하기 전에 `add` 명명 된 컬렉션에는 캐시는 다른 특정 되려면 새 명명 된 캐시 항목을 추가할 요소입니다.  
  
## <a name="see-also"></a>참고자료
- [\<namedCaches > 요소 (캐시 설정)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
