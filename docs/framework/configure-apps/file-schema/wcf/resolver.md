---
title: "&lt;해결 프로그램&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a9b63848590fba6e07a4a32d8ffd70c277448adf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltresolvergt"></a>&lt;해결 프로그램&gt;
피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.  
  
 \<시스템입니다. ServiceModel >  
\<바인딩 >  
\<netPeerBinding >  
\<바인딩 >  
\<해결 프로그램 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`mode`|이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.|  
|`referralPolicy`|피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<헤더 >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|사용자 지정 피어 확인자 서비스의 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<바인딩 >](../../../../../docs/framework/misc/binding.md)|모든 바인딩 기능을 정의 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.|  
  
## <a name="remarks"></a>설명  
 피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다. 또한 이 확인자는 피어 노드가 알려지고 피어 메시에서 사용할 수 있게 되는 메커니즘인 피어 메시를 통해 노드를 "등록"하는 데에도 사용됩니다. 피어 확인자에 대 한 자세한 내용은 참조 하십시오. [피어 확인 자의](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [피어 확인자](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Peerchannel은 응용 프로그램에 사용자 지정 해결 프로그램 추가](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
