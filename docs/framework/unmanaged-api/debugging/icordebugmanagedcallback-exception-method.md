---
title: ICorDebugManagedCallback::Exception 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6152c643395fe52a43424cab33f527d577b5bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413892"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="c21c0-102">ICorDebugManagedCallback::Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="c21c0-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="c21c0-103">관리 코드에서 예외가 throw 되었습니다는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="c21c0-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c21c0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c21c0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c21c0-106">[in] 예외가 throw 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c21c0-107">[in] 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="c21c0-108">[in] 이 값이 `false`, 예외 하지 않았으면 아직 응용 프로그램에 의해 처리 되 고, 그렇지 않으면, 예외 처리 되지 않은 되어 프로세스가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c21c0-109">설명</span><span class="sxs-lookup"><span data-stu-id="c21c0-109">Remarks</span></span>  
 <span data-ttu-id="c21c0-110">스레드 개체에서 특정 예외를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21c0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c21c0-111">Requirements</span></span>  
 <span data-ttu-id="c21c0-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c21c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21c0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c21c0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c21c0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c21c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c21c0-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21c0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c21c0-116">See Also</span></span>  
 [<span data-ttu-id="c21c0-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c21c0-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
