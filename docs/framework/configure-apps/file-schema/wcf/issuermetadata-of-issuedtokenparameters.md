---
title: <issuerMetadata> / <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: e46e56c6285af24941a550b2c4f7dec3b441db69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214808"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a>\<issuerMetadata >의 \<issuedTokenParameters >
\<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<security>  
\<issuedTokenParameters>  
\<issuerMetadata>  
  
## <a name="syntax"></a>구문  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|주소|필수 요소. 엔드포인트의 주소를 지정하는 문자열입니다. 주소는 절대 URI이어야 합니다. 기본값은 빈 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|주소 헤더 컬렉션입니다.|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [사용자 지정 바인딩을 사용하는 보안 기능](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [바인딩](../../../../../docs/framework/wcf/bindings.md)
- [바인딩 확장명](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Custom Binding Security](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
