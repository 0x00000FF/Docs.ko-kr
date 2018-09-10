---
title: 클라이언트 응용 프로그램 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
ms.openlocfilehash: d58510240593f73ff761aa669035f28598006c10
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522002"
---
# <a name="client-application-services"></a>클라이언트 응용 프로그램 서비스
클라이언트 응용 프로그램 서비스를 통해 Microsoft ASP.NET 2.0 AJAX 확장에 포함된 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 로그인, 역할 및 프로필 응용 프로그램 서비스를 사용하는 Windows 기반 응용 프로그램을 쉽게 만들 수 있습니다. 이 서비스를 통해 여러 웹 응용 프로그램과 Windows 기반 응용 프로그램이 단일 서버에서 사용자 정보와 사용자 관리 기능을 공유할 수 있습니다. 예를 들어 이 서비스를 통해 다음 작업을 수행할 수 있습니다.  
  
-   사용자를 인증합니다. 인증 서비스를 통해 사용자 ID를 확인할 수 있습니다.  
  
-   인증된 사용자의 역할을 확인합니다. 역할 서비스를 통해 사용자 역할에 따라 응용 프로그램의 사용자 인터페이스를 변경할 수 있습니다. 예를 들어 관리자 역할에 있는 사용자에게 추가 기능을 제공할 수 있습니다.  
  
-   서버에 있는 사용자별 응용 프로그램 설정을 저장하고 액세스합니다. 웹 설정 서비스(프로필 서비스라고도 함)를 통해 여러 응용 프로그램과 위치에서 설정을 공유할 수 있습니다.  
  
 클라이언트 응용 프로그램 서비스는 응용 프로그램 구성 파일에서 지정할 수 있는 클라이언트 서비스 공급자를 통해 웹 서비스 확장성 모델을 활용합니다. 이 서비스는 네트워크 연결을 사용할 수 없는 경우 인증, 역할 및 설정 데이터를 위해 로컬 캐시를 사용하는 오프라인 기능을 포함합니다.  
  
 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 응용 프로그램 서비스에 대한 자세한 내용은 [ASP.NET 응용 프로그램 서비스 개요](https://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)를 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [클라이언트 응용 프로그램 서비스 개요](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 클라이언트 응용 프로그램 서비스 공급자를 통해 제공되는 기능을 설명합니다.  
  
 [방법: 클라이언트 응용 프로그램 서비스 구성](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Visual Studio 프로젝트 디자이너를 사용하여 응용 프로그램 서비스를 사용하도록 설정하고 구성하는 방법을 설명합니다. 또한 App.config 파일에 대한 해당 변경 내용을 설명합니다.  
  
 [방법: 클라이언트 응용 프로그램 서비스에서 사용자 로그인 구현](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 응용 프로그램이 클라이언트 인증 서비스 공급자를 사용하도록 구성된 경우 사용자의 유효성을 검사하는 방법을 설명합니다.  
  
 [연습: 클라이언트 응용 프로그램 서비스 사용](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 모든 클라이언트 응용 프로그램 서비스 기능을 단일 응용 프로그램에 결합하는 방법을 설명합니다. 이 연습에서는 완벽한 지침을 제공합니다. 예를 들어 클라이언트 응용 프로그램 서비스를 테스트하는 데 사용할 수 있는 ASP.NET 웹 서비스 응용 프로그램을 만드는 방법에 대한 지침을 포함합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 응용 프로그램 서비스 개요](https://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [Microsoft Ajax에서 양식 인증 사용](https://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [Microsoft Ajax에서 역할 정보 사용](https://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [Microsoft Ajax에서 프로필 정보 사용](https://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [ASP.NET 인증](https://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 [역할을 사용하여 인증 관리](https://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)    
 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)
