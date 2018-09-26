---
title: '&lt;제거할&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;원본&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5cfed154af93d72f69efc24c6475b432d0963580
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47188939"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;제거할&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;원본&gt;
추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<원본 >  
\<원본 >  
\<수신기 >  
\<remove>  
  
## <a name="syntax"></a>구문  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 제거할 수신기의 이름을 합니다 `Listeners` 컬렉션입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
|`source`|추적 메시지를 시작하는 추적 소스를 지정합니다.|  
|`listeners`|수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `<remove>` 요소에서 지정 된 수신기를 제거 합니다 `Listeners` 추적 소스에 대 한 컬렉션입니다.  
  
 요소를 제거할 수 있습니다는 `Listeners` 호출 하 여 프로그래밍 방식으로 추적 소스에 대 한 컬렉션을 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 메서드를 <xref:System.Diagnostics.TraceSource.Listeners%2A> 의 속성을 <xref:System.Diagnostics.TraceSource> 인스턴스.  
  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는 `<remove>` 요소를 사용 하기 전에 `<add>` 수신기를 추가 하는 요소 `console` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
