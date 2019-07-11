---
title: ICorDebugRegisterSet::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef7619316cae46df350bd75a2c6838828f7e9c82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747187"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="c29f5-102">ICorDebugRegisterSet::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c29f5-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="c29f5-103">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="c29f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c29f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c29f5-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="c29f5-106">[in] 크기 (바이트)의는 `context` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="c29f5-107">[out에서] Win32를 구성 하는 바이트 배열을 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c29f5-108">설명</span><span class="sxs-lookup"><span data-stu-id="c29f5-108">Remarks</span></span>  
 <span data-ttu-id="c29f5-109">디버거는 Win32 대신이 함수를 호출 해야 `GetThreadContext` 상황에 일시적으로 변경 "도용" 상태에서 스레드 수 있기 때문에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="c29f5-110">반환 되는 데이터는 Win32 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="c29f5-111">비-리프 프레임에 대 한 클라이언트를 사용 하 여 어떤 레지스터 올바른지 확인 해야 [icordebugregisterset:: Getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29f5-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c29f5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c29f5-112">Requirements</span></span>  
 <span data-ttu-id="c29f5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c29f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c29f5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c29f5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c29f5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c29f5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c29f5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c29f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29f5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="c29f5-117">See also</span></span>

- [<span data-ttu-id="c29f5-118">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c29f5-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="c29f5-119">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c29f5-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
