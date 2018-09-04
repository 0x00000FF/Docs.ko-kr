---
title: Basic AJAX Service
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: d8da6469101511b6b5a9ce19a11f1e5e3fe9d83e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524885"
---
# <a name="basic-ajax-service"></a>Basic AJAX Service
이 샘플에는 Windows Communication Foundation (WCF)를 사용 하 여 기본 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스 (웹 브라우저 클라이언트에서 JavaScript 코드를 사용 하 여 액세스할 수 있는 서비스)를 만드는 방법을 보여 줍니다. 이 서비스에서는 HTTP GET 요청에 응답하고 JSON(JavaScript Object Notation) 데이터 형식을 응답에 사용하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 사용됩니다.  
  
 WCF의 AJAX 지원 ASP.NET AJAX를 통해 사용에 최적화 된는 `ScriptManager` 제어 합니다. ASP.NET AJAX와 함께 WCF를 사용 하 여 예제를 참조 합니다 [AJAX 샘플](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 코드에서는 서비스가 HTTP GET 요청에 응답하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 `Add` 작업에 적용됩니다. 이 코드에서는 간편하게 GET을 사용합니다. HTTP GET 요청은 모든 웹 브라우저에서 생성할 수 있습니다. 또한 GET을 사용하여 캐싱을 사용하도록 설정할 수 있습니다. `WebGetAttribute` 특성이 없을 경우 HTTP POST가 기본값입니다.  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 샘플 .svc 파일은 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 표준 끝점을 서비스에 추가하는 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 사용합니다. 엔드포인트는 .svc 파일을 기준으로 빈 주소에서 구성됩니다. 즉, 서비스 주소가 http://localhost/ServiceModelSamples/service.svc, 작업 이름이 아닌 추가 접미사를 사용 하 여 합니다.  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <xref:System.ServiceModel.Description.WebScriptEndpoint>는 ASP.NET AJAX 클라이언트 페이지에서 서비스에 액세스할 수 있도록 하기 위해 미리 구성됩니다. Web.config의 다음 섹션은 엔드포인트에 대한 추가 구성 변경 작업을 수행하는 데 사용할 수 있으며 추가 변경이 필요하지 않은 경우 제거할 수 있습니다.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>는 서비스의 기본 데이터 형식을 XML 대신 JSON으로 설정합니다. 서비스를 호출 하려면 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 후 설치를 완료 하 고이 항목의 뒷부분에 나와 있는 단계를 작성 합니다. 이 테스트 기능은 HTTP GET 요청을 사용해 설정됩니다.  
  
 클라이언트 웹 페이지 SimpleAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다. `ScriptManager` 컨트롤은 서비스에 대한 프록시를 JavaScript를 통해 액세스할 수 있게 만드는 데 사용됩니다.  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 다음 JavaScript 코드를 사용하여 로컬 프록시가 인스턴스화되고 작업이 호출됩니다.  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 서비스 호출에 성공할 경우 `onSuccess` 처리기가 호출되고 작업 결과가 텍스트 상자에 표시됩니다.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a>참고 항목
