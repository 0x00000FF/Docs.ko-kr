---
title: "&lt;webHttpBinding&gt;의 &lt;security&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;webHttpBinding&gt;의 &lt;security&gt;
[\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)로 구성된 끝점의 보안 요구 사항을 지정합니다.  
  
## 구문  
  
```  
  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|모드|끝점에서 전송 수준 보안을 사용하거나 보안을 사용하지 않는지 여부를 지정합니다.  기본값은 `None`입니다.  이 특성은 <xref:System.ServiceModel.WebHttpSecurityMode> 형식입니다.|  
  
## Mode 특성  
  
|값|설명|  
|-------|--------|  
|없음|보안이 해제되어 있습니다.|  
|전송|HTTPS를 사용하여 보안이 제공됩니다.  서비스는 SSL 인증서로 구성해야 합니다.  메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.  클라이언트 인증은 [\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)의 `ClientCredentialType` 특성을 통해 제어됩니다.|  
|TransportCredentialOnly|이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나  HTTP 기반 클라이언트 인증을 제공합니다.  이 모드는 주의해서 사용해야 합니다.  이 모드는 다른 방식\(예: IPsec\)에 의해 전송 보안이 제공되며 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 인프라에서 클라이언트 인증만 제공하는 환경에서 사용해야 합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|전송 보안 설정을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|SOAP 메시지 대신 HTTP 요청에 응답하는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 웹 서비스에 대한 끝점을 구성하는 데 사용되는 바인딩 요소입니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.WebHttpSecurity>   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [자격 증명 형식 선택](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)   
 [WCF 웹 HTTP 프로그래밍 모델](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)