---
title: <Library> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce001ed25d7704301d7f809887a445e3492e93fc
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422530"
---
# <a name="library-element-net-native"></a>\<라이브러리 > 요소 (.NET 네이티브)
런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.  
  
 \<Directives> 요소  
\<Library> 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수 특성입니다. 어셈블리의 이름을 지정합니다. 이 `<Library>` 요소의 자식 요소는 이 어셈블리에 있는 형식 및 형식 멤버에 대한 런타임 리플렉션 정책을 정의합니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|설명|  
|-----------|-----------------|  
|*assembly_name*|파일 확장명이 없는 어셈블리의 단순한 이름입니다. 이 특성은 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다. 예를 들어 Extensions.dll 어셈블리의 이름은 "Extensions"입니다. 어셈블리에서 조건부 메타데이터 포함을 지원하는 특수 *assembly_name* 형식에 대한 내용은 설명 섹션을 참조하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|특정 어셈블리의 모든 형식에 정책을 적용합니다.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|특정 네임스페이스의 모든 형식에 정책을 적용합니다.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|생성된 제네릭 형식에 정책을 적용합니다. 예를 들어 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소를 사용하면 `List<String>` 형식에 대한 정책을 정의할 수 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|런타임 지시문 파일의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 요소는 `<Library>` 요소를 포함하지 않을 수도 있고 하나 이상 포함할 수도 있습니다.  
  
 `<Library>` 요소는 런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용되며 정책을 표현하지는 않습니다. 컴파일 타임에 컴파일러 도구는 `<Library>` 요소로 지정된 라이브러리에서만 자식 요소가 식별한 프로그램 요소를 검색합니다. 반면 .NET Framework 핵심 라이브러리를 비롯한 모든 라이브러리에서 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 요소의 자식 요소가 식별한 프로그램 요소를 검색합니다.  
  
 `<Library>` 지시문은 조건부로 사용할 수 있습니다. 경우의 이름을 합니다 `<Library>` 요소 시작 되 고 별표를 사용 하 여 끝나는 (\*), `<Library>` 지시문이 앱에서 별표 사이 지정 된 어셈블리를 참조할 경우에 적용 합니다. 예를 들어, 다음 런타임 지시문에는 앱에서 Utilities.dll 어셈블리를 참조 하는 경우에 적용 됩니다.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>참고자료

- [\<응용 프로그램 > 요소](../../../docs/framework/net-native/application-element-net-native.md)
- [\<지시문 > 요소](../../../docs/framework/net-native/directives-element-net-native.md)
- [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)
