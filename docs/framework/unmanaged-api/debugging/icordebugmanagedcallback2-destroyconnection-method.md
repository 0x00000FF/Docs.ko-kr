---
title: ICorDebugManagedCallback2::DestroyConnection 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6d4acb7d1156babbd698201c5aea2810644db8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415404"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="7ebe6-102">ICorDebugManagedCallback2::DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="7ebe6-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="7ebe6-103">지정한 연결이 종료 되었습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ebe6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ebe6-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ebe6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ebe6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7ebe6-106">[in] 소멸 된 연결을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="7ebe6-107">[in] 소멸 하는 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ebe6-108">설명</span><span class="sxs-lookup"><span data-stu-id="7ebe6-108">Remarks</span></span>  
 <span data-ttu-id="7ebe6-109">A `DestroyConnection` 호스트 호출 때 콜백 발생 [iclrdebugmanager:: Endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ebe6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ebe6-110">Requirements</span></span>  
 <span data-ttu-id="7ebe6-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ebe6-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ebe6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ebe6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ebe6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ebe6-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ebe6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebe6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ebe6-115">See Also</span></span>  
 [<span data-ttu-id="7ebe6-116">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ebe6-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="7ebe6-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ebe6-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
