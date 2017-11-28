---
title: "발급자 이름 레지스트리 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
caps.latest.revision: "4"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: c6c1b72048f1f7cb421e5a19d34c2c2dea5463ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="validating-issuer-name-registry"></a><span data-ttu-id="33109-102">발급자 이름 레지스트리 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="33109-102">Validating Issuer Name Registry</span></span>
<span data-ttu-id="33109-103">Windows Identity Foundation의 VINR(Validating Issuer Name Registry)을 사용하면 다중 테넌트 응용 프로그램에서 들어오는 토큰이 신뢰할 수 있는 테넌트 및 ID 공급자에 의해 발급되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-103">The Validating Issuer Name Registry (VINR) for Windows Identity Foundation enables multi-tenant applications to ensure that an incoming token has been issued by a trusted tenant and identity provider.</span></span> <span data-ttu-id="33109-104">이 기능은 Microsoft Azure Active Directory에서 발급한 모든 토큰이 동일한 인증서를 사용하여 서명되므로 Microsoft Azure AD를 사용하는 다중 테넌트 응용 프로그램에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-104">This functionality is particularly useful for multi-tenant applications that use Windows Azure Active Directory because all tokens issued by Windows Azure AD are signed using the same certificate.</span></span> <span data-ttu-id="33109-105">동일한 인증서를 사용함에 따라 동일한 지문을 보유하는 여러 테넌트의 요청을 구분하기 위해 응용 프로그램이 유효성 검사 논리를 수행하려면 각 테넌트에 대한 발급자 이름을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-105">In order to differentiate between requests from multiple tenants that use the same certificate – and consequently have the same thumbprint – your application must persist the issuer name for each tenant to perform validation logic.</span></span> <span data-ttu-id="33109-106">VINR은 이러한 기능을 제공하며, 이를 통해 사용자가 사용자 지정 유효성 검사 논리를 추가하거나 발급자 레지스트리 데이터를 구성 파일 이외의 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-106">The VINR provides this functionality, and it also enables you to add custom validation logic or to store the issuer registry data in locations other than a configuration file.</span></span> <span data-ttu-id="33109-107">확장은 응용 프로그램의 WIF 파이프라인에 추가하거나 독립적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-107">The extension can be added to your application’s WIF pipeline or it can be used independently.</span></span>  
  
 <span data-ttu-id="33109-108">VINR은 NuGet 패키지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-108">The VINR is available as a NuGet package.</span></span> <span data-ttu-id="33109-109">자세한 내용은 [발급자 이름 레지스트리 유효성 검사 패키지 다운로드](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33109-109">See [Downloading the Validating Issuer Name Registry Package](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md) for more information.</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="33109-110">시나리오</span><span class="sxs-lookup"><span data-stu-id="33109-110">Scenarios</span></span>  
 <span data-ttu-id="33109-111">VINR을 통해 다음과 같은 주요 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-111">The VINR enables the following key scenario:</span></span>  
  
-   <span data-ttu-id="33109-112">**다중 테넌트 응용 프로그램에서 토큰의 유효성 검사**: 이 시나리오에서 Litware라는 회사는 Microsoft Azure AD와 같은 ID 공급자를 사용하는 다중 테넌트 응용 프로그램을 개발했습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-112">**Validate a Token in a Multi-Tenant Application**: In this scenario, a company named Litware has developed a multi-tenant application that uses an identity provider such as Windows Azure AD.</span></span> <span data-ttu-id="33109-113">이 응용 프로그램은 Contoso 및 Fabrikam, 두 고객을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-113">This application serves two customers: Contoso and Fabrikam.</span></span> <span data-ttu-id="33109-114">Fabrikam의 사용자가 Litware의 응용 프로그램을 인증하는 경우 Microsoft Azure AD에서 생성되는 토큰은 표준 인증서를 통해 서명되며 요청은 Fabrikam에 의해 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="33109-114">When a user from Fabrikam authenticates to Litware’s application, the resulting token from Windows Azure AD is signed using its standard certificate and the request is issued by Fabrikam.</span></span> <span data-ttu-id="33109-115">응용 프로그램은 발급자 이름과 토큰이 모두 유효한지 확인해야 하며, Microsoft Azure AD의 동일한 인증서를 사용하여 서명되는 Contoso의 요청을 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-115">The application needs to verify that both the issuer name and the token is valid, and needs to differentiate requests from Contoso that are signed using the same certificate from Windows Azure AD.</span></span> <span data-ttu-id="33109-116">VINR을 통해 Litware의 응용 프로그램에서 Contoso 및 Fabrikam과 같은 여러 테넌트의 요청을 쉽게 구분하고 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-116">The VINR makes it easy for Litware’s application to differentiate and validate requests from multiple tenants such as Contoso and Fabrikam.</span></span>  
  
## <a name="features"></a><span data-ttu-id="33109-117">기능</span><span class="sxs-lookup"><span data-stu-id="33109-117">Features</span></span>  
 <span data-ttu-id="33109-118">VINR의 특징은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33109-118">The VINR offers the following features:</span></span>  
  
-   <span data-ttu-id="33109-119">**다중 테넌트 응용 프로그램의 발급자 이름 및 토큰 유효성 검사**: 발급자 이름(테넌트) 및 토큰이 ID 공급자의 유효한 인증서를 사용하여 서명되었는지 여부를 확인하여 들어오는 토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-119">**Issuer Name and Token Validation for Multi-Tenant Applications**: Validates the incoming token by verifying the issuer name (tenant) and whether the token was signed using a valid certificate from the identity provider.</span></span>  
  
-   <span data-ttu-id="33109-120">**사용자 지정 유효성 검사 논리 및 데이터 저장소를 위한 확장성**: 고유한 유효성 검사 논리를 삽입하고 기본 구성 파일 이외의 데이터 저장소를 지정할 수 있는 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33109-120">**Extensibility for Custom Validation Logic and Data Stores**: Provides extensibility to inject your own validation logic and to specify a data store other than the default configuration file.</span></span>
