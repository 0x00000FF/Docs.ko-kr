---
title: "동작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 동작
이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 추적 모델의 동작 추적에 대해 설명합니다.동작은 실패의 범위를 줄이도록 돕는 처리 단위입니다.동일한 동작에서 발생하는 오류는 직접적으로 관련됩니다.예를 들어 메시지 암호 해독이 실패하면 작업이 실패합니다.작업 실패와 메시지 암호 해독 실패 둘 다에 대한 추적은 동일한 동작에서 나타나며, 암호 해독 오류와 요청 오류 사이의 직접적인 상관 관계를 보여 줍니다.  
  
## 동작 추적 구성  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 처리 응용 프로그램에 대한 미리 정의된 동작을 제공합니다\([동작 목록](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md) 참조\).사용자 추적을 그룹화하기 위해 프로그래밍 방식으로 동작을 정의할 수도 있습니다.자세한 내용은 [사용자 코드 추적 내보내기](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)를 참조하십시오.  
  
 런타임에 동작 추적을 내보내려면 다음 구성 코드에 나타난 것처럼 `System.ServiceModel` 추적 소스, 또는 다른 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]나 사용자 지정 추적 소스에 대한 `ActivityTracing` 설정을 사용합니다.  
  
```  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 사용 중인 구성 요소 및 특성에 대한 자세한 내용은 [추적 구성](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) 항목을 참조하십시오.  
  
## 동작 보기  
 [Service Trace Viewer 도구\(SvcTraceViewer.exe\)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)에서 동작과 해당 유틸리티를 볼 수 있습니다.ActivityTracing을 사용하도록 설정하면 이 도구에서 추적을 사용하여 동작을 기준으로 추적을 정렬합니다.추적 전송을 볼 수도 있습니다.추적 전송은 여러 가지 동작이 서로 어떻게 관련되는지를 나타냅니다.다른 동작이 시작되게 한 특정 동작을 볼 수 있습니다.예를 들어 메시지 요청이 보안 대화 토큰을 가져오기 위해 보안 핸드셰이크를 시작합니다.  
  
### Service Trace Viewer에서 동작 상호 연결  
 Service Trace Viewer 도구는 다음과 같이 동작의 두 가지 보기를 제공합니다.  
  
-   **목록** 보기: 동작 ID를 사용하여 서로 다른 프로세스 간에 추적을 직접적으로 관련시킵니다.서로 다른 프로세스\(예: 클라이언트, 서비스\)에서 파생되었으나 동일한 동작 ID를 가진 추적은 동일한 동작으로 그룹화됩니다.그러므로 서비스에서 발생하는 오류 및 이로 인해 발생하는 클라이언트의 오류는 Service Trace Viewer 도구의 동일한 동작 보기에 모두 표시됩니다.  
  
-   **그래프** 보기: 동작을 프로세스별로 그룹화합니다.이 보기에서는 동일한 동작 ID를 가진 클라이언트와 서비스의 추적이 각각 서로 다른 동작에 속해 있습니다.서로 다른 프로세스에서 동일한 동작 ID를 가진 동작을 서로 관련시키기 위해 이 도구에서는 관련된 동작 간의 메시지 흐름을 보여 줍니다.  
  
 자세한 내용 및 Service Trace Viewer 도구의 그래픽 보기를 보려면 [Service Trace Viewer 도구\(SvcTraceViewer.exe\)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 및 [Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)을 참조하십시오.  
  
## 동작 범위 정의  
 동작은 디자인 타임에 정의되며 작업의 논리 단위를 나타냅니다.동일한 동작 식별자로 내보낸 추적은 동일한 동작의 일부이므로 직접적으로 관련됩니다.동작\(예: 요청\)이 끝점 경계를 넘나들 수 있기 때문에 동작에 대해 두 가지 범위가 정의됩니다.  
  
-   응용 프로그램별 `Global` 범위.이 범위에서는 동작이 128비트 gAId\(Globally Unique Activity Identifier\)에 의해 식별됩니다.gAid는 끝점 간에 전파됩니다.  
  
-   끝점별 `Local` 범위.이 범위에서는 동작이 동작 추적 및 프로세스 ID를 내보내는 추적 소스 이름과 함께 gAId에 의해 식별됩니다.이 세 가지가 로컬 동작 ID인 lAId를 구성합니다.lAId는 동작의 \(로컬\) 경계를 정의하는 데 사용됩니다.  
  
## 추적 스키마  
 추적은 Microsoft 플랫폼을 통해 스키마를 사용하여 내보낼 수 있습니다.일반적으로 사용되는 스키마는 “e2e”\(“종단 간”\)입니다.이 스키마에는 128비트 식별자\(gAId\), 추적 소스 이름 및 프로세스 ID가 포함됩니다.관리 코드에서는 <xref:System.Diagnostics.XmlWriterTraceListener>가 E2E 스키마에서 추적을 내보냅니다.  
  
 개발자는 TLS\(스레드 로컬 저장소\)에서 Guid를 사용하여 <xref:System.Diagnostics.CorrelationManager.ActivityId%2A> 속성을 설정함으로써 추적과 함께 내보내는 AID를 설정할 수 있습니다.다음은 이에 대한 예입니다.  
  
```  
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```  
  
 다음 예제에서와 같이 TLS에서의 gAId 설정은 추적 소스를 사용하여 추적을 내보낼 때 확인할 수 있습니다.  
  
```  
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 내보낸 추적에는 현재 TLS에 있는 gAId, 매개 변수로 추적 소스의 생성자에게 전달된 추적 소스 이름 및 현재 프로세스 ID가 포함됩니다.  
  
## 동작 수명  
 매우 엄격한 의미에서 동작의 증명은 내보낸 추적에서 동작 ID를 처음 사용할 때 시작되고, 내보낸 추적에서 동작 ID를 마지막으로 사용할 때 끝납니다.<xref:System.Diagnostics>에서 미리 정의된 추적 형식\(Start 및 Stop\)을 제공하여 동작 수명 경계를 명시적으로 표시합니다.  
  
-   Start: 동작의 시작을 나타냅니다.“Start” 추적은 새 처리 중요 시점의 시작에 대한 레코드를 제공합니다.여기에는 지정된 프로세스의 지정된 추적 소스에 대한 새 동작 ID가 포함됩니다. 단, 동작 ID가 끝점을 통해 전파되는 경우는 예외로, 이 경우에는 끝점별로 하나의 "Start"가 표시됩니다.새 동작의 시작에 대한 예제에는 처리에 대한 새 스레드 만들기 또는 새 public 메서드 입력이 포함됩니다.  
  
-   Stop: 동작의 종료를 나타냅니다.“Stop” 추적은 기존 처리의 중요 시점 종료에 대한 레코드를 제공합니다.여기에는 지정된 프로세스의 지정된 추적 소스에 대한 기존 동작 ID가 포함됩니다. 단, 동작 ID가 끝점을 통해 전파되는 경우는 예외로, 이 경우에는 끝점별로 하나의 "Stop"이 표시됩니다.동작 중지에 관한 예제에는 처리 스레드 종료 또는 시작이 “Start” 추적으로 표시된 메서드 종료 등이 포함됩니다.  
  
-   Suspend: 동작 처리가 일시 중단됨을 나타냅니다.“Suspend” 추적에는 처리가 나중에 다시 시작되도록 하는 기존 동작 ID가 포함됩니다.현재 추적 소스에서 Suspend 및 Resume 이벤트 사이에 이 동작 ID와 함께 내보낸 추적이 없습니다.예제에는 외부 라이브러리 함수로 호출할 때나 I\/O 완료 포트와 같은 리소스를 대기할 때 동작을 일시 중지하는 작업이 포함됩니다.  
  
-   Resume: 동작을 다시 처리하기 시작함을 나타냅니다.“Resume” 추적에는 현재 추적 소스로부터 마지막으로 내보낸 추적이 “Suspend” 추적인 기존 동작 ID가 포함됩니다.예제에는 호출로부터 외부 라이브러리 함수로 반환하는 경우 또는 I\/O 완료 포트와 같은 리소스를 통해 처리를 다시 시작하기 위해 신호를 받는 경우가 포함됩니다.  
  
-   Transfer: 일부 동작은 다른 동작에 의해 유발되거나 다른 동작과 관련이 있으므로, “Transfer” 추적을 통해 동작을 다른 동작과 연관시킬 수 있습니다.Transfer는 한 동작이 다른 동작으로 리디렉션된 관계를 기록합니다.  
  
 Start 및 Stop 추적은 상관 관계에 중요하지 않습니다.그러나 성능 향상, 프로파일링 및 동작 범위의 유효성 검사에 도움이 될 수 있습니다.  
  
 도구에서는 이러한 형식을 사용하여 동일한 동작의 관련 이벤트 또는 관련 동작에서의 이벤트\(도구가 Transfer 추적을 따를 경우\)를 즉각적으로 찾기 위해 추적 로그 탐색을 최적화합니다.예를 들어 도구는 Start\/Stop 추적을 볼 때 제공된 동작에 대한 로그의 구문 분석을 중지합니다.  
  
 이러한 추적 형식은 프로파일링에도 사용할 수 있습니다.시작 및 중지 마커 간에 사용되는 리소스는 포함된 논리 동작을 비롯하여 동작의 포괄 시간을 나타냅니다.Suspend 추적과 Resume 추적 간의 시간 차이를 구하면 실제 동작 시간을 알 수 있습니다.  
  
 또한 Stop 추적은 특히 구현된 동작의 범위에 대한 유효성을 검사하는 데 유용합니다.처리되는 일부 추적이 주어진 동작 내에서가 아니라 Stop 추적 이후에 나타난다면 이는 코드 오류일 수 있습니다.  
  
## ActivityTracing 사용 지침  
 다음은 ActivityTracing 추적\(Start, Stop, Suspend, Resume 및 Transfer\) 사용에 대한 지침입니다.  
  
-   추적은 트리가 아닌 리디렉션된 순환 그래프입니다.동작을 생성한 동작에 대한 제어를 반환할 수 있습니다.  
  
-   동작은 시스템 관리자 또는 지원 가능성과 관련하여 의미 있는 처리 경계를 나타냅니다.  
  
-   클라이언트와 서버 둘 다에 있는 각 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 메서드는 새 동작을 시작하고 작업이 완료된 후에 새 작업을 끝내고 앰비언트 동작으로 돌아가도록 하는 데 사용됩니다.  
  
-   연결 수신 대기 또는 메시지 대기와 같은 장기 실행\(진행 중\) 동작은 해당 시작\/중지 마커로 표시됩니다.  
  
-   메시지 수신 또는 처리에 의해 트리거된 동작은 추적 경계로 표시됩니다.  
  
-   동작은 동작을 나타내며 반드시 개체를 나타내지는 않습니다.동작은 "이는..\(의미 있는 추적 내보내기가 발생할 때\) 발생했습니다."로 해석되어야 합니다.  
  
## 참고 항목  
 [추적 구성](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)   
 [Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [종단 간 추적 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)   
 [Service Trace Viewer 도구\(SvcTraceViewer.exe\)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)   
 [사용자 코드 추적 내보내기](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)