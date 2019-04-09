---
title: 래핑되지 않은 메시지
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: 30c25bf6bb8b4ffe621007c03a7e913bba4379fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125388"
---
# <a name="unwrapped-messages"></a>래핑되지 않은 메시지
이 샘플에서는 래핑되지 않은 메시지를 보여 줍니다. 기본적으로 메시지 본문은 서비스 작업 매개 변수가 래핑되도록 서식이 지정됩니다. 다음 샘플에서는 `Add` 서비스에 `ICalculator` 요청 메시지를 래핑된 모드로 표시합니다.  
  
```xml  
<s:Envelope   
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 메시지 본문에 있는 `<Add>` 요소가 `n1` 및 `n2` 매개 변수를 래핑합니다. 대조적으로, 다음 샘플에서는 같은 메시지를 래핑되지 않은 모드로 표시합니다.  
  
```xml  
<s:Envelope   
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"   
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 래핑되지 않은 메시지는 포함하는 요소에 `n1` 및 `n2` 매개 변수를 래핑하지 않으며 SOAP 본문 요소의 직계 자식입니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 서비스 작업 매개 변수 형식에 <xref:System.ServiceModel.MessageContractAttribute>를 적용하고 다음 샘플 코드에 표시된 것과 같이 값 형식을 반환하여 래핑되지 않은 메시지를 만듭니다.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 메시지를 보내고 받는 상황을 볼 수 있도록 이 샘플에서는 추적을 사용합니다. 또한 <xref:System.ServiceModel.WSHttpBinding>은 기록하는 메시지의 수를 줄이기 위해 보안 없이 구성되었습니다.  
  
 결과 추적 로그 (c:\logs\Message.log)를 사용 하 여 볼 수 있습니다 합니다 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다. 메시지 내용을 보려면 **메시지** 모두 왼쪽 창과 오른쪽 Service Trace Viewer 도구에서. 이 샘플에서 추적 로그는 C:\LOGS 폴더에 생성되도록 구성됩니다. 샘플을 실행하기 전에 이 폴더를 만들고 사용자에게 이 디렉터리에 대한 네트워크 서비스 쓰기 권한을 부여해야 합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  메시지를 기록할 C:\LOGS 디렉터리를 만듭니다. 사용자에게 이 디렉터리에 대한 네트워크 서비스 쓰기 권한을 부여합니다.  
  
3.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
4.  단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
