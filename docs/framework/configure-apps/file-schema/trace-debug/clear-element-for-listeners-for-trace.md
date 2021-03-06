---
title: <clear>에 <listeners> 대 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153544"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<추적> \<> 청취자를 위한 \<지우기> 요소
추적의 `Listeners` 컬렉션을 지웁니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클리어>**

## <a name="syntax"></a>구문  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
|`listeners`|메시지를 수집, 저장 및 라우팅하는 리스너가 포함됩니다. 리스너들은 추적 출력을 적절한 대상으로 지시합니다.|  
  
## <a name="remarks"></a>설명  
 요소는 `<clear>` 추적에 대 한 `Listeners` 컬렉션에서 모든 수신기를 제거 합니다. 요소를 사용하기 `<clear>` 전에 요소를 사용하여 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다. `<add>`  
  
 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 속성 ()에서`System.Diagnostics.Trace.Listeners.Clear()`메서드를 `Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 호출하여 프로그래밍 방식으로 컬렉션을 지울 수 있습니다.  
  
 이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
> [!NOTE]
> `<clear>` 요소는 <xref:System.Diagnostics.DefaultTraceListener> `Listeners` 컬렉션에서 를 제거하여 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>의 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 동작을 변경합니다. 또는 `Fail` `Assert` 메서드를 호출하면 일반적으로 메시지 상자가 표시됩니다. 그러나 컬렉션에 없는 경우 메시지 <xref:System.Diagnostics.DefaultTraceListener> 상자가 `Listeners` 표시 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 `<clear>` 예제에서는 `<add>` 추적을 위해 `console` `Listeners` 컬렉션에 수신기를 추가하기 위해 요소를 사용하기 전에 요소를 사용하는 방법을 보여 주며 있습니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [추적 및 디버그 설정 스키마](index.md)
- [\<>제거](remove-element-for-listeners-for-trace.md)
- [추적 수신기](../../../debug-trace-profile/trace-listeners.md)
