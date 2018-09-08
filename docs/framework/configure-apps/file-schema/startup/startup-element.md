---
title: '&lt;시작&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d39dc28082fbed932a60228ac216f2f700c2e9f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185547"
---
# <a name="ltstartupgt-element"></a>&lt;시작&gt; 요소
공용 언어 런타임 시작 정보를 지정합니다.  
  
 \<configuration>  
\<startup>  
  
## <a name="syntax"></a>구문  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|선택적 특성입니다.<br /><br /> 사용 여부를 지정 합니다 [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 런타임 정품 인증 정책 사용 하는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 정품 인증 정책입니다.|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|사용 하도록 설정 [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 레거시 런타임 정품 인증 기술에 바인딩하는 선택한 런타임에 대 한 런타임 정품 인증 정책 (같은 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) 대신 구성 파일에서 선택한 런타임에 CLR 버전 2.0에서 해당를 제한 합니다. 따라서 CLR 버전 4 이상을 구성 파일에서을 선택 하면 이전 버전의.NET Framework를 사용 하 여 만든 혼합 모드 어셈블리에 있는 선택한 CLR 버전을 사용 하 여 로드 됩니다. CLR 버전 1.1 또는 CLR 버전 2.0-in-process side-by-side-기능을 효과적으로 사용 하지 않도록 설정 하는 동일한 프로세스로 로드 방지이 값을 설정 합니다.|  
|`false`|에 대 한 기본 활성화 정책을 사용 하는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이며 나중에 레거시 런타임 정품 인증 기술을 프로세스에 1.1 또는 2.0 버전 CLR을 로드할 수 있도록 합니다. 혼합 모드 어셈블리의.NET Framework 4 이상 빌드된.NET Framework 4 또는 나중에 로드를 방해이 값을 설정 합니다. 이 값은 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|응용 프로그램에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다. 런타임 버전 1.1 이상으로 빌드된 응용 프로그램을 사용 해야 합니다  **\<supportedRuntime >** 요소입니다.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 합니다  **\<supportedRuntime >** 런타임의 1.1 이상 버전을 사용 하 여 빌드된 모든 응용 프로그램에서 요소를 사용 합니다. 런타임이 버전 1.0만을 지원 하도록 빌드된 응용 프로그램을 사용 해야 합니다  **\<requiredRuntime >** 요소입니다.  
  
 Microsoft Internet Explorer에서 호스팅되는 응용 프로그램 시작 코드를 무시 합니다  **\<시작 >** 요소와 해당 자식 요소입니다.  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>UseLegacyV2RuntimeActivationPolicy 특성  
 이 특성은 응용 프로그램에서 같은 레거시 활성화 경로 사용 하는 경우에 유용 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), 해당 경로 이전 버전 대신 CLR 버전 4를 활성화 하 고 응용 프로그램이 나 사용 하 여 빌드한는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 하지만 이전 버전의.NET Framework를 사용 하 여 빌드된 혼합 모드 어셈블리에 종속 되어 있습니다. 이러한 시나리오에서는 특성을 설정할 `true`합니다.  
  
> [!NOTE]
>  특성을 설정 `true` CLR 버전 1.1 또는 CLR 버전 2.0-in-process side-by-side-기능을 효과적으로 사용 하지 않도록 설정 하는 동일한 프로세스로 로드 방지 하 고 (참조 [COM Interop에 대 한 Side-by-side-실행](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 파일에서 런타임 버전을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> 사용할 런타임 버전 지정](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [COM Interop에 대 한 Side-by-side-실행](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [In-Process Side-by-Side 실행](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
