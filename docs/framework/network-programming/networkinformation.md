---
title: NetworkInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: acf15eb79fab479036f182c58b8ec94d3ac43ea0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="networkinformation"></a>NetworkInformation
<xref:System.Net.NetworkInformation> 네임스페이스를 사용하면 네트워크 이벤트, 변경 사항, 통계 및 속성에 대한 정보를 수집할 수 있습니다. <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> 클래스를 사용하여 원격 호스트에 연결 가능한지도 확인할 수 있습니다.  
  
## <a name="network-availability-and-events"></a>네트워크 가용성 및 이벤트  
 <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> 클래스를 사용하면 네트워크 주소 또는 가용성이 변경되었는지 확인할 수 있습니다. 이 클래스를 사용하려면 이벤트 처리기를 만들어 변경 사항을 처리한 다음 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 또는 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>와 연결합니다. 자세한 내용은 [방법: 네트워크 가용성 및 주소 변경 검색](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md)을 참조하세요.  
  
## <a name="network-statistics-and-properties"></a>네트워크 통계 및 속성  
 인터페이스 또는 프로토콜을 기반으로 네트워크 통계 및 속성을 수집할 수 있습니다. <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> 및 <xref:System.Net.NetworkInformation.PhysicalAddress> 클래스는 특정 네트워크 인터페이스에 대한 정보를 제공하는 반면 <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> 및 <xref:System.Net.NetworkInformation.UdpStatistics> 클래스는 계층 3 및 계층 4 패킷에 대한 정보를 제공합니다. 자세한 내용은 [방법: 인터페이스 및 프로토콜 정보 가져오기](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md)를 참조하세요.  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>원격 호스트에 연결 가능한지 확인  
 <xref:System.Net.NetworkInformation.Ping> 클래스를 사용하여 원격 호스트가 가동되어 네트워크에 있으며 연결 가능한지 확인할 수 있습니다. 자세한 내용은 [방법: 호스트에 대해 ping 실행](../../../docs/framework/network-programming/how-to-ping-a-host.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)  
 [네트워크 정보 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179564)  
 [NetStat 도구 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179562)  
 [Ping 클라이언트 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179565)
