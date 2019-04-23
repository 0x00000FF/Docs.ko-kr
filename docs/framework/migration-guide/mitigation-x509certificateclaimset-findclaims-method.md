---
title: '완화: X509CertificateClaimSet.FindClaims 메서드'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3b3645d9fc00087e163b9200edb5fbcf0dbbd9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217213"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="4224c-102">완화: X509CertificateClaimSet.FindClaims 메서드</span><span class="sxs-lookup"><span data-stu-id="4224c-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="4224c-103">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱부터 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드는 `claimType` 인수를 해당 SAN 필드의 모든 DNS 항목과 일치시키려 합니다.</span><span class="sxs-lookup"><span data-stu-id="4224c-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)],  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4224c-104">영향</span><span class="sxs-lookup"><span data-stu-id="4224c-104">Impact</span></span>  
 <span data-ttu-id="4224c-105">이 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]로 시작하는 .NET Framework 버전을 대상으로 하는 응용 프로그램에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4224c-105">This change only affects apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="4224c-106">이전 버전의 .NET Framework를 대상으로 하는 앱의 경우에는 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드가 `claimType` 인수를 마지막 DNS 항목에만 일치시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4224c-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4224c-107">완화</span><span class="sxs-lookup"><span data-stu-id="4224c-107">Mitigation</span></span>  
 <span data-ttu-id="4224c-108">이러한 변경을 원치 않는 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]로 시작하는 .NET Framework 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4224c-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="4224c-109">또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이후 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4224c-109">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4224c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4224c-110">See also</span></span>

- [<span data-ttu-id="4224c-111">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="4224c-111">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
