---
title: ICorDebugNativeFrame2::GetStackParameterSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76ff2e502859bff27ee29a280e0d247ca1bbf1e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419558"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="f4ac3-102">ICorDebugNativeFrame2::GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="f4ac3-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="f4ac3-103">X86 운영 체제에 대 한 스택에 매개 변수의 누적 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ac3-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4ac3-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4ac3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4ac3-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="f4ac3-106">[out] 매개 변수는 스택에 누적 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4ac3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f4ac3-107">Return Value</span></span>  
 <span data-ttu-id="f4ac3-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f4ac3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4ac3-109">HRESULT</span></span>|<span data-ttu-id="f4ac3-110">설명</span><span class="sxs-lookup"><span data-stu-id="f4ac3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4ac3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4ac3-111">S_OK</span></span>|<span data-ttu-id="f4ac3-112">스택 크기를 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="f4ac3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f4ac3-113">S_FALSE</span></span>|<span data-ttu-id="f4ac3-114">`GetStackParameterSize` 비 x86 플랫폼에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="f4ac3-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4ac3-115">E_FAIL</span></span>|<span data-ttu-id="f4ac3-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="f4ac3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f4ac3-117">E_INVALIDARG</span></span>|<span data-ttu-id="f4ac3-118">`pSize` `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f4ac3-119">예외</span><span class="sxs-lookup"><span data-stu-id="f4ac3-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4ac3-120">설명</span><span class="sxs-lookup"><span data-stu-id="f4ac3-120">Remarks</span></span>  
 <span data-ttu-id="f4ac3-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 메서드는 스택에서 푸시됩니다 매개 변수에 대 한 스택 포인터를 조정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="f4ac3-122">대신, 반환 값을 사용할 수 있습니다 `GetStackParameterSize` 매개 변수를 조정 하는 네이티브 언에 대 한 스택 포인터를 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ac3-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4ac3-123">Requirements</span></span>  
 <span data-ttu-id="f4ac3-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ac3-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4ac3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4ac3-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4ac3-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4ac3-127">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ac3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ac3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4ac3-128">See Also</span></span>  
 [<span data-ttu-id="f4ac3-129">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ac3-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="f4ac3-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ac3-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f4ac3-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="f4ac3-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
