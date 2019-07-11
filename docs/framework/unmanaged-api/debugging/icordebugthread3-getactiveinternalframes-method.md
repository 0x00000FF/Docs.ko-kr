---
title: ICorDebugThread3::GetActiveInternalFrames 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58aaf0445fe42d083c12541056cb362f9a994944
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765218"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="a81c9-102">ICorDebugThread3::GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="a81c9-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="a81c9-103">내부 프레임의 배열을 반환 합니다 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체)를 스택에 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a81c9-104">구문</span><span class="sxs-lookup"><span data-stu-id="a81c9-104">Syntax</span></span>  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a81c9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a81c9-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="a81c9-106">[in] 예상 하는 내부 프레임 수가 `ppInternalFrames`합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="a81c9-107">[out] 에 대 한 포인터를 `ULONG32` 스택에 내부 프레임 수를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="a81c9-108">[out에서] 배열 스택에 내부 프레임의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a81c9-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a81c9-109">Return Value</span></span>  
 <span data-ttu-id="a81c9-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a81c9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a81c9-111">HRESULT</span></span>|<span data-ttu-id="a81c9-112">설명</span><span class="sxs-lookup"><span data-stu-id="a81c9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a81c9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a81c9-113">S_OK</span></span>|<span data-ttu-id="a81c9-114">합니다 [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="a81c9-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a81c9-115">E_INVALIDARG</span></span>|<span data-ttu-id="a81c9-116">`cInternalFrames` 0이 아닌 하 고 `ppInternalFrames` 됩니다 `null`, 또는 `pcInternalFrames` 는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="a81c9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="a81c9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="a81c9-118">`ppInternalFrames` 내부 프레임의 수보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a81c9-119">예외</span><span class="sxs-lookup"><span data-stu-id="a81c9-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a81c9-120">설명</span><span class="sxs-lookup"><span data-stu-id="a81c9-120">Remarks</span></span>  
 <span data-ttu-id="a81c9-121">내부 프레임은 임시 데이터를 저장 하는 런타임에서 스택에 밀어 넣은 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="a81c9-122">처음 호출할 때는 `GetActiveInternalFrames`를 설정 해야 합니다 `cInternalFrames` 매개 변수를 0 (영) 및 `ppInternalFrames` 매개 변수를 null.</span><span class="sxs-lookup"><span data-stu-id="a81c9-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="a81c9-123">때 `GetActiveInternalFrames` 먼저 반환 `pcInternalFrames` 스택에 내부 프레임 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="a81c9-124">`GetActiveInternalFrames` 다음 호출 해야 두 번째 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="a81c9-125">적절 한 개수를 전달 해야 합니다 (`pcInternalFrames`)에 `cInternalFrames` 매개 변수를 적절 한 크기의 배열에 대 한 포인터를 지정 하 고 `ppInternalFrames`합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="a81c9-126">사용 된 [icordebugstackwalk:: Getframe](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) 실제 반환 방법 스택 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c9-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a81c9-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a81c9-127">Requirements</span></span>  
 <span data-ttu-id="a81c9-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a81c9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a81c9-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a81c9-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a81c9-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a81c9-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a81c9-131">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a81c9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81c9-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="a81c9-132">See also</span></span>

- [<span data-ttu-id="a81c9-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a81c9-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a81c9-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="a81c9-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
