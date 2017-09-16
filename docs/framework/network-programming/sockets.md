---
title: "소켓"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9ddf506ee82d90c8a4d363c1ecc3abd1a8f9dbca
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="sockets"></a>소켓
<xref:System.Net.Sockets> 네임스페이스에는 Windows 소켓 인터페이스의 관리되는 구현이 포함됩니다. <xref:System.Net> 네임스페이스에 있는 다른 모든 네트워크 액세스 클래스는 이 소켓 구현 위에 구축됩니다.  
  
 .NET Framework <xref:System.Net.Sockets.Socket> 클래스는 Winsock32 API에서 제공하는 소켓 서비스의 관리 코드 버전입니다. 대부분의 경우 **Socket** 클래스 메서드는 단순히 데이터를 해당하는 네이티브 Win32 항목으로 마샬링하고 필요한 모든 보안 검사를 처리합니다.  
  
 **Socket** 클래스는 동기 및 비동기의 두 가지 기본 모드를 지원합니다. 동기 모드에서 네트워크 작업을 수행하는 함수 호출(예: <xref:System.Net.Sockets.Socket.Send%2A> 및 <xref:System.Net.Sockets.Socket.Receive%2A>)은 작업이 완료될 때까지 기다린 후 제어를 호출하는 프로그램에 반환합니다. 비동기 모드에서는 이러한 호출이 즉시 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 소켓 만들기](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
    
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)

