---
title: "ICorDebugManagedCallback::ExitThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c39a8c92a8c0be8d0607663a833ac7307ca26d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="4cb70-102">ICorDebugManagedCallback::ExitThread 메서드</span><span class="sxs-lookup"><span data-stu-id="4cb70-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="4cb70-103">관리 되는 코드를 실행 하는 스레드는 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4cb70-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb70-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cb70-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cb70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cb70-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4cb70-106">[in] 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb70-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="4cb70-107">[in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb70-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb70-108">설명</span><span class="sxs-lookup"><span data-stu-id="4cb70-108">Remarks</span></span>  
 <span data-ttu-id="4cb70-109">한 번의 `ExitThread` 콜백이, 스레드가 스레드 열거형에 더 이상 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cb70-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb70-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cb70-110">Requirements</span></span>  
 <span data-ttu-id="4cb70-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb70-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb70-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cb70-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cb70-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb70-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb70-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb70-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cb70-115">See Also</span></span>  
 [<span data-ttu-id="4cb70-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cb70-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
