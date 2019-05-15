---
title: NetTcpBinding 응용 프로그램을 피어 채널 응용 프로그램으로 변환
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582791"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>NetTcpBinding 응용 프로그램을 피어 채널 응용 프로그램으로 변환
연결 매개 변수를 설명하는 바인딩을 사용하여 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]에서 클라이언트 간의 연결을 만들 수 있습니다. 클라이언트 연결을 만들 때이 기술을 지 원하는 바인딩이 필요 피어-투-피어 연결을 사용 하려면.NET Framework 응용 프로그램을 변환 합니다. 피어 채널은 <xref:System.ServiceModel.NetPeerTcpBinding>과 유사한 방식으로 사용할 수 있는 <xref:System.ServiceModel.NetTcpBinding>이라는 바인딩을 제공합니다. 주요 차이점에는 확인자 서비스 지정과 보안 설정 정의가 포함됩니다.  
  
 응용 프로그램에서 기본 확인자와 보안 설정을 사용하는 경우 피어 채널을 사용하도록 일반 클라이언트/서버 기반 응용 프로그램을 변환하려면 응용 프로그램 구성 파일에서 바인딩의 이름을 "NetTcpBinding"에서 "NetPeerTcpBinding"으로 변경해야 합니다. 응용 프로그램 코드베이스는 변경할 필요가 없습니다.  
  
## <a name="see-also"></a>참고자료

- [피어 채널 응용 프로그램 빌드](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)
