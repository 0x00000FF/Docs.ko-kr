---
title: 추적 구성
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: c5079237ff4c97dd9ef164061dc5e7499c1d6e38
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635995"
---
# <a name="configuring-tracing"></a>추적 구성
이 항목에서는 추적을 사용하고, 추적을 내보내도록 추적 소스를 구성하고, 추적 수준을 설정하고, 엔드투엔드 추적 상관 관계를 지원하도록 동작 추적 및 전파를 설정하고, 추적에 액세스하도록 추적 수신기를 설정하는 방법에 대해 설명합니다.  
  
 프로덕션 환경 또는 디버깅 환경에서 설정 권장 사항을 추적하려면 [추적 및 메시지 로깅에 대한 권장 설정을](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)참조하십시오.  
  
> [!IMPORTANT]
> Windows 8에서 애플리케이션이 추적 로그를 생성할 수 있도록 하려면 애플리케이션을 승격된 상태(관리자 권한으로 실행)로 실행해야 합니다.  
  
## <a name="enabling-tracing"></a>추적 사용  
 WCF(Windows 통신 재단)는 진단 추적을 위해 다음 데이터를 출력합니다.  
  
- 작업 호출, 코드 예외, 경고 및 기타 중요한 처리 이벤트와 같은 응용 프로그램의 모든 구성 요소에서 프로세스 이정표에 대한 추적입니다.  
  
- 추적 기능 오작동 시 Windows 오류 이벤트. [이벤트 로깅](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)을 참조하십시오.  
  
 WCF 추적은 위에 <xref:System.Diagnostics>구축됩니다. 추적을 사용하려면 구성 파일 또는 코드에 추적 소스를 정의해야 합니다. WCF는 각 WCF 어셈블리에 대한 추적 소스를 정의합니다. `System.ServiceModel` 추적 소스는 가장 일반적인 WCF 추적 소스이며 전송 입력/이탈에서 사용자 코드 입력/나오기까지 WCF 통신 스택 전반에 걸쳐 이정표를 처리하는 레코드입니다. `System.ServiceModel.MessageLogging` 추적 소스는 시스템을 통해 이동하는 모든 메시지를 기록합니다.  
  
 추적은 기본적으로 사용되지 않습니다. 추적을 활성화하려면 추적 수신기를 만들고 구성에서 선택한 추적 소스에 대해 "끄기"가 아닌 추적 수준을 설정해야 합니다. 그렇지 않으면 WCF는 추적을 생성하지 않습니다. 수신기를 지정하지 않으면 추적이 자동으로 사용되지 않습니다. 수신기는 정의되었지만 수준이 지정되지 않은 경우 수준이 기본적으로 "Off"로 설정됩니다. 이 설정은 추적이 내보내지지 않음을 의미합니다.  
  
 사용자 지정 작업 호출기와 같은 WCF 확장성 지점을 사용하는 경우 고유한 추적을 내보내야 합니다. 확장성 점을 구현하는 경우 WCF가 더 이상 기본 경로에서 표준 추적을 내볼 수 없기 때문입니다. 추적을 내보내 수동 추적 지원을 구현하지 않으면 예상하는 추적이 표시되지 않을 수 있습니다.  
  
 웹 호스팅 응용 프로그램에 대한 Web.config 또는 자체 호스팅 응용 프로그램에 대한 Appname.exe.config와 같은 응용 프로그램의 구성 파일을 편집하여 추적을 구성할 수 있습니다. 다음은 이러한 편집의 예제입니다. 이러한 설정에 대한 자세한 내용은 "추적 을 사용하도록 추적 리스너 구성" 섹션을 참조하십시오.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"
                   type="System.Diagnostics.XmlWriterTraceListener"
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
> Visual Studio에서 WCF 서비스 프로젝트의 구성 파일을 편집하려면 웹 호스팅 응용 프로그램에 대한 Web.config 또는 **솔루션 탐색기에서**자체 호스팅응용 프로그램에 대한 Appname.exe.config와 같은 응용 프로그램의 구성 파일을 마우스 오른쪽 단추로 클릭합니다. 그런 다음 **WCF 구성 컨텍스트** 메뉴 항목 편집을 선택합니다. 이렇게 하면 그래픽 사용자 인터페이스를 사용하여 WCF 서비스에 대한 구성 설정을 수정할 수 있는 [구성 편집기 도구(SvcConfigEditor.exe)가](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)시작됩니다.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>추적을 내보내도록 추적 소스 구성  
 WCF는 각 어셈블리에 대한 추적 소스를 정의합니다. 어셈블리 내에 생성된 추적은 해당 소스에 대해 정의된 수신기를 통해 액세스합니다. 다음 추적 소스가 정의됩니다.  
  
- System.ServiceModel: WCF 처리의 모든 단계를 기록하며 구성을 읽을 때마다 전송, 보안 처리, 사용자 코드로 메시지가 전달되는 등 메시지가 처리됩니다.  
  
- System.ServiceModel.MessageLogging: 시스템을 통해 이동하는 모든 메시지를 기록합니다.  
  
- System.IdentityModel  
  
- System.ServiceModel.Activation  
  
- System.IO.Log: CLFS(Common Log File System)에 대한 .NET Framework 인터페이스에 대해 기록합니다.  
  
- System.Runtime.Serialization: 개체를 읽거나 쓸 때 기록됩니다.  
  
- CardSpace  
  
 다음 구성 예제에 표시된 대로 같은(공유) 수신기를 사용하도록 각 추적 소스를 구성할 수 있습니다.  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 또한, 다음 예제처럼 사용자 정의 추적 소스를 추가하여 사용자 코드 추적을 내보낼 수 있습니다.  
  
```xml  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />
</system.diagnostics>  
```  
  
 사용자 정의 추적 소스를 만드는 데 대한 자세한 내용은 [추적 확장](../../../../../docs/framework/wcf/samples/extending-tracing.md)을 참조하십시오.  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>추적을 사용하도록 추적 수신기 구성  
 런타임시 WCF는 추적 데이터를 수신기에 공급하여 데이터를 처리합니다. WCF는 출력에 사용하는 <xref:System.Diagnostics>형식이 다른 에 대해 미리 정의된 여러 수신기를 제공합니다. 사용자 지정 수신기 형식을 추가할 수도 있습니다.  
  
 `add`를 사용하여 사용할 추적 수신기의 이름과 형식을 지정할 수 있습니다. 예제 구성에서는 수신기 이름을 `traceListener`로 지정하고 표준 .NET Framework 추적 수신기(`System.Diagnostics.XmlWriterTraceListener`)를 사용할 형식으로 추가했습니다. 각 소스에 대한 추적 수신기를 여러 개 추가할 수 있습니다. 추적 수신기가 파일로 추적을 내보내는 경우에는 구성 파일에 출력 파일 위치와 이름을 지정해야 합니다. 이 작업을 수행하려면 `initializeData`를 해당 수신기의 파일 이름으로 설정합니다. 파일 이름을 지정하지 않으면 사용된 수신기 형식에 따라 임의 파일 이름이 생성됩니다. <xref:System.Diagnostics.XmlWriterTraceListener>가 사용되면 확장명이 없는 파일 이름이 생성됩니다. 사용자 지정 수신기를 구현하는 경우 이 특성을 사용하여 파일 이름 이외의 초기화 데이터를 받을 수도 있습니다. 예를 들면 이 특성에 대한 데이터베이스 식별자를 지정할 수 있습니다.  
  
 원격 데이터베이스와 같은 연결을 통해 추적을 보내도록 사용자 지정 추적 수신기를 구성할 수 있습니다. 애플리케이션 배포자인 경우 원격 컴퓨터의 추적 로그에 적절한 액세스 제어를 적용해야 합니다.  
  
 추적 수신기를 프로그래밍 방식으로 구성할 수도 있습니다. 자세한 내용은 [추적 리스너 만들기 및 초기화 및](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) 사용자 지정 [TraceListener 만들기](https://docs.microsoft.com/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)방법을 참조하십시오.  
  
> [!CAUTION]
> `System.Diagnostics.XmlWriterTraceListener`는 스레드로부터 안전하지 않으므로 추적을 출력할 때 추적 소스가 리소스를 단독으로 잠글 수도 있습니다. 여러 스레드에서 이 수신기를 사용하도록 구성된 추적 소스로 추적을 출력하면 리소스 경합이 발생할 수 있으며, 이로 인해 성능이 크게 저하될 수 있습니다. 이 문제를 해결하려면 스레드로부터 안전한 사용자 지정 수신기를 구현해야 합니다.  
  
## <a name="trace-level"></a>추적 수준  
 추적 수준은 추적 소스의 `switchValue` 설정에 의해 제어됩니다. 다음 표에서는 사용할 수 있는 추적 수준에 대해 설명합니다.  
  
|추적 수준|추적 이벤트의 특성|추적 이벤트의 내용|추적 이벤트|사용자 대상|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|꺼짐|해당 없음|해당 없음|내보낸 추적이 없습니다.|해당 없음|  
|위험|"부정적인" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.||다음을 포함하여 처리되지 않은 예외를 기록합니다.<br /><br /> - 아웃오브메모리예외<br />- ThreadAbortException (CLR은 모든 스레드AbortExceptionHandlerHandler를 호출합니다)<br />- 스택 오버 플로우 예외 (잡을 수 없습니다)<br />- 구성 오류예외<br />- 세예외<br />- 응용 프로그램 시작 오류<br />- 실패 패스트 이벤트<br />- 시스템 정지<br />- 포이즌 메시지: 응용 프로그램이 실패하는 메시지 추적.|관리자<br /><br /> 애플리케이션 개발자|  
|Error|"부정적인" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.|예기치 않은 처리가 발생했습니다. 애플리케이션이 예상한 대로 작업을 수행하지 못했습니다. 그러나 애플리케이션이 여전히 실행 중입니다.|모든 예외가 기록됩니다.|관리자<br /><br /> 애플리케이션 개발자|  
|Warning|"부정적인" 이벤트: 예기치 않은 처리 또는 오류 조건을 나타내는 이벤트입니다.|문제가 발생했거나 발생할 수도 있지만 애플리케이션이 여전히 올바르게 작동합니다. 그러나 계속 올바르게 작동하지 않을 수도 있습니다.|- 응용 프로그램이 제한 설정에서 허용하는 것보다 더 많은 요청을 받고 있습니다.<br />- 수신 큐가 최대 구성 용량에 가깝습니다.<br />- 시간 초과가 초과되었습니다.<br />- 자격 증명이 거부됩니다.|관리자<br /><br /> 애플리케이션 개발자|  
|정보|"긍정적인" 이벤트: 성공적인 이정표를 표시하는 이벤트|애플리케이션이 올바르게 작동하는지 여부에 관계 없이 애플리케이션 실행의 중요한 중요 시점과 성공적인 중요 시점입니다.|일반적으로 시스템 상태 모니터링 및 진단, 성능 측정 또는 프로파일링에 유용한 메시지가 생성됩니다. 용량 계획 및 성능 관리에 이러한 정보를 사용할 수 있습니다.<br /><br /> - 채널이 생성됩니다.<br />- 끝점 리스너가 만들어집니다.<br />- 메시지가 입력 / 나뭇잎 전송.<br />- 보안 토큰이 검색됩니다.<br />- 구성 설정을 읽습니다.|관리자<br /><br /> 애플리케이션 개발자<br /><br /> 제품 개발자|  
|자세히|'긍정적인' 이벤트: 성공적인 이정표를 표시하는 이벤트입니다.|사용자 코드와 서비스 모두에 대한 하위 수준 이벤트가 내보전됩니다.|일반적으로 디버깅 또는 애플리케이션 최적화에 이 수준을 사용할 수 있습니다.<br /><br /> - 이해 메시지 헤더.|관리자<br /><br /> 애플리케이션 개발자<br /><br /> 제품 개발자|  
|ActivityTracing||처리 동작과 구성 요소 간의 흐름 이벤트입니다.|이 수준에서 관리자와 개발자가 같은 애플리케이션 도메인의 애플리케이션을 서로 연결할 수 있습니다.<br /><br /> - 시작/중지와 같은 활동 경계에 대한 추적입니다.<br />- 전송에 대한 흔적.|모두|  
|모두||애플리케이션이 올바르게 작동할 수 있습니다. 모든 이벤트를 내보냅니다.|앞의 이벤트 모두|모두|  
  
 Verbose에서 Critical까지의 수준은 서로 위에 쌓입니다. 즉, 각 추적 수준에 Off 수준을 제외한 위의 모든 수준이 포함됩니다. 예를 들어, Warning 수준에서 수신 대기하는 수신기는 Critical, Error 및 Warning 추적을 수신합니다. 모두 수준에는 Verbose에서 Critical까지의 이벤트와 동작 추적 이벤트가 포함됩니다.  
  
> [!CAUTION]
> Information, Verbose 및 ActivityTracing 수준은 컴퓨터에서 사용 가능한 모든 리소스를 모두 사용한 경우 메시지 처리량을 줄일 수도 있는 여러 가지 추적을 생성합니다.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>상관 관계를 위한 동작 추적 및 전파 구성  
 ph x="1" /&gt; 특성에 대한 지정된 `switchValue` 값은 엔드포인트 내에서 동작 경계와 전송에 대한 추적을 내보내는 동작 추적을 활성화하는 데 사용됩니다.  
  
> [!NOTE]
> WCF에서 특정 확장성 기능을 사용하면 활동 추적이 <xref:System.NullReferenceException> 활성화된 시기를 얻을 수 있습니다. 이 문제를 해결하려면 애플리케이션의 구성 파일을 확인하고 추적 소스의 `switchValue` 특성이 `activityTracing`으로 설정되지 않았는지 확인합니다.  
  
 ph x="1" /&gt; 특성은 동작을 메시지 교환에 참여하는 다른 엔드포인트에 전파해야 하는지 여부를 나타냅니다. 이 값을 `true`로 설정하여 두 엔드포인트에서 생성된 추적 파일을 가져오고 한 엔드포인트의 추적 집합이 다른 엔드포인트의 추적 집합으로 이동한 방법을 확인할 수 있습니다.  
  
 활동 추적 및 전파에 대한 자세한 내용은 [전파](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md)를 참조하십시오.  
  
 부울 `ActivityTracing` 값과 부울 값은 `propagateActivity` System.ServiceModel 추적 소스에 적용됩니다. 이 `ActivityTracing` 값은 WCF 또는 사용자 정의 소스를 포함한 모든 추적 소스에도 적용됩니다.  
  
 `propagateActivity` 특성은 사용자 정의 추적 소스에 사용할 수 없습니다. 사용자 코드 동작 ID 전파를 위해 ServiceModel `ActivityTracing`은 설정하지 않고 ServiceModel `propagateActivity` 특성은 `true`로 설정해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
- [방법: 추적 수신기 만들기 및 초기화](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)
- [Creating a Custom TraceListener](https://docs.microsoft.com/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)
