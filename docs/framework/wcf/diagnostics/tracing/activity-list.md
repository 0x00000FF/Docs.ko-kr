---
title: "동작 목록"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e7a371d43237b795536711cf1745030e14d6eca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="activity-list"></a>동작 목록
이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에 정의된 모든 동작을 나열합니다.  
  
> [!NOTE]
>  사용자 추적을 그룹화하기 위해 프로그래밍 방식으로 동작을 정의할 수도 있습니다. 자세한 내용은 참조 [사용자 코드 추적 내보내기](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)합니다.  
  
## <a name="servicemodel-activities"></a>ServiceModel 동작  
 다음 표에서는 주요 사용 시나리오의 모든 동작을 보여 줍니다.  
  
|레이블|작업 이름|활동 유형|설명|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|앰비언트 동작|해당 없음(ServiceModel에 의해 제어되지 않음)|ServiceModel 코드를 호출하기 이전에 TLS에 해당 ID가 설정되어 있는 동작입니다(클라이언트측 또는 서버측).<br /><br /> 예: open이 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 클라이언트에서 호출되거나 serviceHost.open이 호출되는 동작|  
|B|구문<br /><br /> ChannelFactory. ContractType : ‘[Type]’.|구성||  
|C|열기<br /><br /> [ClientBase &#124; ChannelFactory]입니다. ContractType : ‘[Type]’.|열기||  
|I|[ClientBase &#124; 닫기 ChannelFactory]입니다. ContractType : ‘[Type]’.|닫기||  
|M|ServiceHost를 구성합니다. ServiceType: ‘[Type]’.|구성||  
|N|ServiceHost를 엽니다. ServiceType: ‘[Type]’.|열기||  
|Z|ServiceHost를 닫습니다. ServiceType: ‘[Type]’.|닫기||  
|O|‘[address]’를 수신 대기합니다.|ListenAt|이 동작과 다음 동작은 전송 관련 동작입니다. ListenAt 동작은 채널 수신기에서 수신 대기하는 주소에 매핑되는 콘텐츠를 표시합니다. MSMQ의 경우에는 큐가 하나의 주소로 매핑되기 때문에 큐 자체가 콘텐츠입니다. 이 동작은 연결 지향 전송의 경우 들어오는 연결을 수신 대기합니다. MSMQ의 경우에는 MSMQ 메시지를 수신 대기합니다. 이 동작은 ServiceHost.Open() 중에 만들어지며 모든 ReceiveBytes 동작 전송을 비롯하여 수신기 만들기 및 삭제와 관련된 추적을 포함합니다.|  
|P|‘[address]’ 연결에서 바이트를 수신합니다. MSMQ 메시지를 수신합니다.|ReceiveBytes|이 동작에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 메시지를 가져올 데이터가 처리됩니다. 연결 지향 전송이나 http의 경우 들어오는 바이트가 대기합니다. TCP/명명된 파이프의 경우, 연결이 설정될 때 동작이 발생하므로 이 동작의 수명이 연결 수명입니다. http의 경우 이 동작의 수명이 메시지 요청 수명이며 메시지를 보낼 때 동작이 발생합니다. 이 동작에는 모든 메시지(개체) 처리 동작뿐만 아니라 연결 만들기와 삭제에 관련된 추적(해당하는 경우)이 포함됩니다.<br /><br /> MSMQ의 경우 MSMQ 메시지를 검색하는 동작입니다.|  
|Q|[number] 메시지를 처리합니다. 여기서 [number]는 1부터 시작하여 순차적으로 증가하는 값입니다.|ProcessMessage|들어오는 메시지를 처리합니다. 이 동작은 모든 데이터(바이트, MSMQ 메시지)가 수신되어 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 메시지 개체를 구성하면 시작됩니다. 이 동작에서는 헤더 처리를 추적합니다.<br /><br /> 디스패치할 수 있는 메시지가 생성되면 해당 동작 ID를 조회한 후 ServiceHost ProcessAction 동작이 전환됩니다.|  
|D, S|‘[action]’ 작업을 처리합니다.|ProcessAction|수신할 때는 메시지를 사용자 코드로 디스패치하기 위해 전송/보안/RM 스택을 통해 메시지를 처리하고, 전송할 때는 역순으로 처리합니다.<br /><br /> 서버에서이 작업 사용 하 여 전파 된 동작 ID "동작 전파";를 통해 메시지 헤더에서 전송 되는 경우 그렇지 않으면 새 GUID 생성 됩니다.<br /><br /> 요청/회신 계약의 응답 메시지 또한 해당 동작에서 처리됩니다.|  
|T|‘[IContract.Operation]’을 실행합니다.|ExecuteUserCode|서비스에서 디스패치 후 사용자 코드를 실행합니다. 이 동작에서는 사용자가 제공한 코드에서 ServiceHost 코드를 나타내는 경계를 제공합니다.|  
  
## <a name="security-activities"></a>보안 동작  
 다음 표에서는 보안과 관련된 모든 동작을 보여 줍니다.  
  
|작업 이름|활동 유형|설명|  
|-------------------|-------------------|-----------------|  
|보안 세션 설정|SetupSecurity|클라이언트측에만 있습니다. 인증 및 보안 컨텍스트 설정을 위한 모든 RST*/SCT 교환을 포함합니다. 경우 `propagateActivity` = `true`,이 동작이 서비스의 해당 프로세스 작업 RST와 병합 됩니다\*/SCT 활동입니다.|  
|보안 세션 닫기|SetupSecurity|클라이언트측에 있습니다. 보안 세션을 닫기 위한 취소 메시지 교환을 포함합니다. 경우 `propagateActivity` = `true`,이 동작이 서비스에서 "취소" 작업 처리와 병합 됩니다.|  
  
 다음 표에서는 COM+와 관련된 모든 동작을 보여 줍니다.  
  
|작업 이름|활동 유형|설명|  
|-------------------|-------------------|-----------------|  
|COM+ 인스턴스 만들기|TransferToCOMPlus|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 코드의 COM+ 호출별로 하나의 동작 인스턴스|  
|COM + 실행 \<작업 >|TransferToCOMPlus|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 코드의 COM+ 호출별로 하나의 동작 인스턴스|  
  
## <a name="wmi-activities"></a>WMI 동작  
 다음 표에서는 WMI와 관련된 모든 동작을 보여 줍니다.  
  
|작업 이름|활동 유형|설명|  
|-------------------|-------------------|-----------------|  
|WMI 가져오기|WMIGetObject|사용자가 WMI에서 데이터를 검색하고 있습니다.|  
|WMI 넣기|WmiPutInstance|사용자가 WMI로 데이터를 업데이트하고 있습니다.|
