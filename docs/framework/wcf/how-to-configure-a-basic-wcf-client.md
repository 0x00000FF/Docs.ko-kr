---
title: '방법: 기본 Windows Communication Foundation 클라이언트 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: c03bf37c737a19b0a90f12e7ad5db78b75323f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>방법: 기본 Windows Communication Foundation 클라이언트 구성
이 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 6 가지 작업 중 다섯 번째 작업입니다. 모든 6 가지 작업의 개요를 참조 하십시오.는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목입니다.  
  
 이 항목에서는 클라이언트 구성 파일의 서비스 참조 추가 기능을 사용 하 여 생성 된 설명 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 또는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 클라이언트를 구성하려면 클라이언트에서 서비스에 액세스하는 데 사용하는 끝점을 지정해야 합니다. 끝점에는 주소, 바인딩 및 계약이 포함되어 있으며 이러한 각 항목은 클라이언트 구성 프로세스에서 지정되어야 합니다.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>Windows Communication Foundation 클라이언트를 구성하려면  
  
1.  GettingStartedClient 프로젝트에서 생성된 구성 파일(App.config)을 엽니다. 다음 예제에서는 생성된 구성 파일을 보여 줍니다. 아래는 [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 섹션에서 찾을 [ \<끝점 >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소입니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     이 예에서는 다음 주소에 있는 서비스에 액세스 하는 클라이언트에서 사용 하는 끝점을 구성 합니다. http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     끝점 요소는 WCF 클라이언트와 서비스 사이의 통신에 `ServiceReference1.ICalculator` 서비스 계약을 사용하도록 지정합니다. WCF 채널 구성 시스템에서 제공 된 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 합니다. 이 계약은 Visual Studio의 서비스 참조 추가를 사용하여 생성한 것입니다. 실질적으로 GettingStartedLib 프로젝트에 정의된 계약의 사본입니다. <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정 합니다.  
  
2.  이 구성을 사용 하 여 생성된 된 클라이언트를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 클라이언트를 사용 하 여](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)
