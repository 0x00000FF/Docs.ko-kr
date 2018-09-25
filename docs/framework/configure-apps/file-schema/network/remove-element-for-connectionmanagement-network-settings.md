---
title: '&lt;제거&gt; connectionManagement (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d249cc412a1638e62b57b4976adc23fdf8f36e80
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085542"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a>&lt;제거&gt; connectionManagement (네트워크 설정)에 대 한 요소
연결 관리 목록에서 IP 주소 또는 DNS 이름을 제거합니다.  
  
 \<configuration>  
\<system.net>  
\<connectionManagement >  
\<remove>  
  
## <a name="syntax"></a>구문  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`address`|IP 주소 또는 DNS 이름입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|네트워크 호스트에 대한 최대 연결 수를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `remove` 요소가 지정된 된 서버 연결 관리 목록 항목을 제거 합니다.  
  
 값을 `address` 특성 유효한 IP 주소 또는 호스트 이름 이어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 서버 www.adventure-works.com에 대 한 모든 연결 관리 목록 항목을 제거 하 고 www.contoso.com 서버에 대 한 연결 4 및 다른 모든 서버에 두 개의 연결을 사용 하도록 응용 프로그램을 구성 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
