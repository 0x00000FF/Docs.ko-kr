---
title: '&lt;endpointExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 3883a23c679abc83d7cfe9011b7cdb7e4154adfe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146448"
---
# <a name="ltendpointextensionsgt"></a><span data-ttu-id="63a5f-102">&lt;endpointExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="63a5f-102">&lt;endpointExtensions&gt;</span></span>
<span data-ttu-id="63a5f-103">이 섹션에서는 새 표준 엔드포인트를 컴퓨터 또는 응용 프로그램 구성 파일의 extensions 섹션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="63a5f-103">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="63a5f-104">`add` 키워드를 사용하고 요소의 `type` 특성을 해당 끝점 형식으로 설정하고, `name` 특성을 표준 끝점의 이름으로 설정하여 표준 끝점을 이 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a5f-104">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="63a5f-105">다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `<endpointExtensions>` 섹션에 표준 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="63a5f-105">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="63a5f-106">표준 엔드포인트를 등록한 다음 이를 다음 예제와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a5f-106">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="63a5f-107">에 [ \<끝점 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소를 `kind` 특성에 등록 된 표준 끝점 형식을 지정는 `<endpointExtensions>` 섹션.</span><span class="sxs-lookup"><span data-stu-id="63a5f-107">In the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="63a5f-108">`endpointConfiguration` 특성은 동일 하 게 됩니다는 `name` 특성에서 표준 끝점의 구성 요소는 `<standardEndpoints>` 섹션.</span><span class="sxs-lookup"><span data-stu-id="63a5f-108">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
