---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766404"
---
# <a name="localissuer"></a>\<localIssuer>
보안 토큰을 가져오는 데 사용할 로컬 발급자의 주소 및 바인딩을 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
endpointBehaviors 섹션  
\<behavior>  
\<clientCredentials>  
\<issuedToken>  
\<localIssuer>  
  
## <a name="syntax"></a>구문  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|주소|필수 문자열입니다. 로컬 발급자의 URI를 지정합니다.|  
|바인딩|선택적 문자열입니다. 시스템에서 제공한 바인딩 중 하나입니다. 목록에 대해서 [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md)합니다.|  
|bindingConfiguration|선택적 문자열입니다. 구성 파일에서 발견되는 바인딩 구성을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|로컬 발급자의 ID 정보를 지정합니다.|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|로컬 발급자의 주소를 올바로 지정하는 데 필요한 주소 헤더 컬렉션입니다. `add` 키워드를 사용하여 이 컬렉션에 헤더를 추가할 수 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<issuedToken>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 STS(보안 토큰 서비스)에서 발급된 토큰을 가져오려면 클라이언트 응용 프로그램에서 STS와 통신하는 데 사용할 주소 및 바인딩을 구성해야 합니다. 경우는 <xref:System.ServiceModel.WSFederationHttpBinding> 페더레이션 바인딩의 발급자 주소가 때 또는 보안 토큰 서비스에 대 한 URL을 제공 하지 않습니다 `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` 또는 `null`, 클라이언트의 Windows Communication Foundation (WCF) 채널 하여지정된값을사용하여`address`고 `binding` 발급 된 토큰을 가져오려면 STS와 통신할 수 있습니다. 로컬 발급자를 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `address`, `binding` 및 `bindingConfiguration` 요소의 `localIssuer` 특성을 설정합니다.  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
- [방법: 페더레이션된 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
