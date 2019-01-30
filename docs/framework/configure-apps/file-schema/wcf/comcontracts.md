---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 3e3e4bf18b204db5a4068cc3f6cbb1337d5f611d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254316"
---
# <a name="comcontracts"></a><span data-ttu-id="e6170-101">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e6170-101">\<comContracts></span></span>
<span data-ttu-id="e6170-102">`comContracts` 구성 섹션에는 COM+ 통합 서비스 계약의 다양한 속성을 지정할 수 있게 해 주는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="e6170-103">네임스페이스 및 계약 지정</span><span class="sxs-lookup"><span data-stu-id="e6170-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="e6170-104">COM + 통합 서비스 계약은 현재 제한 되며는 `http://tempuri.org` 네임 스페이스, 계약 이름은 지원 COM 인터페이스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="e6170-105">그러나 구성 파일에서 `comContracts` 섹션을 사용하여 대안을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="e6170-106">예를 들어 다음 구성을 사용하여 서비스 계약의 네임스페이스 및 계약 이름과 세션 바인딩에 사용법을 적용할 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="e6170-107">지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="e6170-108">이 섹션이 비어 있으면 서비스 초기화에서는 지원 COM 인터페이스 ID에서 가져온 기본 네임스페이스 및 계약 이름을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="e6170-109">또한 사용할 수 있습니다 합니다 [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) COM + 구성 요소의 인터페이스가 웹 서비스로 노출 된 경우 표시 되는 COM + 메서드를 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-109">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="e6170-110">사용할 수도 있습니다는 [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) 통합에 사용 되는 지속 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-110">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="e6170-111">마지막으로 사용할 수 있습니다 합니다 [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) 형식 UDT (사용자 정의) 서비스 계약에 포함 될 수 있는 포함 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e6170-111">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6170-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6170-112">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="e6170-113">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="e6170-113">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [<span data-ttu-id="e6170-114">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="e6170-114">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [<span data-ttu-id="e6170-115">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="e6170-115">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [<span data-ttu-id="e6170-116">\<comContract></span><span class="sxs-lookup"><span data-stu-id="e6170-116">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [<span data-ttu-id="e6170-117">COM+ 애플리케이션과 통합</span><span class="sxs-lookup"><span data-stu-id="e6170-117">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e6170-118">방법: COM + 서비스 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e6170-118">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
