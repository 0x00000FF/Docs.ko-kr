---
title: <add> AuthenticationModules (네트워크 설정)에 대 한 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: a46e6af97f37974805812fb0d19801d618eee4d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105874"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a>\<추가 > authenticationModules (네트워크 설정)에 대 한 요소
응용 프로그램에 인증 모듈을 추가합니다.  
  
 \<configuration>  
\<system.net>  
\<authenticationModules>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`type`|정규화 된 형식 이름을 (나타난를 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (나타난는 <xref:System.Reflection.Assembly.FullName%2A> 속성)을 쉼표로 구분 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 `add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다. 인증 모듈 목록에 추가 된 순서 대로 호출 됩니다.  
  
 에 대 한 값을 `type` 특성은 유효한 형식 이름 및 쉼표로 구분 하 여 해당 어셈블리 이름 이어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 인증 모듈입니다. 지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
