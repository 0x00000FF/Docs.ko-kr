---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273899"
---
# <a name="certificatevalidation"></a>\<certificateValidation>
토큰 처리기 인증서의 유효성을 검사 하는 데 사용 되는 설정을 제어 합니다. 특정 처리기를 자체 유효성 검사기를 사용 하 여 구성 된 경우이 설정은 무시 됩니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<certificateValidation>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> 사용할 X.509 인증서의 유효성 검사 모드를 지정 하는 값입니다. 기본값은 "PeerOrChainTrust"입니다. 사용자 지정 유효성 검사기를 지정 하려면이 특성을 "Custom"으로 설정 하 고 사용 하 여 유효성 검사기를 지정 합니다 [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) 요소입니다. 선택 사항입니다.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 사용할 X.509 인증서의 해지 모드를 지정 하는 값입니다. 기본값은 "Online"입니다. 선택 사항입니다.|  
|trustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다. 기본값은 "LocalMachine"입니다. 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|인증서 유효성 검사에 대 한 사용자 지정 형식을 지정합니다. 이 이와 같은 경우에 사용 됩니다 합니다 `certificateValidationMode` 특성을 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) 요소 "Custom"으로 설정 됩니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 `<certificateValidation>` 요소 아래에 있는 서비스 수준에서 지정할 수 있습니다 합니다 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서는 `<securityTokenHandlerConfiguration>` 요소입니다. 서비스에 지정 된 토큰 처리기 컬렉션의 설정을 무시 합니다. 일부 토큰 처리기를 사용 하면 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다. 서비스 수준 및 보안 토큰 처리기 컬렉션의 개별 토큰 처리기의 설정을 지정 된 재정의합니다.  
  
## <a name="example"></a>예제  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
