---
title: '&lt;system.Net&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 82e022e28d3559791be3236fb80081807426a456
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192540"
---
# <a name="ltsystemnetgt-element-network-settings"></a>&lt;system.Net&gt; 요소 (네트워크 설정)
.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.  
  
 \<configuration>  
\<system.net>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|인터넷 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|인터넷 호스트에 대 한 연결의 최대 수를 지정 합니다.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|단순 메일 전송 프로토콜 (SMTP) 메일 보내기 옵션을 구성 합니다.|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|클래스에 대 한 기본 네트워크 옵션을 구성 합니다 <xref:System.Net> 및 관련 자식 네임 스페이스입니다.|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|인터넷 호스트의 정보를 요청 하는 데는 모듈을 지정 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[구성](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|모든 네임 스페이스에 대 한 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 요소에는 클래스에 대 한 설정이 포함 되어 있습니다.는 <xref:System.Net> 및 관련 자식 네임 스페이스입니다. 설정을 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 호스트에서 정보를 받는 데 인터넷 요청 모듈을 구성합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 사용 하는 일반적인 구성에서는 <xref:System.Net> 클래스입니다.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
