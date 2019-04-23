---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346238"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>방법: 이중 페더레이션 바인딩 만들기
<xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다. 이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다. 다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다. 3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.  
  
 코드에서 바인딩을 만들 수도 있습니다. 만들려는 바인딩 요소 스택에의 설명을 참조 하세요. [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1. 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.  
  
2. 내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexHttpMessageSecurityBinding`합니다.  
  
3. 내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.  
  
4. 내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.  
  
5. 다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소입니다.  
  
6. 다음은 [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소는 빈 항목 만들기 [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소입니다.  
  
7. 다음은 [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소는 빈 항목 만들기 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 요소입니다.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1. 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.   
  
2. 내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexTcpMessageSecurityBinding`합니다.  
  
3. 내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.  
  
4. 내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.  
  
5. 다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소입니다.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1. 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드의 구성 파일 만들기를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소입니다.   
  
2. 내부를 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 `name` 특성이로 설정 `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`합니다.  
  
3. 내부를 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소를 만들기는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 `authenticationMode` 특성이로 설정 `SecureConversation`합니다.  
  
4. 내 합니다 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만들기는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 `authenticationMode` 특성이로 설정 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`.  
  
5. 다음은 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 빈 항목 만들기 [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소입니다.  
  
6. 다음은 [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소는 빈 항목 만들기 [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소입니다.  
  
## <a name="code-sample"></a>코드 샘플  
  
#### <a name="sample-with-3-bindings"></a>3개의 바인딩에 대한 샘플  
  
1. 구성 파일에 다음 코드를 삽입합니다.  
  
## <a name="example"></a>예제  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
