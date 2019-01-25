---
title: '&lt;제거할&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d2e68a93840022776530bb9ed2f94a7505a8a3b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642794"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;제거할&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;
수신기를 제거 합니다 **수신기** 컬렉션입니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
\<remove>  
  
## <a name="syntax"></a>구문  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**name**|필수 특성입니다.<br /><br /> 제거할 수신기의 이름을 합니다 **수신기** 컬렉션입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다. 수신기는 추적 출력을 적절 한 대상입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`trace`|ASP.NET 추적 서비스를 구성합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  제거는 <xref:System.Diagnostics.DefaultTraceListener> 에서 `Listeners` 의 동작을 변경 하는 컬렉션의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>를 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드. 하지만 호출을 `Assert` 또는 `Fail` 메서드는 메시지 상자를 표시 하는 경우에 메시지 상자가 표시 되지 않습니다 일반적으로 결과 <xref:System.Diagnostics.DefaultTraceListener> 에 없는 경우는 `Listeners` 컬렉션입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 추적에서 기본 추적 수신기를 제거 하는 방법을 보여 줍니다 **수신기** 컬렉션입니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
