---
title: "&lt;바인딩&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eefa3145f50ffa24c1b3cf895c9e5097adb5e9d9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindinggt"></a>&lt;바인딩&gt;
`binding` 요소를 사용하여 WCF(Windows Communication Foundation)에서 제공하는 미리 정의된 다양한 바인딩 형식을 구성할 수 있습니다.  
  
## <a name="system-provided-binding"></a>시스템 제공 바인딩  
 시스템 제공 바인딩은 WCF 메시지 스택의 복잡성을 숨깁니다. 시스템 제공 바인딩을 사용하는 응용 프로그램은 스택을 완전히 제어할 필요가 없습니다. 각 시스템 제공 바인딩에는 바인딩이 처리하는 사용 시나리오에 가장 적합한 특성이 노출됩니다.  
  
 각 시스템 제공 바인딩의 구성 섹션은 바인딩 구성에 사용되는 일부 구성을 정의할 수 있습니다. 각 구성은 고유한 이름으로 식별됩니다.  
  
 시스템 제공 바인딩에는 요소나 특성을 추가할 수 없습니다. 이렇게 하려면 이 항목의 "사용자 지정 바인딩" 섹션에 설명된 것처럼 사용자 지정 바인딩을 구현해야 합니다. 시스템 제공 바인딩과 완전히 같으며 사용자 응용 프로그램이 제어하려는 몇 가지 설정을 추가로 제공하는 사용자 지정 바인딩을 정의할 수 있습니다.  
  
## <a name="custom-binding"></a>사용자 지정 바인딩  
 사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다. 개별 바인딩에서는 스택에 나타나는 순서대로 스택 요소의 구성 요소를 지정함으로써 메시지 스택을 정의하며, 각 요소는 스택의 한 요소를 정의하고 구성합니다. 각 사용자 지정 바인딩에는 `transport` 요소가 하나만 있어야 합니다. 이 요소가 없으면 메시징 스택이 완전하지 않습니다.  
  
 스택에서 요소가 나타나는 순서는 작업이 메시지에 적용되는 순서이므로 중요합니다. 다음과 같은 스택 요소 순서를 사용하는 것이 좋습니다.  
  
1.  Transactions(선택적)  
  
2.  Reliable Messaging(선택적)  
  
3.  Security(선택적)  
  
4.  인코더  
  
5.  전송  
  
 사용자 지정 바인딩은 `name` 특성으로 식별됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [바인딩](../../../docs/framework/wcf/bindings.md)  
 [사용자 지정 바인딩](../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
