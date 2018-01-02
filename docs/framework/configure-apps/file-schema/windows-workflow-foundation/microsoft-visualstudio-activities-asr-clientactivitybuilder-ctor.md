---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
인스턴스를 만듭니다는 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
## <a name="parameter-values"></a>매개 변수 값  
 *operationDescription*  
  
 : 작업 이름, 반환 형식 및 매개 변수 정보를 비롯하여 생성되는 워크플로 활동에서 수행될 작업에 대해 설명합니다. 이 매개 변수 값이 아니어야 **null**합니다. 메시지 계약을 사용하고 한 메시지에 인수를 사용하는 동기 작업을 설명해야 합니다. 이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.  
  
 *configurationName*  
  
 : 끝점 구성 이름을 지정합니다. 이 매개 변수 값 중 하나 여야 하지 합니다 **null** 이거나 비어 있습니다. 이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.  
  
 *proxyNamespace*  
  
 : 작업의 서비스 네임스페이스를 지정합니다. 이 매개 변수 값 중 하나 여야 하지 합니다 **null** 이거나 비어 있습니다. 이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
