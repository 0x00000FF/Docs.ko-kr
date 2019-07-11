---
title: ICorDebugDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d42c85502c12d4d77694626a533c69af97da67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750268"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="0223c-102">ICorDebugDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="0223c-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="0223c-103">지정된 된 주소에서 시작 하는 인접 한 메모리 블록을 가져옵니다 제공된 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0223c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0223c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0223c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0223c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="0223c-106">[in] 요청 된 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="0223c-107">[out] 메모리를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="0223c-108">[in] 대상 주소를 활용 하려면 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="0223c-109">[out] 바이트 수에서에서 실제로 읽는 대상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="0223c-110">보다 적을 수 있습니다이 `bytesRequested`합니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0223c-111">설명</span><span class="sxs-lookup"><span data-stu-id="0223c-111">Remarks</span></span>  
 <span data-ttu-id="0223c-112">지정 된 시작 주소) (에서 첫 번째 바이트를 읽을 수 호출 성공 (자기 같은 null로 끝나는 문자열의 길이 사용 하 여 데이터 구조를 효율적으로 읽을)를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0223c-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0223c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0223c-113">Requirements</span></span>  
 <span data-ttu-id="0223c-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0223c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0223c-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0223c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0223c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0223c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0223c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0223c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0223c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0223c-118">See also</span></span>

- [<span data-ttu-id="0223c-119">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0223c-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="0223c-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0223c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0223c-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="0223c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
