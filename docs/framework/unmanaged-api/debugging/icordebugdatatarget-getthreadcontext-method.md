---
title: ICorDebugDataTarget::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab2fbf6bb08a33158ea450f0f19eca50e280d8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412882"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="9ffc8-102">ICorDebugDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="9ffc8-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="9ffc8-103">지정된 된 스레드에 대 한 현재 스레드 컨텍스트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ffc8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ffc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ffc8-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="9ffc8-106">[in] 식별자를 검색할 수 있는 컨텍스트는 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="9ffc8-107">식별자가 운영 체제에 의해 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="9ffc8-108">[in] 컨텍스트의 어떤 부분 읽도록 나타내는 플랫폼에 관계 없이 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="9ffc8-109">[in] `pContext`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="9ffc8-110">[out] 스레드 컨텍스트를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ffc8-111">설명</span><span class="sxs-lookup"><span data-stu-id="9ffc8-111">Remarks</span></span>  
 <span data-ttu-id="9ffc8-112">Windows 플랫폼에서 `pContext` 이어야 합니다는 `CONTEXT` (WinNT.h에 정의 됨)로 지정 된 컴퓨터 종류에 적합 한는 구조는 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="9ffc8-113">`contextFlags` 동일한 값으로 있어야 합니다.는 `ContextFlags` 필드는 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="9ffc8-114">`CONTEXT` 구조는 특정 프로세서 관련; 대 한 자세한 내용은 WinNT.h 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ffc8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ffc8-115">Requirements</span></span>  
 <span data-ttu-id="9ffc8-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ffc8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ffc8-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ffc8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ffc8-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ffc8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ffc8-119">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ffc8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffc8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ffc8-120">See Also</span></span>  
 [<span data-ttu-id="9ffc8-121">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ffc8-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="9ffc8-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ffc8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9ffc8-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="9ffc8-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
