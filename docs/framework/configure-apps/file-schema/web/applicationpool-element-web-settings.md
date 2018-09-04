---
title: '&lt;applicationPool&gt; 요소 (웹 설정)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1a129abca5888120d03c42689ac825d768733a9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43489944"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;applicationPool&gt; 요소 (웹 설정)
ASP.NET에서 ASP.NET 응용 프로그램 통합된 모드에서 실행 중인 경우 프로세스 전반 동작을 관리 하는 데 사용 되는 구성 설정을 지정 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상 버전.  
  
> [!IMPORTANT]
>  ASP.NET 응용 프로그램에서 호스팅되는 경우 유일한 작업 지원이 요소 및 기능 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상 버전.  
  
 \<configuration>  
\<system.web > 요소 (웹 설정)  
\<응용 프로그램 풀 > 요소 (웹 설정)  
  
## <a name="syntax"></a>구문  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|ASP.NET에서는 CPU 당 동시 요청 수를 지정 합니다.|  
|`maxConcurrentThreadsPerCPU`|각 CPU에 대 한 응용 프로그램 풀에 대 한 동시 스레드를 실행할 수 있습니다를 지정 합니다. CPU 당 요청을 처리 하는 데 사용할 수 있는 관리 되는 스레드 수를 제한할 수 있기 때문에 ASP.NET 동시성을 제어 하는 대체 방법을 제공 합니다. 기본적으로이 설정은 0 이며 ASP.NET CLR 스레드 풀도 만들 수 있는 스레드 수를 제한 하지만 CPU 당 만들 수 있는 스레드 수가 제한 되지 않습니다입니다.|  
|`requestQueueLimit`|단일 프로세스에서 ASP.NET에 대해 대기할 수 있는 요청의 최대 수를 지정 합니다. 둘 이상의 ASP.NET 응용 프로그램을 단일 응용 프로그램 풀에서 실행 중인 응용 프로그램 풀의 모든 응용 프로그램에 대 한 요청의 누적 집합이이 설정은 하기 쉽습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|ASP.NET 응용 프로그램을 호스트와 상호 작용 하는 방법에 대 한 정보를 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 실행할 때 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드의 이후 버전에서이 요소 조합을 사용 하 여 응용 프로그램은 IIS 응용 프로그램 풀에 호스팅되는 경우 ASP.NET 스레드 및 큐 요청을 관리 하는 방법을 구성 합니다. IIS 6을 실행 하거나 실행 하면 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 클래식 모드에서 또는 ISAPI 모드에서 이러한 설정이 무시 됩니다.  
  
 `applicationPool` 설정은.NET Framework의 특정 버전에서 실행 되는 모든 응용 프로그램 풀에 적용 합니다. 설정을은 aspnet.config 파일에 포함 됩니다. 버전 2.0 및.NET framework 4.0에 대 한이 파일의 버전이 있습니다. (버전 3.0 및 3.5는.NET Framework의 공유 aspnet.config 파일 버전 2.0 사용 하 여.)  
  
> [!IMPORTANT]
>  실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 에서 [!INCLUDE[win7](../../../../../includes/win7-md.md)], 모든 응용 프로그램 풀에 대 한 별도 aspnet.config 파일을 구성할 수 있습니다. 이렇게 하면 각 응용 프로그램 풀에 대 한 스레드의 성능을 조정할 수 있습니다.  
  
 에 대 한는 `maxConcurrentRequestsPerCPU` 설정에서 기본 설정인 "5000"는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] CPU 당 5000 개 이상의 요청이 실제로 없으면 ASP.NET에 의해 제어 되는 요청 된 제한 해제 효과적으로 합니다. 기본 설정은 자동으로 CPU 당 동시성을 관리 하도록 CLR 스레드 풀에 따라 대신 달라 집니다. 비동기 요청 처리를 광범위 하 게 사용 하는 또는 네트워크 I/O에서 차단 된 많은 장기 실행 요청이 응용 프로그램의 향상 된 기본 제한에서 이익을 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다. 설정 `maxConcurrentRequestsPerCPU` 를 0으로 설정 하면 관리 되는 스레드 사용 해제 ASP.NET 요청을 처리 합니다. 응용 프로그램 IIS 응용 프로그램 풀에서 실행 되 면 IIS I/O 스레드 요청 유지 및 동시성 IIS 스레드 설정에 의해 제한 됩니다 따라서 합니다.  
  
 `requestQueueLimit` 설정은 동일한 방식으로 작동 합니다 `requestQueueLimit` 특성을 [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) ASP.NET 응용 프로그램에 대 한 Web.config 파일에 설정 된 요소입니다. 그러나 합니다 `requestQueueLimit` aspnet.config 파일의 설정 재정의 `requestQueueLimit` Web.config 파일에서 설정 합니다. 즉, 두 특성 모두 설정 된 경우 (기본적으로 true 이면)는 `requestQueueLimit` aspnet.config 파일에서 설정이 우선 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다음과 같은 경우에서 aspnet.config 파일에서 ASP.NET 프로세스 전반 동작을 구성 하는 방법을 보여 줍니다.  
  
-   응용 프로그램에서 호스트 되는 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 응용 프로그램 풀.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 통합된 모드에서 실행 됩니다.  
  
-   응용 프로그램을 사용 하는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 이상 버전.  
  
 예제에서 값은 기본값입니다.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|네임스페이스||  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있습니다.||  
  
## <a name="see-also"></a>참고 항목  
 [\<system.web> 요소(웹 설정)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
