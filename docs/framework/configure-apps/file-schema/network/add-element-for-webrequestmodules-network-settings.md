---
title: webRequestModules의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f99c5b0dc7eab57d4e3e86f49dbbb3228c7b7d8b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664215"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<webRequestModules (네트워크 설정)에 대 한 > 요소 추가
응용 프로그램에 사용자 지정 웹 요청 모듈을 추가 합니다.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`prefix`|이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.|  
|`type`|이 웹 요청 모듈을 구현 하는 정규화 <xref:System.Type.FullName%2A> 된 형식 이름 (속성으로 표시 됨)과 <xref:System.Reflection.Assembly.FullName%2A> 쉼표로 구분 된 어셈블리 이름 (속성으로 표시 됨)입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 특성 `prefix` 은 지정 된 웹 요청 모듈을 사용 하는 URI 접두사를 정의 합니다. 웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리 하기 위해 등록 되지만 특정 서버 또는 서버의 경로에 대 한 요청을 처리 하도록 등록할 수 있습니다.  
  
 웹 요청 모듈은 URI 일치 접두사가 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 메서드에 전달 될 때 생성 됩니다.  
  
 `prefix` 특성의 값은 유효한 URI의 선행 문자 여야 합니다. 예를 들어 `http` 또는 `http://www.contoso.com`로 이름을 지정할 수 있습니다.
  
 `type` 특성 값은 쉼표로 구분 된 유효한 형식 이름 및 해당 어셈블리 이름 이어야 합니다.
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 HTTP에 대 한 사용자 지정 웹 요청 모듈을 등록 합니다. Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Net.WebRequest>
- [네트워크 설정 스키마](index.md)
