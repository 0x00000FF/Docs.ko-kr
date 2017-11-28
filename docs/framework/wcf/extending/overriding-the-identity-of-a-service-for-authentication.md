---
title: "인증을 위해 서비스 ID 재정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a3125504326f2cb129fef6f1f3e01dba577f599
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overriding-the-identity-of-a-service-for-authentication"></a>인증을 위해 서비스 ID 재정의
일반적으로 선택한 클라이언트 자격 증명 형식에 따라 서비스 메타데이터에 노출되는 ID 형식이 결정되므로 서비스에 ID를 설정할 필요가 없습니다. 예를 들어 다음 구성 코드에서는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소 및 집합은 `clientCredentialType` 특성을 Windows로 합니다.  
  
  
  
 다음 WSDL(웹 서비스 기술 언어) 단편에서는 이전에 정의한 끝점의 ID를 보여 줍니다. 이 예제에서는 서비스가 특정 사용자 계정에서 자체 호스팅된 서비스로 실행 되 고 (username@contoso.com) 사용자 계정 이름 (UPN) id에 계정 이름입니다. UPN을 Windows 도메인의 사용자 로그온 이름이라고도 합니다.  
  
  
  
 참조 id 설정이 보여 주는 샘플 응용 프로그램, [Service Identity 샘플](../../../../docs/framework/wcf/samples/service-identity-sample.md)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]서비스 id, 참조 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos 인증 및 ID  
 서비스는 Windows 자격 증명을 사용 하도록 구성 된 경우 기본적으로는 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 요소를 포함 하는 [ \<userPrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) 또는 [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) 요소가 WSDL에서 생성 됩니다. 서비스를 실행 하는 경우는 `LocalSystem`, `LocalService`, 또는 `NetworkService` 계정, 사용자 이름 (SPN)의 형태로 기본적으로 생성 되는 서비스 `host/` \< *hostname*> 때문에 이러한 계정은 컴퓨터의 SPN 데이터에 대 한 액세스를 권한이 있습니다. 서비스는 서로 다른 계정으로 실행 중인 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 의 형태로 UPN을 생성 \< *username*>@<*domainName*`>`합니다. Kerberos 인증에서 서비스를 인증하려면 UPN 또는 SPN을 클라이언트에 제공해야 하므로 이 작업이 수행됩니다.  
  
 Setspn.exe 도구를 사용하여 도메인의 서비스 계정으로 추가 SPN을 등록할 수도 있습니다. 그런 다음 SPN을 서비스 ID로 사용할 수 있습니다. 이 도구를 다운로드 하려면 [Windows 2000 리소스 키트 도구: Setspn.exe](http://go.microsoft.com/fwlink/?LinkId=91752)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]도구 참조 [Setspn 개요](http://go.microsoft.com/fwlink/?LinkId=61374)합니다.  
  
> [!NOTE]
>  Windows 자격 증명 형식을 협상 없이 사용하려면 서비스의 사용자 계정이 Active Directory 도메인에 등록된 SPN에 대한 액세스 권한이 있어야 합니다. 다음과 같은 방법으로 이 작업을 수행할 수 있습니다.  
  
-   NetworkService 또는 LocalSystem 계정을 사용하여 서비스를 실행합니다. 이러한 계정은 시스템에서 Active Directory 도메인에 연결할 때 설정된 시스템 SPN에 대한 액세스 권한이 있으므로, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 메타데이터(WSDL)의 서비스 끝점에 적절한 SPN 요소를 자동으로 생성합니다.  
  
-   임의의 Active Directory 도메인 계정을 사용하여 서비스를 실행합니다. 이 경우 해당 도메인 계정의 SPN을 설정합니다. Setspn.exe 유틸리티 도구를 사용하여 이 작업을 수행할 수 있습니다. 서비스 계정의 SPN을 만들고 나면 메타데이터(WSDL)를 통해 서비스 클라이언트에 SPN을 게시하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성합니다. 이 작업은 응용 프로그램 구성 파일이나 코드를 통해 노출된 끝점에 대한 끝점 ID를 설정하여 수행합니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Spn, Kerberos 프로토콜 및 Active Directory 참조 [Windows Kerberos 기술 자료에 대 한](http://go.microsoft.com/fwlink/?LinkId=88330)합니다.  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>SPN 또는 UPN이 빈 문자열인 경우  
 SPN 또는 UPN을 빈 문자열과 같게 설정하면 사용되는 보안 수준과 인증 모드에 따라 다른 많은 작업이 수행됩니다.  
  
-   전송 수준 보안을 사용하는 경우 NTLM(NT LanMan) 인증이 선택됩니다.  
  
-   메시지 수준 보안을 사용하는 경우 인증 모드에 따라 인증이 실패할 수 있습니다.  
  
-   `spnego` 모드를 사용하고 `AllowNtlm` 특성이 `false`로 설정된 경우 인증이 실패합니다.  
  
-   `spnego` 모드를 사용하고 `AllowNtlm` 특성이 `true`로 설정된 경우 UPN이 비어 있으면 인증이 실패하지만 SPN이 비어 있으면 성공합니다.  
  
-   "단일 쇼트"라고도 하는 Kerberos direct를 사용하는 경우 인증이 실패합니다.  
  
### <a name="using-the-identity-element-in-configuration"></a>사용 하 여 \<identity > 구성 요소  
 이전에 Certificate에 표시된 바인딩에서 클라이언트 자격 증명 형식을 변경하면`,` 생성된 WSDL에 다음 코드에 표시된 ID 값에 대한 Base64로 serialize된 X.509 인증서가 포함됩니다. 이는 Windows 이외의 모든 클라이언트 자격 증명 형식에 대한 기본값입니다.  
  
  
  
 구성에 <`identity`> 요소를 사용하거나 코드에서 ID를 설정하여 기본 서비스 ID의 값을 변경하거나 ID 형식을 변경할 수 있습니다. 다음 구성 코드에서는 값 `contoso.com`으로 DNS(Domain Name System) ID를 설정합니다.  
  
  
  
### <a name="setting-identity-programmatically"></a>프로그래밍 방식으로 ID 설정  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 자동으로 확인하므로 서비스가 명시적으로 ID를 지정할 필요는 없습니다. 그러나 필요한 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 끝점에 ID를 지정할 수 있습니다. 다음 코드에서는 특정 DNS ID를 사용하여 새 서비스 끝점을 추가합니다.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 지정 클라이언트 Id 검증 도구 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
