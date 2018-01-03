---
title: "ICorDebugManagedCallback::LogMessage 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogMessage
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62204e8fb2e1fabae4183bbcf7b4d42b832d2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="7bea2-102">ICorDebugManagedCallback::LogMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="7bea2-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="7bea2-103">공용 언어 런타임 (CLR) 관리 되는 스레드에서의 메서드를 호출 했습니다 디버거에 알립니다는 <xref:System.Diagnostics.EventLog> 클래스는 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bea2-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bea2-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bea2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bea2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7bea2-106">[in] 이벤트를 기록 하는 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7bea2-107">[in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="7bea2-108">[in] 값은 [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) 이벤트 로그에 작성 된 설명 메시지의 심각도 수준을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="7bea2-109">[in] 추적 스위치의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="7bea2-110">[in] 이벤트 로그에 기록 된 메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bea2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bea2-111">Requirements</span></span>  
 <span data-ttu-id="7bea2-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bea2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bea2-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bea2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bea2-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bea2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bea2-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bea2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bea2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bea2-116">See Also</span></span>  
 [<span data-ttu-id="7bea2-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bea2-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
