---
title: "방법: SSL 인증서를 사용하여 포트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SSL"
  - "WCF, 보안"
  - "WCF, 보안 모드"
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 방법: SSL 인증서를 사용하여 포트 구성
전송 보안을 사용하는 <xref:System.ServiceModel.WSHttpBinding> 클래스에 자체 호스트된 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 만드는 경우에는 X.509 인증서로 포트도 구성해야 합니다.  자체 호스트된 서비스를 만들지 않는 경우에는 IIS\(인터넷 정보 서비스\)에서 서비스를 호스트할 수 있습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [HTTP 전송 보안](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 포트를 구성하려면 컴퓨터에서 실행하는 운영 체제에 따라 다른 도구를 사용해야 합니다.  
  
 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]를 실행하는 경우 HttpCfg.exe 도구를 사용합니다.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에는 이 도구가 함께 설치됩니다.  [!INCLUDE[wxp](../../../../includes/wxp-md.md)]가 있으면 [Windows XP 서비스 팩 2 지원 도구](http://go.microsoft.com/fwlink/?LinkId=88606)에서 이 도구를 다운로드할 수 있습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Httpcfg 개요](http://go.microsoft.com/fwlink/?LinkId=88605)\(영문\).  [Windows 지원 도구 설명서](http://go.microsoft.com/fwlink/?LinkId=94840)\(영문\)에서는 Httpcfg.exe 도구에 대한 구문을 설명합니다.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)]를 실행하는 경우 이미 설치되어 있는 Netsh.exe 도구를 사용합니다.  
  
 이 항목에서는 다음과 같은 여러 절차를 수행하는 방법에 대해 설명합니다.  
  
-   컴퓨터의 현재 포트 구성 결정  
  
-   인증서의 지문 가져오기\(다음 두 절차에 필요\)  
  
-   SSL 인증서를 포트 구성에 바인딩  
  
-   SSL 인증서를 포트 구성에 바인딩 및 클라이언트 인증서 지원  
  
-   포트 번호에서 SSL 인증서 삭제  
  
 컴퓨터에 저장된 인증서를 수정하려면 관리자 권한이 필요합니다.  
  
### 포트의 구성 방법을 확인하려면  
  
1.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 다음 예제와 같이 HttpCfg.exe 도구를 사용하여 **query** 및 **ssl** 스위치로 현재 포트 구성을 봅니다.  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용하여 현재 포트 구성을 봅니다.  
  
    ```  
    netsh http show sslcert  
    ```  
  
### 인증서의 지문을 가져오려면  
  
1.  인증서 MMC 스냅인을 사용하여 클라이언트 인증 용도의 X.509 인증서를 찾습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  인증서의 지문에 액세스합니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3.  인증서의 지문을 메모장 등의 텍스트 편집기에 복사합니다.  
  
4.  16진수 문자 사이의 모든 공간을 제거합니다.  여기에 사용되는 방법 중 하나는 텍스트 편집기의 찾기 및 바꾸기 기능을 사용하여 각 공간을 null 문자로 바꾸는 것입니다.  
  
### SSL 인증서를 포트 번호에 바인딩하려면  
  
1.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 SSL\(Secure Sockets Layer\) 저장소에 "set" 모드의 HttpCfg.exe 도구를 사용하여 인증서를 포트 번호에 바인딩합니다.  도구에서는 다음 예제처럼 지문을 사용하여 인증서를 식별합니다.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   **\-i** 스위치는 구문이 `IP`:`port`와 같으며 컴퓨터의 포트 8012에 인증서를 설정하도록 도구에 지시합니다.  선택적으로, 번호 앞에 있는 4개의 0을 컴퓨터의 실제 IP 주소로 대체할 수 있습니다.  
  
    -   **\-h** 스위치는 인증서의 지문을 지정합니다.  
  
2.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용합니다.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   **certhash** 매개 변수는 인증서의 지문을 지정합니다.  
  
    -   **ipport** 매개 변수는 IP 주소 및 포트를 지정하고 설명한 Httpcfg.exe 도구의 **\-i** 스위치와 같이 작동합니다.  
  
    -   **appid** 매개 변수는 소유 응용 프로그램을 식별하는 데 사용할 수 있는 GUID입니다.  
  
### SSL 인증서를 포트 번호에 바인딩하고 클라이언트 인증서를 지원하려면  
  
1.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 전송 계층에 X.509 인증서를 사용하여 인증하는 클라이언트를 지원하려면 위의 절차를 수행하되 다음 예제처럼 추가 명령줄 매개 변수를 HttpCfg.exe에 전달합니다.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     **\-f** 스위치에는 `n` 구문이 있습니다. 여기서 n은 1에서 7 사이의 숫자입니다.  위의 예제와 같이 값 2를 사용하면 전송 계층에서 클라이언트 인증서가 활성화됩니다.  값 3을 사용하면 클라이언트 인증서가 활성화되고 해당 인증서가 Windows 계정에 매핑됩니다.  다른 값의 동작에 대한 자세한 내용은 HttpCfg.exe 도움말을 참조하세요.  
  
2.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 전송 계층에서 X.509 인증서를 사용하여 인증하는 클라이언트를 지원하려면 위의 절차를 수행하되 다음 예제처럼 추가 매개 변수를 사용합니다.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### 포트 번호에서 SSL 인증서를 삭제하려면  
  
1.  HttpCfg.exe 또는 Netsh.exe 도구를 사용하여 컴퓨터에 있는 모든 바인딩의 포트와 지문을 표시합니다.  정보를 디스크에 인쇄하려면 다음 예제와 같이 리디렉션 문자 "\>"를 사용합니다.  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 HttpCfg.exe 도구를 **delete** 및 **ssl** 키워드와 함께 사용합니다.  **\-i** 스위치를 사용하여 `IP`:`port` 번호를 지정하고 **\-h** 스위치를 사용하여 지문을 지정합니다.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다음 예제와 같이 Netsh.exe 도구를 사용합니다.  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## 예제  
 다음 코드에서는 전송 보안에 설정된 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하여 자체 호스트된 서비스를 만드는 방법을 보여 줍니다.  응용 프로그램을 만들 때에는 주소에 포트 번호를 지정합니다.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## 참고 항목  
 [HTTP 전송 보안](../../../../docs/framework/wcf/feature-details/http-transport-security.md)