---
title: ICorDebug::SetUnmanagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42ee1f0652a6534372a37a630df0e48d289a9a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724608"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="b4cb1-102">ICorDebug::SetUnmanagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="b4cb1-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="b4cb1-103">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4cb1-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4cb1-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4cb1-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4cb1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4cb1-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="b4cb1-106">[in] 에 대 한 포인터를 [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) 관리 되지 않는 이벤트에 대 한 이벤트 처리기를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b4cb1-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4cb1-107">설명</span><span class="sxs-lookup"><span data-stu-id="b4cb1-107">Remarks</span></span>  
 <span data-ttu-id="b4cb1-108">이벤트 처리기 개체 관리 되지 않는 이벤트에 대 한 호출 후 설정 해야 합니다 [icordebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) 을 호출 하기 전에 [icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 또는 [icordebug:: Debugactiveprocess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4cb1-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="b4cb1-109">그러나 레거시 용도로 하지 해야 첫 번째 기본 디버그 이벤트가 발생할 때까지 관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4cb1-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="b4cb1-110">특히 경우 `ICorDebug::CreateProcess` 가 주 스레드를 재개할 때까지 이벤트를 디스패치할 수 없는 네이티브 디버그 CREATE_SUSPENDED 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4cb1-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4cb1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4cb1-111">Requirements</span></span>  
 <span data-ttu-id="b4cb1-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4cb1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4cb1-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4cb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4cb1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4cb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4cb1-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4cb1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cb1-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4cb1-116">See also</span></span>
- [<span data-ttu-id="b4cb1-117">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4cb1-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
