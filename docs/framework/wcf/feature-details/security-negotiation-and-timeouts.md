---
title: 보안 협상 및 시간 제한
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: dfabdb05c7658e3cf9eb5b325597360bbc0bb588
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50037800"
---
# <a name="security-negotiation-and-timeouts"></a>보안 협상 및 시간 제한
클라이언트와 서비스 인증 하는 경우 Windows Communication Foundation (WCF) 인증의 일부로 서비스 자격 증명을 협상 하는 위치 모드를 지원 합니다. 이러한 시나리오에서는 서비스 자격 증명을 클라이언트에 전파하기 위해 클라이언트와 서비스 간에 잠재적 다중 교환이 발생합니다. <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 속성을 통해 다중 교환이 완료되는 데 걸리는 시간이 제어됩니다. 하지만 이 시간 제한은 실제로 교환이 단일 요청 응답 시간보다 더 걸린 경우에만 적용됩니다. 협상이 단일 라운드트립에서 완료되는 경우에는 시간 제한이 적용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [방법: 최대 클럭 오차 설정](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
