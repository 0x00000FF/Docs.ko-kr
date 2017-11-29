---
title: "ICorDebugManagedCallback::EditAndContinueRemap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EditAndContinueRemap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e45cf5376f0c8b4fbe76f56e3adcce22b1ef5c88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="c84b5-102">ICorDebugManagedCallback::EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="c84b5-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="c84b5-103">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c84b5-103">This method has been deprecated.</span></span> <span data-ttu-id="c84b5-104">통합된 개발 환경 (IDE)에 다시 매핑 이벤트 보냈음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c84b5-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="c84b5-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c84b5-106">설명</span><span class="sxs-lookup"><span data-stu-id="c84b5-106">Remarks</span></span>  
 <span data-ttu-id="c84b5-107">`EditAndContinueRemap` 메서드는 이전 버전의 업데이트 된 함수에서 코드를 실행 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c84b5-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="c84b5-108">공용 언어 런타임 호출은 `EditAndContinueRemap` IDE에 매핑 변경 이벤트를 전송 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="c84b5-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c84b5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c84b5-109">Requirements</span></span>  
 <span data-ttu-id="c84b5-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c84b5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c84b5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c84b5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c84b5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c84b5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c84b5-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c84b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84b5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c84b5-114">See Also</span></span>  
 [<span data-ttu-id="c84b5-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c84b5-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
