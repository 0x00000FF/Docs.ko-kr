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
ms.workload: dotnet
ms.openlocfilehash: 8a822e87f03c4fa7e1ce7449f09efd178b87cc99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="json-web-token-handler"></a>JSON 웹 토큰 처리기
Windows Identity Foundation의 JSON 웹 토큰 처리기 확장을 사용하면 응용 프로그램에서 JWT(JSON 웹 토큰)를 만들고 유효성을 검사할 수 있습니다. JWT 토큰 처리기는 다른 내장 보안 토큰 처리기와 같이 WIF 파이프라인에서 실행하도록 구성할 수 있습니다. 그러나 독립적으로 사용하여 경량형 응용 프로그램에서 토큰의 유효성 검사를 수행할 수도 있습니다. JWT 토큰 처리기는 Microsoft Azure Active Directory 인증과 같이 OAuth 2.0 전달자 토큰 체계를 사용하는 경우 특히 유용합니다.  
  
 JWT 토큰 처리기는 NuGet 패키지로 사용할 수 있습니다. 자세한 내용은 [JSON Web Token 처리기 패키지 다운로드](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md)를 참조하세요.  
  
## <a name="scenarios"></a>시나리오  
 JWT 토큰 처리기에서는 다음과 같은 주요 시나리오를 사용할 수 있습니다.  
  
-   **서버 응용 프로그램에서 JWT 토큰의 유효성 검사**: 이 시나리오에서 Litware라는 회사는 웹 로그온 요청을 처리하는 데 WIF를 사용하는 서버 응용 프로그램을 보유합니다. Litware를 사용하면 응용 프로그램이 인증에 JWT 토큰을 사용할 수 있습니다. 응용 프로그램이 JWT 토큰 처리기로 업데이트된 다음 응용 프로그램 구성이 WIF 파이프라인에서 JWT 토큰 처리기를 추가하도록 업데이트됩니다. 업데이트되고 새 요청이 WIF 파이프라인을 시작하면 JWT 토큰이 새 처리기를 사용하여 유효성 검사되고 인증이 성공적으로 완료됩니다.  
  
-   **REST 웹 서비스에서 JWT 토큰 유효성 검사**: 이 시나리오에서 Litware라는 회사는 Microsoft Azure Active Directory로 보호되는 REST 웹 서비스를 보유하고 있습니다. 웹 서비스에 대한 요청은 Microsoft Azure AD의 인증을 받아야 하며, 성공적으로 인증되면 JWT 토큰이 발급됩니다. Litware에는 웹 서비스에 액세스해야 하는 클라이언트 응용 프로그램이 있습니다. 클라이언트가 웹 서비스에 대한 요청을 만들고 Microsoft Azure AD의 JWT 토큰을 제공합니다. 그런 다음 웹 서비스에서 JWT 토큰 처리기를 사용하여 해당 토큰의 유효성을 검사합니다. JWT 토큰 처리기가 토큰의 유효성을 검사하면 원하는 리소스가 웹 서비스에 의해 클라이언트로 반환됩니다.  
  
## <a name="features"></a>기능  
 JWT 토큰 처리기의 특징은 다음과 같습니다.  
  
-   **JWT 토큰 유효성 검사**: 응용 프로그램의 WIF 파이프라인의 일부 또는 WIF에 독립적으로 호출되는 방식 중 하나인 토큰 처리기의 유효성 검사 논리로 JWT 토큰의 유효성을 쉽게 검사할 수 있습니다.  
  
-   **JWT 토큰 만들기**: JWT 토큰 처리기를 사용하여 다운스트림 서비스에서 인증을 위해 JWT 토큰을 만들 수 있습니다.
