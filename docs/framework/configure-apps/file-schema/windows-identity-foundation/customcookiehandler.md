---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791731"
---
# <a name="customcookiehandler"></a>\<customCookieHandler>
사용자 지정 쿠키 처리기 형식을 설정합니다. 이 요소를 사용할 수만 있습니다 경우 합니다 `mode` 특성을 `<cookieHandler>` 요소는 "Custom" 합니다. 사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<customCookieHandler>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|파생 되는 사용자 지정 형식 지정을 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 합니다 `type` 특성을 참조 하십시오 [사용자 지정 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성 된 <xref:System.IdentityModel.Services.CookieHandler> 는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여 합니다.|  
  
## <a name="remarks"></a>설명  
 설정 하 여 사용자 지정 쿠키 처리기를 지정 하면를 `mode` 특성을 `<cookieHandler>` 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 하는 "Custom"으로 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소. 이 요소가 있을 수 없습니다 될 때 지정 되는 `mode` 특성은 "이 Chunked" 또는 "Default"로 설정 합니다. 사용자 지정 쿠키 처리기에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 합니다 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 형식의 사용자 지정 쿠키 처리기를 사용 하려면 SAM `MyNamespace.MyCustomCookieHandler`합니다.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.IdentityModel.Services.CookieHandler>
