---
title: ICorDebugStepperEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58f148eb4c3206ba12eed41df670846d7beab77a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771629"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="215bf-102">ICorDebugStepperEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="215bf-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="215bf-103">ICorDebugStepper 인스턴스 수가 지정 된 현재 위치부터 시작 하는 열거형에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="215bf-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="215bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="215bf-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="215bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="215bf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="215bf-106">[in] 수가 `ICorDebugStepper` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215bf-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="215bf-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugStepper` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="215bf-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="215bf-108">[out] 개수에 대 한 포인터 `ICorDebugStepper` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="215bf-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="215bf-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="215bf-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="215bf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="215bf-110">Requirements</span></span>  
 <span data-ttu-id="215bf-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="215bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="215bf-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="215bf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="215bf-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="215bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="215bf-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="215bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
