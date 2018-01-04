---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5387e197cdf26a393ba23fd5696eb095dfd17a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="callbackbehavior"></a>CallbackBehavior
CallbackBehavior  
  
## <a name="syntax"></a>구문  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>메서드  
 CallbackBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 CallbackBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 true이면 서비스가 이중 세션을 닫을 경우 세션이 자동으로 닫힙니다.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 데이터 형식: string  
액세스 형식: 읽기 전용  
  
 서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 지정합니다.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 연결되어 있는 알 수 없는 serialization 데이터를 보낼지 여부를 지정하는 값입니다.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 선택하면 콜백 시 예외에 대한 세부 정보가 서비스로 반환되는 오류에 첨부됩니다.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 serialize된 개체에 허용되는 최대 항목 수입니다.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 시스템 또는 응용 프로그램에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
