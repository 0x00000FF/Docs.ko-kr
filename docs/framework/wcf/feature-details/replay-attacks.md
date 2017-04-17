---
title: "재생 공격 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 재생 공격
공격자가 두 당사자 간에 메시지 스트림을 복사하고 하나 이상의 당사자에게 스트림을 재생하는 경우 *재생 공격*이 발생합니다.완화되지 않은 경우 공격을 받기 쉬운 컴퓨터는 스트림을 올바른 메시지로 처리하여 항목에 대한 중복 주문과 같은 잘못된 결과의 범위에 있게 됩니다.  
  
## 바인딩이 반사 공격을 받기 쉬운 경우  
 *반사 공격*은 메시지가 받는 사람으로부터 회신으로 온 경우 보낸 사람에게 메시지를 다시 재생하는 것입니다.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메커니즘의 표준 *재생 검색*은 이를 자동으로 처리하지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모델이 서명된 메시지 ID를 요청 메시지에 추가하고 응답 메시지에 서명된 `relates-to` 헤더가 있어야 하므로 반사 공격은 기본적으로 완화됩니다.따라서 요청 메시지를 응답으로 재생할 수 없습니다.보안 RM\(신뢰할 수 있는 메시지\) 시나리오에서 반사 공격은 다음과 같은 이유로 완화됩니다.  
  
-   시퀀스 만들기 및 시퀀스 만들기 응답 메시지 스키마는 다릅니다.  
  
-   단면 시퀀스의 경우 클라이언트가 보내는 시퀀스 메시지는 클라이언트가 그러한 메시지를 인식할 수 없으므로 재생될 수 없습니다.  
  
-   이중 시퀀스의 경우 두 시퀀스 ID는 고유해야 합니다.따라서 나가는 시퀀스 메시지를 들어오는 시퀀스 메시지로 재생할 수 없습니다\(모든 시퀀스 헤더 및 본문도 서명됨\).  
  
 반사 공격을 받기 쉬운 바인딩은 WS\-Addressing이 없는 바인딩 즉, WS\-Addressing이 사용되지 않는 바인딩을 사용자 지정하고 대칭 키 기반 보안을 사용하는 바인딩입니다.<xref:System.ServiceModel.BasicHttpBinding>은 기본적으로 WS\-Addressing을 사용하지 않지만, 이 공격에 노출될 수 있는 방식으로는 대칭 키 기반 보안을 사용하지 않습니다.  
  
 사용자 지정 바인딩을 완화하는 것은 보안 컨텍스트를 설정하지 않거나 WS\-Addressing 헤더를 요청하는 것입니다.  
  
## 웹 팜: 공격자가 여러 노드에 요청 재생  
 클라이언트는 웹 팜에 구현된 서비스를 사용합니다.공격자는 팜의 한 노드로 보내진 요청을 팜의 다른 노드에 재생합니다.또한, 서비스를 다시 시작하는 경우 재생 캐시가 플러시되어 공격자가 요청을 재생할 수 있습니다.캐시에 이전에 사용된 메시지 서명 값이 있고 캐시가 재생되지 않으므로 그러한 서명은 한 번만 사용할 수 있습니다.재생 캐시는 웹 팜에서 공유되지 않습니다.  
  
 완화 방안은 다음과 같습니다.  
  
-   상태 저장 보안 컨텍스트 토큰\(보안 대화 사용 또는 사용 안 함\)과 함께 메시지 모드 보안을 사용합니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
-   전송 수준 보안을 사용하도록 서비스를 구성합니다.  
  
## 참고 항목  
 [보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [정보 공개](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [권한 상승](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [서비스 거부](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [변조](../../../../docs/framework/wcf/feature-details/tampering.md)   
 [지원되지 않는 시나리오](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)