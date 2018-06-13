---
title: ICorDebugInternalFrame2::IsCloserToLeaf 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d26d4dc046841a891c8a36530bd579d100b8f5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416126"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="0837a-102">ICorDebugInternalFrame2::IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="0837a-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="0837a-103">확인 여부는 `this` 내부 프레임 보다 더 가까운 리프에 지정된 된 ICorDebugFrame 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0837a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0837a-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0837a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0837a-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="0837a-106">[in] 비교에 대 한 포인터 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="0837a-107">[out] `true` 경우는 `this` 내부 프레임 보다에 더 가까운 리프로 지정 된 프레임 `pFrameToCompare`, 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0837a-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0837a-108">Return Value</span></span>  
 <span data-ttu-id="0837a-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0837a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0837a-110">HRESULT</span></span>|<span data-ttu-id="0837a-111">설명</span><span class="sxs-lookup"><span data-stu-id="0837a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0837a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0837a-112">S_OK</span></span>|<span data-ttu-id="0837a-113">비교 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="0837a-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0837a-114">E_FAIL</span></span>|<span data-ttu-id="0837a-115">비교를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="0837a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0837a-116">E_INVALIDARG</span></span>|<span data-ttu-id="0837a-117">`pFrameToCompare` 또는 `pIsCloser`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0837a-118">설명</span><span class="sxs-lookup"><span data-stu-id="0837a-118">Remarks</span></span>  
 <span data-ttu-id="0837a-119">`IsCloserToLeaf` 데 사용할 수는 내부 다른 스택 프레임의 프레임 인터리빙에 대 한 정책을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0837a-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0837a-120">Requirements</span></span>  
 <span data-ttu-id="0837a-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0837a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0837a-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0837a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0837a-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0837a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0837a-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0837a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0837a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0837a-125">See Also</span></span>  
 [<span data-ttu-id="0837a-126">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0837a-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="0837a-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0837a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0837a-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="0837a-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
