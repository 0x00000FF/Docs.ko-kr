---
title: "인스턴스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="instances"></a>인스턴스
카운터 이름: Instances  
  
## <a name="description"></a>설명  
 현재 서비스에 포함된 인스턴스 컨텍스트 수입니다.  
  
 대체로 인스턴스 컨텍스트 수는 인스턴스 수와 같습니다. 그러나 다음 시나리오는 이 규칙의 예외입니다.  
  
-   서비스 메서드가 명시적으로 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.  
  
-   <xref:System.ServiceModel.ReleaseInstanceMode>가 <xref:System.ServiceModel.OperationBehaviorAttribute> 인스턴스에 적용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
