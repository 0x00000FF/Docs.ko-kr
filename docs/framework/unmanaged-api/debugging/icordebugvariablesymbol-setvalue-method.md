---
title: ICorDebugVariableSymbol::SetValue 메서드
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bfbadc5553e86b2db10d66298c8d24d2a0f8bde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211578"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="b1ea6-102">ICorDebugVariableSymbol::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="b1ea6-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="b1ea6-103">바이트 배열의 값을 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ea6-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1ea6-104">Syntax</span></span>  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1ea6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1ea6-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="b1ea6-106">[in] 값을 설정할 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="b1ea6-107">이 매개 변수는 개체의 멤버 필드에 쓸 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="b1ea6-108">[in] 새 값을 반영하도록 컨텍스트를 업데이트해야 하는 스레드의 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="b1ea6-109">[in] 스레드 컨텍스트의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="b1ea6-110">[in] 값을 쓰는 데 사용되는 스레드 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="b1ea6-111">[in] `pValue` 버퍼의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b1ea6-112">[in] 설정할 값이 들어 있는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1ea6-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1ea6-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1ea6-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1ea6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1ea6-115">Requirements</span></span>  
 <span data-ttu-id="b1ea6-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1ea6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1ea6-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1ea6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1ea6-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1ea6-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1ea6-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b1ea6-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1ea6-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1ea6-120">See also</span></span>

- [<span data-ttu-id="b1ea6-121">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1ea6-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="b1ea6-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1ea6-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
