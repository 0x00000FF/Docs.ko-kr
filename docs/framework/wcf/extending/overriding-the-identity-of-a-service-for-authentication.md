---
title: 인증을 위해 서비스 ID 재정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 8c0807a7b811cf2cb3a13576018373d135e3e5cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554467"
---
# <a name="overriding-the-identity-of-a-service-for-authentication"></a>인증을 위해 서비스 ID 재정의
일반적으로 선택한 클라이언트 자격 증명 형식에 따라 서비스 메타데이터에 노출되는 ID 형식이 결정되므로 서비스에 ID를 설정할 필요가 없습니다. 예를 들어 다음 구성 코드에서는 합니다 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소 집합과 `clientCredentialType` Windows 특성.  
  
  
  
 다음 WSDL(웹 서비스 기술 언어) 단편에서는 이전에 정의한 엔드포인트의 ID를 보여 줍니다. 이 예제에서는 특정 사용자 계정으로 자체 호스팅 서비스로 서비스 중인지 (username@contoso.com) 한 사용자 계정 이름 (UPN) id의 계정 이름을 포함 합니다. UPN을 Windows 도메인의 사용자 로그온 이름이라고도 합니다.  
  
  
  
 Id 설정을 보여 주는 샘플 응용 프로그램을 참조 하세요 [Service Identity 샘플](../../../../docs/framework/wcf/samples/service-identity-sample.md)합니다. 서비스 id에 대 한 자세한 내용은 참조 하세요. [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos 인증 및 ID  
 기본적으로 서비스는 Windows 자격 증명을 사용 하도록 구성 된 경우는 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 포함 하는 요소는 [ \<userPrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) 또는 [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) 요소가 WSDL에서 생성 됩니다. 서비스를 실행 하는 경우는 `LocalSystem`, `LocalService`, 또는 `NetworkService` 계정, 서비스 사용자 이름 (SPN)의 형태로 기본적으로 생성 됩니다 `host/` \< *hostname*> 때문에 이러한 계정이 컴퓨터의 SPN 데이터에 액세스할을 수 있습니다. Windows Communication Foundation (WCF)의 형태로 UPN을 생성 서비스를 다른 계정으로 실행 하는 경우 \< *사용자 이름*>@<*domainName* `>` . Kerberos 인증에서 서비스를 인증하려면 UPN 또는 SPN을 클라이언트에 제공해야 하므로 이 작업이 수행됩니다.  
  
 Setspn.exe 도구를 사용하여 도메인의 서비스 계정으로 추가 SPN을 등록할 수도 있습니다. 그런 다음 SPN을 서비스 ID로 사용할 수 있습니다. 이 도구를 다운로드 하려면 참조 [Windows 2000 Resource Kit Tool: Setspn.exe](https://go.microsoft.com/fwlink/?LinkId=91752). 도구에 대 한 자세한 내용은 참조 하세요. [Setspn 개요](https://go.microsoft.com/fwlink/?LinkId=61374)합니다.  
  
> [!NOTE]
>  Windows 자격 증명 형식을 협상 없이 사용하려면 서비스의 사용자 계정이 Active Directory 도메인에 등록된 SPN에 대한 액세스 권한이 있어야 합니다. 다음과 같은 방법으로 이 작업을 수행할 수 있습니다.  
  
-   NetworkService 또는 LocalSystem 계정을 사용하여 서비스를 실행합니다. 해당 계정에 컴퓨터 시스템을 Active Directory 도메인에 연결할 때 설정 된 SPN에는 액세스할 수 있으므로 WCF 서비스의 메타 데이터 (WSDL)에서 서비스의 끝점 내에서 적절 한 SPN 요소를 자동으로 생성 합니다.  
  
-   임의의 Active Directory 도메인 계정을 사용하여 서비스를 실행합니다. 이 경우 해당 도메인 계정의 SPN을 설정합니다. Setspn.exe 유틸리티 도구를 사용하여 이 작업을 수행할 수 있습니다. 서비스의 계정에 대 한 SPN을 만든 후 메타 데이터 (WSDL)를 통해 서비스 클라이언트에 SPN을 게시 하는 WCF를 구성 합니다. 이 작업은 응용 프로그램 구성 파일이나 코드를 통해 노출된 엔드포인트에 대한 엔드포인트 ID를 설정하여 수행합니다.  
  
 Spn에 대 한 자세한 정보, Kerberos 프로토콜 및 Active Directory에 대 한 참조 [Kerberos 기술 보완에 대 한 Windows](https://go.microsoft.com/fwlink/?LinkId=88330)합니다.  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>SPN 또는 UPN이 빈 문자열인 경우  
 SPN 또는 UPN을 빈 문자열과 같게 설정하면 사용되는 보안 수준과 인증 모드에 따라 다른 많은 작업이 수행됩니다.  
  
-   전송 수준 보안을 사용하는 경우 NTLM(NT LanMan) 인증이 선택됩니다.  
  
-   메시지 수준 보안을 사용하는 경우 인증 모드에 따라 인증이 실패할 수 있습니다.  
  
-   `spnego` 모드를 사용하고 `AllowNtlm` 특성이 `false`로 설정된 경우 인증이 실패합니다.  
  
-   `spnego` 모드를 사용하고 `AllowNtlm` 특성이 `true`로 설정된 경우 UPN이 비어 있으면 인증이 실패하지만 SPN이 비어 있으면 성공합니다.  
  
-   "단일 쇼트"라고도 하는 Kerberos direct를 사용하는 경우 인증이 실패합니다.  
  
### <a name="using-the-identity-element-in-configuration"></a>사용 하 여 \<identity > 구성에서 요소  
 이전에 Certificate에 표시된 바인딩에서 클라이언트 자격 증명 형식을 변경하면`,` 생성된 WSDL에 다음 코드에 표시된 ID 값에 대한 Base64로 serialize된 X.509 인증서가 포함됩니다. 이는 Windows 이외의 모든 클라이언트 자격 증명 형식에 대한 기본값입니다.  
  
  
  
 구성에 <`identity`> 요소를 사용하거나 코드에서 ID를 설정하여 기본 서비스 ID의 값을 변경하거나 ID 형식을 변경할 수 있습니다. 다음 구성 코드에서는 값 `contoso.com`으로 DNS(Domain Name System) ID를 설정합니다.  
  
  
  
### <a name="setting-identity-programmatically"></a>프로그래밍 방식으로 ID 설정  
 서비스가 없습니다 identity (id)를 명시적으로 지정 하려면 WCF가 자동으로 결정 되기 때문에. 그러나 WCF 허용 필요한 경우 끝점에서 id를 지정할 수 있습니다. 다음 코드에서는 특정 DNS ID를 사용하여 새 서비스 엔드포인트를 추가합니다.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>참고자료
- [방법: 사용자 지정 클라이언트 Id 검증 도구 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)
- [서비스 ID 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
