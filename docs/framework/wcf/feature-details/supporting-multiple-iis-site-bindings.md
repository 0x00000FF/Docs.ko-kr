---
title: 여러 IIS 사이트 바인딩 지원
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 2c42ba7cf3713e5d165d10ce7049df8200d612fb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517877"
---
# <a name="supporting-multiple-iis-site-bindings"></a>여러 IIS 사이트 바인딩 지원
인터넷 정보 서비스 (IIS) 7.0에서 Windows Communication Foundation (WCF) 서비스를 호스팅하는 경우에 동일한 사이트의 동일한 프로토콜을 사용 하는 여러 기본 주소를 제공 하는 것이 좋습니다. 이렇게 하면 동일한 서비스에서 여러 다른 URI에 응답할 수 있습니다. 수신 대기 하는 서비스를 호스트 하려는 경우에 유용 http://www.contoso.com 고 http://contoso.com입니다. 내부 사용자에 대한 기본 주소와 외부 사용자에 대한 별도의 기본 주소가 있는 서비스를 만들려는 경우에 유용합니다. 예를 들어: http://internal.contoso.com 고 http://www.contoso.com입니다.  
  
> [!NOTE]
>  이 기능은 HTTP 프로토콜을 통해서만 사용할 수 있습니다.  
  
## <a name="multiple-base-addresses"></a>여러 기본 주소  
 이 기능은 IIS에서 호스팅되는 WCF 서비스에 사용할 수만 있습니다. 이 기능은 기본적으로 사용하지 않도록 설정되어 있습니다. 추가 사용 하도록 설정 해야 합니다는 `multipleSiteBindingsEnabled` 특성을 <`serviceHostingEnvironment`> Web.config 파일에 요소 파일 및 설정 `true`다음 예제에서와 같이 합니다.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 IIS에서 WCF 서비스 호스팅, IIS 응용 프로그램을 포함 하는 가상 디렉터리 URI에 따라 하나의 기본 주소를 만듭니다. 인터넷 정보 서비스 관리자를 사용하여 웹 사이트에 하나 이상의 바인딩을 추가하여 동일한 프로토콜을 사용하는 기본 주소를 추가할 수 있습니다. 각 바인딩에 대해 프로토콜(HTTP 또는 HTTPS), IP 주소, 포트 및 호스트 이름을 지정합니다. 인터넷 정보 서비스 관리자를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [IIS 관리자 (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164057)합니다. 사이트에 바인딩을 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [(IIS 7) 웹 사이트 만들기](https://go.microsoft.com/fwlink/?LinkId=164060)  
  
 동일한 사이트에 대 한 여러 기본 주소 지정 스키마 가져오기 및 서비스에 의해 생성 된 WSDL/MEX 정보에 WCF 도움말 페이지의 내용을 영향을 줍니다. WCF 도움말 페이지를 사용 하는 서비스와 통신할 수 있는 WCF 클라이언트 생성 명령줄이 표시 됩니다. 이 명령줄에는 웹 사이트에 대한 IIS 바인딩에 지정된 첫 번째 주소만 포함됩니다. 마찬가지로 스키마를 가져올 때도 IIS 바인딩에 지정된 첫 번째 기본 주소만 사용됩니다. WSDL 및 MEX 데이터에는 IIS 바인딩에 지정된 모든 기본 주소가 포함됩니다.  
  
> [!WARNING]
>  이는 서비스에 두 개의 기본 주소가 있으면 하나는 내부 사용자용이고 다른 하나는 외부 사용자용이며, 두 주소 모두 서비스에서 생성되는 WSDL/MEX 정보에 지정됨을 의미합니다.
