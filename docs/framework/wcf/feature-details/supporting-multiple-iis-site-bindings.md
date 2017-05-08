---
title: "여러 IIS 사이트 바인딩 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 여러 IIS 사이트 바인딩 지원
IIS\(인터넷 정보 서비스\) 7.0에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅하는 경우 동일한 사이트에 대해 동일한 프로토콜을 사용하는 여러 기본 주소를 제공할 수 있습니다.이렇게 하면 동일한 서비스에서 여러 다른 URI에 응답할 수 있습니다.이는 http:\/\/www.contoso.com 및 http:\/\/contoso.com에서 수신 대기하는 서비스를 호스팅하거나내부 사용자에 대한 기본 주소와 외부 사용자에 대한 별도의 기본 주소가 있는 서비스를 만들려는 경우에유용합니다\(예: http:\/\/internal.contoso.com 및 http:\/\/www.contoso.com\).  
  
> [!NOTE]
>  이 기능은 HTTP 프로토콜을 통해서만 사용할 수 있습니다.  
  
## 여러 기본 주소  
 이 기능은 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서만 사용할 수 있습니다.이 기능은 기본적으로 사용하지 않도록 설정되어 있습니다.이 기능을 사용하도록 설정하려면 다음 예제와 같이 `multipleSiteBindingsEnabled` 특성을 Web.config 파일의 \<`serviceHostingEnvironment`\> 요소에 추가하고 `true`로 설정해야 합니다.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled=”true”/>  
```  
  
 IIS에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하는 경우 응용 프로그램이 들어 있는 가상 디렉터리의 URI를 기반으로 하나의 기본 주소가 만들어집니다.인터넷 정보 서비스 관리자를 사용하여 웹 사이트에 하나 이상의 바인딩을 추가하여 동일한 프로토콜을 사용하는 기본 주소를 추가할 수 있습니다.각 바인딩에 대해 프로토콜\(HTTP 또는 HTTPS\), IP 주소, 포트 및 호스트 이름을 지정합니다.인터넷 정보 서비스 관리자 사용에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [IIS 관리자\(IIS 7\)](http://go.microsoft.com/fwlink/?LinkId=164057)\(영문 페이지일 수 있음\)를 참조하십시오.바인딩을 사이트에 추가하는 방법에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [웹 사이트 만들기\(IIS 7\)](http://go.microsoft.com/fwlink/?LinkId=164060)\(영문 페이지일 수 있음\)를 참조하십시오.  
  
 동일한 사이트에 대해 여러 기본 주소를 지정하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 도움말 페이지의 내용, 스키마 가져오기 및 서비스에서 생성되는 WSDL\/MEX 정보에 영향을 줍니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 도움말 페이지에는 서비스와 통신할 수 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 생성하는 데 사용할 명령줄이 표시됩니다.이 명령줄에는 웹 사이트에 대한 IIS 바인딩에 지정된 첫 번째 주소만 포함됩니다.마찬가지로 스키마를 가져올 때도 IIS 바인딩에 지정된 첫 번째 기본 주소만 사용됩니다.WSDL 및 MEX 데이터에는 IIS 바인딩에 지정된 모든 기본 주소가 포함됩니다.  
  
> [!WARNING]
>  이는 서비스에 두 개의 기본 주소가 있으면 하나는 내부 사용자용이고 다른 하나는 외부 사용자용이며, 두 주소 모두 서비스에서 생성되는 WSDL\/MEX 정보에 지정됨을 의미합니다.