---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c44260d3b5baa18bc24f85cdbea94016b43291e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489789"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="e1e1e-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드</span><span class="sxs-lookup"><span data-stu-id="e1e1e-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="e1e1e-103">병합된 어셈블리의 RVA(상대 가상 주소)가 지정된 경우 병합된 어셈블리에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1e1e-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1e1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1e1e-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="e1e1e-106">[in] 병합된 어셈블리의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="e1e1e-107">병합된 어셈블리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="e1e1e-108">주소에 대 한 포인터를 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 병합 된 어셈블리 메타 데이터를 사용 하 여 메모리 버퍼에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1e1e-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1e1e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1e1e-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e1e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1e1e-111">Requirements</span></span>  
 <span data-ttu-id="e1e1e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1e1e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e1e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1e1e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1e1e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1e1e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1e1e-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e1e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e1e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1e1e-116">See also</span></span>
- [<span data-ttu-id="e1e1e-117">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1e1e-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e1e1e-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1e1e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
