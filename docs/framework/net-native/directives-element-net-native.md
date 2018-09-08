---
title: '&lt;지시문&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8921d2841f9a7b4228ae3b8735d7047453f71bcb
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44130213"
---
# <a name="ltdirectivesgt-element-net-native"></a>&lt;지시문&gt; 요소(.NET 네이티브)
.NET 네이티브에 대 한 모든 런타임 지시문 파일의 루트 요소입니다.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a>구문  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`xmlns`|XML 네임스페이스입니다. 해당 값은 항상 **"http://schemas.microsoft.com/netfx/2013/01/metadata"** 합니다.|  
  
## <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버의 컨테이너로 사용됩니다.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|런타임에 자식 형식 및 형식 멤버에 메타데이터가 필요한 어셈블리를 정의합니다.|  
  
## <a name="remarks"></a>설명  
 각 런타임 지시문 파일은 `<Directives>` 요소를 하나만 포함할 수 있습니다.  
  
 `<Directives>` 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 요소를 포함하지 않거나 하나 포함할 수 있으며 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소를 포함하지 않거나 하나 이상 포함할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)
