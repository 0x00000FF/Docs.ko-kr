---
title: "Windows Forms의 마우스 캡처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7cc62780579c852aaa637a3ccc13ce2929423868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a>Windows Forms의 마우스 캡처
*마우스 캡처* 컨트롤 명령 모든 마우스 입력을 받는 시점을 나타냅니다. 컨트롤이 마우스를 캡처, 포인터의 테두리 내는 여부에 관계 없이 마우스 입력을 받습니다.  
  
## <a name="setting-mouse-capture"></a>마우스 캡처를 설정합니다.  
 Windows Forms 컨트롤에서 마우스 단추를 누르면 있을 때 마우스 단추를 놓을 때 컨트롤에서 마우스를 놓으면 컨트롤이 마우스가 캡처됩니다.  
  
 <xref:System.Windows.Forms.Control.Capture%2A> 의 속성은 <xref:System.Windows.Forms.Control> 클래스는 컨트롤이 마우스 캡처 하는지 여부를 지정 합니다. 컨트롤이 마우스 캡처를 손실 하는 시기를 확인 하려면 처리는 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 이벤트입니다.  
  
 전경 창이 마우스를 캡처할 수 있습니다. 배경 창이 마우스를 캡처할 때 창을 마우스 포인터가 표시 된 창 영역 내에 있을 때 발생 하는 마우스 이벤트에 대 한 메시지를 받습니다. 또한 전경 창이 마우스를 캡처, 경우에 계속 클릭할 수 다른 창은 전경으로 전환 합니다. 마우스가 캡처되는지 바로 가기 키 작동 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
