---
title: DataContractJsonSerializer로 제어 문자 직렬화
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: 209f7827e61ef72de1d64fad46dc9f241fa6edef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346579"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>완화: DataContractJsonSerializer로 제어 문자 직렬화

.NET Framework 4.7부터 제어 문자가 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>로 serialize되는 방식이 ECMAScript V6 및 V8에 맞게 변경되었습니다. 
 
## <a name="impact"></a>영향

.NET framework 4.6.2 이하 버전에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>가 ECMAScript V6 및 V8 표준과 호환되는 방식으로 `\b`, `\f`, `\t` 등의 일부 특수 제어 문자를 serialize하지 않았습니다.

.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이러한 제어 문자의 serialization이 ECMAScript V6 및 V8과 호환됩니다. 다음 API가 영향을 받습니다.

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a>완화

.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이 동작이 기본적으로 사용되도록 설정됩니다.

이 동작을 원치 않는 경우 app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 이 기능을 옵트아웃(opt out)할 수 있습니다.

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>참조

- [애플리케이션 호환성](application-compatibility.md)
