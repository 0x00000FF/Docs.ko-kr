---
title: ICLRDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e2ec063d46ce9c890927391107888032e31378
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092597"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="1d660-102">ICLRDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="1d660-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="1d660-103">지정된 된 버퍼에 지정 된 가상 메모리 주소에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="1d660-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d660-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d660-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d660-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d660-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1d660-106">[in] 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d660-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="1d660-107">[out] 데이터를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d660-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="1d660-108">[in] 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="1d660-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="1d660-109">[out] 바이트 수에 대 한 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d660-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d660-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d660-110">Requirements</span></span>  
 <span data-ttu-id="1d660-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d660-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d660-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1d660-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1d660-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d660-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d660-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d660-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d660-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d660-115">See also</span></span>

- [<span data-ttu-id="1d660-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d660-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
