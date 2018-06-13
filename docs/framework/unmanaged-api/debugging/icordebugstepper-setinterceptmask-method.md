---
title: ICorDebugStepper::SetInterceptMask 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7654a91180dd0b4148cfb85b35bf1ce730764f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422687"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="b0a1d-102">ICorDebugStepper::SetInterceptMask 메서드</span><span class="sxs-lookup"><span data-stu-id="b0a1d-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="b0a1d-103">한 단계씩 코드의 형식을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0a1d-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0a1d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0a1d-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="b0a1d-106">[in] 코드의 형식을 지정 하는 CorDebugIntercept 열거형의 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0a1d-107">설명</span><span class="sxs-lookup"><span data-stu-id="b0a1d-107">Remarks</span></span>  
 <span data-ttu-id="b0a1d-108">인터셉터에 대 한 비트가 설정 된 경우 스텝 퍼 가로채기 코드가의 지정된 된 형식 발생 될 때 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="b0a1d-109">비트가 가로채기 코드가 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="b0a1d-110">`SetInterceptMask` 메서드에 있을 수 있습니다와 상호 작용 예기치 못한 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (사용자의 관점에서 볼).</span><span class="sxs-lookup"><span data-stu-id="b0a1d-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="b0a1d-111">예를 들어 경우만 표시 됨 (즉,-내부) 클래스 초기화 코드의 부분에 매핑 정보가 및 STOP_NO_MAPPING_INFO 설정 되어 있지 않습니다 (참조는 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 메서드 및 CorDebugUnmappedStop 열거형) 스텝 퍼 클래스 초기화 건너뛸 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="b0a1d-112">기본적으로의 INTERCEPT_NONE 값만는 `CorDebugIntercept` 열거형이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a1d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0a1d-113">Requirements</span></span>  
 <span data-ttu-id="b0a1d-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a1d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0a1d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0a1d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0a1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0a1d-117">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
