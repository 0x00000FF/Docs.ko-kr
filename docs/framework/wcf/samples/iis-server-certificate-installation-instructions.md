---
title: "IIS(인터넷 정보 서비스) 서버 인증서 설치 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4b9496d471ca262e640c927619ccea8e4b4f4145
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>IIS(인터넷 정보 서비스) 서버 인증서 설치 지침
IIS(인터넷 정보 서비스)와 안전하게 통신하는 샘플을 실행하려면 서버 인증서를 만들어 설치해야 합니다.  
  
## <a name="step-1-creating-certificates"></a>1단계: 인증서 만들기  
 컴퓨터의 인증서를 만들려면 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 IIS와의 보안 통신을 사용하는 각 샘플에 포함된 Setup.bat를 실행합니다. 이 일괄 처리 파일을 실행하기 전에 경로에 Makecert.exe가 포함된 폴더가 있는지 확인합니다. Setup.bat에서 인증서를 만드는 데 사용되는 명령은 다음과 같습니다.  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>2단계. 인증서 설치  
 만든 인증서를 설치하는 데 필요한 단계는 사용 중인 IIS의 버전에 따라 다릅니다.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>IIS 5.1(Windows XP) 및 IIS 6.0(Windows Server 2003)에 IIS를 설치하려면  
  
1.  인터넷 정보 서비스 관리자 MMC 스냅인을 엽니다.  
  
2.  기본 웹 사이트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  
  
3.  선택 된 **디렉터리 보안** 탭 합니다.  
  
4.  클릭는 **서버 인증서** 단추입니다. 웹 서버 인증서 마법사가 시작됩니다.  
  
5.  마법사에서 필요한 작업을 완료합니다. 인증서를 할당하는 옵션을 선택합니다. 표시된 인증서 목록에서 ServiceModelSamples-HTTPS-Server 인증서를 선택합니다.  
  
     ![IIS 인증서 마법사](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6.  HTTPS 주소 https://localhost/servicemodelsamples/service.svc를 사용하여 브라우저에서 서비스에 대한 액세스를 테스트합니다.  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Httpcfg.exe를 사용하여 SSL을 이전에 구성한 경우  
  
1.  Makecert.exe를 사용하거나 Setup.bat를 실행하여 서버 인증서를 만듭니다.  
  
2.  IIS 관리자를 실행하고 이전 단계에 따라 인증서를 설치합니다.  
  
3.  다음 코드 줄을 클라이언트 프로그램에 추가합니다.  
  
> [!IMPORTANT]
>  이 코드는 Makecert.exe로 만든 인증서 같은 테스트 인증서에만 필요합니다. 프로덕션 코드에 사용하지 않는 것이 좋습니다.  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>IIS 7.0(Windows Vista 및 Windows Server 2008)에서 IIS를 설치하려면  
  
1.  **시작** 메뉴를 클릭 **실행**, 다음 입력 **inetmgr** 를 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.  
  
2.  마우스 오른쪽 단추로 클릭는 **기본 웹 사이트** 선택 **바인딩 편집...**  
  
3.  클릭는 **추가** 의 단추는 **사이트 바인딩** 대화 상자.  
  
4.  선택 **HTTPS** 에서 **형식** 드롭 다운 목록입니다.  
  
5.  선택 된 **ServiceModelSamples HTTPS 서버** 에서 **SSL 인증서** 드롭다운 목록에서 클릭 하 고 **확인**합니다.  
  
6.  HTTPS 주소 https://localhost/servicemodelsamples/service.svc를 사용하여 브라우저에서 서비스에 대한 액세스를 테스트합니다.  
  
> [!NOTE]
>  설치한 테스트 인증서는 신뢰할 수 있는 인증서가 아니므로 이 인증서로 보안된 로컬 웹 주소를 검색할 때 추가 Internet Explorer 보안 경고가 발생할 수 있습니다.  
  
## <a name="removing-certificates"></a>인증서 제거  
  
-   앞서 설명한 대로 인터넷 정보 서비스 관리자를 사용하는 것은 동일하고, 인증서나 바인딩을 추가하는 대신 제거합니다.  
  
-   다음 명령을 사용하여 컴퓨터 인증서를 제거합니다.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
