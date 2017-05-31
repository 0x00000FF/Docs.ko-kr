---
title: "완화: CspParameters.ParentWindowHandle에 HWND 필요 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: 31898c86adc687b63a1b7f02eee98aae9b16c5f7
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>완화: CspParameters.ParentWindowHandle에 HWND 필요

.NET Framework 2.0에 도입된 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 속성을 사용하면 응용 프로그램에서 키에 액세스하는 데 필요한 UI(PIN 프롬프트 또는 동의 대화 상자)가 지정된 창에 대한 모달 자식 항목으로 열리도록 부모 창 핸들 값을 등록할 수 있습니다. .NET Framework 4.7을 대상으로 하는 응용 프로그램부터, 창 핸들(HWND)을 이 속성에 할당할 수 있습니다.

.NET Framework 4.6.2 이하 버전에서 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 속성에 할당된 값은 메모리에서 HWND 값의 위치를 나타내는 <xref:System.IntPtr>로 예상됩니다. Windows 7 및 이전 버전의 Windows 운영 체제에서는 이 속성을 `form.Handle`로 설정해도 아무 영향이 없지만 Windows 8 이상 버전에서는 "매개 변수가 잘못되었습니다."라는 메시지와 함께 <xref:System.Security.Cryptography>가 표시됩니다.

.NET Framework 4.7을 대상으로 하는 앱부터 다음과 같은 코드를 사용하여 Windows Forms 응용 프로그램에서 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>속성을 설정할 수 있습니다.

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>영향

부모 창 관계를 등록하려는 .NET Framework 4.7 이상을 대상으로 하는 응용 프로그램에서는 다음과 같은 간단한 형식을 사용하는 것이 좋습니다.

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>완화

올바른 값이 `form.Handle` 값을 포함하는 메모리 위치의 주소임을 확인한 개발자는 <xref:System.Security.AppContext> 스위치 `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle`을 `true`로 설정하여 이러한 동작 변경을 옵트아웃(opt out)할 수 있습니다.

- 프로그래밍 방식으로 <xref:System.Security.AppContext> 인스턴스의 호환성 스위치 설정

- 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

반대로 .NET Framework 4.7에사 실행되지만 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램에 대한 새로운 동작을 옵트인(opt in)하려는 사용자는 <xref:System.Security.AppContext> 스위치를 `false`로 설정할 수 있습니다.
 
## <a name="see-also"></a>참고 항목

[.NET Framework 4.7.1의 대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

