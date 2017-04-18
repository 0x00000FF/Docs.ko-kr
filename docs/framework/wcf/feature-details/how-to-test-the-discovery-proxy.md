---
title: "방법: 검색 프록시 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 검색 프록시 테스트
이 항목은 검색 프록시를 구현하는 방법에 대해 설명하는 네 항목 중 네 번째 항목입니다.  이전 항목인 [방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 응용 프로그램 구현](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)에서는 검색 프록시를 사용하여 서비스를 찾은 다음 이 서비스를 호출하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램을 구현했습니다.  이 항목에서는 검색 프록시, 서비스 및 클라이언트 응용 프로그램이 올바로 작동하는지 확인하는 방법에 대해 설명합니다.  
  
### 검색 프록시 실행  
  
1.  관리자 권한으로 명령 프롬프트를 엽니다.  
  
2.  "Windows 방화벽에서 이 프로그램의 일부 기능을 차단했습니다."라는 메시지가 포함된 대화 상자가 나타날 수 있습니다.  이 메시지가 나타나면 **차단 해제** 단추를 클릭합니다.  
  
3.  명령 프롬프트 내에서 검색 프록시인 DiscoveryProxy.exe를 실행합니다.  
  
4.  DiscoveryProxy.exe에 다음 텍스트가 표시됩니다. `Proxy started. Hit Enter to exit`  
  
### 검색 가능한 서비스 실행  
  
1.  관리자 권한으로 명령 프롬프트를 엽니다.  
  
2.  명령 프롬프트 내에서 검색 가능한 서비스인 Service.exe를 실행합니다.  
  
3.  DiscoveryProxy.exe에 다음 텍스트가 표시됩니다. `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### 클라이언트 응용 프로그램 실행  
  
1.  명령 프롬프트를 엽니다.  
  
2.  명령 프롬프트 내에서 클라이언트 응용 프로그램인 client.exe를 실행합니다.  
  
3.  몇 초 후에 클라이언트 응용 프로그램에 "Connecting to \[Service\-Endpoint\]"라는 텍스트가 표시됩니다.  
  
4.  service.exe에 "Greeting request received, I will respond."라는 텍스트가 표시됩니다.  
  
5.  client.exe에 "Hello Client\!"라는 텍스트가 표시됩니다.  
  
### 응용 프로그램 종료  
  
1.  클라이언트 응용 프로그램을 종료합니다.  
  
2.  서비스를 종료합니다.  검색 프록시에 다음 텍스트가 표시됩니다. `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`  
  
3.  검색 프록시를 종료합니다.  
  
## 참고 항목  
 [WCF Discovery 개요](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [방법: 검색 프록시 구현](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)   
 [방법: 검색 프록시에 등록할 검색 가능한 서비스 구현](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)   
 [방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 응용 프로그램 구현](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)