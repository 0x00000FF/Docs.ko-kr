---
title: ICorDebugCode::GetILToNativeMapping 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8614dd612fff2886c4e44a977d05a575fce74eec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648945"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="6572c-102">ICorDebugCode::GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="6572c-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="6572c-103">Microsoft MSIL (intermediate language) 오프셋과 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6572c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6572c-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6572c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6572c-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="6572c-106">[in] `map` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="6572c-107">[out] 반환 되는 요소의 실제 수에 대 한 포인터를 `map` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="6572c-108">[out] 배열을 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조가 각각 나타내는 MSIL 오프셋에서 매핑을 네이티브 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="6572c-109">반환 되는 요소의 배열에 순서가 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6572c-110">설명</span><span class="sxs-lookup"><span data-stu-id="6572c-110">Remarks</span></span>  
 <span data-ttu-id="6572c-111">`GetILToNativeMapping` 메서드가이 "ICorDebugCode" 인스턴스에 just-in-time (JIT) MSIL 코드에서 컴파일된 네이티브 코드를 나타내는 경우에 의미 있는 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6572c-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6572c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6572c-112">Requirements</span></span>  
 <span data-ttu-id="6572c-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6572c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6572c-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6572c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6572c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6572c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6572c-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6572c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6572c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="6572c-117">See also</span></span>
- [<span data-ttu-id="6572c-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="6572c-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
