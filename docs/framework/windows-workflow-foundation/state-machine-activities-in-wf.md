---
title: "WF의 상태 시스템 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed2b5ace499af3c050529e9f0f2cdd3634c247fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="state-machine-activities-in-wf"></a>WF의 상태 시스템 활동
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]은 상태 시스템 워크플로를 만들기 위한 여러 시스템 제공 활동 및 활동 디자이너를 제공합니다.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|익숙한 상태 시스템 패러다임을 사용하여 포함된 활동을 실행합니다.|  
|<xref:System.Activities.Statements.State>|상태 시스템의 상태를 나타냅니다.|  
|<xref:System.Activities.Core.Presentation.FinalState>|상태 시스템의 종료 상태를 나타냅니다. <xref:System.Activities.Core.Presentation.FinalState>는 사용될 경우 종료 상태로 미리 구성되는 <xref:System.Activities.Statements.State>를 만드는 활동 디자이너입니다. 자세한 내용은 참조 [FinalState 활동 디자이너](/visualstudio/workflow-designer/finalstate-activity-designer)합니다.|  
|<xref:System.Activities.Statements.Transition>|두 상태 간 전환을 나타냅니다. 없는 **도구 상자** 에 대 한 항목 <xref:System.Activities.Statements.Transition>; 전환 워크플로 디자이너에서 두 상태 사이의 선을 끌어서 또는 만든 상태가 다른 위로 가져갈 때 표시 되는 삼각형에 상태를 삭제 하 여 . 자세한 내용은 참조 [전환 활동 디자이너](/visualstudio/workflow-designer/transition-activity-designer)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
