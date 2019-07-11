---
title: ICorDebugProcess::ReadMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d74da502492065dbffb5e5499581263760636c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737073"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="b9b66-102">ICorDebugProcess::ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="b9b66-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="b9b66-103">이 프로세스에 대 한 메모리의 지정된 된 영역을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b66-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9b66-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9b66-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b9b66-106">[in] `CORDB_ADDRESS` 읽을 메모리의 기본 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="b9b66-107">[in] 메모리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b9b66-108">[out] 메모리의 콘텐츠를 받는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="b9b66-109">[out] 지정된 된 버퍼에 전송 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b66-110">설명</span><span class="sxs-lookup"><span data-stu-id="b9b66-110">Remarks</span></span>  
 <span data-ttu-id="b9b66-111">`ReadMemory` 디버기에 서의 관리 되지 않는 부분에 의해 사용 중인 메모리 영역을 검사 하는 interop 디버깅에서 사용할 메서드는 주로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="b9b66-112">또한이 메서드 Microsoft MSIL (intermediate language) 코드와 네이티브 JIT 컴파일된 코드를 읽는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="b9b66-113">반환 되는 데이터에서 제거 됩니다. 관리 되는 중단점을 `buffer` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="b9b66-114">설정 된 기본 중단점 조정 없이 만들어질 [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="b9b66-115">프로세스 메모리의 캐싱 없음이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b66-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b66-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9b66-116">Requirements</span></span>  
 <span data-ttu-id="b9b66-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9b66-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b66-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9b66-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9b66-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b66-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9b66-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b66-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
