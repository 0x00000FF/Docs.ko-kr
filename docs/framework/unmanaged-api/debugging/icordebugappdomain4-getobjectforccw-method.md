---
title: ICorDebugAppDomain4::GetObjectForCCW 메서드
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eeb0b80ba691d813e3193f7ae746129c6725e1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506539"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="228a7-102">ICorDebugAppDomain4::GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="228a7-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="228a7-103">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="228a7-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="228a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="228a7-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="228a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="228a7-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="228a7-106">[in] CCW(COM 호출 가능 래퍼) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="228a7-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="228a7-107">[out] 지정된 된 CCW 포인터에 해당 하는 관리 되는 개체를 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="228a7-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="228a7-108">설명</span><span class="sxs-lookup"><span data-stu-id="228a7-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="228a7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="228a7-109">Requirements</span></span>  
 <span data-ttu-id="228a7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="228a7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="228a7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="228a7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="228a7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="228a7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="228a7-113">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="228a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228a7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="228a7-114">See also</span></span>
- [<span data-ttu-id="228a7-115">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="228a7-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="228a7-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="228a7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
