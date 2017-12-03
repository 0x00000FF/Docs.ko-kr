---
title: "핵심 통신: Webhost 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 707b97c49d6a6f5262719e91f8cb38fe7da53601
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-webhost-support"></a>핵심 통신: Webhost 지원
이 항목에서는 Webhost 지원에 의해 생성된 모든 예외를 보여 줍니다.  
  
## <a name="exception-list"></a>예외 목록  
  
|리소스 코드|리소스 문자열|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|이 서비스는 ASP.NET 호환성이 필요하며 IIS에서 호스팅되어야 합니다. Web.config에서 ASP.NET 호환성이 설정된 상태로 IIS에서 서비스를 호스팅하거나 AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode 속성을 Required가 아닌 값으로 설정하십시오.|  
|Hosting_ListenerNotFoundForActivationInRecycling|지정된 주소에서 활성 상태로 수신 대기하고 있는 채널이 없습니다. 응용 프로그램이 재활용되면 서비스가 닫힙니다.|  
|Hosting_NonHTTPInCompatibilityMode|ASP.NET 호환성 하에 지원되는 유일한 프로토콜은 HTTP 및 HTTPS입니다. 지정된 끝점을 제거하거나 응용 프로그램에 대한 ASP.NET 호환성을 사용하지 않습니다.|  
|Hosting_ProcessNotExecutingUnderHostedContext|현재 호스팅 환경 내에서 지정된 호스팅 프로세스를 호출할 수 없습니다. 이 API는 IIS(인터넷 정보 서비스) 또는 Windows Process Activation Service에서 호스팅되는 호출 응용 프로그램이 필요합니다.|  
|Hosting_ServiceCompatibilityRequire|서비스에 ASP.NET 호환성이 필요하기 때문에 서비스를 활성화할 수 없습니다. ASP.NET 호환성이 이 응용 프로그램에 사용하도록 설정되지 않았습니다. Web.config 파일에서 ASP.NET 호환성을 사용하도록 설정하거나 AspNetCompatibilityRequirementsAttribute.AspNetCompatibility를 설정합니다.|
