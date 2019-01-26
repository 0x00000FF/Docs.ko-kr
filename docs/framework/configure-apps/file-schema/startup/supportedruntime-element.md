---
title: '&lt;supportedRuntime&gt; Element'
ms.date: 04/10/2018
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 3fdc3bae488fe47732fe91cbb2ac23aae3e33b81
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084395"
---
# <a name="ltsupportedruntimegt-element"></a>&lt;supportedRuntime&gt; Element

응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다. 이 요소는 .NET Framework 1.1 이상 버전으로 작성된 모든 응용 프로그램에서 사용되어야 합니다.  
  
[\<구성>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
&nbsp;&nbsp;[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  
  
## <a name="syntax"></a>구문
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a>특성
  
|특성|설명|  
|---------------|-----------------|  
|**version**|선택적 특성입니다.<br /><br /> 응용 프로그램이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다. 유효한 값에 대 한는 `version` 특성을 참조 합니다 ["런타임 버전" 값](#version) 섹션. **참고:**  .NET Framework 3.5를 통해를 "*런타임 버전*" 형식으로 지정 *주요*. *사소한*. *빌드*합니다. [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터는 주 및 부 버전 번호만 필요합니다(즉, "v4.0.30319"가 아니라 "v4.0"만 필요). 짧은 문자열이 권장됩니다.|  
|**sku**|선택적 특성입니다.<br /><br /> 이 응용 프로그램이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.<br /><br /> .NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.  존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.<br /><br /> Sku 특성의 유효한 값에 대 한 참조를 ["sku id" 값](#sku) 섹션입니다.|  
  
## <a name="remarks"></a>설명

경우는  **\<supportedRuntime >** 응용 프로그램 구성 파일에 요소가 없으면, 응용 프로그램을 빌드하려면 사용 된 런타임 버전이 사용 됩니다.  

합니다  **\<supportedRuntime >** 런타임의 1.1 이상 버전을 사용 하 여 빌드된 모든 응용 프로그램에서 요소를 사용 합니다. 런타임이 버전 1.0만을 지원 하도록 빌드된 응용 프로그램을 사용 해야 합니다 [ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 요소입니다.  
  
> [!NOTE]
>  사용 하는 경우는 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 구성 파일을 지정 하려면 함수를 사용 해야 합니다는 `<requiredRuntime>` 런타임의 모든 버전에 대 한 요소입니다. 합니다 `<supportedRuntime>` 사용 하는 경우 요소는 무시 됩니다 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)합니다.  
  
.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다. .NET Framework 4.0 이상 버전을 원하는 앱의 경우 `version` 특성은 .NET Framework 4 이상 버전에 공통적으로 적용되는 CLR 버전을 나타내며, `sku` 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.  
  
> [!NOTE]
>  응용 프로그램에서는 사용 레거시 활성화 경로 같은 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), 해당 경로 이전 버전 대신 CLR 버전 4를 활성화 하 고 를사용하여응용프로그램을빌드할경우또는[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]종속 되어 있지만 이전 버전의.NET Framework를 사용 하 여 빌드된 혼합 모드 어셈블리에 없는 지정 하는 데 충분 합니다 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 지원 되는 런타임 목록에서. 또한 합니다 [ \<시작 > 요소](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일에서 설정 해야 합니다 `useLegacyV2RuntimeActivationPolicy` 특성을 `true`입니다. 그러나 이 특성을 `true`로 설정하면 .NET Framework의 이전 버전으로 빌드된 모든 구성 요소가 빌드 시 사용된 런타임 대신 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]을(를) 사용하여 실행됩니다.  
  
실행할 수 있는 모든 .NET Framework 버전을 사용하여 응용 프로그램을 테스트하는 것이 좋습니다.  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a>"런타임 버전" 값  
`runtime` 특성이 지정된 된 응용 프로그램에 필요한 공통 언어 런타임 (CLR) 버전을 지정 합니다. 모든.NET Framework v4.x 버전을 지정 하는 참고를 `v4.0` CLR. 다음 표에 대 한 유효한 값을 *런타임 버전* 의 값을 `version` 특성입니다.  

|.NET Framework 버전|`version` 특성|  
|----------------------------|-------------------------|  
|1.0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0-4.7.2|"v4.0"|  

<a name="sku"></a>   
## <a name="sku-id-values"></a>"sku id" 값

`sku` 특성 대상 프레임 워크 모니커 (TFM)를 사용 하 여 앱 대상으로 하 고 실행 하는 데 필요한.NET Framework의 버전을 나타냅니다. 다음 테이블에서 지원 되는 유효한 값을 나열 합니다 `sku` 특성을.NET Framework 4를 사용 하 여 시작 합니다.
  
|.NET Framework 버전|`sku` 특성|  
|----------------------------|---------------------|  
|4.0|".NETFramework,Version=v4.0"|  
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|  
|4.0, 플랫폼 업데이트 1|".NETFramework,Version=v4.0.1"|  
|4.0, Client Profile, 업데이트 1|".NETFramework,Version=v4.0.1,Profile=Client"|  
|4.0, 플랫폼 업데이트 2|".NETFramework,Version=v4.0.2"|  
|4.0, Client Profile, 업데이트 2|".NETFramework,Version=v4.0.2,Profile=Client"|  
|4.0, 플랫폼 업데이트 3|".NETFramework,Version=v4.0.3"|  
|4.0, Client Profile, 업데이트 3|".NETFramework,Version=v4.0.3,Profile=Client"|  
|4.5|".NETFramework,Version=v4.5"|  
|4.5.1|".NETFramework,Version=v4.5.1"|  
|4.5.2|".NETFramework,Version=v4.5.2"|  
|4.6|".NETFramework,Version=v4.6"|  
|4.6.1|".NETFramework,Version=v4.6.1"|  
|4.6.2|".NETFramework,Version=v4.6.2"|  
|4.7|".NETFramework,Version=v4.7"|
|4.7.1|".NETFramework,Version=v4.7.1"|
|4.7.2|".NETFramework,Version=v4.7.2"|

## <a name="example"></a>예제  
 다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다. 구성 파일을 앱에.NET Framework 4.7 대상으로 지정 함을 나타냅니다.  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

- [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [In-Process Side-by-Side 실행](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
