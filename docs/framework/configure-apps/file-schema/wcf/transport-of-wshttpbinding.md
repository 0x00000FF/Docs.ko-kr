---
title: "&lt;wsHttpBinding&gt;의 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1ea5fc60f4dc64fd895469b580b81379da26191
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a>&lt;wsHttpBinding&gt;의 &lt;transport&gt;
HTTP 전송의 인증 설정을 정의합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<wsHttpBinding >  
\<바인딩 >  
\<보안 >  
\<전송 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<wsHttpBinding>  
    <binding>  
        <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport  
            clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"  
            proxyCredentialType="Basic|Digest|None|Ntlm|Windows"  
            realm="string" />  
                <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always" protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                </extendedProtecutionPolicy>  
            </transport>  
        </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="type"></a>형식  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`clientCredentialType`|클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다. 이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.|  
|`proxyCredentialType`|클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다. 이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.|  
|`realm`|다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다. 기본값은 빈 문자열입니다.<br /><br /> 인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며, 액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다. 사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.|  
|`policyEnforcement`|이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.<br /><br /> 1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).<br />2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.<br />3.  Always – 정책이 항상 적용됩니다. 확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType 특성  
  
|값|설명|  
|-----------|-----------------|  
|`None`|보안이 해제되어 있습니다.|  
|`Basic`|기본 인증을 사용합니다.|  
|`Digest`|다이제스트 인증을 사용합니다.|  
|`Ntlm`|Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.|  
|`Windows`|Windows 통합 인증을 사용합니다.|  
|`Certificate`|X.509 인증서를 사용하여 클라이언트를 인증합니다.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType 특성  
  
|값|설명|  
|-----------|-----------------|  
|`None`|보안이 해제되어 있습니다.|  
|`Basic`|기본 인증을 사용합니다.|  
|`Digest`|다이제스트 인증을 사용합니다.|  
|`Ntlm`|Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.|  
|`Windows`|Windows 통합 인증을 사용합니다.|  
|`Certificate`|X.509 인증서를 사용하여 클라이언트를 인증합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|보안 기능을 나타내는 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [서비스 및 클라이언트 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)
