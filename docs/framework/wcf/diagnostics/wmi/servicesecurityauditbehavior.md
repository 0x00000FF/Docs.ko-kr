---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>구문  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>메서드  
 ServiceSecurityAuditBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 ServiceSecurityAuditBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="auditloglocation"></a>AuditLogLocation  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 감사 로그의 위치입니다.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 감사 이벤트 로깅에 사용되는 메시지 인증 수준의 형식입니다.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 감사 로그에 기록되는 권한 부여 이벤트의 형식입니다.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 감사 로그 쓰기의 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
