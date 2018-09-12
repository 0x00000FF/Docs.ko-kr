---
title: '방법: 개발 중 사용할 임시 인증서 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: ca495c23b30144013b8efe22b7bf6f3cf38b16cd
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44509949"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>방법: 개발 중 사용할 임시 인증서 만들기
보안 서비스 또는 Windows Communication Foundation (WCF)를 사용 하 여 클라이언트를 개발할 때 자격 증명으로 사용할 X.509 인증서를 제공 하는 데 필요한 경우가 있습니다. 일반적으로 인증서는 루트 인증 기관이 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 있는 인증서 체인의 일부입니다. 인증서 체인을 사용하면 일반적으로 루트 인증 기관이 조직 또는 비즈니스 사업부에 있는 인증서 집합의 범위를 지정할 수 있습니다. 개발 시 이를 에뮬레이트하려면 보안 요구 사항에 맞는 두 개의 인증서를 만듭니다. 첫 번째 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 있는 자체 서명된 인증서이고, 두 번째 인증서는 첫 번째 인증서에서 만들어지고 로컬 컴퓨터 위치의 개인 저장소나 현재 사용자 위치의 개인 저장소에 있습니다. 이 항목에서는 Powershell을 사용 하 여 이러한 두 인증서를 만드는 단계를 안내 [New-selfsignedcertificate)](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet.  
  
> [!IMPORTANT]
>  New-selfsignedcertificate cmdlet을 생성 하는 인증서는 테스트 목적 으로만 제공 됩니다. 서비스 또는 클라이언트를 배포할 때는 인증 기관에서 제공하는 적절한 인증서를 사용해야 합니다. 조직에서 Windows Server 인증서 서버에서 수 또는 타사 수이 있습니다.  
>   
>  기본적으로 [New-selfsignedcertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet는 자체 서명 된 인증서를 만들고 이러한 인증서가 안전 하지 않습니다. 저장소를 신뢰할 수 있는 루트 인증 기관에 자체 서명 된 인증서를 배치 더욱 긴밀 하 게 배포 환경의 시뮬레이션 하는 개발 환경을 만들 수 있습니다.  
  
 인증서 만들기 및 사용에 대 한 자세한 내용은 참조 하세요. [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다. 자격 증명으로 인증서를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)합니다. Microsoft Authenticode 기술 사용에 대 한 자습서를 참조 하세요 [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919)합니다.  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>자체 서명된 루트 인증 기관 인증서를 만들고 개인 키를 내보내려면  
  
다음 명령은 "RootCA" Current User Personal 저장소에서 주체 이름으로 자체 서명 된 인증서를 만듭니다. 
```
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```
이후 단계에서 필요한 곳에 가져올 수 있도록 인증서를 PFX 파일로 내보냅니다 해야 합니다. 개인 키를 사용 하 여 인증서를 내보낼 때 암호는 보호 해야 합니다. 암호를 저장 하는 것을 `SecureString` 사용 하 여는 [Export-pfxcertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-pfxcertificate?view=win10-ps) PFX 파일에 연결 된 개인 키를 사용 하 여 인증서를 내보내려면 cmdlet. 또한 공용 인증서만 사용 하 여 CRT 파일에 저장 합니다 [인증서 내보내기](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) cmdlet.
```
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>루트 인증 기관 인증서로 서명된 새 인증서를 만들려면  
  
다음 명령은 서명한 인증서를 만듭니다를 `RootCA` "SignedByRootCA" 발급자의 개인 키를 사용 하 여 주체 이름이 있습니다.
```
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert 
```
마찬가지로, PFX 파일 및 CRT 파일로 공개 키만 개인 키로 서명 된 인증서를 저장합니다.
```
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword 
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt        
```
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>신뢰할 수 있는 루트 인증 기관 저장소에 인증서 설치  
 자체 서명된 인증서를 만들면 신뢰할 수 있는 루트 인증 기관 저장소에 설치할 수 있습니다. 이때 인증서로 서명된 모든 인증서는 컴퓨터에 의해 신뢰됩니다. 따라서 인증서가 더 이상 필요하지 않으면 즉시 저장소에서 삭제합니다. 이 루트 인증 기관 인증서를 삭제하면 해당 인증서로 서명된 다른 모든 인증서의 권한이 해제됩니다. 루트 인증 기관 인증서는 단순히 필요에 따라 인증서 그룹의 범위를 지정할 수 있는 메커니즘입니다. 예를 들어 피어 투 피어 응용 프로그램에서는 일반적으로 제공된 인증서로 개인의 ID를 신뢰하므로 루트 인증 기관이 필요하지 않습니다.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>신뢰할 수 있는 루트 인증 기관에 자체 서명된 인증서를 설치하려면  
  
1.  인증서 스냅인을 엽니다. 자세한 내용은 [방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요.  
  
2.  인증서를 저장할 폴더( **로컬 컴퓨터** 또는 **현재 사용자**)를 엽니다.  
  
3.  **신뢰할 수 있는 루트 인증 기관** 폴더를 엽니다.  
  
4.  **인증서** 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 클릭한 다음 **가져오기**를 클릭합니다.  
  
5.  화면에 표시되는 마법사 지침에 따라 TempCa.cer를 저장소로 가져옵니다.  
  
## <a name="using-certificates-with-wcf"></a>WCF에서 인증서 사용  
 임시 인증서를 설정했으면 클라이언트 자격 증명 형식으로 인증서를 지정하는 WCF 솔루션을 이 인증서를 사용하여 개발할 수 있습니다. 예를 들어 다음 XML 구성에서는 메시지 보안과 인증서를 클라이언트 자격 증명 형식으로 지정합니다.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>인증서를 클라이언트 자격 증명 형식으로 지정하려면  
  
-   서비스의 구성 파일에서 다음 XML을 사용하여 보안 모드를 메시지로 설정하고 클라이언트 자격 증명 형식을 인증서로 설정합니다.  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 클라이언트에 대 한 구성 파일에서 인증서 사용자의 저장소에서 발견 되어 SubjectName 필드 값 "CohoWinery."를 검색 하 여 찾을 수를 지정 하려면 다음 XML을 사용  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 WCF에서의 인증서 사용에 대한 자세한 내용은 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 인증서를 마우스 오른쪽 단추로 클릭한 다음 **삭제** 를 클릭하여 **신뢰할 수 있는 루트 인증 기관** 및 **개인**폴더에서 임시 루트 인증 기관 인증서를 모두 삭제합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [서비스 및 클라이언트에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
