---
title: WCF 분석 추적
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 006f8aa0bc2f32e43269aa83433e8ca7a773a1c9
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44494293"
---
# <a name="wcf-analytic-tracing"></a>WCF 분석 추적
이 샘플에는 Windows Communication Foundation (WCF) ETW에 기록 하는 분석 추적 스트림에 고유한 추적 이벤트를 추가 하는 방법을 보여 줍니다. [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]합니다. 분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다. 이 샘플에 사용 하는 방법을 보여 줍니다는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> WCF 서비스와 통합 하는 쓰기 이벤트에는 Api입니다.  
  
 에 대 한 자세한 내용은 합니다 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api 참조 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>합니다.  
  
 Windows에서 이벤트 추적에 대 한 자세한 내용은 참조 하세요 [디버깅 및 ETW를 사용한 성능 조정 개선](https://go.microsoft.com/fwlink/?LinkId=166488)합니다.  
  
## <a name="disposing-eventprovider"></a>EventProvider 삭제  
 이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다. WCF 서비스에 대 한 추적을 구현할 때 사용할 수 있는 가능성이 <xref:System.Diagnostics.Eventing.EventProvider>의 서비스의 수명에 대 한 리소스입니다. 이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다. 어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다. 관리 되지 않는 리소스를 삭제 하는 방법에 대 한 자세한 내용은 참조 하세요. [Dispose 메서드 구현](https://go.microsoft.com/fwlink/?LinkId=166436)합니다.  
  
## <a name="self-hosting-vs-web-hosting"></a>자체 호스팅 및 웹 호스팅  
 웹 호스팅 서비스에 대 한 WCF의 분석 추적은 추적을 내보내는 서비스를 식별 하는 데 사용 되는 "HostReference" 라는 필드를 제공 합니다. 확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다. 웹 호스트의 형식을 참조할 때 파이프를 '&#124;' 문자는 실제로 결과 표시 문자열에는 다음 중 하나일 수 있습니다.  
  
-   응용 프로그램이 루트에 없는 경우  
  
     \<사이트 이름 >\<ApplicationVirtualPath >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
-   응용 프로그램이 루트에 있는 경우  
  
     \<사이트 이름 >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
 자체 호스팅된 서비스에 대 한 WCF의 분석 추적은 "HostReference" 필드를 채우지 않습니다. 이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.  
  
## <a name="custom-event-details"></a>사용자 지정 이벤트 상세 정보  
 WCF의 ETW 이벤트 공급자 매니페스트는 서비스 코드 내에서 WCF 서비스 작성자 내보내도록 설계 된 세 가지 이벤트를 정의 합니다. 다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.  
  
|이벤트|설명|이벤트 ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.|301|  
|UserDefinedWarningOccurred|이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.|302|  
|UserDefinedErrorOccurred|서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.|303|  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 WCFAnalyticTracingExtensibility.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
     웹 브라우저에서 클릭 **Calculator.svc**합니다. 서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다. 이 URI를 복사합니다.  
  
4.  WCF 테스트 클라이언트 (WcfTestClient.exe)를 실행 합니다.  
  
     WCF 테스트 클라이언트 (WcfTestClient.exe)에 \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install > WcfTestClient.exe \Common7\IDE\ (기본 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 설치 디렉터리는 C:\Program Files\Microsoft Visual Studio 10.0).  
  
5.  WCF 테스트 클라이언트 내에서 선택 하 여 서비스를 추가할 **파일**를 차례로 **서비스 추가**합니다.  
  
     입력 상자에 엔드포인트 주소를 추가합니다.  
  
6.  클릭 **확인** 는 대화 상자를 닫습니다.  
  
     ICalculator 서비스가 아래 왼쪽된 창에서 추가 된 **내 서비스 프로젝트**합니다.  
  
7.  이벤트 뷰어 응용 프로그램을 엽니다.  
  
     서비스를 호출 하기 전에 이벤트 뷰어를 시작 하 고 WCF 서비스에서 내보낸 추적 이벤트에 대 한 이벤트 로그에서이 수신 대기 하는지 확인 합니다.  
  
8.  **시작** 메뉴에서 **관리 도구**를 차례로 **이벤트 뷰어**합니다. 사용 하도록 설정 합니다 **분석** 하 고 **디버그** 로그 합니다.  
  
9. 이동할 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **Applications and Services Logs**를 **Microsoft**를 **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램**를 선택 **뷰**를 차례로 **분석 및 디버그 로그 표시**합니다.  
  
     있는지 확인 합니다 **분석 및 디버그 로그 표시** 옵션을 선택 합니다. 사용 하도록 설정 합니다 **분석** 로그 합니다.  
  
     이동할 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **Applications and Services Logs**를 **Microsoft**를 **Windows**합니다  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용**합니다.  
  
10. WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.  
  
    1.  WCF 테스트 클라이언트에서 두 번 클릭 **add ()** ICalculator 서비스 노드에서 합니다.  
  
         합니다 **add ()** 메서드가 두 개의 매개 변수를 사용 하 여 오른쪽 창에 나타납니다.  
  
    2.  첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.  
  
    3.  클릭 **Invoke** 메서드를 호출 합니다.  
  
11. 로 이동 합니다 **이벤트 뷰어** 열려 있는 창입니다. 이동할 **이벤트 뷰어**, **Applications and Services Logs**합니다 **Microsoft**를 **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.  
  
12. 마우스 오른쪽 단추로 클릭 합니다 **분석** 노드와 선택 **새로 고침**합니다.  
  
     오른쪽 창에 이벤트가 나타납니다.  
  
13. ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.  
  
     이 이벤트를 내 보냈으므로 `Add()` ICalculator 서비스의 메서드에 같음 페이로드 및 "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>정리하려면(옵션)  
  
1.  오픈 **이벤트 뷰어**합니다.  
  
2.  이동할 **이벤트 뷰어**를 **Applications and Services Logs**를 **Microsoft**를 **Windows**를 차례로  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용 안 함**합니다.  
  
3.  이동할 **이벤트 뷰어**, **Applications and Services Logs**합니다 **Microsoft**를 **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 지우기**합니다.  
  
4.  클릭 **의 선택을 취소** 이벤트의 선택을 취소 합니다.  
  
## <a name="known-issue"></a>알려진 문제  
 알려진 문제가 합니다 **이벤트 뷰어** ETW 이벤트가 디코딩되지 실패할 수 있습니다. 라는 오류 메시지가 표시 될 수 있습니다: "이벤트 ID에 대 한 설명을 \<id > 원본에서 Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없습니다. 이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다. 설치 또는 로컬 컴퓨터의 구성 요소를 복구 합니다. " 이 오류가 발생 하는 경우 선택할 **새로 고침** 에서 합니다 **작업** 메뉴. 그러면 이벤트가 올바르게 디코딩됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](https://go.microsoft.com/fwlink/?LinkId=193959)
