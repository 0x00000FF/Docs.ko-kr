---
title: Windows Communication Foundation 서비스에 대한 바인딩 구성
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: 7b5a91091a0902928eb2b72bdf69612f2e3f2f48
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029413"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Windows Communication Foundation 서비스에 대한 바인딩 구성
응용 프로그램을 만들 때 응용 프로그램의 배포 후 관리자에게 결정을 맡겨야 할 경우가 있습니다. 예를 들어, 서비스 주소 또는 URI(Uniform Resource Identifier)가 무엇인지 미리 알 수 없는 경우가 있습니다. 주소를 하드 코딩하는 대신 관리자가 서비스를 작성한 후에 이를 수행하도록 하는 것이 좋습니다. 이러한 유연성은 구성을 통해 수행됩니다.  
  
> [!NOTE]
>  사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 사용 하 여는 `/config` 스위치를 신속 하 게 구성 파일을 만듭니다.  
  
## <a name="major-sections"></a>주요 섹션  
 Windows Communication Foundation (WCF) 구성 스키마에 다음 세 가지 주요 섹션이 포함 되어 있습니다 (`serviceModel`하십시오 `bindings`, 및 `services`):  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a>ServiceModel Elements  
 제한 된 섹션을 사용할 수는 `system.ServiceModel` 서비스 유형을 서비스에 대 한 설정 뿐 아니라 하나 이상의 끝점을 사용 하 여 구성 요소입니다. 각 엔드포인트는 주소, 계약 및 바인딩과 함께 구성할 수 있습니다. 끝점에 대 한 자세한 내용은 참조 하세요. [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)합니다. 엔드포인트가 지정되지 않으면 런타임에서 기본 엔드포인트를 추가합니다. 기본 엔드포인트, 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.  
  
 바인딩은 전송(HTTP, TCP, 파이프, 메시지 큐) 및 프로토콜(보안, 안전성, 트랜잭션 흐름)을 지정하며, 엔드포인트가 외부와 통신하는 방법을 지정하는 각각의 바인딩 요소로 구성됩니다.  
  
 예를 들어, 지정 된 [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소는 끝점에 대 한 전송으로 HTTP를 사용 하도록 나타냅니다. 이 엔드포인트를 사용하는 서비스가 열려 있는 경우 이 요소는 런타임에 엔드포인트를 연결하는 데 사용됩니다.  
  
 바인딩에는 미리 정의된 바인딩 및 사용자 지정 바인딩의 두 종류가 있습니다. 미리 정의된 바인딩에는 일반적인 시나리오에서 사용되는 유용한 요소의 조합이 있습니다. WCF에서 제공 하는 미리 정의 된 바인딩 형식의 목록은 참조 하세요. [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)합니다. 서비스 응용 프로그램에서 필요로 하는 올바른 기능의 조합을 가진 미리 정의된 바인딩 컬렉션이 없는 경우 사용자 지정 바인딩을 만들어 응용 프로그램의 요구 사항을 충족시킬 수 있습니다. 사용자 지정 바인딩에 대 한 자세한 내용은 참조 하세요. [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.  
  
 다음 4 개의 예제에는 WCF 서비스를 설정 하는 데 가장 일반적인 바인딩 구성을 보여 줍니다.  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>엔드포인트를 지정하여 바인딩 형식 사용  
 첫 번째 예제에서는 주소, 계약 및 바인딩으로 구성된 엔드포인트를 지정하는 방법에 대해 보여 줍니다.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 이 예제에서 `name` 특성은 구성의 서비스 형식을 나타냅니다. `HelloWorld` 계약을 사용하여 코드에 서비스를 만드는 경우 서비스는 예제 구성에 정의된 모든 끝점으로 초기화됩니다. 어셈블리에는 하나의 서비스 계약을 구현 하는 경우는 `name` 서비스 가능한 형식만 사용 하기 때문에 특성을 생략할 수 있습니다. 특성에는 `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` 형식으로 된 문자열만 있습니다.  
  
 `address` 특성은 다른 끝점이 서비스와 통신하는 데 사용하는 URI를 지정합니다. URI는 절대 경로 또는 상대 경로일 수 있습니다. 상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다. 주소가 구성되지 않으면 해당 엔드포인트의 주소를 기본 주소로 가정합니다.  
  
 `contract` 특성은 이 끝점이 공개하는 계약을 지정합니다. 서비스 구현 형식은 계약 형식을 구현해야 합니다. 서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.  
  
 `binding` 특성은 이 특정 끝점에 사용할 미리 정의된 바인딩 또는 사용자 지정 바인딩을 선택합니다. 바인딩을 명시적으로 선택하지 않는 엔드포인트에서는 기본 바인딩 선택인 `BasicHttpBinding`이 사용됩니다.  
  
#### <a name="modifying-a-predefined-binding"></a>미리 정의된 바인딩 수정  
 다음 예제에서는 미리 정의된 바인딩을 수정합니다. 그런 다음 서비스에서 엔드포인트를 구성하는 데 해당 바인딩을 사용할 수 있습니다. 바인딩은 <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> 값을 1초로 설정하여 수정합니다. 속성은 <xref:System.TimeSpan> 개체를 반환합니다.  
  
 이 변경된 바인딩은 바인딩 섹션에 있습니다. 엔드포인트를 만들 때 `binding` 요소에 있는 `endpoint` 특성을 설정하면 변경된 이 바인딩을 사용할 수 있습니다.  
  
> [!NOTE]
>  바인딩에 특정 이름을 지정하는 경우 서비스 엔드포인트에 지정된 `bindingConfiguration`이 해당 이름과 일치해야 합니다.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a>서비스에 적용할 동작 구성  
 다음 예제에서는 특정 동작이 서비스 형식에 맞게 구성됩니다. 합니다 `ServiceMetadataBehavior` 요소를 사용 하도록 설정 하는 데 사용 됩니다 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스를 쿼리하고 메타 데이터에서 WSDL 웹 서비스 설명 언어 () 문서를 생성 합니다.  
  
> [!NOTE]
>  동작에 특정 이름을 지정하는 경우 서비스 또는 엔드포인트 섹션에 지정된 `behaviorConfiguration`이 해당 이름과 일치해야 합니다.  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 위의 구성을 사용하면 클라이언트가 “HelloWorld” 형식이 지정된 서비스를 호출하고 해당 메타데이터를 가져올 수 있습니다.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a>다른 바인딩 값을 사용하는 두 개의 엔드포인트로 서비스 지정  
 마지막 이 예제에서는 두 개의 엔드포인트가 `HelloWorld` 서비스 형식에 맞게 구성됩니다. 각 끝점은 서로 다른 사용자 지정 `bindingConfiguration` 동일한 바인딩 유형의 특성입니다 (각 수정 된 `basicHttpBinding`).  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 다음 예제와 같이 `protocolMapping` 섹션을 추가하고 바인딩을 구성하면 기본 구성을 사용하여 같은 동작을 지정할 수 있습니다.  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a>참고 항목  
 [단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md)  
 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)  
 [엔드포인트 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
