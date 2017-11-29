---
title: "JSON 웹 토큰 처리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 6772d484fa4d0ed3948ecee26adb2cf886340f11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="json-web-token-handler"></a><span data-ttu-id="34d29-102">JSON 웹 토큰 처리기</span><span class="sxs-lookup"><span data-stu-id="34d29-102">JSON Web Token Handler</span></span>
<span data-ttu-id="34d29-103">Windows Identity Foundation의 JSON 웹 토큰 처리기 확장을 사용하면 응용 프로그램에서 JWT(JSON 웹 토큰)를 만들고 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-103">The JSON Web Token Handler extension for Windows Identity Foundation enables you to create and validate JSON Web Tokens (JWT) in your applications.</span></span> <span data-ttu-id="34d29-104">JWT 토큰 처리기는 다른 내장 보안 토큰 처리기와 같이 WIF 파이프라인에서 실행하도록 구성할 수 있습니다. 그러나 독립적으로 사용하여 경량형 응용 프로그램에서 토큰의 유효성 검사를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-104">The JWT Token Handler can be configured to run in the WIF pipeline like other built-in security token handlers, but it can also be used independently to perform token validation in lightweight applications.</span></span> <span data-ttu-id="34d29-105">JWT 토큰 처리기는 Microsoft Azure Active Directory 인증과 같이 OAuth 2.0 전달자 토큰 체계를 사용하는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-105">The JWT Token Handler is particularly useful when using an OAuth 2.0 bearer token scheme, such as authenticating to Windows Azure Active Directory.</span></span>  
  
 <span data-ttu-id="34d29-106">JWT 토큰 처리기는 NuGet 패키지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-106">The JWT Token Handler is available as a NuGet package.</span></span> <span data-ttu-id="34d29-107">자세한 내용은 [JSON Web Token 처리기 패키지 다운로드](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34d29-107">See [Downloading the JSON Web Token Handler Package](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md) for more information.</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="34d29-108">시나리오</span><span class="sxs-lookup"><span data-stu-id="34d29-108">Scenarios</span></span>  
 <span data-ttu-id="34d29-109">JWT 토큰 처리기에서는 다음과 같은 주요 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-109">The JWT Token Handler enables the following key scenarios:</span></span>  
  
-   <span data-ttu-id="34d29-110">**서버 응용 프로그램에서 JWT 토큰의 유효성 검사**: 이 시나리오에서 Litware라는 회사는 웹 로그온 요청을 처리하는 데 WIF를 사용하는 서버 응용 프로그램을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-110">**Validate a JWT Token in a Server Application**: In this scenario, a company named Litware has a server application that uses WIF to handle web sign-on requests.</span></span> <span data-ttu-id="34d29-111">Litware를 사용하면 응용 프로그램이 인증에 JWT 토큰을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-111">Litware wants to enable their application to use JWT tokens for authentication.</span></span> <span data-ttu-id="34d29-112">응용 프로그램이 JWT 토큰 처리기로 업데이트된 다음 응용 프로그램 구성이 WIF 파이프라인에서 JWT 토큰 처리기를 추가하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-112">The application is updated with the JWT Token Handler, and then the application configuration is updated to add the JWT Token Handler in the WIF pipeline.</span></span> <span data-ttu-id="34d29-113">업데이트되고 새 요청이 WIF 파이프라인을 시작하면 JWT 토큰이 새 처리기를 사용하여 유효성 검사되고 인증이 성공적으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-113">After the updates have been made and a new request enters the WIF pipeline, the JWT token is validated using the new handler and successful authentication occurs.</span></span>  
  
-   <span data-ttu-id="34d29-114">**REST 웹 서비스에서 JWT 토큰 유효성 검사**: 이 시나리오에서 Litware라는 회사는 Microsoft Azure Active Directory로 보호되는 REST 웹 서비스를 보유하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-114">**Validate a JWT Token in a REST Web Service**: In this scenario, a company named Litware has a REST web service that is secured by Windows Azure Active Directory.</span></span> <span data-ttu-id="34d29-115">웹 서비스에 대한 요청은 Microsoft Azure AD의 인증을 받아야 하며, 성공적으로 인증되면 JWT 토큰이 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-115">Requests to the web service must be authenticated by Windows Azure AD, which issues a JWT token upon successful authentication.</span></span> <span data-ttu-id="34d29-116">Litware에는 웹 서비스에 액세스해야 하는 클라이언트 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-116">Litware has a client application that needs to access the web service.</span></span> <span data-ttu-id="34d29-117">클라이언트가 웹 서비스에 대한 요청을 만들고 Microsoft Azure AD의 JWT 토큰을 제공합니다. 그런 다음 웹 서비스에서 JWT 토큰 처리기를 사용하여 해당 토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-117">The client makes a request to the web service and presents its JWT token from Windows Azure AD, which is then validated by the web service using the JWT Token Handler.</span></span> <span data-ttu-id="34d29-118">JWT 토큰 처리기가 토큰의 유효성을 검사하면 원하는 리소스가 웹 서비스에 의해 클라이언트로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-118">After the JWT Token Handler has validated the token, the desired resource is returned to the client by the web service.</span></span>  
  
## <a name="features"></a><span data-ttu-id="34d29-119">기능</span><span class="sxs-lookup"><span data-stu-id="34d29-119">Features</span></span>  
 <span data-ttu-id="34d29-120">JWT 토큰 처리기의 특징은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-120">The JWT Token Handler offers the following features:</span></span>  
  
-   <span data-ttu-id="34d29-121">**JWT 토큰 유효성 검사**: 응용 프로그램의 WIF 파이프라인의 일부 또는 WIF에 독립적으로 호출되는 방식 중 하나인 토큰 처리기의 유효성 검사 논리로 JWT 토큰의 유효성을 쉽게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-121">**Validate a JWT Token**: JWT tokens can be easily validated by the token handler’s validation logic, either as a part of the application’s WIF pipeline or called independently of WIF</span></span>  
  
-   <span data-ttu-id="34d29-122">**JWT 토큰 만들기**: JWT 토큰 처리기를 사용하여 다운스트림 서비스에서 인증을 위해 JWT 토큰을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d29-122">**Create a JWT Token**: The JWT Token Handler can be used to create JWT tokens for authorization in downstream services</span></span>
