---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eaa3998d3d0b1642c0c92380ec1228eea69d4da8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700893"
---
# <a name="findcriteria"></a>\<findCriteria>
클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다. 조건 (찾으려는 서비스 지정) 하는 검색 조건으로 그룹화 할 수 있습니다 및 찾기 종료 조건 (검색 지속 기간).  
  
 \<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|duration|네트워크에서 서비스로부터 응답을 기다리는 최대 시간을 지정하는 Timespan 값입니다. 기본 시간은 20초입니다.|  
|maxResults|네트워크 또는 인터넷에서 서비스로부터 기다리는 최대 응답 횟수를 지정하는 정수입니다 `duration` 특성에 지정된 시간이 경과되기 전에 최대 응답이 수신되는 경우 찾기 작업이 종료됩니다.|  
|scopeMatchBy|Probe 메시지의 범위와 엔드포인트의 범위를 일치시키는 동안 사용할 일치 알고리즘을 지정하는 URI입니다.<br /><br /> 다섯 가지의 범위 일치 규칙이 지원됩니다. 범위 일치 규칙을 지정하지 않으면 `ScopeMatchByPrefix`가 사용됩니다. 이에 대한 자세한 내용은 <xref:System.ServiceModel.Discovery.FindCriteria>를 참조하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<contractTypeNames>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|워크플로 서비스 계약 형식의 이름을 포함 하는 구성 요소의 컬렉션입니다.|  
|\<확장 >의 \<findCriteria >|확장을 제공하는 XML 요소 개체의 컬렉션입니다.|  
|[\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|찾기 작업 중에 특정 서비스를 찾기 위해 사용하는 절대 URI를 포함하는 개체의 컬렉션입니다.<br /><br /> 특정 서비스를 찾으면 서비스 URI와 범위 URI 간에 성공한 일치 항목이 생깁니다. 이때 경우에 따라 일치의 복잡한 문제를 처리하는 범위 규칙이 사용됩니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
