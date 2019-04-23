---
title: 클레임 만들기 및 리소스 값
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: bd9a8b7faf3cd7a648ff6b2a50ac68f21561497c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093698"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="15b32-102">클레임 만들기 및 리소스 값</span><span class="sxs-lookup"><span data-stu-id="15b32-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="15b32-103"><xref:System.IdentityModel.Claims.Claim> 클래스는 기본 제공 클레임 형식의 인스턴스를 만들 수 있는 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15b32-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="15b32-104">이러한 메서드 중에서 다음 메서드는 제공된 리소스에 대해 의미를 확인하거나 형식을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15b32-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <span data-ttu-id="15b32-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A>(바이트 배열의 길이 또는 콘텐츠를 확인하지 않음)</span><span class="sxs-lookup"><span data-stu-id="15b32-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <span data-ttu-id="15b32-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A>(바이트 배열의 길이 또는 콘텐츠를 확인하지 않음)</span><span class="sxs-lookup"><span data-stu-id="15b32-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="15b32-107">전달된 리소스 값이 올바른 형식인지 또는 정확한 종류의 정보를 포함하고 있는지(또는 둘 다인지) 확인하기 위해 위의 메서드를 호출할 때는 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15b32-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="15b32-108">다음 메서드는 특정 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15b32-108">The following methods take specific types:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="15b32-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="15b32-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="15b32-110">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="15b32-110">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
