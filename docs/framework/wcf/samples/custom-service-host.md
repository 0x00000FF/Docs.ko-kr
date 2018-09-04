---
title: 사용자 지정 서비스 호스트
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 51256b115749aef4ed3691e49ccf36ee65f5cbf1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529292"
---
# <a name="custom-service-host"></a>사용자 지정 서비스 호스트
이 샘플에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 사용자 지정 파생 항목을 사용하여 서비스의 런타임 동작을 변경하는 방법을 보여 줍니다. 이 접근 방식을 사용하면 일반적인 방법으로 여러 서비스를 구성하는 대신 재사용 가능한 대체 방법이 제공됩니다. 또한 샘플에서는 <xref:System.ServiceModel.Activation.ServiceHostFactory> 클래스를 사용하여 IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service) 호스팅 환경에서 사용자 지정 ServiceHost를 사용하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>시나리오 정보  
 잠재적으로 중요 한 서비스 메타 데이터가 실수로 공개를 방지 하려면 Windows Communication Foundation (WCF) 서비스에 대 한 기본 구성 메타 데이터 게시를 해제 합니다. 이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.  
  
 여러 서비스에 메타데이터 게시를 사용하도록 설정하면 각각의 개별 서비스에 동일한 구성 요소가 추가되어 기본적으로 동일한 구성 정보가 많이 생성될 수 있습니다. 각 서비스를 개별적으로 구성하는 대신 메타데이터 게시를 한 번 사용한 다음 여러 가지 다른 서비스에서 해당 코드를 다시 사용하도록 하는 명령 코드를 작성할 수 있습니다. 이 작업은 새 클래스를 만들어 수행합니다. 새 클래스는 <xref:System.ServiceModel.ServiceHost>에서 파생되며 `ApplyConfiguration`() 메서드를 재정의하여 메타데이터 게시 동작을 명령적으로 추가합니다.  
  
> [!IMPORTANT]
>  쉽게 구별할 수 있도록 이 샘플에서는 보안이 설정되지 않은 메타데이터 게시 끝점을 만드는 방법을 보여 줍니다. 이러한 끝점은 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 끝점을 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다.  
  
## <a name="implementing-a-custom-servicehost"></a>사용자 지정 ServiceHost 구현  
 <xref:System.ServiceModel.ServiceHost> 클래스는 상속자가 서비스의 런타임 동작을 변경하기 위해 재정의할 수 있는 여러 가지 유용한 가상 메서드를 노출합니다. 예를 들어, `ApplyConfiguration`() 메서드는 구성 저장소에서 서비스 구성 정보를 읽고 그에 따라 호스트의 <xref:System.ServiceModel.Description.ServiceDescription>을 변경합니다. 기본 구현에서는 응용 프로그램의 구성 파일에서 구성을 읽습니다. 사용자 지정 구현에서는 명령 코드를 사용하여 `ApplyConfiguration`을 추가로 변경하거나 기본 구성 저장소를 완전히 바꾸도록 <xref:System.ServiceModel.Description.ServiceDescription>()을 재정의할 수 있습니다. 예를 들어, 응용 프로그램의 구성 파일 대신 데이터베이스에서 서비스의 끝점 구성을 읽을 수 있습니다.  
  
 이 샘플에서는 메타데이터 게시를 사용하도록 설정하는 ServiceMetadataBehavior가 서비스의 구성 파일에 명시적으로 추가되지 않은 경우에도 이 동작을 추가하는 사용자 지정 ServiceHost를 빌드합니다. <xref:System.ServiceModel.ServiceHost>에서 상속되며 `ApplyConfiguration`()을 재정의하는 새 클래스를 만들어 이 작업을 수행합니다.  
  
```  
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to   
    //alter the ServiceDescription prior to opening  
    //the service host.   
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();       
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 응용 프로그램의 구성 파일에 제공된 구성을 무시하지 않으므로 `ApplyConfiguration`()을 재정의하는 경우 제일 먼저 기본 구현이 호출됩니다. 이 메서드가 완료되면 다음 명령 코드를 사용하여 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 명령적으로 설명에 추가할 수 있습니다.  
  
```  
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,   
    //so we do not have any work to do.  
    return;  
}  
```  
  
 마지막으로 `ApplyConfiguration`()을 재정의하기 위해 기본 메타데이터 끝점을 추가합니다. 규칙에 따라 서비스 호스트의 BaseAddresses 컬렉션에 각 URI마다 메타데이터 끝점이 하나씩 생성됩니다.  
  
```  
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a>자체 호스팅 환경에서 사용자 지정 ServiceHost 사용  
 이제 사용자 지정 ServiceHost 구현을 완료했으므로 `SelfDescribingServiceHost`의 인스턴스 내부에 해당 서비스를 호스트하여 모든 서비스에 메타데이터 게시 동작을 추가할 수 있습니다. 다음 코드에서는 자체 호스팅 시나리오에서 해당 서비스를 사용하는 방법을 보여 줍니다.  
  
```  
SelfDescribingServiceHost host =   
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 사용자 지정 호스트는 기본 <xref:System.ServiceModel.ServiceHost> 클래스를 사용하여 서비스를 호스트한 경우처럼 응용 프로그램 구성 파일에서 서비스의 엔드포인트 구성을 계속 읽습니다. 그러나 사용자 지정 호스트의 내부에서 메타데이터 게시를 사용하도록 설정하는 논리를 추가했으므로 구성에서 메타데이터 게시 동작을 더 이상 명시적으로 사용하도록 설정할 필요가 없습니다. 이 접근 방식을 사용하면 여러 서비스가 포함된 응용 프로그램을 빌드할 때 같은 구성 요소를 반복해서 작성하지 않고도 각 서비스에서 메타데이터 게시를 사용하도록 설정할 수 있다는 장점이 있습니다.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>IIS 또는 WAS 환경에서 사용자 지정 ServiceHost 사용  
 자체 호스팅 시나리오에서는 결국 응용 프로그램 코드를 통해 서비스 호스트 인스턴스를 만들고 여는 작업을 수행하므로 사용자 지정 서비스 호스트 사용이 간단합니다. 그러나 IIS 또는 WAS 호스팅 환경에서 WCF 인프라를 동적으로 인스턴스화합니다 서비스의 호스트를에서 들어오는 메시지에 응답 합니다. 이 호스팅 환경에서 사용자 지정 서비스 호스트를 사용할 수도 있지만 ServiceHostFactory 형식의 추가 코드가 필요합니다. 다음 코드에서는 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 인스턴스를 반환하는 `SelfDescribingServiceHost`의 파생 항목을 보여 줍니다.  
  
```  
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,   
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)   
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,     
                                             baseAddresses);  
    }  
}  
```  
  
 이 샘플에서 볼 수 있듯이 사용자 지정 ServiceHostFactory 구현은 매우 간단합니다. 모든 사용자 지정 논리는 ServiceHost 구현 내에 있고 팩터리는 파생 클래스의 인스턴스를 반환합니다.  
  
 서비스 구현에서 사용자 지정 팩터리를 사용하려면 서비스의 .svc 파일에 일부 메타데이터를 추가해야 합니다.  
  
```  
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"  
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"  
               language=c# Debug="true" %>  
```  
  
 여기서는 `Factory` 지시문에 추가 `@ServiceHost` 특성을 추가하고 사용자 지정 팩터리의 CLR 형식 이름을 특성의 값으로 전달했습니다. WCF 호스팅 인프라 먼저 ServiceHostFactory의 인스턴스를 만듭니다 및 서비스 호스트 자체를 호출 하 여 인스턴스화할 IIS 또는 WAS는이 서비스에 대 한 메시지를 받으면 `ServiceHostFactory.CreateServiceHost()`합니다.  
  
## <a name="running-the-sample"></a>샘플 실행  
 이 샘플에서는 완전한 기능을 갖춘 클라이언트 및 서비스 구현을 제공하지만 샘플의 핵심은 사용자 지정 호스트를 사용하여 서비스의 런타임 동작을 변경하는 방법을 보여 주는 것이므로 다음 단계를 수행합니다.  
  
#### <a name="to-observe-the-effect-of-the-custom-host"></a>사용자 지정 호스트의 효과를 확인하려면  
  
1.  서비스의 Web.config 파일을 열고 서비스에서 메타데이터를 사용하도록 명시적으로 설정하는 구성이 없는지 확인합니다.  
  
2.  서비스의.svc 파일을 열고 확인 해당 @ServiceHost 지시문에 사용자 지정 ServiceHostFactory의 이름을 지정 하는 Factory 특성이 포함 되어 있습니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션을 빌드하려면 [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3.  솔루션을 빌드한 후 Setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다. 이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.  
  
4.  단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
5.  [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램을 제거하려면 Cleanup.bat를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: IIS에서 WCF 서비스 호스트](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
