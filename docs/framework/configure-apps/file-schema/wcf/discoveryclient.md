---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128442"
---
# <a name="discoveryclient"></a>\<discoveryClient>
클라이언트 응용 프로그램에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.  
  
\<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<discoveryClient>  
  
## <a name="syntax"></a>구문  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|discoveryEndpoint|클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다. 조건 (찾으려는 서비스 지정) 하는 검색 조건으로 그룹화 할 수 있습니다 및 찾기 종료 조건 (검색 지속 기간).|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
