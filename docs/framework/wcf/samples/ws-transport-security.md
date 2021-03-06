---
title: WS 전송 보안
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: 221bf2e0d304e93242bb5fea6854c1c9bb72aec2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143462"
---
# <a name="ws-transport-security"></a>WS 전송 보안
이 샘플에서는 <xref:System.ServiceModel.WSHttpBinding> 바인딩의 SSL 전송 보안을 사용하는 방법을 보여 줍니다. 기본적으로 `wsHttpBinding` 바인딩은 HTTP 통신을 제공합니다. 전송 보안용으로 구성된 경우, 바인딩은 HTTPS 통신을 지원합니다. 이 샘플은 계산기 서비스를 구현하는 [시작 하기를](../../../../docs/framework/wcf/samples/getting-started-sample.md) 기반으로 합니다. `wsHttpBinding`은 클라이언트 및 서비스의 애플리케이션 구성 파일에 지정 및 구성됩니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 샘플의 프로그램 코드는 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md) 서비스의 코드와 동일합니다. 샘플을 빌드하고 실행하기 전에 Web Server Certificate Wizard를 사용하여 인증서를 만들고 할당해야 합니다. 구성 파일 설정의 엔드포인트 정의와 바인딩 정의를 사용하면 클라이언트의 다음 샘플 구성에 표시된 것과 같이 `Transport` 보안 모드를 활성화할 수 있습니다.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 지정된 주소에서는 https:// 체계를 사용합니다. 바인딩 구성에서는 보안 모드를 `Transport`로 설정합니다. 서비스의 Web.config 파일에도 같은 보안 모드를 지정해야 합니다.  
  
 이 샘플에 사용된 인증서는 Makecert.exe로 만든 테스트 인증서이므로 브라우저에서 와 같은 https://localhost/servicemodelsamples/service.svchttps 주소에 액세스하려고 할 때 보안 경고가 나타납니다. WCF(Windows 통신 재단) 클라이언트가 테스트 인증서를 사용하여 작업할 수 있도록 보안 경고를 억제하기 위해 클라이언트에 몇 가지 추가 코드가 추가되었습니다. 이 코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 다음 명령을 사용하여 ASP.NET 4.0을 설치합니다.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
3. [IIS(인터넷 정보 서비스) 서버 인증서 설치 지침을](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)수행했습니까?  
  
4. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
5. 단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
