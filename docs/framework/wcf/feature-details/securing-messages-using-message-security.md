---
title: "메시지 보안을 사용하여 메시지에 보안 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
caps.latest.revision: "16"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: be727fe2b69258a058ba99dc8aa40ae148d3dd99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="securing-messages-using-message-security"></a>메시지 보안을 사용하여 메시지에 보안 설정
이 절에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하는 경우의 <xref:System.ServiceModel.NetMsmqBinding> 메시지 보안에 대해 설명합니다  
  
> [!NOTE]
>  이 항목을 읽기 전에 것이 좋습니다 읽어 [보안 개념](../../../../docs/framework/wcf/feature-details/security-concepts.md)합니다.  
  
 다음 그림에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 사용하는 대기 중인 통신의 개념적 모델을 제공합니다. 이 그림과 용어는 전송 보안 개념을  
  
 설명하는 데 사용됩니다.  
  
 ![응용 프로그램 다이어그램 큐에 대기](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "분산-큐-그림")  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 대기 중인 메시지를 보내는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지는 MSMQ(Message Queuing) 메시지의 본문으로 첨부됩니다. 전송 보안은 MSMQ 메시지 전체를 보호하지만, 메시지(또는 SOAP) 보안은 MSMQ 메시지의 본문만 보호합니다.  
  
 클라이언트에서 대상 큐의 메시지를 보호하는 전송 보안과 달리, 메시지 보안의 핵심 개념은 클라이언트에서 받는 응용 프로그램(서비스)의 메시지를 보호하는 것입니다. 따라서 메시지 보안을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 보호하는 경우에는 MSMQ가 활용되지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지 보안에서는 인증서 또는 Kerberos 프로토콜 등의 기존 보안 인프라와 통합되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지에 보안 헤더를 추가합니다.  
  
## <a name="message-credential-type"></a>메시지 자격 증명 형식  
 메시지 보안을 사용하면 서비스 및 클라이언트에서 서로 자격 증명을 제출하여 인증할 수 있습니다. <xref:System.ServiceModel.NetMsmqBinding.Security%2A> 모드를 `Message` 또는 `Both`(즉, 전송 보안과 메시지 보안 모두 사용)로 설정하면 메시지 보안을 선택할 수 있습니다.  
  
 서비스에서 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 속성을 사용하여 클라이언트 인증에 사용되는 자격 증명을 검사할 수 있습니다. 이 방법을 사용하여 서비스에서 구현하는 추가 인증 검사를 수행할 수도 있습니다.  
  
 이 절에서는 서로 다른 자격 증명 형식과 큐에서 그러한 형식을 사용하는 방법에 대해 설명합니다.  
  
### <a name="certificate"></a>인증서  
 Certificate 자격 증명 형식에서는 X.509 인증서를 사용하여 서비스와 클라이언트를 식별합니다.  
  
 일반적인 시나리오에서 클라이언트와 서비스에는 신뢰할 수 있는 인증 기관의 유효한 인증서가 발급됩니다. 그런 다음 연결이 설정되고, 클라이언트에서 서비스의 인증서를 통해 서비스의 유효성을 인증하여 서비스 신뢰 여부를 결정합니다. 마찬가지로 서비스에서는 클라이언트의 인증서를 사용하여 클라이언트 신뢰를 확인합니다.  
  
 연결되지 않은 쿼리의 성질을 생각하면, 클라이언트와 서비스는 동시에 온라인 상태가 아닐 수도 있습니다. 따라서 클라이언트와 서비스는 out-of-band로 인증서를 교환해야 합니다. 특히 신뢰할 수 있는 저장소에 서비스의 인증서(인증 기관에 체인으로 연결 가능)를 가지고 있는 클라이언트는 올바른 서비스와 통신하고 있는 것을 신뢰해야 합니다. 클라이언트 인증의 경우 서비스에서는 메시지와 함께 첨부된 X.509 인증서를 저장소에 있는 인증서와 비교하여 클라이언트를 인증합니다. 인증서는 인증 기관에 연결되어 있어야 합니다.  
  
 Windows를 실행하는 컴퓨터에서 인증서는 다양한 종류의 저장소에 저장됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]다른 저장소 참조 [인증서 저장소](http://go.microsoft.com/fwlink/?LinkId=87787)합니다.  
  
### <a name="windows"></a>Windows  
 Windows 메시지 자격 증명 형식에는 Kerberos 프로토콜이 사용됩니다.  
  
 Kerberos 프로토콜은 도메인에서 사용자를 인증하고 인증된 사용자가 도메인에 있는 다른 엔터티와 보안 컨텍스트를 구성할 수 있게 해 주는 보안 메커니즘입니다.  
  
 대기 중인 통신에 Kerberos 프로토콜을 사용하는 경우의 문제는 KDC(키 배포 센터)에서 배포하는 클라이언트 ID가 포함된 티켓의 수명이 비교적 짧다는 것입니다. A *수명* 티켓의 유효성을 나타내는 Kerberos 티켓에 연결 합니다. 따라서 대기 시간이 긴 경우에는 클라이언트를 인증하는 서비스에서 토큰이 여전히 유효한지 확신할 수 없습니다.  
  
 이 자격 증명 형식을 사용하는 경우 서비스는 SERVICE 계정에서 실행해야 합니다.  
  
 메시지 자격 증명을 선택할 때, 기본적으로 Kerberos 프로토콜이 사용됩니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Kerberos 탐색을 위한 프로토콜 Distributed Windows 2000의 보안](http://go.microsoft.com/fwlink/?LinkId=87790)합니다.  
  
### <a name="username-password"></a>Username Password  
 이 속성을 이용하면 메시지의 보안 헤더에 사용자 이름 암호를 사용하여 클라이언트를 서버에 인증할 수 있습니다.  
  
### <a name="issuedtoken"></a>IssuedToken  
 클라이언트에서는 보안 토큰 서비스를 사용하여 서비스에서 클라이언트에 사용할 메시지에 첨부되는 토큰을 발급할 수 있습니다.  
  
## <a name="using-transport-and-message-security"></a>전송 및 메시지 보안 사용  
 전송 보안과 메시지 보안을 모두 사용하는 경우에는 전송과 SOAP 메시지 수준 모두에서 메시지 보호에 사용되는 인증서가 같아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전송 보안을 사용하여 메시지에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 [메시지 큐에 대한 메시지 보안](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
 [보안 개념](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 [서비스 및 클라이언트에 보안 설정](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
